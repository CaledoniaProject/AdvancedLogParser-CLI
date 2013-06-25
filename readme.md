## Advanced Log Parser
Read and understand logs with SQL phrase.

## Example usage

Insert the first two fields from /etc/passwd into table 'parser',

<pre>
./logparser.pl \
        --regex '^(?&lt;name>[^:]+):(?&lt;password>[^:]+)' \
        --file   '/etc/passwd' \
        --report '/run/shm/logparser-cmd.db' \
        --table  'parser'
</pre>

## Example output

List first entry from generated table,

<pre>
%> echo 'select * from parser limit 1;' | sqlite3 -batch /run/shm/logparser-cmd.db 
password    name      
----------  ----------
x           root  
</pre>
