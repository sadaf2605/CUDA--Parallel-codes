<div class="problem-description"><h3>MP5: Parallel Scan</h3>

<h5><em>Due Date</em>: Feb 1, 2013 at 11:59 p.m. PST</h5>

<h5>If you did not do well on this MP, then we will allow you to resubmit and recieve up to 80% of the score.</h5>

<h5>Your previous attempt is found <a href="/mp/4prev">here</a>.</h5>

<h5>A detail of you grade is found <a href="/mp/4/grade">here</a> (this is not posted yet).</h5>

<h4>Objective</h4>

<p>Implement a kernel the performs parallel scan on a 1D list.
The scan operator used will be addition.
You should implement the work efficient kernel in Lecture 6.3.
Your kernel should be able to handle input lists of arbitrary length.
However, for simplicity, you can assume that the input list will be at most 2048 * 65,535 elements so that it can be handled by only one kernel launch.
The boundary condition can be handled by filling "identity value (0 for sum)" into the shared memory of the last block when the length is not a multiple of the thread block size.</p>

<h4>Prerequisites</h4>

<p>Before starting this lab, make sure that:</p>

<ul>
<li><p>You have completed MP4</p></li>
<li><p>You can have completed lecture 6.1 through 6.3</p></li>
</ul>

<h4>Instruction</h4>

<p>Edit the code in the code tab to perform the following:</p>

<ul>
<li>allocate device memory</li>
<li>copy host memory to device</li>
<li>initialize thread block and kernel grid dimensions</li>
<li>invoke CUDA kernel</li>
<li>copy results from device to host</li>
<li>deallocate device memory</li>
<li>implement the work efficient scan routine</li>
<li>use shared memory to  reduce the number of global accesses, handle the boundary conditions in when loading input list elements into the shared memory</li>
</ul>

<p>Instructions about where to place each part of the code is
demarcated by the <code>//@@</code> comment lines.</p>

<h4>Questions</h4>

<p>These are questions that you are encouraged to think about. 
You will not be graded on them, however, so feel free to attempt them and discuss them on the forum.</p>

<ul>
<li><p>Describe how you handled arrays not a power of two in size, how you minimized 
shared memory bank conflicts, and any other performance-enhancing optimizations 
you added.</p></li>
<li><p>What is the FLOPS rate for the GPU kernel?</p></li>
<li><p>Name two applications of scan.</p></li>
<li><p>In both scan and reduction, the operator used was the Plus operator.
What would happen if we use a Subtract operator?</p></li>
<li><p>What is the minimum, maximum, and average number of "real" operations that a 
thread will perform? "Real" operations are those that directly contribute to the 
final reduction value.</p></li>
<li><p>How many times does your thread block synchronize?</p></li>
<li><p>Compare the mapping of thread indices to data indices in the work efficient scan kernel versus the reduction kernel. Explain why both have similar control divergence behavior.</p></li>
</ul>

<h4>Grading</h4>

<p>You will be grading based on the following rubric:</p>

<ul>
<li>Compilation (no warning): 5%</li>
<li>Run time (with respect to other students): 15%</li>
<li>Correctness (generates correct values, follows objective, and deals with boundary conditions correctly): 80%</li>
</ul>

<p>If we cannot compile your program, then you will get 0 points.
Note that we only grade the last program submitted and do not accept
programs beyond the deadline.</p>

<p>For the run time grade, we will take the average time of all the final submissions. If your time is no more than 10% above the average time, then you will get full marks. Otherwise, you will lose points.</p>

<p>Note that the datasets that we test against are not the same as the ones provided, so make sure to code the algorithm for correctness on general datasets not just the ones provided.</p>

<h4>Suggestions</h4>

<ul>
<li><p>Develop your application incrementally</p></li>
<li><p>Do not wait until the last minute to attempt the lab</p></li>
<li><p>You may find "Parallel Prefix Sum (Scan) with CUDA" by Mark Harris to be helpful</p></li>
<li><p>Check for CUDA errors, here is some example <code>wbCheck</code> that you can use (included in the template code):</p>

<pre><code> #define wbCheck(stmt) do {                                 \
         cudaError_t err = stmt;                            \
         if (err != cudaSuccess) {                          \
             wbLog(ERROR, "Failed to run stmt ", #stmt);    \
             return -1;                                     \
         }                                                  \
     } while(0)
</code></pre></li>
</ul>

<p>using this in your code would look like <code>wbCheck(cudaMalloc(...))</code></p>

<ul>
<li><p>Make sure that your algorithm handles boundary conditions where the length of the input list may not be a multiple of the block/tile size</p></li>
<li><p>Do not modify the template code written -- only insert code where the <code>//@@</code> demarcation is placed</p></li>
<li><p>Make sure that you test your program using all the datasets provided (the datasets can be selected using the dropdown next to the submission button)</p></li>
<li><p>Even though you can submit multiple times, only your last submission is graded</p></li>
</ul></div>