# GrafanaRaspberryPi

## Install Grafana on Raspberry Pi

1. Add the APT key used to authenticate packages:
```sh
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
```
2. Add the Grafana APT repository:
```sh
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
3. Install Grafana:
```sh
sudo apt-get update
```
```sh
sudo apt-get install -y grafana
```
4. Enable the Grafana server:  
```sh
sudo /bin/systemctl enable grafana-server
```
5. Start the Grafana server:
```sh
sudo /bin/systemctl start grafana-server
```
6. Open a browser and go to http://"ip-address">:3000, (IP-address is the address of the Raspberry Pi). You get the ip with the following command
```sh
ifconfig
```
7. Log in to Grafana with the default username **admin**, and the default password **admin**


## Install InfluxDB on Raspberry Pi

1. Add the InfluxDB repository key to yozr Raspberry Pi.
Adding the key will allow the package manager on Raspbian to search the repository and verify the packages its installing.
```sh
wget -qO- https://repos.influxdata.com/influxdb.key | sudo apt-key add -
```
2. Now enter the following command to add the InfluxDB repository to the sources list. 
```sh
echo "deb https://repos.influxdata.com/debian buster stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
```
3. Run the following command on your Raspberry Pi to update the package list.
```sh
sudo apt update
```
4. To install InfluxDB to our Raspberry Pi, all we need to do is run the command below.
```sh
sudo apt install influxdb
``` 
5. Run the following two commands to enable InfluxDB to start at boot on your Raspberry Pi.
```sh
sudo systemctl unmask influxdb
``` 
```sh
sudo systemctl enable influxdb
``` 
6. To start up the InfluxDB server, we will need to run the following command. The service manager will then start up the service and begin monitoring it.
```sh
sudo systemctl start influxdb
``` 
