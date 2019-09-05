## MySQL

### Audit Plugin
use server_audit.so from `MariaDB 10.4.7`.

MariaDB Audit Plugin version `1.4.8`.



## Q&A
### unknown variable 'server_audit_*' when starting MySQL with Audit Plugin configured
```bash
db_1  | ERROR: mysqld failed while attempting to check config
db_1  | command was: "mysqld --default-authentication-plugin=mysql_native_password --verbose --help"
db_1  |
db_1  | 2019-09-05T01:20:42.853281Z 0 [ERROR] unknown variable 'server_audit_events=CONNECT,QUERY,TABLE,QUERY_DDL,QUERY_DML,QUERY_DCL'
db_1  | 2019-09-05T01:20:42.859449Z 0 [ERROR] Aborting
```

just add `--plugin-load=server_audit.so` in command line parameters to pass the configuration test.