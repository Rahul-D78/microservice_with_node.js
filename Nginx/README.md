### How to configure `Nginx` as the load balancer for the `Node.JS` projects .

```$sudo apt install```

#### Steps to be followed :-
1. Navigate to the nginx configuration file .

```$ cd ~/etc/nginx/nginx.conf```

2. Add the Following setting for the load balancing purpose .

```$
http {
  upstream backend {
    server 127.0.0.1:3000;
    server 127.0.0.1:4000;
  }
  
  server {
    listen 80;
    root /home/ro.../nodejs/microservices/;
  
    location / {
      proxy_pass http://backend;
    }
  }
}
events {}
```
