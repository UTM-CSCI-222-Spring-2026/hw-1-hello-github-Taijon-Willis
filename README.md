[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=22100713)
# Assignment: Hello, GitHub (Intro to Codespaces, g++, make, and git)

Welcome to your first assignment! In this activity, you will:

- Learn your way around GitHub Codespaces
- Write and run a basic C++ program
- Compile with g++ and make (no Makefile)
- Use basic git commands: add, commit, push, and pull
- Deal with common git/GitHub sync errors
- Submit your results using the autograder report

---------------------------------------------------------------------------

🎓 From CompileIt to the Real World

In your previous course, you used a tool called CompileIt, which helped
simplify the coding and compilation process. Now that you’re leveling up,
it's time to graduate to the tools that real-world programmers use every
day. That means writing code in a full development environment, using
the Linux command line, compiling with g++, managing projects with
make, and tracking changes with git.

This may feel like a big step, but it’s an exciting one — these are the
same tools used by professional software developers around the world.
Let’s get started!

---------------------------------------------------------------------------

🌐 Before We Begin: What Are GitHub, Git, and Codespaces?

GitHub is a website that hosts git repositories — these are collections of
code and history for a project. You’re using GitHub to store your code,
share it with others, and submit assignments.

Git is a version control system. It lets you track changes to your code,
revert back to earlier versions, and collaborate with others without
overwriting each other's work.

GitHub Codespaces is a cloud-based development environment. Think of it as
a fully configured Linux computer that lives in your browser. It includes a
code editor, terminal, and the tools you need to get started right away.

---------------------------------------------------------------------------

📁 Repository vs Codespace – What’s the Difference?

- Your repository is the project on GitHub.com — it stores your code,
  tracks changes, and runs the autograder.

- Your Codespace is a temporary development environment where you do your
  work.

Keep BOTH tabs open:
- The Codespace tab is where you write and test code.
- The Repository tab is where you view commits and check the autograder.

---------------------------------------------------------------------------

🚀 Step 1: Launching Codespaces

1. Click the "Open in GitHub Codespaces" button on your GitHub
   repository page.
2. Wait for the Codespace to finish setting up.

---------------------------------------------------------------------------

🖥️ Step 2: Getting Oriented

In the Codespaces tab, locate the following:

- File Panel (left) – shows your files
- Editor Panel (center) – where you write code
- Terminal (bottom) – command-line interface

The file panel and editor should be pretty much self-explanatory. The
terminal is a little more complex. This is a command-line interface
where you can run commands to compile code, manage files, and use git.
Codespaces gives you a containerized Linux environment, so you have
access to all the standard Linux commands.

If you have never used a command line before, don't worry! We will be
covering how to get around in here. For now, just keep in mind that
this is not a document. It is a user interface. You type a command,
and press enter. The command is executed, and you see the output. You
cannot go back and edit past interactions, but you can use the up and
down arrows to scroll through your command history and repeat
commands.

---------------------------------------------------------------------------

💻 Step 3: Open the Starter File

1. In the File Panel, click on `hello.cpp`
2. Enter your name and a brief description of the program in the comment
   at the top of the file. This comment is a special doxygen comment. 
   Doxygen is a handy tool that allows us to generate documentation for
   our programs. We will learn more about this later, for now just remember
   to fill in the doxygen comment for any program that you create in 
   this class.
2. Enter code in the main function which prints the words "Hello,
   world!" to the console.

---------------------------------------------------------------------------

⚙️ Step 4: Compile and Run

Using g++:

    g++ hello.cpp -o hello
    ./hello

Using make:

    make hello
    ./hello

Delete and rebuild:

    rm hello
    make hello

Do you notice something about using `make`? It automatically compiled
your code without you need to specify the whole command line! `make`
is smart enough to compile single file programs where the source file
has the same name as the executable. Later on, we will learn how to
use make to automate the build process for larger projects. From now
on, we will use `make` to compile our code.

---------------------------------------------------------------------------

📝 Step 5: Using Git

    git add hello.cpp
    git commit -m "Initial version - incorrect output"
    git push

Check the autograder:
- Go to your repository tab
- Click the ❌ red X on your commit. You will see this ❌ if your
  tests fail. (Yes, I had you do it wrong on purpose 😄)
- Click "Details" to see the autograder result   We will fix this
  soon, but first, let's induce a common GitHub error.

---------------------------------------------------------------------------

🧪 Step 6: Inducing a GitHub Error

1. On the GitHub repository page, click "Add file > Create new file"
2. Name it added.md and write your favorite movie quote in it
3. Click "Commit Changes" and commit directly to main

Now your repository has a new file that your Codespace does not know
about. This will cause a sync error when you try to push your changes.
Learning the procedure for resolving this error is an important
skill for working with GitHub.

---------------------------------------------------------------------------

🛠️ Step 7: Fix and Push Again

Fix hello.cpp to print the message we want, "Hello, GitHub!" instead
of "Hello, world!".

Rebuild and test your program:

    make hello
    ./hello

Try pushing:

    git add hello.cpp
    git commit -m "Fixed output"
    git push

It will fail because your remote repository has changes that your
local repository does not. You need to pull those changes first.

---------------------------------------------------------------------------

🔄 Step 8: Pull and Resolve

In order to resolve a sync error in git, we need to pull the changes.
Sometimes this will work automatically, but sometimes it will result
in merge conflicts. We probably will not experience a merge conflict
in this class, so we will just focus on pulling in changes.

Try running the following command:

    git pull

Now, this will likely result in an error message like this:

    hint: You have divergent branches...
    hint: Configure pull behavior using:
      git config pull.rebase false  # merge
      git config pull.rebase true   # rebase
      git config pull.ff only       # fast-forward only

This is because your local git configuration does not know how you
want to handle pulling changes. For this class, we will always want
the merge behavior, so we will run the following command:

    git config pull.rebase false

Now try pulling again:

    git pull

This time, you should see a message showing the files that have
changed. Have a look at your Codespace file panel. You should see
that there is a new file! This process of pushing and pulling is how
GitHub can be used to collaborate with others as well as providing
a way for you to back up your own work.

Now that we have pulled the changes, we can push our own changes to
see if we pass the autograder tests. Run the command:

    git push

Now, go back to your repository tab. Once the test completes, you
should see a ✅ green check mark next to your commit. If you do not,
click the ❌ and look at the autograder report to see what went wrong.
Keep making changes, adding, committing, and pushing until you see the
green check mark.

---------------------------------------------------------------------------

🧾 Final Step: Submit to Canvas

1. In your GitHub repository, click the ✅ green check mark
2. Click "Details" to open the autograder report
3. Copy the URL of that page
4. Paste it into your Canvas assignment submission

Note that I will be checking both the autograder and your repository
history. If you did not do the section about fixing the sync error,
please go back and do it now (or else you'll lose points!)

---------------------------------------------------------------------------

✅ Assignment Complete!

You’ve:
- Used GitHub Codespaces
- Written and compiled a C++ program
- Used g++, make, git
- Resolved sync conflicts
- Submitted your work with the autograder

🎉 Great job!Get practice using GitHub Codespaces and basic git commands.
