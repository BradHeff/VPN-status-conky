# Get VPN Status on Conky

this script will check for a folder called tun0

    /proc/sys/net/ipv4/conf/tun0
 
when you connect to your vpn via NetworkManager, a folder is created called tun0. So if the folder exist the script will return On and when you are not connected the folder is then removed so the script will return Off.

in your conky script you will need to have color2 (On) and color3 (Off) declared with color codes (green and red) like below.

## Conky 1.10.*

    color2 = '8AD749',
    color3 = 'F80E27',
    
## Conky 1.9.*

    color2 8AD749
    color3 F80E27

Once that is done its time to call our python script from the conky config, we do that like this

    VPN Status${alignr}${execpi 10 python /home/CHANGEME/vpn.py}
    

