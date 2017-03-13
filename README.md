# Install_postgress_on_mac_linux

This is a guide on how  to install PostgreSQL on Mac OX or Linux. 

### Commands with Homebrew 

```
a. brew update
b. brew upgrade
c. brew doctor
d. brew install postgresql --with-python

```

### Activate PostgreSQL

Activate PostgreSQL:

```

a. mkdir -p ~/Library/LaunchAgents 
b. ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
c. launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
```


The above command comes from a fresh install of `postgresql` via `Homebrew` which will show you:

```
If builds of PostgreSQL 9 are failing and you have version 8.x installed,
you may need to remove the previous version first. See:
  https://github.com/Homebrew/homebrew/issues/2510

To migrate existing data from a previous major version (pre-9.4) of PostgreSQL, see:
  https://www.postgresql.org/docs/9.4/static/upgrading.html

To have launchd start postgresql at login:
  ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
Then to load postgresql now:
  launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
Or, if you don't want/need launchctl, you can just run:
  postgres -D /usr/local/var/postgres
```



If you already had previously `postgresql` installed, you would see:

```
To reload postgresql after an upgrade:
  launchctl unload ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
  launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
Or, if you don't want/need launchctl, you can just run:
  postgres -D /usr/local/var/postgres
```


Now, test `postgresql` with:
```
a. createdb
b. psql
```
You should see something like:
```
psql (9.4.5)
Type "help" for help.

djobukata=#
```
Where `djobukata` is your username.

### References 

1. https://launchschool.com/blog/how-to-install-postgresql-on-a-mac

2. https://www.postgresql.org/download/macosx/

3. https://www.codementor.io/devops/tutorial/getting-started-postgresql-server-mac-osx




