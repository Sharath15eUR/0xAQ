# Module 3 – Network Authentication Tools - Assignment
1. Write a config file so that wpa_supplicant can associate to FT Dot1x WLAN
```
ctrl_interface=/var/run/wpa_supplicant GROUP=netdev
update_config=1
fast_reauth=1

network={
    ssid="ASUS_X00TD"
    key_mgmt=FT-EAP
    pairwise=CCMP
    group=CCMP
    proto=RSN
    eap=PEAP
    identity="aaquil"
    password="testing"
    phase1="fast_provisioning=2"
    phase2="auth=MSCHAPV2"
    priority=1
}
```
2. Bring up a Freeradius, wpa_supplicant in linux machine, use "eapol_test" utility in wpa_supplicant and try connecting successfully to the Freeradius. Also, please capture the radius packets that is exchanged between eapol_test and Freeradius using "tcpdump" command.
   wpa_supplicant.conf
   ```
   ctrl_interface=/var/run/wpa_supplicant
   update_config=1
   network={
      ssid="ASUS_X00TD"
      key_mgmt=WPA-EAP
      eap=PEAP
      identity="aaquil"
      password="testing"
      phase2="auth=MSCHAPV2"
    }
   ```
   clients.conf
   ```
   client localhost {
        ipaddr = 127.0.0.1
        secret = testing
        proto = *
        require_message_authenticator = no
        nas_type = other
   }
   ```
   user
   ```
   aaquil  Cleartext-Password := "testing"
   ```
   Commands
   Terminal 1 - wpa_supllicant
   ```
   eapol_test -c wpa_supplicant.conf -a 127.0.0.1 -s testing 
   ```
   Terminal 2 - freeradius
   ```
   systemctl start freeradius
   freeradius -X
   #if you get failed port address already in use then 
   service freeradius restart
   service freeradius stop
   freeradius -X
   ```
   Terminal 3 - tcpdump
   ```
   tcpdump -i lo -nn -s 0 -v port 1812
   ```
   
   ![execution](https://github.com/Sharath15eUR/0xAQ/assets/88236255/9d7b70e6-4036-4c0c-a5da-ba6957c70a13)

