##Unlimited-WiFi-TGV-Lyria
This script allows you to have unlimited connection in Lyria TGV by periodically changing your MAC address.

#Usage
To run the script, follow these steps:

Open a terminal window.
Navigate to the directory where you saved the macaddress.sh file.
Make the script executable by running the command chmod +x macaddress.sh.
Run the script by executing the command ./macaddress.sh.
How it works
The script uses the nmcli command-line tool to disconnect from the WiFi network, change the MAC address, and reconnect to the network. It then sends a request to an API provided by Lyria TGV to check the remaining data allowance. If the remaining data is greater than 1000 MB, the script continues to run. If the remaining data is less than or equal to 1000 MB, the script exits.

Disclaimer
This script is intended for educational purposes only. Use of this script may be a violation of Lyria TGV's terms of service or local laws. Use at your own risk.

