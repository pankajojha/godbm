goDBM
========
GODBM Database backup between remote hosts (or local) .

## Feature
- GOdbm will release you from an annoying replication setting

# TODO
- To add dbmaintain 

## Install
```
go get github.com/pankajojha/godbm
```

## Usage
Write down setting file in toml.
```
[database]
  [database.local]
  host = "localhost"
  management_system = "mysql"
  name = "app_development"
  user = "root"
  password = ""

  [database.test]
  host = "xxx.xxx.xxx.xxx"
  management_system = "mysql"
  name = "app_staging"
  user = "root"
  password = ""

  [database.prod]
  host = "xxx.xxx.xxx.xxx"
  management_system = "mysql"
  name = "app_staging"
  user = "root"
  password = ""

[ssh]
  [ssh.local]
  host = "localhost" # or "127.0.0.1"

  [ssh.test]
  host = "xxx.xxx.xxx.xxx"
  port = "22"
  user = "pankajojha"
  key = "~/.ssh/id_rsa_staging"

  [ssh.prodction]
  host = "yyy.yyy.yyy.yyy"
  port = "22"
  user = "remoteuser"
  key = "~/.ssh/id_rsa_prod"

```

```
godbm sync -from production -to local -c config/godbm.toml
```
