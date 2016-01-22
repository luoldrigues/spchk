SPCHK (Server Port Checker)
================
This script is quite similar of [SUP](https://github.com/luoldrigues/sup), however this one is so much more flexible. It's not just to keep a service running, it was made to check if a port in the server is listening. If its port is down, the [Server Port Checker](https://github.com/luoldrigues/spchk) will execute a command setted by you, such as, your PHP script, service or even another script which may send an email to the server administrator.

Installation
============
```sh
$ sudo su -
$ cd /tmp/
$ wget https://github.com/luoldrigues/spchk/archive/master.zip
$ unzip master.zip; cd spchk-master
$ mv spchk /usr/local/bin
$ spchk --help
```

Help
====
```sh
$ spchk --help
Usage: $FILENAME [OPTIONS...]

OPTIONS:
  -p, --port       Port of the process
  -e, --execute    Command to execute if the process is not working
  -v, --verbose    Verbosely list processed
  -h, --help       Show this help
      --usage      Give you a short usage message
      --version    Print program version

Examples:
   $FILENAME -p 8000 -e "php -q /var/www/html/script.php" -v
   $FILENAME -p 80 -e \"systemctl start httpd.service\"
   $FILENAME --usage

You might use this program in your crontab
Cron example:
  */15 * * * * $0 -p 8000 -e "php -q /var/www/html/script.php"
  The line above execute every 15 minutes to check the script.php is working at port 8000
  For more details see 'man crontab'
```

Usage
=====
```sh
$ spchk --usage
Usage: $FILENAME --port <number> --execute <command> [--verbose] [--usage] [--version]

Examples:
   $FILENAME --port 8000 --execute "php -q /var/www/html/script.php" --verbose
   $FILENAME --port 80 --execute "systemctl start httpd.service"
   $FILENAME --help
```

Version
=======
```sh
$ spchk --version
spchk version 0.1
GNU License <http://gnu.org/licenses/gpl.html>.
This is a free software! You are allowed to change and redistribute it for free.
Written by Luan Rodrigues - https://github.com/luoldrigues
```

Compatible
==========
- Red Hat 7
- Centos 7
- Fedora 7

