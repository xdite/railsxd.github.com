--- 
title: Best Practice of Installing Ruby on Rails on clean Mac
layout: post
---

## Mac 裝機步驟 ##

<div class="warning">
警告: 請絕對不要跳著裝！
</div>

### 系統套件 ###

1. Software Update
2. Install Xcode ( **Mac OS X Install CD 那一塊的** >> **選擇安裝**）

3. Install [Homebrew](http://github.com/mxcl/homebrew)
<pre>ruby -e "$(curl -fsS https://gist.github.com/raw/323731/install_homebrew.rb)"</pre>
    *  `>` brew install git
    *  `>` brew update


### Imagemagick / MYSQL / Sphinx ###

1. 安裝 Imagemagick

    `>` brew install imagemagick
2. 安裝 MySQL
  
    `>` brew install mysql
 
    **請注意以下指令 MySQL 版號，請自行更正**
    <pre>
    unset TMPDIR
    mysql_install_db
    cp /usr/local/Cellar/mysql/5.1.54/com.mysql.mysqld.plist ~/Library/LaunchAgents
    launchctl load -w ~/Library/LaunchAgents/com.mysql.mysqld.plist
    /usr/local/Cellar/mysql/5.1.54/bin/mysql_secure_installation
    </pre>

    * Set root password? `[`Y/n`]` **Y**
    * New password: **123456**
    * Re-enter new password: **123456**
    * Remove anonymous users? `[`Y/n`]` **Y**
    * Disallow root login remotely? `[`Y/n`]` **Y**
    * Remove test database and access to it? `[`Y/n`]` **Y**
    * Reload privilege tables now? `[`Y/n`]` **Y**

3. 安裝 Sphinx

    `>` brew install sphinx

### 安裝 RVM 與 REE ###

1. 安裝 RVM 
    <pre>
    bash &lt;&lt;( curl http://rvm.beginrescueend.com/releases/rvm-install-head )
    echo &quot;[[ -s $HOME/.rvm/scripts/rvm ]] &amp;&amp; 
    source $HOME/.rvm/scripts/rvm&quot; &gt;&gt; ~/.profile &amp;&amp; . ~/.profile
    source ~/.profile
    </pre>

    `>` rvm install ree

    `>` rvm ree --default

    **解決使用 rvm 裝 ree 後，不能在 irb 打中文的問題**
    <pre>
      brew install readline
      brew link readline
      rvm --reconfigure --force -C --with-readline-dir=/usr/local install ree
    </pre>

    <div class="info">
        <p>
             使用 RVM 安裝 gem 和 passenger-install-apache2-module 不需要加上 sudo , 因為使用 sudo 會使用非 RVM 的 ruby 環境, 安裝目錄也不一樣.)
        </p>
    </div>

### 安裝必要 Ruby gems ###

<pre>
gem install rails
gem install rails -v=2.3.8
gem install mysql2
gem install mysql
gem install passenger
gem install nokogiri
gem install capistrano
gem install capistrano-ext
gem install delayed_job
gem install hoptoad_notifier
gem install facebooker2
gem install factory_girl
gem install sphinx
</pre>


### 設定 HTTP Server ###

請使用 [Pow](/todo.html)
#### TODO ####