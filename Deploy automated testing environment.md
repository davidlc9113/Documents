# Deploy automated testing environment
@(testing)[automated testing]

## 1. Install Ruby

Execute command `ruby -v` in terminal to check Ruby version. If it does not work or the version is less than 1.9.3, you should install Ruby manually.

### Ubuntu Linux / OS X / ...

#### Install system dependence

  - Ubuntu Linux is required to install `libssl-dev`, `libreadline-dev` and `libffi-dev`.
    ```bash
    $ sudo apt-get install libssl-dev libreadline-dev libffi-dev
    ```

  - OS X is required to install [Xcode](http://developer.apple.com/xcode/) and [Homebrew](http://brew.sh/). Then you should install `readline` by Homebrew.
    ```bash
    $ brew install readline
    ```

####  Install Ruby by [rbenv](https://github.com/sstephenson/rbenv)

  1. clone rbenv and its plugins to `~/.rbenv`
    ```bash
    $ # copy all following content to teminal
    git clone git://github.com/sstephenson/rbenv.git ~/.rbenv
    git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
    git clone git://github.com/jamis/rbenv-gemset.git  ~/.rbenv/plugins/rbenv-gemset
    git clone git://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash
    git clone https://github.com/rkh/rbenv-update.git ~/.rbenv/plugins/rbenv-update
    ```

  2. add content to shell config (Ubuntu Linux: `~/.bashrc`, OS X: `~/.bash_profile`, zsh: `~/.zshrc`)
    ```bash
    # rbenv
    export PATH="$HOME/.rbenv/bin:$PATH"
    eval "$(rbenv init -)"
    ```

  3. open a new terminal to install Ruby
    ```bash
    # list all available versions
    $ rbenv install --list
    # install specified version
    $ rbenv install 2.2.0
    # config Ruby version
    $ rbenv global 2.2.0
    ```

### Windows

- Installer
    1. [Install RubyInstaller](http://rubyinstaller.org/downloads/)
    2. [Install devkit](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit#installation-instructions)
- [chocolatey](https://chocolatey.org/packages/ruby)
```bash
# administrative PowerShell
C:\> choco install ruby
```

## 2. Update [RubyGems](https://rubygems.org/)
```bash
$ # copy all following content to teminal
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem update --system
gem install rdoc
gem rdoc --all --overwrite
gem update
gem install bundler
```

## 3. [Bundle](http://bundler.io/) install
```bash
# Change directory to this project in terminal
$ cat Gemfile  # check comments and install dependence of some specified gems
$ bundle install
```
