---


---

<h1 id="learn-bash">Learn Bash</h1>
<p>Bash (Bourne Again Shell) is a relatively simple coding language meant for many simple things. I like using it because there’s a lot that you can do with it, but also a complexity of some things that makes it just challenging enough to want to learn it.</p>
<h2 id="how-to-get-bash">How to Get Bash</h2>
<ol>
<li>
<p>First, go to <a href="https://replit.com/~">Repl</a> and sign in or sign up.</p>
</li>
<li>
<p>Next, when you are logged in and on the home page, open a new Repl, select Bash, and name it whatever you want.</p>
</li>
<li>
<p>A new Repl will open, and commands go on the left text box, and the output will go on the right. You can add or delete files and folders on the left side. For a full documentation on how Repl works, use <a href="https://docs.replit.com/">this</a>.</p>
</li>
</ol>
<p><code>This is where single lines code will go.</code></p>
<p>This is where multiple</p>
<p>lines of code will go.</p>
<blockquote>
<p>This is what output / message you should get.</p>
</blockquote>
<h1 id="learning-bash">Learning Bash</h1>
<h4 id="echo-command">Echo Command</h4>
<p>Firstly, let’s start with the echo command. This is the basis of everything you will be doing in bash. It is used in about 80% of all of the commands! Here’s an example:</p>
<p><code>echo "Hello, World!</code> or <code>echo Hello, World!</code></p>
<blockquote>
<p>Hello, World!</p>
</blockquote>
<p>To get them on separate lines, just add a semicolon between echo commands:</p>
<p><code>echo "Hello, World!"; echo "Hello, World!</code></p>
<blockquote>
<p>Hello, World!</p>
</blockquote>
<blockquote>
<p>Hello, World!</p>
</blockquote>
<h4 id="declaring-a-variable">Declaring a Variable</h4>
<p>Declaring a variable is simple, just use this syntax:</p>
<p><code>Variable="String"</code></p>
<p>But <strong>do not</strong> use this:</p>
<p><code>Variable= "String"</code> or <code>Variable= 'String'</code></p>
<p>It will return an error:</p>
<blockquote>
<p>Variable: command not found</p>
</blockquote>
<p>And for the second one:</p>
<blockquote>
<p>Variable: String not found</p>
</blockquote>
<h4 id="using-a-variable">Using a Variable:</h4>
<p>You can use this</p>
<p><code>Echo $Variable</code></p>
<blockquote>
<p>String</p>
</blockquote>
<p>You can use this also:</p>
<p><code>echo "$Variable"</code></p>
<blockquote>
<p>String</p>
</blockquote>
<p>But <strong>do not</strong> use this:</p>
<p><code>echo '$Variable'</code></p>
<blockquote>
<p>$Variable</p>
</blockquote>
<h4 id="parameter-extension">Parameter Extension</h4>
<p>Parameter extensions are important because you can use them for more then one thing, not just using a declared variable.</p>
<p><code>echo ${Variable}</code></p>
<blockquote>
<p>String</p>
</blockquote>
<p>Let’s say we rename our variable to this:</p>
<p><code>Variable="Very Many Strings!"</code></p>
<p>And use this command:</p>
<p><code>echo ${Variable/Very/A}</code></p>
<p>This will substitute the first occurrence of “Very” with “A”</p>
<blockquote>
<p>A Many Strings</p>
</blockquote>
<h4 id="lengths">Lengths</h4>
<p>This command makes it so that “Very Many Strings!” has only the first 7 characters showing:</p>
<p>Length=7</p>
<p>echo ${Variable:0:Length}</p>
<blockquote>
<p>Very Ma</p>
</blockquote>
<p>This command makes it so that the last 5 characters show up:</p>
<p><code>echo ${Variable: -5}</code></p>
<blockquote>
<p>ings!</p>
</blockquote>
<p>This command shows you how many characters the string is:</p>
<p><code>echo ${#Variable}</code></p>
<blockquote>
<p>18</p>
</blockquote>
<h4 id="indirect-expansion">Indirect Expansion</h4>
<p>This is an expansion of a current variable:</p>
<p>OtherVariable=“Variable”</p>
<p>echo ${!OtherVariable}</p>
<blockquote>
<p>Very Many Strings!</p>
</blockquote>
<h4 id="foo">Foo</h4>
<p>Foo is the default value for the variable if the variable declaration is empty:</p>
<p><code>echo ${Foo:-"Default Value"}</code></p>
<blockquote>
<p>Default Value</p>
</blockquote>
<p>This works for null, <code>(Foo=0)</code> empty string, <code>(Foo="")</code> and zero <code>(Foo=0)</code>.</p>
<h4 id="arrays">Arrays</h4>
<p>Let’s declare an array with 6 elements:</p>
<p><code>array0=(one two three four five six)</code></p>
<p>Printing the first element:</p>
<p><code>echo $array0</code> or <code>echo ${array0[0]}</code></p>
<blockquote>
<p>one</p>
</blockquote>
<p>This command is to print all elements:</p>
<p><code>echo ${array0[@]}</code></p>
<blockquote>
<p>one two three four five six</p>
</blockquote>
<p>This command is to print it in number form:</p>
<p><code>echo ${#array0[@]}</code></p>
<blockquote>
<p>6</p>
</blockquote>
<p>This command prints all numbers in the 5th element:</p>
<p><code>echo ${#array0[2]}</code></p>
<blockquote>
<p>5</p>
</blockquote>
<p>This command prints 2 elements starting from 4th:</p>
<p><code>echo ${array0[@]:3:2}</code></p>
<blockquote>
<p>four five</p>
</blockquote>
<p>This command prints all elements starting on a different line:</p>
<p>for i in “${array0[@]}” do</p>
<p>echo “$i”</p>
<p>done</p>
<blockquote>
<p>one</p>
</blockquote>
<blockquote>
<p>two</p>
</blockquote>
<blockquote>
<p>three</p>
</blockquote>
<blockquote>
<p>four</p>
</blockquote>
<blockquote>
<p>five</p>
</blockquote>
<blockquote>
<p>six</p>
</blockquote>
<h4 id="brace-expansion">Brace Expansion</h4>
<p>These commands use ellipses to write out the numbers 1 to 10 or the alphabet so that you don’t have to write all of it out yourself.</p>
<p><code>echo {1..10}</code></p>
<blockquote>
<p>1 2 3 4 5 6 7 8 9 10</p>
</blockquote>
<p><code>echo {a..z}</code></p>
<blockquote>
<p>a b c d e f g h i j k l m n o p q r s t u v w x y z</p>
</blockquote>
<p>Note that you <strong>do not</strong> have to put an <code>$</code> symbol before the curly brackets. You must have <em><strong>2</strong></em> dots between the numbers or letters.</p>
<h4 id="built-in-variables">Built in Variables</h4>
<p>Here are some useful built in variables, like:</p>
<p>Last program’s return value:</p>
<p><code>echo $?</code></p>
<p>Script’s PID:</p>
<p><code>echo $$</code></p>
<p>Number of arguments passed to script:</p>
<p><code>echo $#</code></p>
<p>All arguments passed to script:</p>
<p><code>echo $@</code></p>
<p>Script’s arguments separated into different variables:</p>
<p><code>echo $1 $2 ...</code></p>
<h4 id="listing-a-directory">Listing a Directory</h4>
<p>According to google, a directory is a file system cataloging structure which contains references to other computer files, and possibly other directories. On many computers, directories are known as folders, or drawers, analogous to a workbench or the traditional office filing cabinet.</p>
<p>Note: PWD means Print Working Directory.</p>
<p>This first command prints your working directory. The directory name is the name of the Repl. For the purposes of this lesson, let’s sat that the name of the Repl is <strong>Bash Test</strong>.</p>
<p><code>echo "My directory is $(pwd)</code> or</p>
<p><code>echo My directory is $PWD</code></p>
<blockquote>
<p>My directory is /home/runner/Bash-Test</p>
</blockquote>
<h4 id="clear-command">Clear Command</h4>
<p>If your terminal has too much stuff in it, you can just type clear at the end of your script, and the terminal will clear after whatever scripts you write appear and are done. Note that if clear does not go at the end, then whatever scripts come after clear will stay in the terminal.</p>
<p>Command:</p>
<p><code>clear</code></p>
<blockquote>
<p><em>Nothing Here</em></p>
</blockquote>
<p>Alternatively, you can just press Ctrl/Cmd L to clear the terminal when your Repl is not running.</p>
<h4 id="reading-a-value-from-an-input">Reading a Value from an Input</h4>
<p>This command makes it so that you can ask the user a question.</p>
<p>echo “What’s your Name?”</p>
<p>read Name</p>
<p>echo “Hello, $Name.”</p>
<p>Note that you didn’t have to declare a variable, just make sure that whatever word comes after the <code>read</code> command is spelled and capitalized the exact same as what’s after the <code>echo</code> command.</p>
<blockquote>
<p>What’s your name?</p>
</blockquote>
<blockquote>
<p>(User Input): John</p>
</blockquote>
<blockquote>
<p>Hello, John.</p>
</blockquote>
<h4 id="if..then-statements">If…Then Statements</h4>
<p>Let’s say we created a variable that made $USER = John.</p>
<p><code>USER="John"</code></p>
<p>Then we can create an if…then statement that makes the computer ask itself if the name the user puts in is the same as the username.</p>
<p>if [ $Name != $USER ]</p>
<p>then</p>
<p>echo “I’m sorry, your name is not your username.”</p>
<p>else</p>
<p>echo “Your name is your username!”</p>
<p>fi</p>
<blockquote>
<p>What’s your name?</p>
</blockquote>
<blockquote>
<p>John</p>
</blockquote>
<blockquote>
<p>Hello, John.</p>
</blockquote>
<blockquote>
<p>Your name is your username!</p>
</blockquote>
<p>If the name is not john, then:</p>
<blockquote>
<p>What’s your name?</p>
</blockquote>
<blockquote>
<p>Jane</p>
</blockquote>
<blockquote>
<p>Hello, Jane.</p>
</blockquote>
<blockquote>
<p>I’m sorry, your name is not your username.</p>
</blockquote>
<p>Note: if <code>$Name</code> is empty, then, bash sees this as</p>
<p><code>if [ != $USER ]</code></p>
<p>This is incorrect syntax, so this is how to fix this:</p>
<p><code>if [ "SName" != $USER ]</code></p>
<p>So then bash sees that line, if <code>$Name</code> is empty, as:</p>
<p><code>if [ "" != $USER ]</code></p>
<p>This is the correct syntax.</p>
<h4 id="conditional-execution">Conditional Execution</h4>
<p>Conditional execution uses phrases like <code>||</code> and <code>&amp;&amp;</code> as “or” and “and” to specify, for example, if this <strong>or</strong> this happened, then execute the command, and <strong>only if</strong> this <strong>and</strong> this happens, then the command gets executed.</p>
<p>echo “Always executed” || echo “Only executed if first command fails”</p>
<blockquote>
<p>Always Executed</p>
</blockquote>
<p>echo “Always executed” &amp;&amp; echo “Only executed if first command does NOT fail”</p>
<blockquote>
<p>Always Executed</p>
</blockquote>
<blockquote>
<p>Only executed if first command does NOT fail.</p>
</blockquote>
<p>Note: to use “or” and “and” statements, you need multiple sets of square brackets.</p>
<p>First we need to set up some read and echo commands:</p>
<p>echo “What’s your name?”</p>
<p>read name</p>
<p>echo “What’s your age?”</p>
<p>read age</p>
<p>Your name is $name and you are $old years old.</p>
<p>Here is an example of using an “and” parameter:</p>
<p>if [ “<span class="katex--inline">KaTeX parse error: Expected 'EOF', got '&amp;' at position 19: …e" == "John" ] &amp;̲&amp; [ "</span>age” == -eq 15 ]"</p>
<p>then</p>
<p>echo “This will run if the name is John and the age is 15.”</p>
<p>fi</p>
<blockquote>
<p>What’s your name?</p>
</blockquote>
<blockquote>
<p>John</p>
</blockquote>
<blockquote>
<p>What’s your age?</p>
</blockquote>
<blockquote>
<p>15</p>
</blockquote>
<blockquote>
<p>Your name is John and you are 15 years old.</p>
</blockquote>
<blockquote>
<p>This will run if the name is John and the age is 15.</p>
</blockquote>
<p>This next one does not need the age bracket.</p>
<p>This is an example of using an “or” parameter:</p>
<p>if [ “<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi><mi>a</mi><mi>m</mi><mi>e</mi><mi mathvariant="normal">"</mi><mo>=</mo><mo>=</mo><mi mathvariant="normal">"</mi><mi>J</mi><mi>o</mi><mi>h</mi><mi>n</mi><mi mathvariant="normal">"</mi><mo stretchy="false">]</mo><mi mathvariant="normal">∣</mi><mi mathvariant="normal">∣</mi><mo stretchy="false">[</mo><mi mathvariant="normal">"</mi></mrow><annotation encoding="application/x-tex">name" == "John" ] || [ "</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.69444em; vertical-align: 0em;"></span><span class="mord mathnormal">nam</span><span class="mord mathnormal">e</span><span class="mord">"</span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">==</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 1em; vertical-align: -0.25em;"></span><span class="mord">"</span><span class="mord mathnormal" style="margin-right: 0.09618em;">J</span><span class="mord mathnormal">o</span><span class="mord mathnormal">hn</span><span class="mord">"</span><span class="mclose">]</span><span class="mord">∣∣</span><span class="mopen">[</span><span class="mord">"</span></span></span></span></span>name” == “Jane” ]</p>
<p>then</p>
<p>echo “This will run if your name is John OR Jane”</p>
<p>fi</p>
<blockquote>
<p>What’s your name?</p>
</blockquote>
<blockquote>
<p>Jane (or John)</p>
</blockquote>
<blockquote>
<p>How old are you?</p>
</blockquote>
<blockquote>
<p>87</p>
</blockquote>
<blockquote>
<p>Your name in Jane (or John) and you are 87 years old.</p>
</blockquote>
<blockquote>
<p>This will run if your name is John OR Jane.</p>
</blockquote>
<h4 id="regex-pattern">Regex Pattern</h4>
<p>For those who don’t know, the Regex pattern is a pattern that you put into the computer that a string has to follow otherwise it is invalid. The best example is an email. Let’s create a variable as Email and Regex pattern:</p>
<p><a href="mailto:Email=you@example.com">Email=you@example.com</a></p>
<p>if [[ “$Email” =~ [a-z]+@[a-z]{2,}.(com|net|org) ]]</p>
<p>then</p>
<p>echo "Valid Email!!</p>
<p>fi</p>
<blockquote>
<p>Valid Email</p>
</blockquote>
<p>Please note that the Regex pattern only works using <code>=~</code> within <strong>double</strong> square brackets. <code>[[ PARAMS ]]</code></p>
<p>See <a href="https://www.gnu.org/software/bash/manual/bashref.html#Conditional-Constructs">this</a> for more on Regex patterns and Conditional Constructs.</p>
<h4 id="ping">Ping</h4>
<p>Use the command alias to send only 5 packets:</p>
<p><code>alias ping="ping -c 5"</code></p>
<p>Escape the alias:</p>
<p>Note: This one <strong>does not</strong> work in Repl.</p>
<p><code>\ping 192.168.1.1</code></p>
<p>Print all Aliases</p>
<p><code>alias -p</code></p>
<h4 id="math">Math</h4>
<p>Math is simple. Use <code>+</code> for adding, <code>-</code> sor subtracting, <code>*</code> for multiplying, and <code>/</code> for dividing. Make sure to use double parentheses.</p>
<p><code>echo $(( 10 + 5 ))</code></p>
<blockquote>
<p>15</p>
</blockquote>
<p><code>echo $(( 10 - 5 ))</code></p>
<blockquote>
<p>5</p>
</blockquote>
<p><code>echo $(( 10 * 5 ))</code></p>
<blockquote>
<p>50</p>
</blockquote>
<p><code>echo $(( 10 / 5 ))</code></p>
<blockquote>
<p>2</p>
</blockquote>
<p><code>echo $(( 10 + 5 - 8 * 7 / 6 ))</code></p>
<blockquote>
<p>8</p>
</blockquote>
<p>Bash math <strong>does not</strong> follow order of operations, it just does the math left to right.</p>
<h4 id="other-files">Other Files</h4>
<p>There are many things that you can do to other files. Before I get into anything about other files, I want you to <a href="https://docs.replit.com/getting-started/creating-files">create a text file</a>, and name it <code>file.txt</code>. Inside of <strong>file.txt</strong>, I want you to type or copy/paste this sentence once:</p>
<p>The quick brown fox jumps over the lazy dog.</p>
<p>Let’s get started with some code. Firstly, this command will list all of the directories inside of the Repl:</p>
<p><code>ls</code></p>
<blockquote>
<p><code>main.sh</code> file.txt</p>
</blockquote>
<p>This command will list all of the directories on a different line:</p>
<p><code>ls -l</code></p>
<blockquote>
<p>total 4</p>
</blockquote>
<blockquote>
<p>-rw-r–r-- 1 runner runner 5 (month, date, time) <code>main.sh</code></p>
</blockquote>
<blockquote>
<p>-rw-r–r-- 1 runner runner 0 (month, date, time) file.txt</p>
</blockquote>
<p>This command sorts the directory by last modified date:</p>
<p><code>ls-t</code></p>
<blockquote>
<p><code>main.sh</code></p>
</blockquote>
<blockquote>
<p>file.txt</p>
</blockquote>
<p>or</p>
<blockquote>
<p>file.txt</p>
</blockquote>
<blockquote>
<p><code>main.sh</code></p>
</blockquote>
<p>This command will recursively <code>ls</code> this directory and all of it’s subdirectories:</p>
<p><code>ls -R</code></p>
<p>Note: Make sure the “R” is capitalized.</p>
<blockquote>
<p>.:</p>
</blockquote>
<blockquote>
<p><code>main.sh</code> file.txt</p>
</blockquote>
<p>This command will list all txt files <strong>only</strong>.</p>
<p><code>ls -l | grep "\.txt"</code></p>
<blockquote>
<p>-rw-r–r-- 1 runner runner 1 (month day time) file.txt</p>
</blockquote>
<p>This command makes it so that you can read the contents of other files without having to click on that file and see what’s in that file.</p>
<p><code>cat file.txt</code></p>
<blockquote>
<p>The quick brown fox jumps over the lazy dog.</p>
</blockquote>
<p>This command makes it easier to see what’s in a file, if you have many of them that you’re using the <code>cat</code> command on.</p>
<p><code>Contents=$(cat file.txt)</code></p>
<p>Note: <code>\n</code> means the next text will be printed on a new line.</p>
<p>Note: <code>-e</code> to interpret the newline escape characters as escape characters.</p>
<p><code>echo -e"START OF FILE\n$Contents\nEND OF FILE"</code></p>
<blockquote>
<p>START OF FILE</p>
</blockquote>
<blockquote>
<p>The quick brown fox jumps over the lazy dog.</p>
</blockquote>
<blockquote>
<p>END OF FILE</p>
</blockquote>
<h4 id="renaming-and-moving-files">Renaming and Moving Files</h4>
<p>These commands make it so that you can rename, add, delete, and clone directories and files right from bash.</p>
<p>This command clones <code>file.txt</code> and names the new file <code>clone.txt</code>.</p>
<p>cp file.txt clone.txt</p>
<p>ls</p>
<blockquote>
<p><code>main.sh</code> file.txt clone.txt</p>
</blockquote>
<p>This next command moves the contents of a file to another one with a different name and deletes the source one. This literally means just renaming the file.</p>
<p>mv file.txt main.txt</p>
<p>ls</p>
<blockquote>
<p><code>main.sh</code></p>
</blockquote>
<blockquote>
<p>main.txt</p>
</blockquote>
<h4 id="cd-commands">CD Commands</h4>
<p>These commands just change, clone, and add directories, as well as move to different directories.</p>
<p>These commands move you to the home directory:</p>
<p><code>cd ~</code> or <code>cd</code></p>
<p>This command moves up one directory:</p>
<p><code>cd ..</code></p>
<p>This command moves you to the last directory:</p>
<p><code>cd -</code></p>
<p>These commands move you to specific directories:</p>
<p><code>cd /home/username/documents</code> or <code>cd ~/Documents/</code></p>
<h4 id="subdirectories">Subdirectories</h4>
<p>Subdirectories are directories in which you can hold other information under current directories. Example:</p>
<p>This command uses subshells to work across directories:</p>
<p>mkdir someDir</p>
<p>(echo “First, I’m here: $PWD”) &amp;&amp; (cd someDir; echo “Then, I’m here: $PWD”)</p>
<blockquote>
<p>First, I’m here: /home/runner/Bash-Test</p>
</blockquote>
<blockquote>
<p>Then, I’m here: /home/runner/Bash-Test/someDir</p>
</blockquote>
<p>This command makes a new directory:</p>
<p><code>mkdir</code></p>
<p>Example of this being used:</p>
<p>mkdir oneDir</p>
<p>cd oneDir</p>
<p>echo I’m in this directory: $PWD</p>
<blockquote>
<p>I’m in this directory: /home/runner/Bash-Test/oneDir</p>
</blockquote>
<p>This command will create directories as needed:</p>
<p><code>mkdir -p myNewDir/with/intermediate/directories</code></p>
<p>You can see all of the directories in your files section.</p>
<h4 id="redirecting">Redirecting</h4>
<p>Redirecting puts various messages, like errors, in directories so that you can easily go through them. Take this python code for example:</p>
<p>cat &gt; <a href="http://hello.py">hello.py</a> &lt;&lt; EOF</p>
<p>from <strong>future</strong> import print_function</p>
<p>import sys</p>
<p>print("#stdout", file=sys.stdout)</p>
<p>print("#stderr", file=sys.stderr)</p>
<p>for line in sys.stdin:</p>
<p>print(line, file=sys.stdout)</p>
<p>EOF</p>
<p>You can redirect command input and output (stdin, stdout, and stderr). Read from stdin until <code>^EOF$</code> and overwrite <code>hello.py</code> with the lines between “EOF.”</p>
<p>There are various commands that you can use here.</p>
<p>Pass <code>input.in</code> as input to the script</p>
<p><code>python hello.py &lt; "input.in"</code></p>
<p>Redirect output from the script to output.out:</p>
<p><code>python hello.py &gt; "output.out"</code></p>
<p>Redirect error output to error.err:</p>
<p><code>python hello.py 2&gt; "error.err"</code></p>
<p>Redirect both output and errors to output-and-error.log:</p>
<p><code>python hello.py &gt; "output-and-error.log" 2&gt;&amp;1</code></p>
<p>Redirect all errors to the “black hole (/dev/null)” or no output.</p>
<p><code>python hello.py &gt; /dev/null 2&gt;&amp;1</code></p>
<p>The output error will rewrite the file if it exists. Use <code>&gt;&gt;</code> if you want to append.</p>
<p><code>python hello.py &gt;&gt; "output.out" 2&gt;&gt; "error.err"</code></p>
<p>Overwrite output.out, append to error.err, and count lines:</p>
<p>info bash ‘Basic Shell Features’ ‘Redirections’ &gt; output.out 2&gt;&gt; error.err</p>
<p>wc -l output.out error.err</p>
<p>Run a command and print it’s file descriptor. (Example: /dev/fd/123)</p>
<p><code>echo &lt;(echo "#helloworld")</code></p>
<p>Overwrite output.out with <code>#helloworld</code>:</p>
<p>cat &gt; output.out &lt;(echo “#helloworld”)</p>
<p>echo “#helloworld” &gt; output.out</p>
<p>echo “#helloworld” | cat &gt; output.out</p>
<p>echo “#helloworld” | tee output.out &gt;/dev/null</p>
<p>Cleaning up temporary files:</p>
<p><em>Warning: The command RM cannot be undone!</em></p>
<p>rm -v output.out error.err output-and-error.log</p>
<p>rm -r tempDir/</p>
<p>This recursively deletes all of it.</p>
<h4 id="substituting-commands">Substituting Commands</h4>
<p>Substituting commands means that you use parentheses to substitute commands with other commands using <code>$( )</code>.</p>
<p>This command displays the number of files in the current directory:</p>
<p><code>echo "There are $(ls | wc -l) items here."</code></p>
<blockquote>
<p>There are 2 items here</p>
</blockquote>
<p>You <em>can</em> use backticks, but that cannot be nested, so the preferred method is using <code>$( )</code>.</p>
<p>Bash uses a case statement that works similarly to switch in Java and C++.</p>
<p>case “$Variable” in</p>
<h1 id="list-patterns-for-the-conditions-you-want-to-meet">List patterns for the conditions you want to meet</h1>
<ol start="0">
<li>
<p>echo “There is a zero.”;;</p>
</li>
<li>
<p>echo “There is a one.”;;</p>
</li>
</ol>
<p>*) echo “It is not null.”;; # match everything</p>
<p>esac</p>
<h4 id="loops">Loops</h4>
<p>For loops itearate for as many arguments given.</p>
<p>The contents of <code>$Variable</code> is printed 3 times.</p>
<p>for Variable in {1…3}</p>
<p>do</p>
<p>echo “$Variable”</p>
<p>done</p>
<blockquote>
<p>1</p>
</blockquote>
<blockquote>
<p>2</p>
</blockquote>
<blockquote>
<p>3</p>
</blockquote>
<p>This is using the traditional “for” loop way:</p>
<p>for ((a=1; a &lt;= 3; a++))</p>
<p>do</p>
<p>echo $a</p>
<p>done</p>
<blockquote>
<p>1</p>
</blockquote>
<blockquote>
<p>2</p>
</blockquote>
<blockquote>
<p>3</p>
</blockquote>
<p>They can also be used to act on files.</p>
<p>This will run the command <code>cat</code> on <code>file1</code> and <code>file2</code>:</p>
<p>for Variable in file1 file2</p>
<p>do</p>
<p>cat “$Variable”</p>
<p>done</p>
<p>This can <em>also</em> be used from an output from a command.</p>
<p>This will <code>cat</code> the output from <code>ls</code>.</p>
<p>for Output in $(ls)</p>
<p>do</p>
<p>cat “$Output”</p>
<p>done</p>
<p>Bash can also do patterns, like this to <code>cat</code> all of the markdown files in the current directory. Create 3 markdown files and name them whatever you want so that this command will work. I named mine “a,” “b,” and “c.”</p>
<p>for Output in ./*.markdown</p>
<p>do</p>
<p>cat “$Output”</p>
<p>done</p>
<p>While Loop:</p>
<p>while [ true ]</p>
<p>do</p>
<p>echo “loop body here…”</p>
<p>break</p>
<p>done</p>
<blockquote>
<p>Loop body here…</p>
</blockquote>
<p>You can also define functions:</p>
<p>{</p>
<p>echo “Arguments work just like script arguments: $@”</p>
<p>echo “And: $1 $2…”</p>
<p>echo “This is a function”</p>
<p>return 0</p>
<p>}</p>
<p>Call the function <code>foo</code> with 2 arguments, “arg1” and “arg2”</p>
<p><code>foo arg1 arg2</code></p>
<blockquote>
<p>Arguments work just like script arguments: arg1 arg2</p>
</blockquote>
<blockquote>
<p>And: arg1 arg2…</p>
</blockquote>
<blockquote>
<p>This is a function</p>
</blockquote>
<p>Or simply:</p>
<p>bar ()</p>
<p>{</p>
<p>echo “Another way to declare functions!”</p>
<p>return 0</p>
<p>}</p>
<p>Call the function <code>bar</code> with no arguments.</p>
<p><code>bar</code></p>
<blockquote>
<p>Another way to declare functions!</p>
</blockquote>
<p>Calling your function:</p>
<p><code>foo "My name is" $Name</code></p>
<h4 id="useful-commands-to-know">Useful Commands to Know</h4>
<p>Prints last 10 lines of file.txt:</p>
<p><code>tail -n 10 file.txt</code></p>
<p>Prints first 10 lines of file.txt:</p>
<p><code>head -n 10 file.txt</code></p>
<p>Sort file.txt’s lines:</p>
<p><code>sort file.txt</code></p>
<p>Report or omit any repeated lines:</p>
<p><code>uniq -d file.txt</code></p>
<p>Prints only the first column before the <code>'</code> character:</p>
<p><code>cit -d ',' -f 1 file.txt</code></p>
<p>Replaces every occurrence of “quick” with “fast” in file.txt:</p>
<p><code>sed -i 's/quick/fast/g' file.txt</code></p>
<p>Print to stdout all lines of file.txt which match some regex. This example prints lines which start in “foo” and end in “bar.”</p>
<p><code>grep "^foo.*bar$" file.txt</code></p>
<p>Use the option <code>-c</code> to instead print the number of lines that matches the regex:</p>
<p><code>grep -c "^foo.*bar$" file.txt</code></p>
<p>This option recursively greps the regex:</p>
<p><code>grep -r "^foo.*bar" someDir</code></p>
<p>This gives the line numbers that matches the regex:</p>
<p><code>grep -n "^foo.*bar$" file.txt</code></p>
<p>This also recursively greps the regex but ignores binary:</p>
<p><code>grep -rI "^foo.*bar$" someDir</code></p>
<p>Perform the same initial search, but filter out the lines containing “razzi.”</p>
<p><code>grep "^foo.*bar$" file.txt | grep -v "razzi"</code></p>
<p>The <code>trap</code> command allows you to execute a command whenever your script receives a signal. Here, <code>trap</code> will execute <code>rm</code> if it receives any of the three listed signals:</p>
<p><code>trap "rm $TEMP_FILE; exit" SIGHUP SIGINT SIGTERM</code></p>
<p><code>Sudo</code> is used to perform commands as the superuser:</p>
<pre><code>NAME1=$(whoami)

NAME2=$(sudo whoami)

echo "Was $NAME1, then became more 	powerful $NAME2"
</code></pre>
<h4 id="how-to-get-help-if-needed">How to get Help if Needed</h4>
<p>In Repl there’s an option, on the right where you’ve been using the “console” tab, there’s another tab where only these following commands will work, but they can give you all the help that you need. This is the “shell” tab. if you ever need any help, just click on that and put in any of these following commands:</p>
<p><code>help</code></p>
<p><code>help help</code></p>
<p><code>help for</code></p>
<p><code>help return</code></p>
<p><code>help source</code></p>
<p><code>help .</code></p>
<h5 id="read-bash-manpage-documentation">Read Bash manpage documentation:</h5>
<p><code>apropos bash</code></p>
<p><code>man 1 bash</code></p>
<p><code>man bash</code></p>
<h5 id="read-info-documentation">Read info documentation:</h5>
<p><code>apropos info</code> or <code>grep '^info.*('</code> &lt;-- This one for Console.</p>
<p><code>man info</code></p>
<p><code>info info</code></p>
<p><code>info 5 info</code></p>
<h5 id="read-bash-info-documentation">Read Bash info documentation:</h5>
<p><code>info bash</code></p>
<p><code>info bash 'Bash Features'</code></p>
<p><code>info bash 6</code></p>
<p><code>info --apropos bash</code></p>
<h1 id="thank-you-so-much">Thank you so Much!</h1>
<p>If you have actually read through this, then I thank you so much! This took me about 12 total hours to complete, and if there are any mistakes, then please don’t hesitate to email me at: <code>26grogab@elmbrookstudents.org</code>.</p>
<p>I want to disclaim so people don’t yell at me in the comments: <em><strong>This is not my tutorial, I just put this into markdown and made it a little bit easier for people to understand.</strong></em> You can find the original tutorial <a href="https://learnxinyminutes.com/docs/bash/">here</a>. I created all of this markdown in <a href="https://stackedit.io/">Stackedit</a>. Again, thank you so much for reading all of this!</p>

