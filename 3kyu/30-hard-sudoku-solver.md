### Problem:
<p>This kata is a harder version of <a href="http://www.codewars.com/kata/sudoku-solver/python" target="_blank">http://www.codewars.com/kata/sudoku-solver/python</a> made by @pineappleclock</p>
<p>Write a function that will solve a 9x9 Sudoku puzzle. The function will take one argument consisting of the 2D puzzle array, with the value 0 representing an unknown square.</p>
<p>The Sudokus tested against your function will be &quot;insane&quot; and can have multiple solutions. The solution only need to give one valid solution in the case of the multiple solution sodoku. </p>
<p>It might require some sort of brute force.</p>
<p>Consider applying algorithm with</p>
<ul>
<li>Backtracking <a href="https://www.wikiwand.com/en/Sudoku_solving_algorithms#Backtracking" target="_blank">https://www.wikiwand.com/en/Sudoku_solving_algorithms#Backtracking</a></li>
<li>Brute Force</li>
</ul>
<p>For Sudoku rules, see the Wikipedia : <a href="http://www.wikiwand.com/en/Sudoku" target="_blank">http://www.wikiwand.com/en/Sudoku</a></p>
<p>Used puzzle from : <a href="http://www.extremesudoku.info/sudoku.html" target="_blank">http://www.extremesudoku.info/sudoku.html</a></p>
<pre><code class="language-python">puzzle = [[<span class="hljs-number">5</span>,<span class="hljs-number">3</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">7</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">1</span>,<span class="hljs-number">9</span>,<span class="hljs-number">5</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">9</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">3</span>],
          [<span class="hljs-number">4</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">3</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">1</span>],
          [<span class="hljs-number">7</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">2</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">2</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">4</span>,<span class="hljs-number">1</span>,<span class="hljs-number">9</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">5</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">7</span>,<span class="hljs-number">9</span>]]

solve(puzzle)</code></pre>
<pre style="display: none;"><code class="language-ruby">puzzle = [[<span class="hljs-number">5</span>,<span class="hljs-number">3</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">7</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">1</span>,<span class="hljs-number">9</span>,<span class="hljs-number">5</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">9</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">3</span>],
          [<span class="hljs-number">4</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">3</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">1</span>],
          [<span class="hljs-number">7</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">2</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">6</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">6</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">2</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">4</span>,<span class="hljs-number">1</span>,<span class="hljs-number">9</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">5</span>],
          [<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">8</span>,<span class="hljs-number">0</span>,<span class="hljs-number">0</span>,<span class="hljs-number">7</span>,<span class="hljs-number">9</span>]]

solve(puzzle)</code></pre>

### Solution