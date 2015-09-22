# PgBackup

This gem adds rake tasks to your application for creating and restoring postgres dumps. 

## Requirements
``` 
bundler
rake 
capistrano # optional
```

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'pg_backup'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install pg_backup

## Usage

```
rake pg_backup:dump:create # create a dump from local db and save it locally
rake pg_backup:dump:load   # import latest dump from local file 
```

### Capistrano integration
add to your ```Capfile```
```
require "pg_backup/capistrano"
````
this adds some capistrano tasks
```
cap <env> pg_backup:dump:create    # creates remote dump in remote dir
cap <env> pg_backup:dump:load      # imports latest remote dump in remote db
cap <env> pg_backup:dump:download  # downloads latest remote dump to local dir
cap <env> pg_backup:dump:upload    # uploads to remote 
```

### deploy-mate integration
add to your ```Capfile```

```
require "pg_backup/deploy_mate"
```

## Credits
https://gist.github.com/hopsoft/56ba6f55fe48ad7f8b90

## Contributing

1. Fork it ( https://github.com/[my-github-username]/pg_backup/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
