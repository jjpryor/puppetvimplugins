# puppetvim
Useful and handy config &amp; plugins for Vim to enable puppet syntax and style
checking from within Vim.

We will be using Vundle to install/manage the following Vim plugins:

+ https://github.com/vim-airline/vim-airline
+ https://github.com/vim-airline/vim-airline-themes
+ https://github.com/scrooloose/syntastic/
+ https://github.com/voxpupuli/vim-puppet/
+ https://github.com/godlygeek/tabular


## Known Dependencies
+ Red Hat family OS
+ `vim-enhanced` command
+ `git` command
+ `puppet` agent
+ `puppet-lint` command


## Depedency Installation
Run the following in a shell as root.
```shell
yum install git vim-enhanced
yum install https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm
yum install puppet-agent
which puppet
```

We need `puppet-lint` and it gets installed as a ruby `gem`.
```shell
/opt/puppetlabs/puppet/bin/gem install puppet-lint
ln -s /opt/puppetlabs/puppet/bin/puppet-lint /usr/local/sbin/puppet-lint
which puppet-lint
```

## Backup
As normal user, backup your `.vimrc` &amp; `.vim`
```shell
mv ~/.vimrc ~/.vimrc-bak
mv ~/.vim ~/.vim-bak
```


##Enable
```shell
touch ~/.vimrc
mkdir -p .vim/bundle
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Edit the `.vimrc` file 
```shell
foo
```

Run vim and install Vundle 
```shell
PluginInstall
```

Test it with puppet code:
```shell
puppet module install puppetlabs-ntp
```
It should install the module to either
`/etc/puppetlabs/code/environments/production/modules/ntp/manifests` or
`~/.puppetlabs/etc/code/modules/ntp/manifests`

It should look like:

![Image of syntax](https://raw.githubusercontent.com/jjpryor/puppetvim/master/vimsyntaxcheck.png)
