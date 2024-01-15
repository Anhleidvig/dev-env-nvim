# basics
sudo apt-get update
sudo apt-get install g++
sudo apt-get install fd-find
sudo apt-get install ripgrep
sudo apt-get install unzip

# homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/anhleidvig/.bashrc
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
sudo apt-get install build-essential
brew install gcc

# git
sudo apt-get install git
sudo add-apt-repository ppa:git-core/ppa
sudo apt update 
sudo apt install git

# nvim config
mkdir ~/.config
cd ~/.config
git clone https://github.com/Anhleidvig/dev-env-nvim.git nvim
brew install jesseduffield/lazygit/lazygit
sudo add-apt-repository ppa:neovim-ppa/unstable
sudo apt-get install neovim

# oh-my-posh
brew install jandedobbeleer/oh-my-posh/oh-my-posh
brew update && brew upgrade oh-my-posh

# NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install node
nvm install v18.19.0

# PHP
sudo add-apt-repository ppa:ondrej/php

sudo apt-get install -y php7.4 php7.4-cli php7.4-fpm php7.4-mbstring php7.4-curl php7.4-bz2 php7.4-zip php7.4-xml php7.4-gd php7.4-mysql php7.4-intl php7.4-sqlite3 php7.4-soap php7.4-bcmath php7.4-memcached php7.4-redis php7.4-xmlrpc php7.4-imagick

sudo apt-get install -y php8.3 php8.3-cli php8.3-fpm php8.3-mbstring php8.3-curl php8.3-bz2 php8.3-zip php8.3-xml php8.3-gd php8.3-mysql php8.3-intl php8.3-sqlite3 php8.3-soap php8.3-bcmath php8.3-memcached php8.3-redis php8.3-xmlrpc php8.3-imagick

OPTIONAL: sudo apt install -y apt-transport-https nginx mysql-client mysql-server

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer

# .bashrc
#GIT
eval "$(ssh-agent)"

# OH MY POSH
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bashrc

eval "$(oh-my-posh init bash --config ~/dev-env/oh-my-posh/themes/kali.omp.json)"

# NVM
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
