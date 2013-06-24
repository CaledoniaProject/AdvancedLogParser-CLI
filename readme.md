## Advanced Log Parser
Read and understand logs with SQL phrase.

## Example:

<pre>
    ./logparser.pl --regex '^(?<name>[^:]+):(?<password>[^:]+)' \
       --file   '/etc/passwd' \
       --report '/run/shm/logparser-cmd.db' \
       --table  'parser'
</pre>

## Example output

<pre>
%> echo 'select * from parser limit 1;' | sqlite3 -batch /run/shm/logparser-cmd.db 
password    name      
----------  ----------
x           root  
</pre>