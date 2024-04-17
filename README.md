# cheat-sheet-rspec-bundler-pry

### File Path
```
mon_projet
├── lib
│   ├── app
│   │   ├── scrapper.rb
│   │   └── email_sender.rb
│   └── views
│       ├── done.rb
│       └── index.rb
├── db
│   └── thing.csv
├── spec
│   ├── spec_helper.rb
│   └── scrapper_spec.rb
├── app.rb
├── README.md
├── Gemfile
├── Gemfile.lock
├── Autres fichiers (.env, .gitignore)
└── .rspec
```

-----

## Rspec Install
`$ rspec --init`

### Tests syntax
```
require_relative '../lib/hello'

describe "the hello function" do
  it "says hello" do
    expect(hello).to eq("Hello world!")
  end
end
```

### Launch Test
`$ rspec nomdefichierdetest`

-----

## Bundler 
In folder `$ touch Gemfile`

In Gemfile:
```
source "https://rubygems.org"
ruby '3.2.2'
gem 'rspec'
gem 'pry'
```
Get the Bundle 
`$ bundle install`

In app.rb
```
require 'bundler'
Bundler.require

$:.unshift File.expand_path("./../lib", __FILE__)
require 'app/fichier_1'
require 'views/fichier_2'
```
 

### Install gem en particulier 
gem install nomdegem 
find gems => https://rubygems.org/ 

-----

## PRY
add pry in Gemfile `gem 'pry'` 
add pry in .rb app `require 'pry'` 

execute pry within the .rb file `binding.pry`

-----

## Dotenv
add pry in Gemfile `gem 'dotenv'` 

in .env (repo root) :
```
NEW_API="my-api-key"
```

in .rb app file :
```
require 'dotenv'

Dotenv.load 

puts ENV['NEW_API']
```

in .gitignore (repo root) : 
```
.env
```