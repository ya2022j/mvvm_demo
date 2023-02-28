

### todolist



* 用Go语言撸一个前后端分离权限管理系统脚手架 https://mp.weixin.qq.com/s/-g0pJeV226n5GKM1D-TqcQ
* Flask+Vue前后端分离工程化最佳实践 https://mp.weixin.qq.com/s/1OUmXb7bRf1mRjCjA2r76w
* Django+Vue前后端分离入门教程 https://mp.weixin.qq.com/s/0mm6jblBBOraBFwUyDMFeg
* Gin + Gorm 实战 CRUD https://mp.weixin.qq.com/s/vvuOMAgaSgszhC7ZawwYIw
* [开源]基于Gin + Vue前后端分离的工单系统，可灵活配置流程与模版https://mp.weixin.qq.com/s/Dhc0EknnMBf0bV1iuBS30A

* vue2 playground
* https://stackblitz.com/edit/vue2-vue-cli-zcp6h7?file=src%2FApp.vue
* https://codesandbox.io/s/vue-2-playground-forked-e50p17?file=/src/main.js

* vue3 playground 
* https://codesandbox.io/s/elated-williams-xt8qr0
* https://stackblitz.com/edit/vue-fcxxry?file=src%2FApp.vue

* nginx conf 

```shell


user  nobody;
worker_processes  1;

error_log  logs/error.log;
error_log  logs/error.log  notice;
error_log  logs/error.log  info;

pid        logs/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       mime.types;

    default_type  application/octet-stream;

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  logs/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    #keepalive_timeout  0;
    keepalive_timeout  65;

    #gzip  on;


server {
 listen  80;
     server_name 127.0.0.1;
     proxy_set_header    Host  $host;
     proxy_set_header    X-Real-IP  $remote_addr;
     proxy_set_header    REMOTE-HOST  $remote_addr;


     location / {

                 add_header 'Access-Control-Allow-Credentials' 'true';
            add_header 'Access-Control-Allow-Origin' '*';
	     proxy_pass http://127.0.0.1:8000/;

     }
 }
 }



```
