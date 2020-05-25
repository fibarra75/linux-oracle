# linux-oracle
Operación básica de Oracle 12c en RHEL 7

Con cuenta oracle (utilizar su)
Comando para subir el motor
dbstart <sid> 

Para verificar si la instancia esta arriba

$> lsnrctl status

Listening Endpoints Summary...\
  (DESCRIPTION=(ADDRESS=(PROTOCOL=tcp)(HOST=0.0.0.0)(PORT=1521)))\
  (DESCRIPTION=(ADDRESS=(PROTOCOL=ipc)(KEY=EXTPROC1521)))\
  (DESCRIPTION=(ADDRESS=(PROTOCOL=tcps)(HOST=roble)(PORT=5500))(Security=(my_wallet_directory=/u01/app/oracle/admin/oradnet/xdb_wallet))(Presentation=HTTP)(Session=RAW))\
Services Summary...\
Service "oradnet" has 1 instance(s).\
  Instance "oradnet", status READY, has 1 handler(s) for this service...\
Service "oradnetXDB" has 1 instance(s).\
  Instance "oradnet", status READY, has 1 handler(s) for this service...\
The command completed successfully\

Consultar proceso\
$> ps -ef | grep smon\

oracle   31236     1  0 00:18 ?        00:00:00 ora_smon_oradnet\
oracle   31491 30140  0 00:22 pts/1    00:00:00 grep --color=auto smon\

Si la instancia no sube o se baja luego de unos minutos, se debe revisar los archivos alert_*.log
y *_clmn_2811.trc

Ingresar a sqlplus
$> sqlplus / as sysdba
SQL> connect sys as sysdba;
SQL> show parameter dump;

$> find /u01 -name alert_*.log





