# Logrotate
## What is?

It's a fundamental and necessary tool, but not only if you work as a system administrator, which in that case is necessary and justified. The need for logs is unquestionable. You need to have information about what happens in the teams you manage. You keep all this information in records, in logs. However, you cannot save it forever, because it takes up space, and your goal is not to fill your file system with this information, but you need to keep as many records as possible, to know for sure what is happening.

## Configuration
`weekly` » Indicates that the rotation is weekly. That is, each week the oldest record is overwritten.

`rotate 4` » sets a maximum of four records to be saved.

`create` » indicates that a new record is created when the oldest one is rotated 

`compress` » defines that the logs will be saved compressed 

Finally, the line /etc/logrotate.d is included, where it is indicated that all the files found in that directory will be included.

## logrotate.d
Aditional options:

`notifempty` » indicating that it is not rotated in case the file is empty.
 
`missingok` » indicates that an error message will not occur if the log file does not exist 

`posrotate` » to endscript are the flags that point to the script that is executed after the log file, the log, has been rotated. Indicate that this script is executed just before being compressed.

## How to check

*all*

`sudo logrotate /etc/logrotate.conf`

*only 1*

`sudo logrotate /etc/logrotate.d/FILE`

*check status*

`cat /var/lib/logrotate/status`

## Other options
`size <value>` » force rotate when file size is greater than <value> 

`delaycompress` » postpones the compression of the record for one cycle. For example, if you rotate daily, nothing else that was rotated will be compressed, but the next day.
 
`create` » creates an empty log file with the given permissions for a user and group. The definition is create <mode> <user> <group>.


