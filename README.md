# squidmagic

squidmagic is a tool designed to analyze a web-based network traffic to detect central command and control (C&C) servers and Malicious site, using Squid proxy server and Spamhaus.

## Install Squid and configure Proxy server and Zeromq. (Ubuntu)

```
apt-get -y install squid3
```
```
apt-get install libzmq3-dev
```

## simple squid3 configuration to Allow all machines to all sites

```
http_access allow all 
```

## instalation

	git clone https://github.com/ch3k1/squidmagic
	cd squidmagic
	pip install -r requirements.txt

## configuration

```
[spamhaus]
query_url = http://www.spamhaus.org/query/bl?ip=
```

## usage

```
squidmagic # python squidmagic.py /var/log/squid3/access.log

                 _     _                       _      
                (_)   | |                     (_)     
 ___  __ _ _   _ _  __| |_ __ ___   __ _  __ _ _  ___ 
/ __|/ _` | | | | |/ _` | '_ ` _ \ / _` |/ _` | |/ __|
\__ \ (_| | |_| | | (_| | | | | | | (_| | (_| | | (__ 
|___/\__, |\__,_|_|\__,_|_| |_| |_|\__,_|\__, |_|\___|
        | |                               __/ |       
        |_|                              |___/        
     Analyzing...

Analyzing by SBL Advisory...
	Spam server detected, ip is 65.182.101.221
Analyzing by SBL_CSS Advisory...
	safe server detected, host or ip is 65.182.101.221
Analyzing by PBL Advisory...
	safe server detected, host or ip is 65.182.101.221

```

### Run server

```
php server.php

Array
(
    [status] => unsafe
    [host] => 65.182.101.221
)
Array
(
    [status] => unsafe
    [host] => 65.182.101.221
)
Array
(
    [status] => unsafe
    [host] => 65.182.101.221
)

```

