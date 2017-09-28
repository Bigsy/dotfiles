# dotfiles
    git init --bare $HOME/.myconf
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    config config status.showUntrackedFiles no
    
    config status
    config add .vimrc
    config commit -m "Add vimrc"
    config push
    
    git clone --separate-git-dir=$HOME/.myconf git@github.com:Bigsy/dotfiles.git $HOME/myconf-tmp
    cp ~/myconf-tmp/.gitmodules ~  # If you use Git submodules
    rm -r ~/myconf-tmp/
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    
    
