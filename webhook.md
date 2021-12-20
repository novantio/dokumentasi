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

