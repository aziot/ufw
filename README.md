# ufw
Rules for the ufw firewall

# How to create the rules for ipv4 e.g. 
cat firewall.gr.ipv4.txt  | sed -e "s/\(.*\)/### tuple ### allow any any 0.0.0.0\/0 any \1 in\n-A ufw-user-input -s \1 -j ACCEPT\n/g" >> firewall.ipv4.txt

## add the contents of firewall.ipv4.txt into /etc/ufw/user.rules

## Similarly for ipv6
cat firewall.gr.ipv6.txt  | sed -e "s/\(.*\)/### tuple ### allow any any ::\/0 any \1 in\n-A ufw6-user-input -s \1 -j ACCEPT\n/g" >> firewall.ipv6.txt
