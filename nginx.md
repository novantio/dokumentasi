# definition
for configure webserver nginxx

# config
reverse proxy
```
location /content {
     proxy_pass   http://10.15.16.21/content;
}
```

remove element tag using reverse proxy
```
location /mmmmm/ {
     proxy_set_header Accept-Encoding "";
     proxy_pass   http://localhost:3000/;
     proxy_set_header   Host http://localhost:3000/;
     proxy_pass_request_headers      on;
     sub_filter '</body>' '<style>.EmbedFrame-footer{display:none;}</style></body>';
     sub_filter_once on;	
}
```
