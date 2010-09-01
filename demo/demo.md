!SLIDE command

# gem install padrino

!SLIDE incremental bullets

# padrino g[[en]erate]

* projekt
* aplikace
* kontroler
* model
* mailer
* migrace

!SLIDE command

## Projekt
#padrino g project blog -t cucumber \
#-d datamapper -c compass -s jquery
#cd blog
## VISOR TIME!

!SLIDE command

## rvm a git
# echo 'rvm use 1.8.7@blog' > .rvmrc
# cd .
# git init
# git add .
# git commit -m 'initial commit'
# bundle install 
## VISOR TIME!

!SLIDE command

## komponenty
# padrino g controller blog
# padrino g model post
## VISOR TIME!

!SLIDE code

## mvim db/migrate/001_create_posts.rb 

    @@@Ruby

    create_table :posts do
      column :id, DataMapper::Property::Integer, :serial => true
      column :title, DataMapper::Property::String
      column :content, DataMapper::Property::String
      column :posted_on, DataMapper::Property::DateTime
    end

## VIM TIME!

!SLIDE command

## setup
# padrino g admin
# padrino rake dm:migrate
# padrino rake seed
## VISOR TIME!

!SLIDE command

## scaff
# mvim app/models/post.rb
# padrino g admin_page post
# padrino start
## VISOR TIME!

!SLIDE code

## app/controllers/posts.rb

    @@@Ruby
    get :index, :map => "/" do
      @posts = Post.all
      render 'posts/index'
    end

## VIM TIME!

!SLIDE code

## app/views/posts/index.haml

    @@@Ruby
    %h1 My posts

      %ul
        -@posts.each do |post|
          %li= post.title

## VIM TIME!

!SLIDE

# Bang! Bang! Bang!

## Padrino has ended his set (crowd applauds)

