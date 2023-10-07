# Team Server

###

### Install Java

```
sudo apt-get update
sudo apt-get install openjdk-11-jdk
sudo apt install proxychains socat
sudo update-java-alternatives -s java-1.11.0-openjdk-amd64
```

### SystemD Service

```
cd /etc/systemd/system/
```

```
vi cobaltc2.service
```

````
```
[Unit]
Description=RFS CobalStrike
After=network.target
Wants=network.target

[Service]
Type=Simple
WorkingDirectory=/opt/cobaltstrike-v4.7
ExecStart=/opt/cobaltstrike-v4.7/teamserver 192.168.159.195 20232023
Restart=always


[Install]
WantedBy=default.target
```
````

```
sudo systemctl daemon-reload
```

```
sudo systemctl restart cobaltc2.service
```

```
sudo systemctl enable cobaltc2.service
```

```
sudo systemctl status cobaltc2.service
```

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Configure CobaltStrike Keystore

```
keytool -list -v -keystore cobaltstrike.store
```

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

```
keytool -keystore cobaltstrike.store -genkey -alias cobalstrikestore
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
