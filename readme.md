## Advanced Log Parser
Read and understand logs with SQL phrase.

## Quick start

Insert the first two fields from /etc/passwd into a table called 'parser',

<pre>
./logparser.pl \
        --regex '^(?&lt;name>[^:]+):(?&lt;password>[^:]+)' \
        --file   '/etc/passwd' \
        --report '/run/shm/logparser-cmd.db' \
        --table  'parser'
</pre>

## Perform database query

List first entry from generated table,

<pre>
%> echo 'select * from parser limit 1;' | sqlite3 -batch /run/shm/logparser-cmd.db 
password    name      
----------  ----------
x           root  
</pre>
