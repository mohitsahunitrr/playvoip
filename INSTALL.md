Installation
------------

1. Modify values on config.php under 'web' and astwebhelper under 'bin'

2. Copy all files and directories under 'web' to your web document root

3. Go to 'etc' under this package and edit to suit your server needs, 
   hints: 
   - search for: "219.83.41.153" (search without quotes)
   - and search for: "theusername:thepassword" (search without quotes)

4. Copy files under 'etc' to /etc to replace existing configurations on your /etc/asterisk

5. Copy script astwebhelper under 'bin' to /usr/local/sbin

6. Setup a database on your MySQL server and insert queries on file voiprakyat.sql under 'sql'

7. Configure crond to run astwebhelper every minute
   run command:

   ```
   crontab -e
   ````

   and add this line:

    ```
    * * * * * /usr/local/sbin/astwebhelper >/dev/null 2>&1
    ```

8. run this command to make sure asterisk configuration files writable by updateconf.php:

   ````
   chmod 666 /etc/asterisk/*_additional.conf
   ````

9. IF you DO NOT have module ooh323 on your asterisk server, then you MUST REMOVE file ooh323.conf
   from your asterisk configuration directory (/etc/asterisk/ooh323.conf)
