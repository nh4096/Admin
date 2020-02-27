## Running Jupyter Notebook as a `systemd` service

Environment
* Ubuntu 18.04
* Python 3.6
* Jupyter 4.4.0

Important directories
+ Configuration `/apps/jupyter/config`
+ Notebook directory `/apps/jupyter/notebooks` 

### Steps

1. We will launch Jupyter Notebook by a *system* user `jupyter`. This means its UID is small (say 990), and login is not permitted.
```
sudo useradd -M -s /sbin/nologin -u 990 jupyter
```
Or better
```
sudo useradd -r -s /sbin/nologin jupyter
```

2. Create directories and set permissions
```
sudo mkdir -p /apps/jupyter
sudo mkdir -p /apps/jupyter/config
sudo mkdir -p /apps/jupyter/notebooks
sudo chown -R jupyter:jupyter /apps/jupyter
```
Should disable terminal in jupyter, otherwise the user gains login permission.

3. Generate configuration files
```
jupyter notebook --generate-config
sudo mv .jupyter/jupyter_notebook_config.py /apps/jupyter/config/
jupyter notebook password
sudo mv .jupyter/jupyter_notebook_config.json /apps/jupyter/config/
```
Edit, for example to change IP address
```
sudo -u jupyter vim /apps/jupyter/jupyter_notebook_config.py
```

4. Create `/etc/systemd/system/notebook.service` with the following content
```
[Unit]
Description=Jupyter Notebook
After=network.target

[Service]
Type=simple
User=jupyter
WorkingDirectory=/apps/jupyter/notebooks
ExecStart=/usr/local/bin/jupyter notebook --config=/apps/jupyter/jupyter_notebook_config.py
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

5. Launch service
```
sudo systemctl daemon-reload
sudo systemctl start notebook
```
