## Winston's Ansible Examples

Playing around with Ansible. This is some of the stuff I came up with for experimentation with it.

## My First Ansible Run - Installing Ruby 

```
ansible-wak$ ansible-playbook setup-learnansible.yml -i inventories

PLAY [webservers] **************************************************************

TASK [setup] *******************************************************************
ok: [54.89.216.138]

TASK [web : Update the apt-get repos] ******************************************
changed: [54.89.216.138]

TASK [web : Install dependencies for Ruby 2.3.3] *******************************
ok: [54.89.216.138] => (item=[u'build-essential', u'libyaml-dev', u'libsqlite3-0', u'libsqlite3-dev', u'sqlite3', u'libxml2-dev', u'libxslt-dev', u'autoconf', u'libc6-dev', u'ncurses-dev', u'automake', u'libtool', u'bison', u'subversion'])

TASK [web : Create a working directory] ****************************************
ok: [54.89.216.138]

TASK [web : Download Ruby 2.3.3] ***********************************************
ok: [54.89.216.138]

TASK [web : Unpack Ruby 2.3.3] *************************************************
ok: [54.89.216.138]

TASK [web : Build ruby] ********************************************************
changed: [54.89.216.138] => (item=./configure --enable-shared)
changed: [54.89.216.138] => (item=make)
changed: [54.89.216.138] => (item=make install)

TASK [web : Add ruby symlinks] *************************************************
changed: [54.89.216.138] => (item=erb)
changed: [54.89.216.138] => (item=gem)
changed: [54.89.216.138] => (item=irb)
changed: [54.89.216.138] => (item=rake)
changed: [54.89.216.138] => (item=rdoc)
changed: [54.89.216.138] => (item=ruby)

TASK [web : Remove the a working directory] ************************************
changed: [54.89.216.138]

PLAY RECAP *********************************************************************
54.89.216.138              : ok=9    changed=4    unreachable=0    failed=0   

ansible-wak$ ssh learnansible
Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 3.13.0-98-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Tue Feb 28 02:14:41 UTC 2017

  System load:  0.01              Users logged in:                0
  Usage of /:   41.9% of 7.74GB   IP address for eth0:            172.30.0.21
  Memory usage: 11%               IP address for docker0:         172.17.0.1
  Swap usage:   0%                IP address for br-9d7fd9faf2ae: 172.18.0.1
  Processes:    101

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

10 packages can be updated.
10 updates are security updates.

New release '16.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Tue Feb 28 02:20:02 2017 from c-68-45-235-208.hsd1.in.comcast.net
ubuntu@ip-172-30-0-21:~$ which ruby
/usr/local/bin/ruby
ubuntu@ip-172-30-0-21:~$ ruby -v
ruby 2.3.3p222 (2016-11-21 revision 56859) [x86_64-linux]
ubuntu@ip-172-30-0-21:~$ exit
logout
Connection to 54.89.216.138 closed.
ansible-wak$
``` 
