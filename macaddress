#!/bin/bash
wifiSSID=_WIFI_LYRIA
while true
do
  #Disconnect from Network, spoof MAC Address, Connect again
  nmcli connection down $wifiSSID 
  sleep 2
  nmcli connection modify $wifiSSID 802-11-wireless.cloned-mac-address random
  sleep 5
  nmcli device wifi connect $wifiSSID 
  sleep 2
  curl -X POST https://wifi.tgv-lyria.com/router/api/connection/activate/auto

  url="https://wifi.tgv-lyria.com/router/api/connection/status"
  response=$(curl -s "$url")

  remaining_data=$(echo "$response" | jq -r '.remaining_data')

  while [ "$remaining_data" -gt 10000]
  do
    echo "Remaining Data: $remaining_data"
    sleep 5
    response=$(curl -s "$url")
    remaining_data=$(echo "$response" | jq -r '.remaining_data')
  done
done
