# puppetvim
Useful and handy config &amp; plugins for Vim to enable puppet syntax and style
checking from within Vim.

## Known Dependencies
+ Red Hat family OS
+ `vim-enhanced` command
+ `git` command


## Depedency Installation
Run the following in a shell as root.
```shell
yum install git vim-enhanced
yum install https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm
yum install puppet-agent
which puppet
/opt/puppetlabs/puppet/bin/gem install puppet-lint
ln -s /opt/puppetlabs/puppet/bin/puppet-lint /usr/local/sbin/puppet-lint
which puppet-lint
```

As normal user
## Installation
```shell
touch ~/.vimrc
mkdir -p .vim/bundle
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
vim ~/.vimrc
```

Test it with puppet code:
```shell
puppet module install puppetlabs-ntp
cd /etc/puppetlabs/code/environments/production/modules/ntp/manifests
```

