# Setup Service To Auto Start On Boot

If you want a Python script to run on system boot, it's best to set it to run as a service. 

First, create the service file in the appropriate location:

```bash
sudo nano /etc/systemd/system/service_name.service
```

Add the following text to the file, adapting it for the actual location of the `example_script.py` file:

```
[Unit]
Description=My Example Service
After=network.target

[Service]
ExecStart=/usr/bin/python3 /home/username/some_folder/example_script.py 
WorkingDirectory=/home/username/some_folder
StandardOutput=inherit
StandardError=inherit
StartLimitIntervalSec=30
StartLimitBurst=100
Restart=always
User=username

[Install]
WantedBy=multi-user.target
```

A note one `StartLimitIntervalSec=30` and `StartLimitBurst=100`, as these are not always included: if the service restart count exceeds the value of `StartLimitBurst` within the time (in seconds) specified by the value of `StartLimitInterval`, the service startup will fail.

Now start the service:

```bash
sudo systemctl start service_name.service
```

The Python script should now be running as a service. To have the script run on system boot, run one last command:

```bash
sudo systemctl enable service_name.service
```

That's it! The Python script will now auto-start any time the system boots. 

There are now additional commands you can run to start, stop, or check the status of the service.

To disable auto-start: 

```bash
sudo systemctl disable service_name.service
```

View the status and logs with: 

```bash
sudo systemctl status service_name.service
```

Stop the service with: 

```bash
sudo systemctl stop service_name.service
```

Restart the service with: 

```bash
sudo systemctl restart service_name.service
```
