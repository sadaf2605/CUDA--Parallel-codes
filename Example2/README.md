<div class="problem-description"><h3>MP2: Basic Matrix-Matrix Multiplication (Resubmit)</h3>

<h5><em>Due Date</em>: Jan 28, 2013 at 11:59 p.m. PST</h5>

<h5>If you did not do well on this MP, then we will allow you to resubmit and recieve up to 80% of the score.</h5>

<h5>Your previous attempt is found <a href="/mp/2prev">here</a>.</h5>

<h5>A detail of you grade is found <a href="/mp/2/grade">here</a>.</h5>

<h4>Objective</h4>

<p>Implement a basic dense matrix multiplication routine.</p>

<h4>Prerequisites</h4>

<p>Before starting this lab, make sure that:</p>

<ul>
<li><p>You have completed MP 1</p></li>
<li><p>You can have completed lecture 3 video</p></li>
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
</ul>

<p>Instructions about where to place each part of the code is
demarcated by the <code>//@@</code> comment lines.</p>

<h4>Grading</h4>

<p>You will be grading based on the following rubric:</p>

<ul>
<li>Compilation (no warning): 15%</li>
<li>Runtime (with respect to other students): 5%</li>
<li>Correctness (deals with simple and edge cases): 80%</li>
</ul>

<p>If we cannot compile your program, then you will get a 0 points.
Note that we only grade the last program submitted and do not accept
programs beyond the deadline.</p>

<p>For the runtime grade, we will take the average time of all the final submissions. If your time is no more than 10% above the average time, then you will get full marks. Otherwise, you will lose points.</p>

<p>Note that the datasets that we test against are not the same as the ones provided, so make sure to code the algorithm for correctness on general datasets not just the ones provided.</p>

<h4>Suggestions</h4>

<ul>
<li><p>Develop your application incrementally</p></li>
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
<li><p>Make sure that your algorithm handles boundary conditions where the size of the matrix may not be a multiple of the block size</p></li>
<li><p>Make sure that your algorithm handles rectangular matrices, not just square matrices as shown in the slides.</p></li>
<li><p>Do not modify the template code written -- only insert code where the <code>//@@</code> demarcation is placed</p></li>
<li><p>Do not wait until the last minute to attempt the lab</p></li>
<li><p>Make sure that you test your program using all the datasets provided (the datasets can be selected using the dropdown next to the submission button)</p></li>
<li><p>Even though you can submit multiple times, only your last submission is graded</p></li>
</ul></div>