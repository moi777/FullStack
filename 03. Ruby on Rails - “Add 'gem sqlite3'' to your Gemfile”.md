**1.Issue Description!**

I'm trying to start the server mode with the command ```rails s```

My environment:

- macOS Mojave 10.14

- ruby 2.6.0p0 (2018-12-25 revision 66547) [x86_64-darwin18]

- Rails 5.0.7.2

Error from terminal:

```
Specified 'sqlite3' for database adapter, but the gem is not loaded. Add gem 'sqlite3' to your Gemfile.
```

**2.Problem Solved!**

Check the installed version: ```gem list sqlite3```, it gives me: sqlite3 (1.4.0, 1.3.13)


Manually modify the Gemfile.lock, add sqlite3 constraint:

```
gem 'sqlite3', '~> 1.3.6'
```

And then run:

```
bundle update
``` 

Upon running ```rails server```, refresh the webpage and everything works! 

**Reference**

https://github.com/rails/rails/issues/35153

https://stackoverflow.com/questions/54527277/cant-activate-sqlite3-1-3-6-already-activated-sqlite3-1-4-0/54606137#54606137

https://stackoverflow.com/questions/38176304/no-connection-pool-for-activerecordbase
