Initialised a Git repo

```sh
  git init
```

Thereafter added the file to be staged and added a commit message
->

```sh
  git add . #Stages the file - git knows about the change but it's not permanent in the repo
  git commit -m "First commit" #Commit will include the changes staged within the files
```

To see current state of repository & working directory

```sh
  git status

  #Which will show us if the file has been modified / removed etc
```

We can customize what goes into a commit by arranging the files to be staged along with their commits

```sh
  git add a.html
  git add b.html
  git commit -m "Changes for a and b"

  #Thereafter stage and commit another unrelated piece of code change

  git add c.html
  git commit -m "Unrelated change to c"
```

The -m flag allows us to write out commit message within the command line

```sh
  #message command
  -m "commit message here"
```

If we skip it, our terminal will open our default option editor (in my case Vim).
In Vim we press 'a' to type in the text editor and once we have included our message, we can go and exit 'editing phase' by pressing the esc and then :wq to save and exit the editor.

Will look similar to this:

```sh
  <Your commit message here>
  # Please enter the commit message for your changes. Lines starting
  # with '#' will be ignored, and an empty message aborts the commit.
  #
  # On branch main
  # Changes to be committed:
  #       modified:   hello.html
  #
```

#### NOTE: Git expects a commit message for every commit

Viewing history in Git by using `sh git log `
This will print the commit history within your repository which consists of:

- The Sha-1
- Author name - email
- Date
- Commit message

However you can style and dictate as to what gets printed in the console!

```sh
  git log --pretty=oneline
  or try git log --pretty <press tab> #this will show the other options available such as --pretty=short, --pretty=full etc
```

If however you wish to spice things up with specifics:

```sh
  git log --pretty=oneline --max-count=2
  git log --pretty=oneline --since='5 minutes ago'
  git log --pretty=oneline --until'1 days ago'
  git log --pretty=oneline --until'1 days ago'
  git log --pretty=oneline --author=<author name>
  git log --pretty=oneline --all
```

```sh
  #How to log commits by author name or email
  git log --author="<author name | email>"
```

Super useful one for getting a commit by the commit message:

#### Main pattern for git logging that is super useful

```sh
  git log --grep="<regex or string in here>" #example git log --grep="changed header"
```

Below is a link that explores some more `sh git log`options:
![https://www.w3docs.com/learn-git/git-log.html]

#### Git tag

Some common uses for Git tags include marking releases, marking significant milestones in development, and indicating a specific version of a project that corresponds to a particular environment or configuration.

```sh
  git tag <tagname> #This will enable you to jump to said commit using tag name such as command below:
  git checkout <tagname>
```

#### Using the bellow command will remove any changes made to a file that you wish not to keep (discard)

```sh
  git checkout <filename>  #This will cause you to discard changes made in said file. You will lose it if you have not staged it before.
```
