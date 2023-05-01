Download Link: https://assignmentchef.com/product/solved-cs2106-lab-1-advanced-c-programming
<br>
There are <strong>three exercises </strong>in this lab. Although the main motivation for this lab is to familiarize you with some advanced aspects of C programming, the <strong>techniques </strong>used in these exercises are quite commonly used in OS related topics.




The first two exercises focus on <strong>linked list</strong>. The linked list is a “simple” yet powerful data structure that allows elements of a list to be stored in non-consecutive memory locations (as opposed to array). Operating System frequently make use of variations of linked list to keep track of important information, e.g. the process list, the free memory lists, file representation etc.




The last exercise is on <strong>function pointer</strong>. Unlike normal pointer, which points to memory location for <strong>data storage, </strong>a function pointer <strong>points to a piece of code (function)</strong>. By dereferencing a function pointer, we <strong>invoke the function </strong>that is referred by that pointer. This technique is commonly used in <strong>system call / interrupt handlers</strong>.




<strong>2.1 Exercise 1 </strong><strong><u>[Lab Demo Exercise]</u> </strong>




Linked list in C is based on pointers of structure. In ex1, the structure is as follows:

<strong> </strong>

<strong>typedef struct NODE{     int data;     struct NODE* next; } node; </strong>

<h2><sub>                                                                           </sub>node</h2>

<strong> </strong>

A linked list is basically a series of node structure hooked up by the next pointer.




This exercise requires you to write <strong>two functions</strong>:







<table width="507">

 <tbody>

  <tr>

   <td width="507"><strong>node* addToHead(node* list, int newValue); </strong></td>

  </tr>

  <tr>

   <td width="507">This function takes an existing linked list <strong>list </strong>and an integer value <strong>newValue</strong>. The function will:o   Make a new <strong>node </strong>to store <strong>newValue</strong>o   Make this new <strong>node</strong> to be the <strong>first node </strong>(head) of <strong>list</strong> o Return the modified list</td>

  </tr>

 </tbody>

</table>




<table width="507">

 <tbody>

  <tr>

   <td width="507"><strong>void destroyList(node* list); </strong></td>

  </tr>

  <tr>

   <td width="507">This function takes an existing linked list <strong>list </strong>and <strong>destroy every node </strong>in the linked list by return the memory to system.</td>

  </tr>

 </tbody>

</table>




The program should:

<ol>

 <li>Read a new integer value</li>

 <li>Insert this integer value to the head position of linked list</li>

 <li>Go to step a, until user terminates input by pressing <strong>Ctrl-D </strong>o <strong>Ctrl-D</strong> is the “end-of-file” signal</li>

 <li>Print out the whole list</li>

 <li>Destroy the list</li>

 <li>Print out the list (should be empty!)</li>

</ol>




The skeleton file <strong>ex1.c</strong> has the following: o The input/output code is already written.

o A useful function <strong>printList()</strong> is written to print out a correctly constructed linked list.




<table width="516">

 <tbody>

  <tr>

   <td width="142"><strong>Sample Input: </strong></td>

   <td width="373"> </td>

  </tr>

  <tr>

   <td width="142"><strong>1</strong></td>

   <td width="373">//List =  1</td>

  </tr>

  <tr>

   <td width="142"><strong>2</strong></td>

   <td width="373">//List = 2à1</td>

  </tr>

  <tr>

   <td width="142"><strong>3</strong></td>

   <td width="373">//List = 3à2à1   <strong> </strong></td>

  </tr>

  <tr>

   <td width="142"><strong>4</strong><strong>[Ctrl-D] </strong></td>

   <td width="373">//List = 4à3à2à1</td>

  </tr>

 </tbody>

</table>




<table width="516">

 <tbody>

  <tr>

   <td width="232"><strong>Sample Output: </strong></td>

   <td width="24"> </td>

   <td width="259"> </td>

  </tr>

  <tr>

   <td width="232"><strong>My List: </strong><strong>4 3 2 1  </strong><strong>My List After Destroy: </strong> </td>

   <td width="24"> </td>

   <td width="259">//Should be empty</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>Important Note: </strong>

<strong> </strong>

The correctness of your program cannot be entirely verified just by the output. For example, the linked list can be freed in the wrong way (<em>hint!</em>) but still seems to work. So, as a programmer, you need to scrutinize the code instead of just relying on the output.




This marks an important progression of your skill and understanding J. Of course, it is also a source of major pain for you as there is now no “simple way” to ensure your code is 100% correct. Just a friendly warning: most, if not all, lab exercises in CS2106 share this characteristic.

<strong>             </strong>

<h3>2.2 Exercise 2</h3>

<strong> </strong>

This exercise is the same as exercise 1 except the addition to linked list can be <strong>at any position</strong>. To indicate a position, an <strong>integer index is used</strong>. The index is similar to those in array, i.e. first position = 0, second position = 1, N<sup>th</sup> = N-1. The new value is to be inserted “before” the supplied index. If the index supplied is &gt;= N (when the linked list has N nodes), then the new value is added at the end of linked list.




In addition, user can insert <strong>multiple copies </strong>of the same value in one call. You can assume the number of copy is ≥ 1.




You need to write at least <strong>two functions </strong>for this exercise:

<table width="497">

 <tbody>

  <tr>

   <td width="497">node* insertAt(node* list, int position, int copies,                int newValue);Insert <strong>copies</strong> number of the integer <strong>newValue</strong> and <strong>before </strong>the index <strong>position</strong> in the linked list <strong>list</strong>. </td>

  </tr>

  <tr>

   <td width="497">void destroyList(node* list); This function takes an existing linked list <strong>list </strong>and <strong>destroy every node </strong>in the linked list by <u>returning the memory</u> to system. You can use the same implementation as in ex1. </td>

  </tr>

 </tbody>

</table>




You are allowed to write additional functions if needed.




The program should:

<ol>

 <li>Read three integer values:</li>

</ol>

o The position, number of copy and the new value

<ol>

 <li>Insert this integer value accordingly</li>

 <li>Go to step a, until user terminates input by pressing <strong>Ctrl-D </strong>o <strong>Ctrl-D</strong> is the “end-of-file” signal</li>

 <li>Print out the whole list</li>

 <li>Destroy the list</li>

 <li>Print out the list (should be empty!)</li>

</ol>




<table width="516">

 <tbody>

  <tr>

   <td width="516"><strong>Sample Input: </strong></td>

  </tr>

  <tr>

   <td width="516"><strong>0 33 1    </strong>//insert <strong>one </strong>33 before index 0. List = 33<strong>0  </strong><strong>11 2     </strong>//insert <strong>two </strong>11 before index 0. List = 11à11à33<strong>1  </strong><strong>22 1     </strong>//insert <strong>one </strong>22 before index 1. List = 11à22à11à33<strong>5 44 2    </strong>//insert <strong>two</strong> 44 before index 5. List = 11à22à11à33à44à44 <strong>[Ctrl-D] </strong></td>

  </tr>

 </tbody>

</table>




<table width="516">

 <tbody>

  <tr>

   <td width="516"><strong>Sample Output: </strong></td>

  </tr>

  <tr>

   <td width="516"><strong>My List: </strong><strong>11 22 11 33 44 44  My List After Destroy: </strong>//Should be empty</td>

  </tr>

 </tbody>

</table>

<strong>2.3 Exercise 3 </strong>

<strong> </strong>

Suppose we have two functions:




<strong>void f( int x ); </strong>




<h2>void g( int y );</h2>




They are considered as the same “type” of functions because <strong>the number and datatype of parameters, as well as the return type is the same</strong>. (More accurately, we say the <strong>function signature </strong>of the two functions are the same).




In C, it is possible to define a <strong>function pointer</strong> to refer to a function. For example:




<strong>void (*fptr) ( int ); </strong>




To understand this declaration, imagine if you replace <strong>(*fptr)</strong> as <strong>F</strong>, then you have:




<h2>void F( int );</h2>

So, <strong>F</strong> is “a function that takes an integer as input, and return nothing (void)”.




Now, since <strong>(*fptr)</strong> is <strong>F</strong>, <strong>fptr</strong> is “<strong>a pointer to</strong> a function that takes an integer as input, and return nothing (void)”. Simple eh?  J




Try your understanding of the following declarations:




<table width="520">

 <tbody>

  <tr>

   <td width="253"><strong>Declaration </strong></td>

   <td width="267"><strong>Meaning </strong></td>

  </tr>

  <tr>

   <td width="253"><strong>int (*fp) (); </strong></td>

   <td width="267"><strong>fp</strong> is a pointer to a function that takes no parameter and returns integer.</td>

  </tr>

  <tr>

   <td width="253"><strong>int (*fp) (int, double);</strong></td>

   <td width="267"><strong>fp</strong> is a pointer to a function that takes integer and double values and returns integer.</td>

  </tr>

  <tr>

   <td width="253"><strong>int* (*fp) ( );</strong></td>

   <td width="267"><strong>fp</strong> is a pointer to a function that takes no parameter and returns integer pointer.</td>

  </tr>

 </tbody>

</table>




Just like a normal pointer, you need to “point” it to a correct location before you can perform dereferencing later. Using the <strong><em>f()</em></strong> and <strong><em>g()</em></strong> functions at the beginning of this section, we can:




<strong>fptr = f;      </strong>           //fptr points to function f




OR




<strong>fptr = g;      </strong>           //fptr points to function g




Both of the above assignments are valid, as <strong>fptr</strong> must point to a function that takes an integer as input, and return nothing. Both <strong>f()</strong> and <strong>g()</strong> fit the type restriction.




We can now dereference <strong>fptr</strong>. When a function pointer is dereferenced, the function it is pointing to get invoked (called). E.g.




<h2>fptr = f;</h2>

<strong>(*fptr) ( 3 );</strong>                          //Exactly the same as <strong>f( 3 ); </strong>




OR




<h2>fptr = g;</h2>

<strong>(*fptr) ( 3 );</strong>                          //Exactly the same as <strong>g( 3 );</strong>







If you look closely, you can see that we can invoke either <strong>f()</strong> or <strong>g()</strong> just by changing the pointer as the dereferencing statement is the same <strong>“(*fptr) (3);</strong>”







The function pointer can be applied in various interesting problems. However, you must agree that declaring a function pointer is quite troublesome. For example, to have 3 function pointers like <strong>fptr</strong>, we need to write:




<strong>void (*fp1) ( int ); void (*fp2) ( int ); void (*fp3) ( int ); </strong>







To simplify the declaration, we can use <strong>typedef</strong> as follows:




<h2>typedef void (*funcPtrType) ( int );</h2>







The above creates a <strong>new datatype </strong>named “<strong>funcPtrType</strong>”, which is a <strong>function pointer that points to a function. </strong>

<strong> </strong>

With the help of this new datatype, we can now declare function pointer variables easily:

<strong>funcPtrType fp1, fp2, fp3; </strong> //Quite an improvement!







Remember that the above is just a shortcut for the declaration, it <strong>does not </strong>affect the usage/meaning of the function pointer in any way. E.g.




<strong>fp1 = f;</strong>                              //points <strong>fp1</strong> to <strong>f() (*fp1) (123); </strong>        //Same as <strong>f(123); </strong>Now we are ready to tackle exercise 3. The idea of this lab is quite simple, we are going to simulate the spell repertoire of the famous wizard H. Potter. Each of his spell requires 3 integers: &lt;Spell Number&gt; &lt;X&gt; &lt;Y&gt; and produce two effects: &lt;Name of the spell&gt; and &lt;Z&gt;, where &lt;Z&gt; is the result of a mythical (I mean <strong><em>Math</em></strong>ematical) combination of &lt;X&gt; and &lt;Y&gt;.




Below is the summary of the spells to be simulated:

<strong> </strong>

<table width="503">

 <tbody>

  <tr>

   <td width="119"><strong>Spell Number </strong></td>

   <td width="96"><strong>Spell Name </strong></td>

   <td width="289"><strong>Result </strong></td>

  </tr>

  <tr>

   <td width="119">1</td>

   <td width="96"><em>lumos </em></td>

   <td width="289">X is guaranteed to be smaller or equal to Y Z = X + (X+1) + (X+2) + …. + Y</td>

  </tr>

  <tr>

   <td width="119">2</td>

   <td width="96"><em>alohomora </em></td>

   <td width="289">Z = GCD(X, Y)</td>

  </tr>

  <tr>

   <td width="119">3</td>

   <td width="96"><em>expelliarmus </em></td>

   <td width="289">If X can be expressed as Y<sup>n</sup>*Q, then Z = Qi.e. remove factor Y from the number X, such that Z no longer has Y as a factor.</td>

  </tr>

  <tr>

   <td width="119">4</td>

   <td width="96"><em>sonorus </em></td>

   <td width="289">Z = X<sup>Y</sup></td>

  </tr>

 </tbody>

</table>




Your program should print out the <strong>&lt;Spell Name&gt; </strong>and the <strong>&lt;Z&gt;</strong> based on the user supplied &lt;Spell Number&gt; &lt;X&gt; &lt;Y&gt;. The program will continue to receive input until the user press Ctrl-D (a.k.a. end-of-file signal) to terminate.




<table width="519">

 <tbody>

  <tr>

   <td width="519"><strong>Now the fun part</strong>: Your code <strong>must conform to the following restrictions: </strong>•       You are <strong>not allowed to use selection statement nor repetition statement</strong>, i.e no “<strong>if-else</strong>”, “<strong>switch-case</strong>”, “<strong>while</strong>“, “<strong>for</strong>” etc <strong>to determine which spell to cast</strong>.•       Each “spell” must be self-contained as a function. Printing (i.e. for the spell name) should <strong>not </strong>be performed in the function.</td>

  </tr>

 </tbody>

</table>




Hint:

<ul>

 <li>You’ll need function pointers (duh!) and <strong>array</strong>……</li>

 <li>You can assume that the <strong>input are always valid</strong> and will not result in any overflow / underflow in calculation, i.e. you do not need to validate input.</li>

</ul>

<table width="516">

 <tbody>

  <tr>

   <td width="142"><strong>Sample Input: </strong></td>

   <td width="45"> </td>

   <td width="328"> </td>

  </tr>

  <tr>

   <td width="142"><strong>2 13 7      </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 2, GCD(13, 7)</td>

  </tr>

  <tr>

   <td width="142"><strong>1 1 100  </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 1, 1 + 2 + 3 + ….. + 100</td>

  </tr>

  <tr>

   <td width="142"><strong>3 2835 3  </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 3, removes factor 3 from 2835</td>

  </tr>

  <tr>

   <td width="142"><strong>2 30 105  </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 2, GCD(30, 105)</td>

  </tr>

  <tr>

   <td width="142"><strong>4 3 5       </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 4, 3<sup>5</sup></td>

  </tr>

  <tr>

   <td width="142"><strong>1 20 20  </strong><strong>[Ctrl-D] </strong></td>

   <td width="45"><strong> </strong></td>

   <td width="328">// Spell 1, 20</td>

  </tr>

 </tbody>

</table>




<table width="516">

 <tbody>

  <tr>

   <td width="516"><strong>Sample Output: </strong></td>

  </tr>

  <tr>

   <td width="516"><strong>alohomora 1    </strong>//Output format:<strong> Spell_Name&lt;space&gt;Z&lt;newline&gt; lumos 5050 expelliarmus 35 alohomora 15 sonorous 243 lumos 20 </strong></td>

  </tr>

 </tbody>

</table>

Note that the skeleton file <strong>ex3.c</strong> contains demo code to show you the idea behind function pointer. <u>You need to replace the code for the actual exercise</u>.




<strong>For your pondering: </strong>

<strong> </strong>

Function pointer, though seems like a weird C language quirks, is actually a very powerful programming technique. Consider the following:

<ul>

 <li>How can we quickly change the mapping of the functions (say 1=sonorus, 2=lumos, etc in this exercise)?</li>

 <li>How can we easily add a new spell without disturbing the current code structure?</li>

 <li>How can we modify the functionalities without affecting other part of the code (say lumos calculates the prime factorization now instead)?</li>

 <li>Is the function pointer approach faster / easier to write than selection statement (think about when you have many more options, say 100+)?</li>

</ul>




This mechanism is available in many other programming languages, albeit with a different name, e.g. JavaScript allows you to bind function to a variable, functional programming languages, e.g. Python allows you to pass function around as a “value” (more formally known as <strong>function as first class citizen</strong>), etc.