````
sudo cp /lib/systemd/system/wpa_supplicant.service /etc/systemd/system/wpa_supplicant.service
wpa_passphrase 'ESSID' 'passphrase' | sudo tee -a /etc/wpa_supplicant/wpa_supplicant.conf
sudo systemctl daemon-reload
sudo systemctl enable wpa_supplicant.service
sudo systemctl enable dhclient.service
sudo systemctl disable systemd-networkd
sudo systemctl enable networking
````
