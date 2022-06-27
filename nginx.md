# definition
for configure webserver nginxx
- [config](#config)
- [restart](#restart)
- [custom header](#customheader)

## config
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
## restart nginx
to restart nginx
windows
```
nginx -s reload
```
linux
```
systemctl restart nginx
```

## customheader

on request header client, with dash
```
'custom-header': '1',
```
on server
```
if ($http_custom_header = '1') {
	return 200 'set 1';
}
```
