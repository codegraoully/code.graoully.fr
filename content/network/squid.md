---
title: "Squid et squid guard"
date: 2020-04-01T09:00:00+00:00
draft: false
images:
tags:
  - proxy
  - Linux
  - GNU/Linux
---


`sudo yum install squidGuard`

```
cd /var/squidGuard
rm blacklists.tar.gz
wget -c ftp://ftp.ut-capitole.fr/blacklist/blacklists.tar.gz
tar xvzf blacklists.tar.gz
cd blacklists
```

/etc/squid/squid.conf
```
# SquidGuard
url_rewrite_program /usr/bin/squidGuard
url_rewrite_children 8
```

`sudo chown -R squid:squid /var/squidGuard`
`sudo chown -R squid:squid /var/log/squidGuard`