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
