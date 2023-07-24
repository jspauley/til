# Configure Firewall To Receive MQTT Data

If the device running the Mosquitto Broker has a firewall enabled, you'll need to allow the correct port in order for external clients to be able to establish a connection and send data.

First, let's check the status of the firewall:

```bash
sudo ufw status
```

Now let's add a rull to allow access to port 1883 used by the Moqsuitto Broker:

```bash
sudo ufw allow 1883
```

You can double check the status again to make sure the port has been configured correctly.
