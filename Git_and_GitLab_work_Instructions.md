*The work instruction provides a comprehensive guide for utilizing
**Git** and **GitLab** effectively, offering step-by-step procedures and
best practices to facilitate version control and collaborative software
development within the team.*

**<span class="underline">Purpose:</span>**

*The document aims to provide instructions for using Git on a local
machine, as well as collaborating on a GitLab repository to facilitate
effective version control management within the team.*

**<span class="underline">scope:</span>**

*The document aims to provide step-by-step instructions for beginners
and intermediate users, guiding them through the process of setting up
and utilizing Git on a local machine. It will cover essential Git
commands, branching strategies, merging, resolving conflicts, and best
practices for effective version control. Additionally, the document will
include detailed guidelines for collaborating on a shared GitLab
repository, demonstrating how to push, pull, and manage changes as a
team. By addressing common challenges and providing practical examples,
the document seeks to empower the team with the necessary skills for
efficient version control management, fostering seamless collaboration
and productivity.*

**<span class="underline">Description:</span>**

*The document will empower team members with the knowledge and guidance
needed to efficiently use Git on their local machines and collaborate on
GitLab for effective version control management*.

  - *The document will outline the appropriate moments during the
    software development process when Git actions are essential, such as
    when creating new features, fixing bugs, or preparing for a release.
    It will also highlight the relevance of specific GitLab operations
    during team collaboration phases, including code reviews and merging
    branches.*

  - *The document will clarify the roles and responsibilities of team
    members involved in Git-related tasks. It will identify individuals
    responsible for initiating code changes, conducting code reviews,
    merging code, and handling repository management on GitLab.*

  - *The document will provide detailed, step-by-step procedures for
    each Git activity, including initializing a repository, creating
    branches, committing changes, resolving conflicts, and using
    advanced features like rebasing. Similarly, it will outline the
    workflow for collaborating on a GitLab repository, detailing how to
    request merges, review code, and perform version control tasks
    effectively.*

  - *The document will list the necessary tools and software required to
    work with Git on a local machine, such as installing Git,
    configuring user settings, and using a preferred code editor or
    integrated development environment (IDE). Additionally, it will
    mention the use of GitLab's web interface and its integrations with
    various development tools for collaboration.*

*  
*

# Contents

[1 GIT 3](#git)

[1.1 Introduction 3](#introduction)

[1.2 GIT Installation and Steps 4](#git-installation-and-steps)

[1.2.1 Configure Git 4](#configure-git)

[1.2.2 Set Up SSH Key: 4](#set-up-ssh-key)

[1.2.3 choose id\_rsa file Location: 4](#choose-id_rsa-file-location)

[1.2.4 Set PassPhrase: 4](#set-passphrase)

[1.2.5 Create a new Git repository 5](#create-a-new-git-repository)

[1.2.6 Make changes to your code: 5](#make-changes-to-your-code)

[1.2.7 Track and stage changes: 5](#track-and-stage-changes)

[1.2.8 Commit changes: 5](#commit-changes)

[1.2.9 Push changes to a remote repository:
6](#push-changes-to-a-remote-repository)

[1.2.10 Pull changes from a remote repository:
6](#pull-changes-from-a-remote-repository)

[1.2.11 Branching and merging: 6](#branching-and-merging)

[2. GitLab 6](#gitlab)

[2.1 Steps to login to GitLab 6](#steps-to-login-to-gitlab)

[2.2 Creating a New GitLab Project 7](#creating-a-new-gitlab-project)

[2.3 Clone the GitLab Project onto your Local Git:
7](#clone-the-gitlab-project-onto-your-local-git)

[2.4 Create Local GIT Repository to GITLAB:
8](#create-local-git-repository-to-gitlab)

[2.5 Handling Issues in Gitlab 9](#handling-issues-in-gitlab)

*  
*

# **GIT**

## Introduction

> Git is a distributed version control system (VCS) that helps you
> manage and track changes to your source code or any other set of
> files. It was created by Linus Torvalds, the creator of Linux, and is
> widely used in software development.
> 
> Here are some key aspects of Git:

  - > Version Control

<!-- end list -->

  - Git tracks changes to files over time, allowing you to view the
    history and revert to previous versions if needed.

  - It helps teams collaborate on projects by providing a centralized
    repository where multiple people can work on the same codebase
    simultaneously.

<!-- end list -->

  - > Distributed

<!-- end list -->

  - Unlike centralized version control systems, Git is distributed. Each
    developer has a complete local copy of the entire repository,
    including the full history.

  - This allows developers to work offline, commit changes locally, and
    synchronize with remote repositories later.

<!-- end list -->

  - > Repository

<!-- end list -->

  - A Git repository is a collection of files and directories along with
    the version history and metadata.

  - Git repositories can be local on your computer or hosted remotely on
    platforms like GitHub, GitLab, or Bitbucket.

<!-- end list -->

  - > Commit

<!-- end list -->

  - A commit is a recorded change to the repository. It represents a
    snapshot of the project at a specific point in time.

  - Each commit has a unique identifier (SHA-1 hash) and includes the
    author, timestamp, and a message describing the changes.

<!-- end list -->

  - > Remote Repository

<!-- end list -->

  - Git enables you to push your local changes to a remote repository
    hosted on a server.

  - Popular remote repository hosting services include GitHub, GitLab,
    and Bitbucket.

<!-- end list -->

  - > Pull and Push

<!-- end list -->

  - To update your local repository with the latest changes from the
    remote repository, you "pull" the changes.

  - Conversely, to share your local changes with others, you "push" them
    to the remote repository.

<!-- end list -->

  - > Branching and Merging

<!-- end list -->

  - Git makes branching and merging effortless, enabling developers to
    create separate branches to work on new features, bug fixes, or
    experiments.

  - Branches are lightweight and can be easily merged back into the main
    branch (typically called "master" or "main").

> Git is widely used in the software development industry due to its
> powerful features, speed, and flexibility. It provides a robust
> solution for managing source code, tracking changes, and collaborating
> effectively with others.

## GIT-Installation and Steps

> If you don't have Git installed on your laptop, you can download and
> install it from Portal manager.
> 
> “**GIT git 2.40.0 MUI**”.

### Configure Git

> Open a terminal or command prompt /git bash.

1.  > Check git is installed on your system.

> git --version

2.  > Set your username by running:

> git config --global user.name "Your Name"

3.  > Set your email address by running:

> git config --global user.email "your@email.com"

4.  > Run below command to check the username and email details.

> git config --global –list

### Set Up SSH Key:

> Set up SSH key: GitLab typically uses SSH for secure communication.
> Generate an SSH key pair on your laptop if you don't have one already.
> Open a terminal or command prompt and run the following command:
> 
> ssh-keygen -t rsa -b 4096 -C "your\_email@example.com"
> 
> Replace "your\_email@example.com" with the email address associated
> with your GitLab account. Press Enter to accept the default file
> location and optionally set a passphrase for added security.

### choose id\_rsa file Location:

  - When you see the prompt "Enter file in which to save the key
    (/c/Users/user.name /.ssh/id\_rsa): or (/P:/.ssh/id\_rsa):" during
    the SSH key generation process, it is asking you to specify the file
    path where you want to save the generated SSH key.

  - By default, it suggests the file path
    \`(/c/Users/user.name/.ssh/id\_rsa) or (/P:/.ssh/id\_rsa)\`. This is
    a common default location for SSH keys on Windows systems, but you
    can choose a different location if you prefer.

  - If you want to accept the default file path, simply press Enter
    without making any changes. The SSH key will be saved in the
    suggested file path.

  - If you want to specify a different file path, you can enter the
    desired location and filename. For example, you could enter
    \`(/c/Users/user.name/.ssh/my\_key\_rsa) or (/P:/.ssh/id\_rsa)\` to
    save the key with a different filename.

  - After providing the file path, the SSH key generation process will
    continue, and the key pair (public and private keys) will be
    generated and saved in the specified location.
    
    1.  ### Set PassPhrase:

<!-- end list -->

  - When you see the prompt "Enter passphrase (empty for no
    passphrase):" during the SSH key generation process, it is asking
    you to set a passphrase for your SSH key. A passphrase is an extra
    layer of security that adds a password-like protection to your
    private key.

  - Here are a few things to consider when deciding whether to set a
    passphrase:

  - **Passphrase for added security:** Setting a passphrase adds an
    additional layer of protection to your private key. If someone gains
    unauthorized access to your private key file, they would still need
    to know the passphrase to use it.

  - **Convenience vs. Security:** On the other hand, having a passphrase
    means you will need to enter it every time you use your private key.
    This can be slightly inconvenient, especially if you use your key
    frequently. However, it helps ensure that even if someone gains
    access to your private key file, they cannot use it without knowing
    the passphrase.

  - **Choosing a passphrase:** If you decide to set a passphrase, choose
    a strong and unique passphrase that is difficult to guess. It is
    recommended to use a combination of uppercase and lowercase letters,
    numbers, and special characters.

  - If you want to set a passphrase, enter your desired passphrase at
    the prompt. You will be asked to confirm the passphrase by entering
    it again.

  - If you prefer not to set a passphrase and have an empty passphrase,
    simply press Enter without typing anything. Keep in mind that this
    reduces the security of your private key since anyone who gains
    access to the key file can use it without a passphrase.

  - Choose an option based on your security preferences and convenience,
    and proceed accordingly.
    
    1.  ### Create a new Git repository

> Navigate to the directory where you want to initialize your
> repository.

1.  > Create new directory

> mkdir myFirstProject
> 
> cd myFirstProject

2.  > Run the following command to create a new repository:

> git init
> 
> (hidden folder .git will be created)

3.  > Below command can be used to know the status (mostly used all
    > times for conformation)

> git status

### Make changes to your code:

> Create or modify files in your local repository using your preferred
> code editor.

### Track and stage changes:

1.  > Use the following command to view the status of your repository:

> git status

2.  > Stage your changes to be committed by running:

> git add \<file\> \# Stage a specific file
> 
> git add . \# Stage all files

### Commit changes:

> Commit the staged changes along with a descriptive commit message:
> 
> git commit -m "Your commit message"

### Push changes to a remote repository:

> If you have a remote repository, push your commits to it:
> 
> git push origin \<branch-name\>

### Pull changes from a remote repository:

> If you're collaborating with others, it's essential to sync your local
> repository with the remote changes periodically:
> 
> git pull origin \<branch-name\>

### Branching and merging:

> Create a new branch to work on a specific feature or bug fix:
> 
> git branch \<branch-name\>
> 
> git checkout \<branch-name\>
> 
> After making changes and committing them, switch back to the main
> branch:
> 
> git checkout main
> 
> Merge your branch into the main branch:
> 
> git merge \<branch-name\>
> 
> common Git commands used in various situations can be found in
> APPENDIX A

# GitLab 

> GitLab is a web-based platform that provides a set of tools for
> version control, continuous integration and deployment, project
> management, and collaboration. It offers functionalities similar to
> other popular version control systems like Git, but with additional
> features that facilitate the entire software development lifecycle.
> 
> Here are the basic steps to get started with GitLab:

## Steps to login to GitLab

  - > Request for GitLab Account creation by ServiceDesk-AKKODIS

> ServiceDesk-AKKODIS -\> New business solution -\> Red button: Get it
> now\!
> 
> Once all the Data are filled, then “Submit a Request”
> 
> Once the request is approved.

  - > Visit the Akkodis internal GitLab website
    > (<https://gitlab.akka.eu/>)

> You may encounter Privacy Error "Your connection isn't private" first
> time, then click on the advanced and select "Continue to
> gitlab-internal.akka.eu (unsafe)"

  - > **Add SSH Key in GITLAB:**

<!-- end list -->

  - > Copy the public key: Assuming you have generated your SSH key
    > pair, you need to access the contents of the public key file. Open
    > the public key file (usually located at \`\~/.ssh/id\_rsa.pub\`)
    > in a text editor, and copy the entire contents of the file.

  - > Access GitLab settings: Log in to your GitLab account and navigate
    > to your user settings or profile. Look for the "Settings" or
    > "Profile Settings" option.

  - > Add the public key to GitLab: In the GitLab settings, find the
    > "SSH Keys" section. It is typically located in the left-hand
    > navigation menu. Click on "SSH Keys" to open the SSH keys
    > management page.

  - > Add the public key: On the SSH keys page, you will see an input
    > field where you can paste your public key. Paste the contents of
    > the public key file that you copied earlier into this field.

  - > Save the key: After pasting the public key, give it a recognizable
    > title in the "Title" field. This title can be anything you like
    > and is used for identification purposes. Once you have entered the
    > title, click on the "Add key" or "Save key" button to save the SSH
    > key in your GitLab account.

  - > GitLab should now have your SSH public key stored in your account.
    > You can use this key to authenticate and securely communicate with
    > GitLab repositories using the SSH protocol.
    
    1.  ## Creating a New GitLab Project

<!-- end list -->

  - Select "New project" or click on the "New project" button on the
    right corner of the dashboard.

  - On the "Create a new project" page, you'll need to fill in the
    necessary details for your project:

  - Provide a project name: Enter a unique and descriptive name for your
    project.

  - The project URL usually GitLab weblink with Project name

  - Choose the project's visibility: You can make it either Internal
    (The project can be accessed by any logged in user except external
    users.) or private (only visible to project members).

  - Once you've filled in the necessary details, click on the "Create
    project" button at the bottom of the page.

  - GitLab will create your new project and redirect you to the
    project's page.

  - From the project page, you can perform various actions, such as
    managing repository files, setting up CI/CD pipelines, creating
    issues, and collaborating with other team members.
    
    1.  ## Clone the GitLab Project onto your Local Git:

To clone a GitLab project onto your local machine, you can follow these
steps:

  - > **Obtain the repository URL:** Open the GitLab project in your web
    > browser and locate the repository URL. You can find it by clicking
    > on the "Clone" button, which should reveal the HTTPS or SSH URL.

  - > **Choose a directory for the clone:** Decide on a directory on
    > your local machine where you want to clone the GitLab project. You
    > can use the command line or terminal to navigate to this
    > directory.

  - > **Clone the repository:** In the terminal or command prompt, use
    > the \`git clone\` command followed by the repository URL. Here are
    > two examples using different protocols:

> Clone with HTTPS:

  - git clone https://gitlab.com/username/repository.git

> Clone with SSH (requires SSH key setup):

  - git clone git@gitlab.com:username/repository.git

  - 
  - > Replace \`username\` with your GitLab username and \`repository\`
    > with the name of the project you want to clone.

  - > **Enter credentials (if using HTTPS):** If you are cloning via
    > HTTPS, you might be prompted to enter your GitLab username and
    > password. Provide the required credentials to proceed with the
    > cloning process.

  - > **Confirm the clone:** Once the cloning process completes, you
    > should see a new directory created in your chosen location. This
    > directory will have the same name as the GitLab repository.

  - > By following these steps, you will have successfully cloned the
    > GitLab project onto your local machine. You can now make changes,
    > create branches, and interact with the repository locally.

> **NOTE:**
> 
> *When you see the message "The authenticity of host '...' can't be
> established" with an ED25519 key fingerprint, it means that your SSH
> client (such as Git) is encountering an unknown host key for the
> GitLab server you're trying to connect to. The host key is used to
> verify the authenticity and integrity of the server you're connecting
> to.*
> 
> *In this case, the message is informing you that the host key for the
> GitLab server with the IP address 172.25.252.203 and port 22522 is not
> recognized or stored in your SSH known\_hosts file.*
> 
> *To proceed, you have a few options:*
> 
> *1. \*\*Verify the host key\*\*: If you trust the GitLab server and
> want to proceed with the connection, you can manually verify the host
> key. Compare the displayed ED25519 key fingerprint
> (\`SHA256:l3BakSLP\*\*\*\*\*\*\*\*\*XYHnbJQe+8C2YUcw\`) with the known
> host key of the GitLab server. This key fingerprint can often be found
> in the server's documentation or provided by the server administrator.
> If they match, you can confirm and continue connecting to the server.*
> 
> *2. \*\*Update the known\_hosts file\*\*: If you want to store the
> host key in your SSH known\_hosts file to avoid future warnings, you
> can update the file with the new host key. To do this, run the
> following command in your terminal:*
> 
> *ssh-keyscan -p 22522 -t ed25519 gitlab-internal.akka.eu \>\>
> \~/.ssh/known\_hosts*
> 
> *This command fetches the host key for the specified GitLab server and
> appends it to your known\_hosts file. After running this command, the
> warning should no longer appear when connecting to the server.*
> 
> *3. \*\*Investigate further\*\*: If you are unsure or suspect any
> security concerns, it's best to reach out to the system administrator
> or support team responsible for the GitLab server. They can provide
> guidance and help verify the authenticity of the server.*
> 
> *Remember, it's important to exercise caution when connecting to
> unknown or unfamiliar servers, especially when handling sensitive
> information. Verify the authenticity of the server and ensure you
> trust it before proceeding.*

## Create Local GIT Repository to GITLAB:

To add a local Git repository to GitLab, you can follow these steps:

  - > **Create a new repository on GitLab**: Log in to your GitLab
    > account and create a new empty repository. Give it a name and,
    > optionally, provide a description.

  - > **Initialize your local repository**: If you haven't already,
    > navigate to the directory of your local Git repository using the
    > command line or terminal.

  - > Connect the local repository to the remote GitLab repository: In
    > the terminal, execute the following commands:

  - > Add the GitLab repository as a remote:

> git remote add origin \<GitLab\_repository\_URL\>
> 
> Replace \`\<GitLab\_repository\_URL\>\` with the SSH or HTTPS URL of
> your GitLab repository. You can find this URL on the GitLab repository
> page, typically under the "Clone" button.

  - > **Verify the remote connection**:

> git remote -v
> 
> This command lists the configured remotes for your local repository.
> It should display the GitLab remote you just added.

  - > **Push your local repository to GitLab**: After adding the remote
    > connection, you can push your local repository to GitLab:

> git push -u origin master

  - > This command pushes your local "master" branch to the "origin"
    > remote repository on GitLab. If you're using a different branch
    > name, replace "master" with your branch name.

  - > If this is the first time pushing to the remote repository, you
    > may be prompted to enter your GitLab username and password or
    > provide your SSH passphrase.

  - > Verify the repository on GitLab: Refresh the GitLab repository
    > page in your web browser, and you should see the files and commits
    > from your local repository.

  - > By following these steps, you will successfully add your local Git
    > repository to GitLab and establish the connection between them.
    > This allows you to push and pull changes between your local
    > repository and the GitLab repository for collaborative
    > development.
    
    1.  ## Handling Issues in Gitlab

  - Navigate to your GitLab project.
    
      - Open your web browser and go to the GitLab website (e.g.,
        https://gitlab.com).
    
      - Sign in to your GitLab account.
    
      - Locate and select the project where you want to add an issue.

  - Go to the "Issues" section.
    
      - Within the project, find the "Issues" tab or link and click on
        it. This will take you to the issues page.

  - Create a new issue.
    
      - On the issues page, click on the "New issue" button or similar
        option to create a new issue.

  - Provide issue details.
    
      - In the new issue form, enter the relevant details:
    
      - **Title**: Give a concise and descriptive title for the issue.
    
      - **Description**: Provide a detailed description of the issue,
        including steps to reproduce, expected behavior, and any
        additional information that may be helpful for understanding and
        resolving the issue.
    
      - **Assignee**: If there is a specific person responsible for
        addressing the issue, you can assign it to them.
    
      - **Labels**: Add relevant labels to categorize and track the
        issue (e.g., bug, feature request, documentation).
    
      - **Milestone**: If your project uses milestones, you can
        associate the issue with a specific milestone.
    
      - **Due date**: Optionally, you can set a due date for the issue.

  - Submit the issue.

> Once you have provided all the necessary information, click on the
> "Submit issue" button or similar option to create the issue.
> 
> Additional actions.
> 
> After creating the issue, you may perform additional actions, such as
> adding comments, attaching files, or editing the issue details.

1.  **Common Git commands**

usage:

| git \[-v | --version\]                                        |  |
| ------------------------------------------------------------- |  |
| \[-h | --help\]                                               |  |
| \[-C \<path\>\]                                               |  |
| \[-c \<name\>=\<value\>\]                                     |  |
| \[--exec-path\[=\<path\>\]\]                                  |  |
| \[--html-path\]                                               |  |
| \[--man-path\]                                                |  |
| \[--info-path\]                                               |  |
| \[-p | --paginate | -P | --no-pager\]                         |  |
| \[--no-replace-objects\]                                      |  |
| \[--bare\]                                                    |  |
| \[--git-dir=\<path\>\]                                        |  |
| \[--work-tree=\<path\>\]                                      |  |
| \[--namespace=\<name\>\]                                      |  |
| \[--config-env=\<name\>=\<envvar\>\] \<command\> \[\<args\>\] |  |

start a working area (see also: git help tutorial)

| clone | Clone a repository into a new directory                        |
| ----- | -------------------------------------------------------------- |
| init  | Create an empty Git repository or reinitialize an existing one |

work on the current change (see also: git help everyday)

| add     | Add file contents to the index                        |
| ------- | ----------------------------------------------------- |
| mv      | Move or rename a file, a directory, or a symlink      |
| restore | Restore working tree files                            |
| rm      | Remove files from the working tree and from the index |

examine the history and state (see also: git help revisions)

| bisect | Use binary search to find the commit that introduced a bug |
| ------ | ---------------------------------------------------------- |
| diff   | Show changes between commits, commit and working tree, etc |
| grep   | Print lines matching a pattern                             |
| log    | Show commit logs                                           |
| show   | Show various types of objects                              |
| status | Show the working tree status                               |

grow, mark and tweak your common history

| branch | List, create, or delete branches                            |
| ------ | ----------------------------------------------------------- |
| commit | Record changes to the repository                            |
| merge  | Join two or more development histories together             |
| rebase | Reapply commits on top of another base tip                  |
| reset  | Reset current HEAD to the specified state                   |
| switch | Switch branches                                             |
| tag    | Create, list, delete or verify a tag object signed with GPG |

collaborate (see also: git help workflows)

| fetch | Download objects and refs from another repository                  |
| ----- | ------------------------------------------------------------------ |
| pull  | Fetch from and integrate with another repository or a local branch |
| push  | Update remote refs along with associated objects                   |

'git help -a' and 'git help -g' list available subcommands and some

concept guides. See 'git help \<command\>' or 'git help \<concept\>'

to read about a specific subcommand or concept.

See 'git help git' for an overview of the system.
