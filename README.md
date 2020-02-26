# PiTunnel
Reverse SSH Tunnel for Raspberry Pi. It will also work on any linux distro.

## Pre-requisites
* Python 2.7
* pyton-pip
* A VM/Server with Public/Static IP (If you don't have one, try [portmap.io](https://portmap.io/ "portmap.io URL"))

## Usage
1. Clone this Repo
2. Go inside the Repo Directory
3. Install requirements
  ```shell
  pip install -r requirements.txt
  ```
4. Run the script with args
  ```shell
  python tunnel.py <LOCAL_PORT> <VM_IP>:<VM_PORT_TO_MAP> <VM_USERNAME> <PATH_TO_KEY_FILE>
  ```
  ```shell
  python tunnel.py 80 192.18.13.16:8080 root /home/pi/pi-tunnel/mykey.pem
  ```
  OR

5. Add to `crontab`
  ```shell
  crontab -e
  @reboot /usr/bin/python /home/pi/py-tunnel/tunnel.py 80 192.18.13.16:8080 root /home/pi/pi-tunnel/mykey.pem  > /home/pi/pi-tunnel/pi-tunnel.log 2>&1 &
  ```
