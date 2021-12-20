# nssm

## definition
NSSM - the Non-Sucking Service Manager
make .bat or any command into windows service

## command
Service installation
``` nssm install <servicename> ```

Service removal
``` nssm remove <servicename> ```

Starting and stopping a service
```
nssm start <servicename>
nssm stop <servicename>
nssm restart <servicename>
```
Querying a service's status
``` nssm status <servicename> ```

Sending controls to services
```
nssm pause <servicename>
nssm continue <servicename>
nssm rotate <servicename>
```
