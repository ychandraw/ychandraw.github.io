---
title: "Common Git Commands Line"
date: 2021-02-21
categories:
  - reference
tags:
  - github
  - git
---

Git has so many command line which we can used. Remember all of them would be a waste to our brain memory. When we frequently use the common Git commands line, those will be stored somewhere deep down under our concious.

I just want to list down what are the common git commands line which i frequently used for my reference usage on github and hopefully you get the benefit of it as well.

## Common Git Commands
### git clone

*git clone* command used to copy existing remote repository and create a local working copy of it. What _git clone_ does, it will:
- Copy the remote repository files and folders to our local computer,
- Automatically create a remote connection called `origin` which pointing back to original remote repository. This remote connection is established by creating Git refs to the remote branch heads under `refs/remotes/origin` and by initializing `remote.origin.url` and `remote.origin.fetch` configuration variables.

Command:
```shell
$ git clone <remote_URL>
```
The `<remote_URL>` commonly use the *https* protocol. Example: https://github.com/xyz/xyz.github.io.git

Sample Usage:
```shell
$ git clone https://github.com/xyz/xyz.github.io.git
```
The outcome of above command is to copy the remote repository to the current folder and creating a new folder called `xyz.github.io.git`. 

If you want to clone it to specific folder location, you could specified the folder name at behind. Example:

```shell
$ git clone https://github.com/xyz/xyz.github.io.git my_folder
```
___

### git config
*git config* command used to set the configuration or setting for 'git'. Configuration names are *dot delimited strings* composed of a `section` and a `key` based on their hierarchy. There are 2 most important setting for git which are `user.name` and `user.email`. These settings set the user name and the user email used when commits from local computer.

Command:
```shell
$ git config <setting> <command>
```

Sample Usage:
```shell
$ git config user.name "chandra.wijaya"
$ git config user.email "chandra.wijaya@xyz.com"
```

There is a configuration levels which defined as arguments to specify which configuration level to operate on. There are 3 configuration levels as below:

`--local`
  
As default, if when we dont specify an argument, `git config` command will write to local level and it will apply only to the current local repository that you are currently in. 

Local configuration values are stored in a local repository folder `.git` directory on `.git/config` file.

`--global`

A `--global` argument is used to write the git settings to **all repositories** for a operating system user local computer. Global configuration values are stored in a file that is located in a user's home directory. `~/.gitconfig` on unix systems and `C:\Users\\.gitconfig` on windows system.

`--system`

A `--system` argument is used to write the git settings to **all repositories** on a local computer globally. This argument apply to **all operating system users** and **all repositories** inside that local computer. 

The system level configuration file stored in a `gitconfig` file off the system root path. `$(prefix)/etc/gitconfig` on unix systems. On windows this file can be found at `C:\Documents and Settings\All Users\Application Data\Git\config` on Windows XP, and in `C:\ProgramData\Git\config` on Windows Vista and newer.

The priority sequence order for above 3 configuration levels as below: 
1. local 
2. global 
3. system 

This has a meaning that  when looking for a configuration value, `Git config` will start at the 1st local level, then only 2nd global level and last is system level.

___

### git init
When first time we create a local directory without using `clone` method above, we need to initiate `git init` command to turn that local directory into an **empty Git repository**. 

This is the first step in creating a local repository. After that, we can continue with next git command by adding and committing local files / directories inside that local directory.

Command:
```shell
# change directory to my_folder
$ cd /Users/computer-name/Documents/my_folder

# make my_folder directory a git repository
$ git init
Initialized empty Git repository in /Users/computer-name/Documents/my_folder/.git/
```
___

### git add
To add files into staging area (Git index) for `git` we use `git add` command. There are different ways to use this command depending on what we want to achieve. We can add entire directories, add specific files, or even all unstaged files with this `git add` command.

Command:
```shell
$ git add <file or directory name>
```

Sample Usage:
```shell
# To add all files not staged in current directory:
$ git add .

# To add an index.html file only:
$ git add index.html

# To add an entire html directory:
$ git add html
```
___

### git commit
Use the `git commit` command to record the changes made on the files/directories to a local repository. Each **commit** has a unique ID for the purpose of easy reference. There is best practice that we include a message for each commit, to explain what are the changes made on that commit for better understanding and help to find the specific changes we have done earlier in the future.

Command:
```shell
# Adding a commit with message
$ git commit -m "Commit message in quotes"
```

Sample Usage:
```shell
$ git commit -m "My first commit message"
```
