admin-disable-wireless-autoconfig.cmd
```
@ECHO ON ::Executar como admin ::Desativa a descoberta automática de redes pelo adaptador wi-fi netsh wlan set autoconfig enabled=no interface="Wi-Fi"
```

admin-enable-wireless-autoconfig.cmd
```
@ECHO ON ::Executar como admin ::Ativa a descoberta automática de redes pelo adaptador wi-fi netsh wlan set autoconfig enabled=yes interface="Wi-Fi"
```
