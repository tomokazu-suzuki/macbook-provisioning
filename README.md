# macbook-provisioning

## ansibleを実行する前の準備

### xcodeのインストール

~~~
xcode-select --install
~~~

### home-brewのインストール

~~~
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
~~~

### ansibleのインストール

~~~
brew install ansible
~~~

### gitのインストール

~~~
brew install git
~~~

### bash_profileの編集

~~~
# default
export PATH="/usr/local/sbin:$PATH"
export PATH="/usr/local/bin:$PATH"
# set application install path
export HOMEBREW_CASK_OPTS="--appdir=/Applications"

# bashrc
if [ -f ~/.bashrc ] ; then
. ~/.bashrc
fi

# alias
alias vi='vim'
~~~

~~~
$ source ~/.bash_profile
~~~

### elcapitanにアップグレードした場合は下記を実行します

~~~
brew update
~~~

## 使い方

1. provisioningディレクトリを作成します

~~~
mkdir ~/provisioning && cd $_
~~~

1. このリポジトリをcloneします
1. /group_vars/all を編集して、必要なソフトウェアを管理します

1. 下記を実行します

~~~
ansible-playbook playbook.yml -i hosts
~~~

## karabinerのprivate.xmlの設定が反映されない場合

1. 「Change key」タブの「Reload XML」ボタンを押して下さい
