Download Link: https://assignmentchef.com/product/solved-empirical-analysis-comp-2210-assignment
<br>
<h1>Problem Overview</h1>

This assignment is a departure from previous assignments insomuch as its focus is not on program construction, but is instead on experimentation, analysis, critical thinking, and applying the scientific method. The provided resources for this assignment are the following.

<ul>

 <li>jar — A jar file containing the TimingLab class for which you have to experimentally determine time complexity of a method, and the SortingLab class for which you have to experimentally determine the sorting algorithms implemented in various methods.</li>

 <li>java — Source code of a Java class that illustrates basic use of the TimingLab class. <em>This class is for illustration only. </em>You can modify and use it for your own purposes or you can use it as an example to create a different but similar class of your own.</li>

 <li>java — Source code of a class that illustrates basic calls to public methods of SortingLab. <em>This class is for illustration only. </em>You can modify and use it for your own purposes or you can use it as an example to create a different but similar class of your own.</li>

 <li>pdf — A sample report that you are required to use as a style, structure, and formatting guide for the deliverables that you submit for this assignment.</li>

</ul>

There are two parts to this assignment. Each has its own deliverable and is to be done independently of the other.

<h1>Part A: Experimental Discovery of Time Complexity</h1>

You must develop and perform a repeatable experimental procedure that will allow you to empirically discover the time complexity (in term of big-Oh) of the timeTrial(int N) method in the TimingLab class. The parameter N represents the <em>problem size</em>. Thus, by iteratively calling timeTrial with successively larger values of N, you can collect timing data that is useful for characterizing the method’s time complexity.

The constructor TimingLab(int key) will create a TimingLab object whose timeTrial method is tailored specifically to the given key value. You will use your Banner ID number as the key required by the constructor. For example, one student might invoke the constructor TimingLab(903111111) and another student might invoke the constructor TimingLab(903222222). This will create two distinct objects whose timeTrial methods would (very likely) have different time complexities. Note that you <strong>must </strong>use your own Banner ID since grading will be based on Banner ID rather than student name.

You are guaranteed that for any key value used, the associated time complexity will be proportional to <em>N<sup>k </sup></em>for some positive integer <em>k</em>. Thus, you can take advantage of the following property of polynomial time complexity functions <em>T</em>(<em>N</em>).

<em>T</em>(2<em>N</em>)          (2<em>N</em>)<em><sup>k               </sup></em>2<em><sup>k</sup>N<sup>k</sup></em>

<em>T</em>(<em>N</em>) <em>∝ N<sub>k </sub></em>=<em>⇒                      ∝                </em>=               = 2<em><sub>k                                                                               </sub></em>(1)

<em>T</em>(<em>N</em>)             <em>N<sup>k                     </sup>N<sup>k</sup></em>

1

This property tells us that as <em>N </em>is successively doubled, the ratio of the method’s running time on the current problem size to the method’s running time on the previous problem size (i.e., <em>T</em>(2<em>N</em>)<em>/T</em>(<em>N</em>)) converges to a numerical constant, call it <em>R</em>, that is equal to 2<em><sup>k</sup></em>, and thus <em>k </em>= <em>log</em><sub>2</sub><em>R</em>.

As an example, consider the data shown in Table 1. Each row in this table records data for a given run of some method being timed. The first column (N) records the problem size, the second column (Time) records the time taken for the method to run on this problem size, the third column (R) is the ratio discussed above (i.e., <em>Time<sub>i</sub>/Time<sub>i−</sub></em><sub>1</sub>), and the third column (k) is <em>log</em><sub>2</sub><em>R</em>. From Property 1 and Table 1 we can hypothesize that the method being timed has <em>O</em>(<em>N</em><sup>4</sup>) time complexity.

Table 1: Running-time data and calculations

<table width="188">

 <tbody>

  <tr>

   <td width="44"><strong>N</strong></td>

   <td width="66"><strong>Time</strong></td>

   <td width="46"><strong>R</strong></td>

   <td width="32"><strong>k</strong></td>

  </tr>

  <tr>

   <td width="44">8</td>

   <td width="66">0.04</td>

   <td width="46">—</td>

   <td width="32">—</td>

  </tr>

  <tr>

   <td width="44">16</td>

   <td width="66">0.08</td>

   <td width="46">2.25</td>

   <td width="32">1.17</td>

  </tr>

  <tr>

   <td width="44">32</td>

   <td width="66">0.84</td>

   <td width="46">10.37</td>

   <td width="32">3.37</td>

  </tr>

  <tr>

   <td width="44">64</td>

   <td width="66">7.59</td>

   <td width="46">9.03</td>

   <td width="32">3.18</td>

  </tr>

  <tr>

   <td width="44">128</td>

   <td width="66">113.56</td>

   <td width="46">14.97</td>

   <td width="32">3.91</td>

  </tr>

  <tr>

   <td width="44">256</td>

   <td width="66">1829.28</td>

   <td width="46">16.11</td>

   <td width="32">4.01</td>

  </tr>

  <tr>

   <td width="44">512</td>

   <td width="66">29689.21</td>

   <td width="46">16.23</td>

   <td width="32">4.02</td>

  </tr>

 </tbody>

</table>

You are required to use System.nanoTime(), as illustrated in TimingLabClient.java, to generate timing data like that shown in Table 1. Running time values must be expressed in seconds.

To document your work you must write a lab report that fully describes the experiment used to discover the big-Oh time complexity of the given method. The lab report must discuss the experimental procedure (what you did), data collection (all the data you gathered), data analysis (what you did with the data), and interpretation of the data (what conclusions you drew from the data). The lab report must be well written, it must exhibit a high degree of professionalism, and it must be structured like the provided sample. Your experiment must be described in enough detail that it could be reproduced by someone else.

<h1>Part B: Experimental Identification of Sorting Algorithms</h1>

You must develop and perform a repeatable experimental procedure that will allow you to empirically discover the sorting algorithms implemented by the five methods of the SortingLab class — sort1, sort2, sort3, sort4, sort5. The five sorting algorithms implemented are merge sort, randomized quicksort, nonrandomized quicksort, selection sort, and insertion sort.

Insertion sort, selection sort, and merge sort are implemented exactly as described in lecture and the associated note set. Quicksort has two implementations, randomized and non-randomized. Both implementations choose the pivot in the same way: the pivot is always the left-most element (i.e., a[left]) of the current partition. Both implementations also use the same algorithm for the partitioning operation (although it is slightly different than the one presented in lecture). The two implementations are different, however, in the following way. The randomized quicksort implementation makes the worst case probabilistically unlikely by randomly permuting the the array elements before the quicksort algorithm begins. The non-randomized quicksort exposes the algorithm’s worst case by never shuffling the array elements.

To generate timing data you are required to use System.nanoTime(), as illustrated in SortingLabClient.java. Running time values must be expressed in seconds. Using time data to empirically discover the big-Oh time complexity of various methods will allow you to identify all sorting algorithms except for being able to distinguish merge sort from randomized quicksort. Since both algorithms have <em>O</em>(<em>N </em>log<em>N</em>) time complexity, you should use <em>stability </em>to distinguish the two. Recall that the merge sort implementation is stable while the randomized quicksort implementation is not.

The constructor SortingLab(int key) will create a SortingLab object whose sort method implementations are tailored specifically to the given key value. You will use your Banner ID number as the key required by the constructor. For example, one student might invoke the constructor SortingLab(903111111) and another student might invoke the constructor SortingLab(903222222). This will create two distinct objects whose timeTrial methods would (very likely) have different time complexities. Note that you <strong>must </strong>use your own Banner ID since grading will be based on Banner ID rather than student name.

To document your work you must write a lab report that fully describes the experiments used to discover the the sorting algorithm associated with each of the five sort methods. The lab report must discuss the experimental procedure (what you did), data collection (all the data you gathered), data analysis (what you did with the data), and interpretation of the data (what conclusions you drew from the data). The lab report must be well written, it must exhibit a high degree of professionalism, and it must be structured like the provided sample. Your experiment must be described in enough detail that it could be reproduced by someone else.

<strong>Note on the use of jGRASP viewers: </strong>You may find the jGRASP viewers very helpful in confirming your hypotheses, but for the purposes of this assignment they can’t be used as a sole source of data. Your conclusions must be directly supported by time complexities and stability.

<h1>Grading</h1>

Two rubrics (<em>Experimentation Rubric </em>and <em>Written Communication Rubric</em>, both available on Canvas) will be used to score each lab report. Marks of Little/No Ability, Basic, Intermediate, and Advanced are worth 1, 2, 3, and 4 points respectively. Note that you are required to structure and style your reports according to the sample provided. Significant deviation from this sample will negatively impact your grade.

There are 50 points available for each part, giving a total of 100 points for the assignment. Let <em>E </em>be the score from the experiment rubric and <em>W </em>be the score from the writing rubric for a given part. Then the numeric score for that part of the assignment will be computed as

<em>Score </em>= ((<em>E × </em>0<em>.</em>45) + (<em>W × </em>0<em>.</em>05)) <em>× </em>50                                                                  (2)

<h1>Using the provided jar file</h1>

To compile and run the provided source files and any of your own that might use for this assignment, you will need to include resources.jar on the classpath. You can do this from the command line or from within your IDE.

<strong>From the command line. </strong>In the following example, &gt; represents the command line prompt and it is assumed that the current working directory contains both the source code and the jar file. The example applies to both source code files although only one is used for illustration.

&gt; javac -cp .:resources.jar TimingLabClient.java

&gt; java -cp .:resources.jar TimingLabClient

<strong>From the jGRASP IDE</strong>.

<ol>

 <li>Create a project for the assignment (suppose you call it A3Project), and include SortingLabClient.java and TimingLabClient.java.</li>

 <li>Click on <em>Settings → PATH/CLASSPATH → Project → &lt;A3Project&gt;</em>.</li>

 <li>Click on the <em>CLASSPATHS </em></li>

 <li>Click <em>New</em>.</li>

 <li>In the “Path or JAR File” text box, use the <em>Browse </em>button to navigate to resources.jar and select it.</li>

 <li>Click on <em>OK</em>.</li>

 <li>Click on <em>Apply</em>.</li>

 <li>Click on <em>OK</em>.</li>

</ol>

<h1>Increasing the JVM stack size</h1>

In Part B it may be necessary for you to increase the amount of memory allocated to the JVM’s runtime stack. The Xss flag is used to request an amount of memory in bytes. For example, the following command runs the SortingLabClient class with four gigabytes of stack memory.

java -Xss4G -cp .:resources.jar SortingLabClient

You can set the Xss flag in jGRASP at <em>Settings → Compiler Settings → Workspace → Flags/Args → FLAGS2 or ARGS2</em>.

<h1>Assignment Submission</h1>

This assignment appears as two separate assignments in Canvas – A3A and A3B, for Part A and Part B respectively. You must submit a separate lab report as a PDF file to each. Submissions made within the 24 hour period after the published deadline will be assessed a late penalty of 15 points. No submissions will be accepted more than 24 hours after the published deadline.