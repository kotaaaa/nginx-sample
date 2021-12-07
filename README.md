# Overview
- Nginx map, limit_req, location, upstream sample.
- Divide access to host1 or host2 by $uri or $http_referer.

# How to run
```
$ docker build -t nginx_sample:0.0.1 .
$ docker run -it -p 8080:80 nginx_sample:0.0.1
```

# How to Test
```
$ curl http://localhost:8080/path/001
lookup yahoo on 192.168.65.5:53: no such host
$ curl http://localhost:8080/path/002
lookup google on 192.168.65.5:53: no such host
```
# How to give load with apache bench
```
## High qps request won't be accepted by limit_req_zone. 
## 100 reqest by 10 users (concurrency)
$ ab -n 100 -c 10 "http://localhost:8080/path/001"
```

