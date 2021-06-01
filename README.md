# GrafanaRaspberryPi

## Installation on Raspberry Pi

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
