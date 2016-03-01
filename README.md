docker-mcroute
==============

[![](https://badge.imagelayers.io/studiosol/mcrouter:latest.svg)](https://imagelayers.io/?images=studiosol/mcrouter:latest 'Get your own badge on imagelayers.io')


This is a docker image for [facebook's mcrouter](https://github.com/facebook/mcrouter)



# Supported tags and respective `Dockerfile` links

-	[`v0.19.0`, `latest` (*v0.19.0/Dockerfile*)](https://github.com/StudioSol/docker-mcrouter/tree/0.19.0)


# Mcrouter

Mcrouter is a memcached protocol router for scaling memcached
(http://memcached.org/) deployments. It's a core component of cache
infrastructure at Facebook and Instagram where mcrouter handles almost
5 billion requests per second at peak.

Mcrouter is developed and maintained by Facebook.

See https://github.com/facebook/mcrouter/wiki to get started.

# Usage

Start memcache: 

`docker pull studiosol/mcrouter:latest`

`docker run -d --name memcached0 memcached`

`docker run -d --name memcached1 memcached`

`docker run -d -p 5000:5000 --link=memcached0:memcached0 --link=memcached1:memcached1 studiosol/mcrouter:latest mcrouter --config-str='{"pools":{"A":{"servers":["memcached0:11211", "memcached1:11211"]}},"route":"PoolRoute|A"}' -p 5000`



#### Se /exemples 