## Quick Intro

This project is a pg13/centos-7 version of vagrant-postgres10 (also centos 7)
Please see https://github.com/dgapitts/vagrant-postgres10 for more details.

I have highlighted some of the key setup processes below.

### Extra manual steps for root sar crontab 

```
# run system activity accounting tool every 1 minutes
*/1 * * * * /usr/lib64/sa/sa1 1 1
# generate a daily summary of process accounting at 23:53
53 23 * * * /usr/lib64/sa/sa2 -A
```
### systemctl commands for postgresql-13.service for status/start/stop with alias' for vagrant user

These can be run as the standard vagrant user
```
[pg13centos7:vagrant:~] # alias pgstatus='echo "sudo systemctl status postgresql-13.service";sudo systemctl status postgresql-13.service'
[pg13centos7:vagrant:~] # alias pgstart='echo "sudo systemctl start postgresql-13.service";sudo systemctl start postgresql-13.service'
[pg13centos7:vagrant:~] # alias pgstop='echo "sudo systemctl stop postgresql-13.service";sudo systemctl stop postgresql-13.service'
```
