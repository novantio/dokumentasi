# definition
for hook http://url/hook to execute cmd

# command 
to run
```
webhook.exe -hooks hook.json -verbose
```
sample hook.json
```
[
  {
    "id": "build-jk",
    "execute-command": "E:/app/webhook/build-jk.bat",
    "command-working-directory": "E:/app/webhook",
    "response-message": "Rebuild mdtv2...",
  },{
    "id": "build-production",
    "execute-command": "E:/app/webhook/build-prod.bat",
    "command-working-directory": "E:/app/webhook",
    "response-message": "Rebuild mdtv2 prod...",
  },{
    "id": "build-react",
    "execute-command": "E:/App/webhook/build-react.bat",
    "command-working-directory": "E:/app/webhook",
    "response-message": "Rebuild react prod...",
  }
]
```
using url to pass cmd
```localhost:9000/hooks/novantio?gettest=hello```
hook.json
```
[
  {
	 "id":"novantio",
	 "execute-command": "test.bat",
	 "response-message": "Executing simple webhook...",
	 "command-working-directory":"D:/tools/webhook-windows-amd64/webhook-windows-amd64/test",
	 "pass-arguments-to-command":[{
		 "source":"url",
		 "name":"gettest"
	 }]
  }
]
```

