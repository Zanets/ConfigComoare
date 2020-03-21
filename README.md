# ConfigCompare
For poor guy like me who are upgrading kernel...

```
./ConfigConpare <config1 path> <config2 path>
```
It creates four files: diff.conf, f1.igns.conf, f2.igns.conf, same.conf

- diff.conf: different configs
- f1.igns.conf: lines ignored in config1. e.g., comments
- f2.igns.conf: same with f1.igns.conf, but for config2
- same.conf: same configs

The content of diff.conf looks like this
```
CONFIG_NF_CONNTRACK_ZONES: _N_SET | _N_EXIST
CONFIG_NF_CT_PROTO_GRE: y | m
CONFIG_NF_CT_PROTO_ESP: y | _N_SET
CONFIG_NF_CONNTRACK_FTP: y | m
CONFIG_NF_CONNTRACK_H323: y | m
CONFIG_NF_CONNTRACK_IRC: y | m
CONFIG_NF_CONNTRACK_PPTP: y | m
CONFIG_NF_CONNTRACK_IPSEC: y | _N_SET
CONFIG_NF_CONNTRACK_TFTP: y | m
CONFIG_NF_CONNTRACK_RTSP: y | m
CONFIG_NF_CT_NETLINK: y | _N_SET
CONFIG_NF_NAT: y | m
CONFIG_NF_NAT_FTP: y | m
CONFIG_NF_NAT_IRC: y | m
CONFIG_NF_NAT_TFTP: y | m
CONFIG_NF_NAT_REDIRECT: y | m
```
The format is 
```
<Config Name>: <config1 setting> | <config2 setting>
```
`<config setting>` maybe the value in config or `_N_SET` or `_N_EXIST`
`_N_SET` means the config is `# CONFIG_xxxx is not set`
`_N_EXIST` means the config is not exist in this config
