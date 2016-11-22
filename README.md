# telegraf-asterisk
Script to be executed by Telegraf to connect to Asterisk and get some interesting values

## Installation
Copy this script into /usr/local/bin and change permissions to be executed by 'telegraf' user.

<pre>
    cp telegrafAsterisk /usr/local/bin/
    chown telegraf /usr/local/bin/telegrafAsterisk
    chmod 755 /usr/local/bin/telegrafAsterisk
</pre>

Modify the script with your manager account.

Modify telegraf.conf file to add this input plugin to be able to execute this script.

<pre>
    [[inputs.exec]]
    commands = ["/usr/local/bin/telegrafAsterisk"]
    timeout = "5s"
    # name_suffix = "_mycollector"
    data_format = "influx"
</pre>

