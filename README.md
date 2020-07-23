comment by microshaoft

```
docker run -p 3128:3128 chrisdaish/squid
docker exec -it 8149cd49d5f7 tail -f /var/log/squid/access.log
curl -x 127.0.0.1:3128 https://www.cnblogs.com
```




Squid
=====

Slim image (18MB) of Squid 4.8 running under Alpine Linux 3.10.

How to use
=========

```
docker run -p 3128:3128 chrisdaish/squid
```

With bespoke configuration:

```
docker run  -v <configPath>/squid.conf:/etc/squid/squid.conf:ro \
            -v <configPath/cache:/var/cache/squid:rw \
            -v /var/log/squid:/var/log/squid:rw \
            -v /etc/localtime:/etc/localtime:ro \
            -p 3128:3128 \
            chrisdaish/squid
```
