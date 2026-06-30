#M4tr1x walkthrough.
#Los cambios de ip en la máquina se deben a que a he realizado en varios días, o al reinicio de la misma.

Comienzo con un escaneo de puertos.

sudo nmap -p- 10.130.176.252
[sudo] contraseña para mksk:     
Starting Nmap 7.94SVN ( https://nmap.org ) at 2026-06-30 12:53 CEST
Nmap scan report for 10.130.176.252
Host is up (0.031s latency).
Not shown: 65532 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
3306/tcp open  mysql

Nmap done: 1 IP address (1 host up) scanned in 17.06 seconds

Y otro escaneo -sVC

sudo nmap -sVC -p 22,80,3306 10.130.176.252
Starting Nmap 7.94SVN ( https://nmap.org ) at 2026-06-30 12:55 CEST
Nmap scan report for 10.130.176.252
Host is up (0.032s latency).

PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 cc:d2:3b:6e:19:3e:f1:0a:d8:ba:c8:aa:b0:64:73:e5 (RSA)
|   256 9f:a8:bb:9b:09:5a:c4:96:eb:86:49:1b:a8:03:cf:d0 (ECDSA)
|_  256 79:5b:a1:b0:60:91:95:0e:ee:8b:60:46:09:af:21:cb (ED25519)
80/tcp   open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-title: Linux-Bay
|_http-server-header: Apache/2.4.41 (Ubuntu)
3306/tcp open  mysql   MySQL 5.5.5-10.3.39-MariaDB-0ubuntu0.20.04.2
| mysql-info: 
|   Protocol: 10
|   Version: 5.5.5-10.3.39-MariaDB-0ubuntu0.20.04.2
|   Thread ID: 115
|   Capabilities flags: 63486
|   Some Capabilities: Speaks41ProtocolOld, Support41Auth, SupportsTransactions, ConnectWithDatabase, DontAllowDatabaseTableColumn, SupportsCompression, IgnoreSigpipes, InteractiveClient, Speaks41ProtocolNew, IgnoreSpaceBeforeParenthesis, FoundRows, SupportsLoadDataLocal, ODBCClient, LongColumnFlag, SupportsAuthPlugins, SupportsMultipleResults, SupportsMultipleStatments
|   Status: Autocommit
|   Salt: 8Y:Rp[W%M7h(-IeDdH{T
|_  Auth Plugin Name: mysql_native_password
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.85 seconds

Es posible que la version de mysql tenga alguna vulnerabilidad, pero voy a ir en orden de preguntas.

Where did that white rabbit lead you to?

Voy a seguir enumerando, ahora la web.


dirsearch -u http://10.130.176.252/

/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/mksk/reports/http_10.130.176.252/__26-06-30_13-02-35.txt

Target: http://10.130.176.252/

[13:02:35] Starting: 
[13:02:37] 403 -  279B  - /.ht_wsr.txt
[13:02:37] 403 -  279B  - /.htaccess.bak1
[13:02:37] 403 -  279B  - /.htaccess.sample
[13:02:37] 403 -  279B  - /.htaccess.orig
[13:02:37] 403 -  279B  - /.htaccess.save
[13:02:37] 403 -  279B  - /.htaccess_extra
[13:02:37] 403 -  279B  - /.htaccess_orig
[13:02:37] 403 -  279B  - /.htaccess_sc
[13:02:37] 403 -  279B  - /.htaccessBAK
[13:02:37] 403 -  279B  - /.htaccessOLD
[13:02:37] 403 -  279B  - /.htaccessOLD2
[13:02:37] 403 -  279B  - /.htm
[13:02:37] 403 -  279B  - /.html
[13:02:37] 403 -  279B  - /.htpasswd_test
[13:02:37] 403 -  279B  - /.httr-oauth
[13:02:37] 403 -  279B  - /.htpasswds
[13:02:38] 403 -  279B  - /.php
[13:02:40] 301 -  316B  - /admin  ->  http://10.130.176.252/admin/
[13:02:41] 200 -  843B  - /admin/
[13:02:41] 200 -   67B  - /admin/backups/
[13:02:41] 200 -  843B  - /admin/index.php
[13:02:43] 200 -  241B  - /administrator
[13:02:43] 200 -  240B  - /adminpanel
[13:02:43] 200 -    6KB - /adminlogon
[13:02:44] 301 -  318B  - /archive  ->  http://10.130.176.252/archive/
[13:02:44] 200 -    3KB - /attachment.php
[13:02:45] 301 -  316B  - /cache  ->  http://10.130.176.252/cache/
[13:02:45] 200 -   67B  - /cache/
[13:02:45] 200 -    4KB - /calendar.php
[13:02:46] 200 -    3KB - /contact.php
[13:02:47] 200 -    0B  - /css.php
[13:02:48] 200 -  240B  - /e-mail
[13:02:48] 200 -    3KB - /editpost.php
[13:02:48] 200 -  240B  - /error
[13:02:49] 200 -  240B  - /files
[13:02:49] 200 -  240B  - /flag
[13:02:49] 200 -  240B  - /ftp
[13:02:50] 200 -  233B  - /general
[13:02:50] 200 -  109B  - /global.php
[13:02:50] 200 -    1KB - /htaccess.txt
[13:02:51] 200 -   67B  - /images/
[13:02:51] 301 -  317B  - /images  ->  http://10.130.176.252/images/
[13:02:51] 301 -  314B  - /inc  ->  http://10.130.176.252/inc/
[13:02:51] 200 -   67B  - /inc/
[13:02:51] 301 -  318B  - /install  ->  http://10.130.176.252/install/
[13:02:51] 200 -  529B  - /install/
[13:02:51] 200 -  529B  - /install/index.php?upgrade/
[13:02:52] 200 -   67B  - /jscripts/
[13:02:52] 301 -  319B  - /jscripts  ->  http://10.130.176.252/jscripts/
[13:02:52] 200 -  241B  - /login
[13:02:53] 302 -    0B  - /member.php  ->  index.php
[13:02:53] 200 -    5KB - /memberlist.php
[13:02:53] 200 -    0B  - /misc.php
[13:02:53] 200 -    3KB - /modcp.php
[13:02:54] 200 -    3KB - /newreply.php
[13:02:54] 200 -    3KB - /newthread.php
[13:02:54] 200 -    3KB - /online.php
[13:02:55] 200 -  241B  - /panel
[13:02:57] 200 -    3KB - /printthread.php
[13:02:57] 200 -    3KB - /private.php
[13:02:57] 200 -    3KB - /report.php
[13:02:58] 200 -    3KB - /reputation.php
[13:02:58] 302 -    0B  - /rss.php  ->  syndication.php
[13:02:58] 200 -  241B  - /secret
[13:02:58] 200 -    4KB - /search.php
[13:02:58] 403 -  279B  - /server-status/
[13:02:58] 403 -  279B  - /server-status
[13:03:00] 200 -    3KB - /stats.php
[13:03:02] 301 -  318B  - /uploads  ->  http://10.130.176.252/uploads/
[13:03:02] 200 -   67B  - /uploads/
[13:03:02] 200 -    3KB - /usercp.php

Veo bastantes archivos y directorios.

/flag, /secret es una "trampa". No hay nada, y en general no he encontrado nada por los diferentes directorios, en algunas páginas se pasan parámetros a través de la url,
lo cual puedo ver si explotable más adelante.

He mirado la pista de la pregunta porque estaba un poco perdido.

Where did that white rabbit lead you to?
Are you sure it is trying to lead you down just one stop? Perhaps the journey is longer?

He seguido enumerando, los directorios, y mientras se completaban los 
