Installation:
--------------
    ALL:
    ----
    install git
    set up ssh: https://help.github.com/articles/generating-ssh-keys

    Linux:
    ------
    ```
    git clone git@github.com:cldershem/dotfiles.git ~/.dotfiles
    cd ~/.dotfiles
    python ./install.py
    ```

    OS X:
    ----
    ```
    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    sudo easy_install pip
    brew install cmake
    brew install vim
    brew install tmux
    brew install zsh
    brew install wget
    sudo pip install virtualenvwrapper
    sudo pip install flake8

    cd ~/.dotfiles
    git submodule update --init

    chsh -s /bin/zsh

    ln -s ~/.dotfiles/vim ~/.vim
    ln -s ~/.dotfiles/vim/vimrc ~/.vimrc
    ln -s ~/.dotfiles/tmux/tmux.conf ~/.tmux.conf
    ln -s ~/.dotfiles/bashrc ~/.bashrc
    ln -s ~/.dotfiles/git/gitconfig ~/.gitconfig
    ln -s ~/.dotfiles/zsh/zshrc ~/.zshrc
    ln -s ~/.dotfiles/zsh/oh-my-zsh ~/.oh-my-zsh
    ln -s ~/.dotfiles/zsh/cameron.zsh-theme ~/.oh-my-zsh/themes

    cd ~/.vim/bundle/YouCompleteMe
    git submodule update --init --recursive
    ./install.sh --clang-completer
    # or ./install.py  -- changed in recent version

    wget https://github.com/Lokaltog/powerline/raw/develop/font/PowerlineSymbols.otf
    ```
    double click font in finder to install
    select font in Terminal
    possibly disable some zsh plugins
    if using xcode set up alcatraz.io and XVim plugins for X Code and make .xvimrc


??
install make
cd ~/.dotfiles
make

add swap?
https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04

sudo update-alternatives --config editor
choose vim.basic
??


# direnv
```
git clone https://github.com/zimbatm/direnv
cd direnv
make install
```

Use:
------
Add new plugins to pathogen
```
cd ~/.dotfiles
git submodule add git://path.to/plugin vim/bundle/plugin
update install.py
```

Update plugins:
```
cd ~/.dotfiles
git submodule foreach git pull origin master
```
may need to recompile ycm

Don't for get to set up your ssh keys for git.
https://help.github.com/articles/generating-ssh-keys
May need `eval "$(ssh-agent)"`

if trouble
```
git rm --cached ~/.vim/bundle/plugin
```
or better yet just rm the plugin and add it properly next time

# [VIM-Plug](https://github.com/junegunn/vim-plug)
```
>>> curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
>>>    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
>>> nvim ~/.vimrc
>>>>>:PlugInstall
```


References
------------
- http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/

sudo apt-get update && sudo apt-get -y upgrade && sudo apt-get -y install git && \
git clone https://github.com/cldershem/dotfile.git ~/.dotfiles && cd ~/.dotfiles && \
make
