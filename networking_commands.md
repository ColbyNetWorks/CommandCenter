
## Aruba Logging Config SMTP 

```powershell 

snmp-server vrf default
snmp-server trap-source interface vlan110 vrf default
snmp-server community CommunityName1
snmpv3 user Username1 auth sha auth-pass ciphertext thiswillbethecypherpassword priv aes priv-pass ciphertext thiswillbethecypherprivpassword 
snmp-server host 10.10.10.10 trap version v3 user Username1
snmpv3 context Viewname1  vrf default community CommunityName1
snmpv3 user Username1 context Viewname1

```
