--- 
title: Ruby on Rails 書單 與 練習作業
layout: post
---

## 新人需要具備的「一般」基礎技能 ##

1. 對 [Git](http://git-scm.com/) 的觀念與技巧掌握。
2. 對 VIM / Textmate 的基本開發技巧掌握。

    **書單**

    c9s 的 [VIM Hacks](http://c9s.blogspot.com/2009/08/vim-hacks-coscup.html) 與 Oreilly 的 [精通 vi 與 vim](http://tlsj.tenlong.com.tw/WebModule/BookSearch/bookSearchViewAction.do?isbn=9789866840326&sid=48676&aid=69e42ffb) 與 Pragmatic 的 [TextMate: Power Editing for the Mac](http://www.pragprog.com/titles/textmate/textmate)

    **練習**
    
    vgod 的 [給程式設計師的Vim入門圖解說明](http://blog.vgod.tw/2009/12/08/vim-cheat-sheet-for-programmers/) 全部練習一遍
    
3. 熟悉 Linux Command Line 的操作。

    **書單與練習**
    
    Peepcode 的 [Meet the Command Line](http://peepcode.com/products/meet-the-command-line) 、[Advanced Command Line](http://peepcode.com/products/advanced-command-line) 全部練過一遍

4. Git

    **書單**
    
    Peepcode 的 [Git](http://peepcode.com/products/git) 與 [Pro Git](http://progit.org/book/)
    
    **練習**
    
    上 [Github](http://github.com) 開啟一個專案，練習 git commit , git push , git pull, git branch , git checkout , git merge

## 新人需要具備的 Rails 基礎技能 ##

1. 可手刻 CRUD ( Create / Read / Update / Delete ) 並且理解 CRUD 中的 params 傳遞方法
2. route 中 resources 觀念配合 model 裡 has_many 的設計，理解並熟悉 RESTful 觀念。
3. route 的優先順序與 routes 中 resource / namespace 的實作。
4. scope 、 counter_cache、before_filter
5. plugin 的使用： [devise](https://github.com/plataformatec/devise) 、[will_paginate](http://wiki.github.com/mislav/will_paginate)、[paperclip](http://github.com/thoughtbot/paperclip)
6. rake 原理以及撰寫 task
7. ruby on rails 的 production setup 與撰寫 [capistrano](http://www.capify.org/) recipes

### 書單：（案頭必備） ###

* [Ruby Programming — 向 Ruby 之父學程式設計](http://www.books.com.tw/exep/prod/booksfile.php?item=0010350699)
* [Ruby for Rails – Rails 開發者必備的 Ruby 學習手冊 ](http://www.books.com.tw/exep/prod/booksfile.php?item=0010400655)（英文新版： [The Well-Grounded Rubyist](http://www.manning.com/black2/) )
* [Ruby Pocket Reference](http://oreilly.com/catalog/9780596514815)
* [碼上就會：Rails敏捷開發網站](http://www.books.com.tw/exep/prod/booksfile.php?item=0010374225) *(may not suit for Rails3)* （英文新版: [Agile Web Development with Rails (4th edition)](http://pragprog.com/titles/rails4/agile-web-development-with-railsn) )
* [The Rails 3 Way](http://tr3w.com/) *(only for Rails3)*

* [The Rails Way](http://my.safaribooksonline.com/9780321445612) *(may not suit for Rails3)*
* [Rails Recipes](http://www.pragprog.com/titles/fr_rr/rails-recipes) *(may not suit for Rails3)*
* [Advanced Rails Recipes: 84 New Ways to Build Stunning Rails Apps](http://www.pragprog.com/titles/fr_arr/advanced-rails-recipes) *(may not suit for Rails3)*

### 書單：（入門用） ###
* [Ruby on Rails Tutorial: Learn Rails by Example](http://ruby.railstutorial.org/) *(only for Rails3)*

### 線上工具：（必加書籤）###
* [Rails Cast](http://railscasts.com/)
* Ruby API : [String](http://www.ruby-doc.org/core/classes/String.html)、[Array](http://www.ruby-doc.org/core/classes/Array.html)、[Hash](http://www.ruby-doc.org/core/classes/Hash.html)
* APIDock : [Ruby on Rails](http://apidock.com/rails)

### 練習作業 ###

1. 開發一個簡易論壇系統。
    
* 系統要有 Forum 與 Post 兩個 model，寫出 CRUD 介面，並且文章網址是使用 http://example.org/forum/1/post/2 這種表示。  
* CRUD & migration
* has_many 與 belongs_to
* resources 與雙層 resources
* before_filter : find_event
    
    **參考資料**
    
* [深入淺出 RoR (4-3) – RESTful 與 CRUD action](http://rails.pixnet.net/blog/post/22956704)
* [ihower training : Ruby on Rails 入門](http://ihower.tw/training/rails-tutoral.html)

2\. 使用者必須能夠 註冊 / 登入，登入後才可以發表 Post，不然只能瀏覽。只有自己的 Post 才能進行修改與刪除。

* routes 優先權與 route alias
* plugin 安裝與使用
* before_filter : login_required
* session : current_user
* [attr_accessible](http://api.rubyonrails.org/classes/ActiveRecord/Base.html#M002281) / [attr_protected](http://api.rubyonrails.org/classes/ActiveRecord/Base.html#M002280)

    **參考資料**

* [devise](https://github.com/plataformatec/devise)

3\. 論壇的文章要能夠分頁，每一頁 20 筆，每一個論壇要秀出現在論壇裡有多少 post 數量。可用 params 配合 named_scope 在文章列表排序。

* pagination
* counter_cache
* scope :recent

**參考資料**

* [will_paginate](http://wiki.github.com/mislav/will_paginate)
* [Railscast : Counter Cache Column](http://railscasts.com/episodes/23-counter-cache-column)
* [Railscast : named_scope](http://railscasts.com/episodes/108-named-scope)
 
4\. 每篇文章可以上傳附件

* form_for multipart

**參考資料**

* [paperclip](http://github.com/thoughtbot/paperclip)

5\. Admin 可以刪改所有文章，建立一個後台做這件事。網址是 http://example.org/admin/。只有身分是 admin 的人可以進後台。admin 的判別方是 column 裡加一個 boolean，判斷是否 admin。這個 attribute 必須用 attr_accessible / attr_protected 保護。

* route : namespace
* before_filter : require_is_admin

**參考資料**

* [Namespaces added to routes](http://railstips.org/blog/archives/2007/04/28/namespaces-added-to-routes/)

6\. 用 Rake 撰寫自動化步驟，生假資料。寫一個 rake 可以達成以下步驟：「砍 db => 建 db => 跑 migration => 生種子資料」，另一個 rake 是生假文章與假論壇。

* rake -T
* rake db:drop ; rake db:create ; rake db:migrate ; rake db:seed
* rake dev:fake ( 自己寫 namespace : dev, 裡面放一個 task 叫做 fake，fake 資料用 [Populator](http://github.com/ryanb/populator) 生）

**參考資料**

* [Ruby on Rails Rake Tutorial (aka. How rake turned me into an alcoholic)](http://railsenvy.com/2007/6/11/ruby-on-rails-rake-tutorial)
* [What’s New in Edge Rails: Database Seeding](http://ryandaigle.com/articles/2009/5/13/what-s-new-in-edge-rails-database-seeding)

7\. 在租來的 VPS 上面建置 Ruby on Rails production 環境，使用 Ruby Enterprise 與 mod_rails。使用 capistrano 佈署 application。

* cap deploy:setup 
* cap deploy
* cap deploy:rollback
* cap deploy:restart

**參考資料**

* [rails-nginx-passenger-ubuntu](http://github.com/jnstq/rails-nginx-passenger-ubuntu)
* AWDR3 的 deploy 章節 , Ruby Pocket Reference 的 [capistrano](http://www.capify.org/) 章節

<hr>

PS. 實際測試的結果是，完全不懂 Ruby on Rails 的新人，從頭帶過大概兩週可以練完這一份作業。

