# ConnectingNetworks-Firewalls

Toon De Bie -- r0793272 -- 2ITF-CCS01
FIREWALL RULESET FOR NETFILTER

iptables -A INPUT -p tcp -m state --state NEW -m tcp --dport 53 -j ACCEPT
iptables -A INPUT -p udp -m state --state NEW -m udp --dport 53 -j DROP

iptables -t filter -A INPUT -p icmp --icmp-type echo-request -m limit --limit 10/minute -j ACCEPT
iptables -t filter -A INPUT -p icmp -j DROP
iptables -t filter -A OUTPUT -p icmp --icmp-type echo-reply -j ACCEPT

iptables -A OUTPUT -d security.debian.org --dport 80 -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -P OUTPUT DROP

service iptables save
