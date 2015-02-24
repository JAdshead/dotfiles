My Dotfiles
===========

Clone this repo into `~/.dotfiles` and then if you go inside this directory you
can use the following commands:


Not have to do this if use rcm

- `./please add-gitvars`: Helps your adding git env variables to your `.zshrc`.
- `./please add-zshrc`: Sources the zshell settings in your `.zshrc`.
- `./please add-gitconfig`: Include the git configs in your `.gitconfig`.
- `./please add-all`: Adds all the above.
- `./please install-brew`: Installs homebrew (for macosx).



========

Install rcm

```
$ brew tap thoughtbot/formulae
$ brew install rcm
```

Run rcm (this command expects that you cloned your dotfiles to `~/dotfiles/`)
```
$ env RCRC=$HOME/dotfiles/rcrc rcup
```
RCM creates dotfile symlinks (`.vimrc` -> `/dotfiles/vimrc`) from your home directory to your `/dotfiles/` directory.


### Installing Plugins
Plugins are listed in `vimrc.bundles`.

To install them you'll need vundle. Installation directions are here: https://github.com/gmarik/Vundle.vim.
Once vundle is installed. Open vim and type `:BundleInstall`. And then restart vim. You'll need to do this for everything to work.


### Recommended

**MacVim**
By default OSX has an older version of Vim. I recommend installing MacVim and running it from within iterm. This can be done with brew.
```
$ brew install macvim --override-system-vim
```
This overwrites your default Vim installation. You should restart terminal after installing.

**iterm2**  
Use iterm2 instead of Terminal: http://iterm2.com/