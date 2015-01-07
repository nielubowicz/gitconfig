:toc:

= Git configuration

== What is ~/.gitconfig? How does it work?
Your user's gitconfig file, found at `~/.gitconfig`, controls the configuration for all git repos and commands for this user. If you've ever used a `.bashrc` file, or a `.profile` file, this is the same idea. A formatted, nested text file that contains options and configurations for git.

```
[15:02:48]~/Code/gitconfig (master ✘)✭ ᐅ git config --global user.name "A Developer"
[15:03:43]~/Code/gitconfig (master ✘)✭ ᐅ git config --global user.email "adeveloper@mobiquityinc.com"
[15:05:30]~/Code/gitconfig (master ✘)✭ ᐅ cat ~/.gitconfig
[user]
	name = A Developer
	email = adeveloper@mobiquityinc.com
```

== What is the .git/config file in a local repository?
Same as above, except found in your local repo (`~/Code/this-is-a-repo/.gitconfig`), it only applies to this specific repo. This config file contains the URL for your repo as other relevant options.
```
[core]
        ignorecase = true
[remote "origin"]
        url = git@github.com:nielubowicz/gitconfig.git
[branch "master"]
        remote = origin
```

== How to create aliases and shortcuts
Aliases, like their bash and shell cousins, are text-substituted variables for simplifying your life. They live in a section of your `.gitconfig` called `[alias]`. Let's add some simple aliases to your `.gitconfig`
```
[15:03:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global alias.st "status"
[15:04:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global alias.ci "commit"
[15:05:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global alias.br "branch"
[15:06:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global alias.co "checkout"
[15:07:00]~/Code/gitconfig (master ✘)✭ ᐅ cat .git/config
[alias]
  st = status
  ci = commit
  br = branch
  co = checkout
  hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --date=short
```

== What are some other useful Git configurations?
```
color.ui
[15:06:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global color.ui auto
``` 
Sets global color for git commands. 
```
help.autocorrect
[15:06:55]~/Code/gitconfig (master ✘)✭ ᐅ git config --global help.autocorrect 1
```
If you mistype a command, git normally gives you a "Did you mean ...?" prompt. If you set `help.autocorrect` to 1, git will automagically run the intended command. Could be a good idea.

