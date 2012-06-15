# doop - A Hadoop Shell
Doop is a command line utility that acts as though you have a "shell" on HDFS.  You can get the current options, by using:

    $> doop -h

Most of the simple things are there that you'd expect - cd, ls, cat, tail, pwd, and local shell execution (if a command starts with a !).  Here's some example usage:

    hadoop-0.20.2-cdh3u1:/> ls
    Found 3 items
    drwxr-xr-x   - dobby  supergroup          0 2012-03-19 15:46 /home
    drwxr-xr-x   - dobby  supergroup          0 2012-06-15 00:00 /system
    drwxrwxrwx   - dobby  supergroup          0 2012-06-15 15:30 /tmp
    hadoop-0.20.2-cdh3u1:/> cd /tmp
    hadoop-0.20.2-cdh3u1:/tmp> ls
    Found 2 items
    drwxrwxrwx   - dobby           supergroup          0 2012-05-25 16:33 /tmp/_distcp_logs_2wzcfa
    drwxrwxrwx   - dobby           supergroup          0 2012-05-25 22:24 /tmp/_distcp_logs_4kyqq0
    drwxrwxrwx   - dobby           supergroup          0 2012-05-25 22:24 /tmp/tmpfile
    hadoop-0.20.2-cdh3u1:/tmp> cat tmpfile
    this is a temp file
    hadoop-0.20.2-cdh3u1:/tmp> get tmpfile
    Downloading /tmp/tmpfile to /home/bmuller
    hadoop-0.20.2-cdh3u1:/tmp> !cat tmpfile
    this is a temp file    