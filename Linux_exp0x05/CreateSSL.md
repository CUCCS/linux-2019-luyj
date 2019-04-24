### 创建自签名SSL证书

#### 创建自签名SSL证书
- 使用```OpenSSL```生成自签名密钥和证书对
    ```
    # req:指定公钥基础设施标准
    # -nodes:告诉OpenSS以密钥保护证书而跳过选项
    # -days:设置有效期
    # -newkey rsa:2048:生成使用RSA算法的长度为2048的密钥
    # -keyout:私钥存储位置
    # -out:证书存放位置
    sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt
    ```
- 填写相关信息
    ```
    Country Name (2 letter code) [AU]:CN
    State or Province Name (full name) [Some-State]:Beijin
    Locality Name (eg, city) []:Beijin City
    Organization Name (eg, company) [Internet Widgits Pty Ltd]:Bouncy Castles, Inc.
    Organizational Unit Name (eg, section) []:Ministry of Water Slides
    Common Name (e.g. server FQDN or YOUR name) []:pw.sec.cuc.edu.cn
    Email Address []:admin@your_domain.com
    ```
- 创建```Diffie-Hellman```组
    ```
    sudo openssl dhparam -out /etc/nginx/dhparam.pem 4096
    ```
#### 配置Nginx
- 创建SSL密钥和证书的配置文件
    - ```self-signed.conf```
        ```
        ssl_certificate /etc/ssl/certs/nginx-selfsigned.crt;
        ssl_certificate_key /etc/ssl/private/nginx-selfsigned.key;
        ```
    - ```ssl-params.conf```
        ```
        # from https://cipherli.st/
        # and https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html

        ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        ssl_prefer_server_ciphers on;
        ssl_ciphers "EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH";
        ssl_ecdh_curve secp384r1;
        ssl_session_cache shared:SSL:10m;
        ssl_session_tickets off;
        ssl_stapling on;
        ssl_stapling_verify on;
        resolver 8.8.8.8 8.8.4.4 valid=300s;
        resolver_timeout 5s;
        # Disable preloading HSTS for now.  You can use the commented out header line that includes
        # the "preload" directive if you understand the implications.
        #add_header Strict-Transport-Security "max-age=63072000; includeSubdomains; preload";
        add_header Strict-Transport-Security "max-age=63072000; includeSubdomains";
        add_header X-Frame-Options DENY;
        add_header X-Content-Type-Options nosniff;

        ssl_dhparam /etc/ssl/certs/dhparam.pem;
        ```
    - 修改Nginx配置
    ```
    
    ```
