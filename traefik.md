# Traefik Proxy
## Debugging
### Letsencrypt i/o error
Probably a Docker network issue. Recreating the bridge helped:
~~~
# systemctl stop docker
# iptables -t net -F
# ip link set docker0 down
# brctl delbr br100
# systemctl start docker
~~~
