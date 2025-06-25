## 🧾 NGINX Configuration

#### The nginx service uses a custom Dockerfile.

```
FROM nginx:alpine
COPY nginx.conf /etc/nginx/conf.d/nginx.conf
EXPOSE 80

```

## 🔍 Explanation

1.  **Uses the official lightweight Alpine-based NGINX image**

####

##### Uses the official lightweight Alpine-based NGINX image.

- `FROM nginx:alpine`

##### Replaces the default NGINX configuration with a custom one provided in the nginx/ directory.

- `COPY nginx.conf /etc/nginx/conf.d/nginx.conf `

##### Exposes port 80 inside the container for HTTP traffic.

- `EXPOSE 80`

---

## 🗂 Related File

```
nginx/
├── default.conf  # Custom NGINX config file
├── Dockerfile # Contains the above NGINX image build instructions
└── README.md

```

#### This custom setup allows NGINX to reverse proxy traffic to your backend services (e.g., `service_1` and `service_2`).

#### Update `default.conf` to control routing, like:

```
server {
    listen       80;
    listen  [::]:80;
    server_name  localhost;

    location / {
        root   /usr/share/nginx/html;
        index  index.html index.htm;
    }
    location /service1/ {
        proxy_pass http://service_1:8001/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_http_version 1.1;
    }
    location /service2/ {
        proxy_pass http://service_2:8002/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_http_version 1.1;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   /usr/share/nginx/html;
    }

}

```
