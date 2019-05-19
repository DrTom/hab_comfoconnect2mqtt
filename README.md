HAB-ComfoConnect2MQTT
=====================

This application is part of our **personal** "Home-Automation Bus". It
publishes events of a "Zehnder Comfoair Q" to MQTT. To this end it connects to
a "Zehnder ComfoConnect LAN C" device.

This application is based on
[michaelarnauts/comfoconnect](https://github.com/michaelarnauts/comfoconnect/).
The hard work of reverse engineering the protocol happened there. See also
[ORi0N/comfoconnect_openhab_gw](https://github.com/ORi0N/comfoconnect_openhab_gw)
for a similar project.


Deployment:
-----------

```sh
ansible-playbook -i ~/Programming/SystemEngineering/my-servers_ansible/hosts_home.yml \
  deploy/deploy_play.yml \
  -l hab \
  -e "mqtt_password=$MQTT_PASSWORD" 
```


Development:
------------

```sh
python3 -m venv python
source ./python/bin/activate
pip3.7 install -r requirements.txt
./comfoconnect2mqtt* --help
```

