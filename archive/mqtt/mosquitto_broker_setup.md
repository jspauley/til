# Setup An MQTT Broker

If you want to send data via MQTT, but don't have a broker, one can easily be setup on any Linux system. For this tutorial, we'll be using [Mosquitto Broker](https://github.com/eclipse/mosquitto) running on a separate Raspberry Pi.

First, let's get the neccessary things installed:

```bash
sudo apt update && sudo apt upgrade
sudo apt-get install mosquitto mosquitto-clients
```

Next, set the Mosquitto Broker to start when the system starts:

```bash
sudo systemctl enable mosquitto.service
```

You can confirm the version by running:

```bash
mosquitto -v
```

### Enable Remote Access With Authentication

By default, Mosquitto Broker will not accept remote connections. We want to send data to our Broker from external sources, so we'll need to enable remote connections with authentication using a username and password.

First, let's setup a username and password:

```bash
sudo mosquitto_passwd -c /etc/mosquitto/passwd YOUR_USERNAME
```

This will then prompt for a password. Enter it, then confirm it. Make sure this is secure and stored in a safe place. 

Now we need to edit the configuration:

```bash
sudo nano /etc/mosquitto/mosquitto.conf
```

Add the following line to the top of the file:

```
per_listener_settings true
```

And add these three lines to the bottom:

```
allow_anonymous false
listener 1883
password_file /etc/mosquitto/passwd
```

When done, your file should look like this:

```
# Place your local configuration in /etc/mosquitto/conf.d/
#
# A full description of the configuration file is at
# /usr/share/doc/mosquitto/examples/mosquitto.conf.example

per_listener_settings true

pid_file /run/mosquitto/mosquitto.pid

persistence true
persistence_location /var/lib/mosquitto/

log_dest file /var/log/mosquitto/mosquitto.log

include_dir /etc/mosquitto/conf.d
allow_anonymous false 
listener 1883  
password_file /etc/mosquitto/passwd
```

Now let's restart the Mosquitto Broker and check it's status:

```bash
sudo systemctl restart mosquitto
sudo systemctl status mosquitto
```

That's it! You should now have a running MQTT Broker.
