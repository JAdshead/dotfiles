My Dotfiles
===========

Just source this file in `~/.zshrc`

```
export GIT_AUTHOR_NAME='My Name'
export GIT_AUTHOR_EMAIL='my@name.com'
export GIT_COMMITTER_NAME='My Name'
export GIT_COMMITTER_EMAIL='my@name.com'

source ~/.dotfiles/zshrc
```

My initial setup my new systems
================================

System Preferences > Security & Privacy > General > Allow Applications downloaded from -> Select Anywhere

Xcode > Preferences > Downloads, and install Command Line Tools

Install Text editor - Sublime Text 3
-  symlink for Sublime Text
  + ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl
- set as Editor for commands that prompt for input
  + export EDITOR='subl -w'

- install package manager
  + https://sublime.wbond.net/installation#st3
- install Solarized Dark theme


Install Package Manager
- go to http://brew.sh/ and install homebrew
- Ensure that the Homebrew directories are in your PATH:
  + echo "export PATH=/usr/local/bin:$PATH" >> ~/.bash_profile
- reload bash profile
  + source ~/.bash_profile
- brew doctor
- brew update

Install ZSH
-  brew install zsh
-  Before changing the default shell, we make sure the install went okay:
  + Run Zsh by typing /usr/local/bin/zsh
  + launch into a Zsh prompt
  + NOTE: Zsh might bug you to configure it. Tell it to create a blank .zshrc file, because oh-my-zsh is going to configure it.

- Add the brewed Zsh to default shells by editing the shells file and adding the new one:
  + Type subl /etc/shells
  + Add /usr/local/bin/zsh to the bottom of the file and save it
  + Make Zsh the default shell with chsh -s /usr/local/bin/zsh, then close and reopen terminal application.

Install oh-my-zsh
- Run the curl command:
  + curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
- Move Homebrew’s directory further up the PATH, so that software loads from there by preference:
  + Open the zshrc file: subl ~/.zshrc
  + Find the line that starts with export PATH=$PATH (usually at the end of the file)
  + Get rid of the $PATH part which is located just after the = sign
  + Move the /usr/local/bin part to the front of the statement (just after the = sign)
  + Add $PATH at the end of the line (just after the last colon) and save the file

Install Ruby Environment (Rbenv) and builder
- brew install ruby-build rbenv
- Ensure that rbenv is loaded whenever we open a command line session:
  + if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
- Restart Terminal

Install a version of Ruby with ruby-build
- rbenv install {The latest version of ruby e.g 2.0.0-p457}
- rbenv rehash
- rbenv global {version installed e.g 2.0.0-p247}
- Test its the right version
  + ruby -v

Skip gem rdoc generation
- echo 'gem: --no-rdoc --no-ri' >> ~/.gemrc

Install Bundler
- gem install bundler
- rbenv rehash

Install PostgreSQL
Install Git