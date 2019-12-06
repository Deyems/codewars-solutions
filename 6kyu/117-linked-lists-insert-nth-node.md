### Problem:
<p>Linked Lists - Insert Nth</p>
<p>Implement an InsertNth() function (<code>insert_nth()</code> in PHP) which can insert a new node at any index within a list.</p>
<p>InsertNth() is a more general version of the Push() function that we implemented in the first kata listed below.  Given a list, an index &apos;n&apos; in the range 0..length, and a data element, add a new node to the list so that it has the given index. InsertNth() should return the head of the list.</p>
<pre><code class="language-javascript">insertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">0</span>, <span class="hljs-number">7</span>) === <span class="hljs-number">7</span> -&gt; <span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>)
insertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">1</span>, <span class="hljs-number">7</span>) === <span class="hljs-number">1</span> -&gt; <span class="hljs-number">7</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>)
insertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">3</span>, <span class="hljs-number">7</span>) === <span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-number">7</span> -&gt; <span class="hljs-literal">null</span>)</code></pre>
<pre style="display: none;"><code class="language-php">insert_nth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-keyword">NULL</span>, <span class="hljs-number">0</span>, <span class="hljs-number">7</span>); <span class="hljs-comment">// 7 -&gt; 1 -&gt; 2 -&gt; 3 -&gt; NULL</span>
insert_nth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-keyword">NULL</span>, <span class="hljs-number">1</span>, <span class="hljs-number">7</span>); <span class="hljs-comment">// 1 -&gt; 7 -&gt; 2 -&gt; 3 -&gt; NULL</span>
insert_nth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-keyword">NULL</span>, <span class="hljs-number">3</span>, <span class="hljs-number">7</span>); <span class="hljs-comment">// 1 -&gt; 2 -&gt; 3 -&gt; 7 -&gt; NULL</span>
insert_nth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-keyword">NULL</span>, <span class="hljs-number">4</span>, <span class="hljs-number">7</span>); <span class="hljs-comment">// throws new InvalidArgumentException</span></code></pre>
<pre style="display: none;"><code class="language-csharp">Node.InsertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">0</span>, <span class="hljs-number">7</span>)  =&gt; <span class="hljs-number">7</span> -&gt; <span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>
Node.InsertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">1</span>, <span class="hljs-number">7</span>)  =&gt; <span class="hljs-number">1</span> -&gt; <span class="hljs-number">7</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>
Node.InsertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">3</span>, <span class="hljs-number">7</span>)  =&gt; <span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-number">7</span> -&gt; <span class="hljs-literal">null</span>
Node.InsertNth(<span class="hljs-number">1</span> -&gt; <span class="hljs-number">2</span> -&gt; <span class="hljs-number">3</span> -&gt; <span class="hljs-literal">null</span>, <span class="hljs-number">-2</span>, <span class="hljs-number">7</span>) <span class="hljs-comment">// throws new ArgumentException</span></code></pre>
<p>You must throw/raise an exception (<code>ArgumentOutOfRangeException</code> in C#, <code>InvalidArgumentException</code> in PHP) if the index is too large.</p>
<p>The push() and buildOneTwoThree() (<code>build_one_two_three()</code> in PHP) functions do not need to be redefined.  The <code>Node</code> class is also preloaded for you in PHP.</p>
<p>Related Kata in order of expected completion (increasing difficulty):<br>
 <a href="http://www.codewars.com/kata/linked-lists-push-and-buildonetwothree" target="_blank">Linked Lists - Push &amp; BuildOneTwoThree</a><br>
 <a href="http://www.codewars.com/kata/linked-lists-length-and-count" target="_blank">Linked Lists - Length &amp; Count</a><br>
 <a href="http://www.codewars.com/kata/linked-lists-get-nth-node" target="_blank">Linked Lists - Get Nth Node</a><br>
<a href="http://www.codewars.com/kata/linked-lists-insert-nth-node" target="_blank">Linked Lists - Insert Nth Node</a><br>
<a href="http://www.codewars.com/kata/linked-lists-sorted-insert" target="_blank">Linked Lists - Sorted Insert</a><br>
<a href="http://www.codewars.com/kata/linked-lists-insert-sort" target="_blank">Linked Lists - Insert Sort</a><br>
<a href="http://www.codewars.com/kata/linked-lists-append" target="_blank">Linked Lists - Append</a><br>
<a href="http://www.codewars.com/kata/linked-lists-remove-duplicates" target="_blank">Linked Lists - Remove Duplicates</a><br>
<a href="http://www.codewars.com/kata/linked-lists-move-node" target="_blank">Linked Lists - Move Node</a><br>
<a href="http://www.codewars.com/kata/linked-lists-move-node-in-place" target="_blank">Linked Lists - Move Node In-place</a><br>
<a href="http://www.codewars.com/kata/linked-lists-alternating-split" target="_blank">Linked Lists - Alternating Split</a><br>
<a href="http://www.codewars.com/kata/linked-lists-front-back-split" target="_blank">Linked Lists - Front Back Split</a><br>
<a href="http://www.codewars.com/kata/linked-lists-shuffle-merge" target="_blank">Linked Lists - Shuffle Merge</a><br>
<a href="http://www.codewars.com/kata/linked-lists-sorted-merge" target="_blank">Linked Lists - Sorted Merge</a><br>
<a href="http://www.codewars.com/kata/linked-lists-merge-sort" target="_blank">Linked Lists - Merge Sort</a><br>
<a href="http://www.codewars.com/kata/linked-lists-sorted-intersect" target="_blank">Linked Lists - Sorted Intersect</a><br>
<a href="http://www.codewars.com/kata/linked-lists-iterative-reverse" target="_blank">Linked Lists - Iterative Reverse</a><br>
<a href="http://www.codewars.com/kata/linked-lists-recursive-reverse" target="_blank">Linked Lists - Recursive Reverse</a><br></p>
<p>Inspired by Stanford Professor Nick Parlante&apos;s excellent <a href="http://cslibrary.stanford.edu/103/LinkedListBasics.pdf" target="_blank">Linked List teachings.</a></p>

### Solution