# dotfiles
    git init --bare $HOME/.myconf
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    config config status.showUntrackedFiles no
    
    config status
    config add .vimrc
    config commit -m "Add vimrc"
    config push
    
    git clone --separate-git-dir=$HOME/.myconf git@github.com:Bigsy/dotfiles.git .myconf-tmp
    rsync --recursive --verbose --exclude '.git' myconf-tmp/ $HOME/
    rm --recursive myconf-tmp
    alias config='/usr/bin/git --git-dir=$HOME/.myconf/ --work-tree=$HOME'
    
    
