# JUNE 14TH - Active Record Lecture No. 1

### our gemfile

```Ruby
source "https://rubygems.org"

gem 'activerecord'
gem 'sinatra-activerecord'
gem 'rake'
gem 'require_all'
gem 'sqlite3'
gem 'pry'
```

### bin/run.rb

`require_relative 'config/environment.rb'`

### rakefile

```Ruby
require 'bundler/setup'
require 'sinatra/activerecord/rake'

task :console do
    ActiveRecord::Base.logger = Logger.new(STDOUT)
    pry.start
end

desc "says 👋"
task :hello do
    puts "suuuup"
end
```


### Run these commands
``` rake db:create_migration NAME=create_pokemons ```


### Migration file

```Ruby
class CreatePokemon < ActiveRecord::Migraton
    def change
        create_table pokemons do |table|
            table.string "name"
            table.string "element_type"
            table.integer "weight"
            table.integer "level"
        end
    end
end

```

### Run these commands
``` rake db:mgrate ```
