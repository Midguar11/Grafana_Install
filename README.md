# Install Server

- VSpahe Create Ubuntu server
- name " Grafana "
- Connect to SSH Copy my computer ssh key
- ssh midguard@serverip

      sudo su -

# Install Grafana

    sudo apt-get install -y adduser libfontconfig1
    wget https://dl.grafana.com/enterprise/release/grafana-enterprise_8.5.4_amd64.deb
    sudo dpkg -i grafana-enterprise_8.5.4_amd64.deb
    
```
    systemctl daemon-reload
    systemctl start grafana-server
    systemctl status grafana-server
    systemctl enable grafana-server.service
    lsof -i -P
    
    ```
# Cheking and setup

- open browser serverip:3000
- user and pass: admin
- add new pasword

# Install influx Db

    wget -qO- https://repos.influxdata.com/influxdb.key | gpg --dearmor > /etc/apt/trusted.gpg.d/influxdb.gpg
    export DISTRIB_ID=$(lsb_release -si); export DISTRIB_CODENAME=$(lsb_release -sc)
    echo "deb [signed-by=/etc/apt/trusted.gpg.d/influxdb.gpg] https://repos.influxdata.com/${DISTRIB_ID,,} ${DISTRIB_CODENAME} stable" > /etc/apt/sources.list.d/influxdb.list
    apt-get update && sudo apt-get install influxdb
    service influxdb start
    systemctl status influxdb
    
    
