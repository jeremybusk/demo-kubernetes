# Example Using NGINX as your inbound proxy

/etc/nginx/nginx.conf
```
...
stream {
  include /etc/nginx/conf.d/*.stream;
}`
http {
...
```

/etc/nginx/conf.d/demodb.stream
````
upstream k_demodb {
  least_conn;
  server 10.x.x.a:31372;  # k1 - different master kubernetes nodes with exposed port
  server 10.x.x.b:31372;  # k2
  server 10.x.x.c:31372;  # k3
}
server {
  listen 9001; # port that outside world will actually connect to our application. We can set session controls from here.
  proxy_pass k_demodb;
}
```

From outside world you could use keepalived or BGP/OSPF for healthy node ip routing.
