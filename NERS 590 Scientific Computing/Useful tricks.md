**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Useful tricks](#)
	- [bash](#)
	- [vim](#)
	- [Fortran](#)
	- [C/C++](#)
	- [Python](#)
	- [git](#)
	- [Ruby](#)
	- [CMake](#)
		- [TriBITS](#)

# Useful tricks

## bash

* How to RTFM? Manual page of certain `<command>`: use

  `man <command>`
  
  In the manual (manpage) one can:
  
  * **Search**: Type `/` and then the keyword
  * **Undo highlighting** after a search: `ESC+u`
  * **Quit**: `q`
  * **Help**: `h` to see all **commands for navigating manpages** (`man` uses the GNU `less` commands to view the manpages, so hitting `h` will show the `SUMMARY OF LESS COMMANDS`)
* Download files
  
  ```bash
  wget download_url
  # for Mac OS, use the following instead
  curl "download_url" -o "filename"
  ```
* Use `echo` to display any environment variable
  
  ```bash
  echo $HOSTNAME # show the hostname
  echo $PS1 # show the custom bash prompt
  ```
  
* Use `more <filename>` to display the content of a file
* the bash default setting file `~/.bashrc`, in Mac this is `~/.bash_profile`
* change **bash prompt**
    * custom prompt: change the `$PS1` environment variable. 
      
      Reference: [How to: Change / Setup bash custom prompt (PS1)](http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html)

      ```bash
      PS1='\u@\h:\W\$ '
      ## \u means user name, 
      ## \h means hostname up to the first dot
      ## \W means the basename of the current working directory
      ## \w means the current working directory
      ```
    
    * color: [Bash Prompt HOWTO](http://tldp.org/HOWTO/Bash-Prompt-HOWTO/x329.html)
* Documentation available at [Too Long Didn't Program (tldp)](http://tldp.org/LDP/abs/html/index.html)
* **Search command history** when hitting the up/down arrows: add the following lines in the `~/.inputrc` 
  
  ```bash
  ## arrow up
  "\e[A":history-search-backward
  ## arrow down
  "\e[B":history-search-forward
  ```

## vim

* 10 min tutorial [http://www.openvim.com/](http://www.openvim.com/)
* vim default setting: the `~/.vimrc` file. 
    * How to create one? Copy it:
    
      ```
      cp /usr/share/vim/vim73/vimrc_example.vim ~/.vimrc
      ```
      
      with this `.vimrc` file, the syntax *highlighting* will be as default
* Commands:
    * vim help: under *normal mode*, type `:help` enter.
    * *input mode*: `i`
* Searching:
    * Search: Type `/` then any keywords, `n` (`Shift+n`) jump to the next (previous) keyword.
    * Unhighlight the search results: `:nohl` or `:nohlsearch`
* Copy/pasting
    * Copying: `y`
    * Before pasting: `:set paste` this will **disable auto-indent**
    * Pasting: `p`
    * After pasting: `:set nopaste` recover the auto-indent feature
* Formatting
    * switch case: `~` (``Shift+` ``)
    * shift right: `>` (`Shift+.`)
    * shift left: `<` (`Shift+,`)
  
## Fortran

* Dr. C.-K. Shene's [Fortran 90 Tutorial](http://www.cs.mtu.edu/~shene/COURSES/cs201/NOTES/fortran.html)
* Data type & definition (reference: [U of Wisconsin Milwaukee, CS151](http://www.cs.uwm.edu/~cs151/Bacon/Lecture/HTML/ch06s09.html))
    * `real(8)` or `double precision` must be defined as 

      `3.1415926535897932d0`
      
      Without the `d0` (or `d+0`) at the end, compiler will treat it as single precision.
      
    * `integer(8)` number must be defined as 
      
      `9223372036854775807_8`
      
      Without the `_8` at the end, compiler will return `Error: Integer too big for its kind`
      
    * When the length of a string is unsure, must define with the `parameter` option: 

      `character (len=*), parameter :: u = 'hello world'`

## C/C++

* **Data type** & printing/scaning (reference: [Wikipedia: C data types](https://en.wikipedia.org/wiki/C_data_types))
    * When defining `long double`, need to append an `L` at the end of the number: 

      ```c++
      long double y = 3.14159265358979323846264338327950288L;
      ```
      
    * When printing the `long double` variables with `printf`, need to use `%Lf` or `%Le` (note big L) as format specifier. Also, when to use higher precision than `double` is all up to the compiler, in many cases `long double` may just be the same as `double`.
    * When printing `bool` variable, can't directly print "true" or "false". need to do something like 

      ```c++
      printf("%s", b?"true":"false")
      // b is a "bool" variable defined
      //    with the "stdbool.h" library
      ```       
      
    * When using `scanf` to read `double`, need to use `%lf` specifier.
* **C/C++ Library**
    * to compile a C++ library use 
       
      `g++ -c <lib_name>.cpp -o <lib_name>.o`
       
    * to link the library use 

      `g++ main.cpp <lib_name>.o`

* **Pointers**  
    * [Passing 2D array to C++ functions](http://stackoverflow.com/questions/8767166/passing-a-2d-array-to-a-c-function)
    * [Correct way to dynamically allocate a 2D array](http://stackoverflow.com/questions/30117161/why-do-i-need-to-use-type-to-point-to-type)

      ```c
      // correct way
      int (*array2d)[Y] = malloc(sizeof(int[X][Y]));
      
      // wrong way
      int** heap_fiasco;
      heap_fiasco = malloc(X * sizeof(int*));
      for(int x=0; x<X; x++){
            heap_fiasco[x] = malloc(Y * sizeof(int));
      }
      ```


## Python

* Useful tool: [Anaconda](https://www.continuum.io/downloads), Python package manager + IDEs (Spyder is useful IDE for python that looks like MATLAB)
* [The key difference between Python 2.7 and 3.5](http://sebastianraschka.com/Articles/2014_python_2_3_key_diff.html)
* Common commands
    * If-clause `if (condition):`
    * For-loop `for i in range(n):`
    * While-loop `while (condition):`
    * Print `print("Integer: %d, string: %s, raw: %r", 3, "Cool", 'b20t5')`
    * String to list of numbers 
      
      ```python
      string = "1 2 3"
      list = [int(x) for x in string.split()]
      ```

    * **Sometimes need to convert type `byte` to `str`**

* Functions
  
  ```python
  def MyFun(arg1, arg2):
      sum = arg1 + arg2
      print("The sum of %f and %f is %f" % (arg1, arg2, sum))
      return ar1, arg2, sum
  ```
  
* Libraries

  ```python
  from sys import argv
  fileName, input1, input2 = argv
  
  from numpy import sin, pi
  sin(pi)
  
  import numpy as np
  np.sin(np.pi)
  ```

* Files manipulation

  ```python
  f = open(filename)
  text = f.read()
  
  f.seek(0) #back to initial position, can read again
  print(f.readline())
  ```

## git

* Visual, interactive, step-by-step [Learn Git Branching Tutorial](http://learngitbranching.js.org/)
* Local repo
    * **initialize** a repo: `git init`
    * **add** changes to staging area: `git add <filename>`
    * **commit** changes: `git commit -m "describe the commit"`
    
    <img src="gitLocalOp.png" width="300px"/>
    
    * **switch** to a different branch: `git checkout <branch>`
    * **create AND switch** to a new branch: `git checkout -b <branch>`
    * **merge** another branch to the current branch: `git merge <branch>`
* Remote repo
    * create a remote branch: `git remote add <remo branch> <url>`
    * **fetch** a remote branch: `git fetch <remo branch>` (download files and refs from the remo branch)
    * **pull** a remote branch:`git pull <remo branch> <loc branch>` (same as `fetch`+`merge` a remo branch) See also: [How to deal with merge conflicts](https://www.git-tower.com/learn/git/ebook/en/command-line/advanced-topics/merge-conflicts)
    * **push** a remote branch:`git push <remo branch> <loc branch>` (opposite of `git pull`, upload a loc branch and merge to the remo branch)

## Ruby

* `rake -D` list all tasks in Rakefile with descriptions
* `rake -T` list major tasks with their descriptions

## CMake

* `cmake` basics: **build**/configure a package
  
  ```bash
  ## inside the package directory
  cd <RepositoryDirectory>
  mkdir build  
  cd build ## Configure in a separate "build" directory.
             ## It's considered a bad habit to config
             ## directly in the source.
  cmake ../
  make
  ctest
  history # Show command history. 
            # (Not part of the config process)
  ```

* Commands explained: 
    * `cmake` = **configuration**: `./configure` with additional flags/options automated by CMake, produce the `Makefile`.
    * `make` = **compilation**: `g++` or `gcc` or `gfortran` etc. with additional flags/options specified in `Makefile`.
    * `ctest` = testing features allowed by CMake, run the test
* Reference for how to write the CMake controlling file `CMakeLists.txt`: [CMake hello world](http://derekmolloy.ie/hello-world-introductions-to-cmake/) Including 5 examples:
    * hello world
    * project
    * static library
    * shared library
    * using libraries

### TriBITS

* TriBITS = Tribal Build, Integrate, and Test System
* TriBITS is built on top of **CMake**
* TriBITS is a *framework* handling *large software development projects* involving multiple independent development teams and multiple source repositories
