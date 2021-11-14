# TCPDUMP

## Tips and Tricks

**Find all GET requests**

`tcpdump -i lo0 port 7089 -vvAls0|rg GET`
