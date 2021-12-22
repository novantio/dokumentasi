# definition
for setting oracle 

# command
startup database
```
STARTUP PFILE = /u01/app/oracle/admin/orcl/pfile/randomname.ora
```

shutdown database
```
shutdown immediate
```

# config
tnsnames.ora
```
orcl =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = 127.0.0.1)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = orcl)
    )
  )
```
for server
listener.ora
```
LISTENER =
  (DESCRIPTION_LIST =
    (DESCRIPTION =
	 (ADDRESS = (PROTOCOL = IPC)(KEY = EXTPROC1521))
	 (ADDRESS = (PROTOCOL = TCP)(HOST = 127.0.0.1)(PORT = 1521))
    )
  )
SID_LIST_LISTENER=
  (SID_LIST=
    (SID_DESC=
      (GLOBAL_DBNAME=ORCL)
      (ORACLE_HOME=/u01/app/oracle/product/11.2.0/db_1)
      (SID_NAME=ORCL)
	)
)

ADR_BASE_LISTENER = /u01/app/oracle
```
