nsupdateifchanged
====

Updates DNS record if the registered address is different from the actual one.

`nsupdateifchanged -h`  for further information and usage.

    % bin/nsupdateifchanged -h
    DNS data updater - Update DNS if its address is different from actual one.
     Usage: nsupdateifchanged [-d|-v|-f] [-z zone] [interface_name [interface_name ...]]
        interface_name: Network interface name. Plural names can be specified.
            (Default name(s): en0 en1 ens160 ens171 ens214 ens251 ens252)
        -d: Dry run.  Show what should be done without doing anything actually.
        -v: Verbose mode.  Show what are performed.
        -f: Force mode.  Update DNS even if unnecessary.
        -z zone: Use specified zone name.
    
     An A record for a valid IP address of the specified interface is sent
     to an adequate DNS server.
     Hostname and DNS zone name are retrieved from the result of hostname
     command.
     Multiple A records will be registered if all the records are valid.
     Zone name is picked up from search directive in /etc/resolv.conf
     if -z is not specified and hostname is not fully qualified.

Auto update
----
Set up crontab to update the DNS record at OS boot time and periodically.
Sample descriptions for crontab are in the directory 'crontab'.

