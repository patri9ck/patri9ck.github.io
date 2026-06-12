[< Main page](index.md)

To ensure a secure connection including authentication and encryption, you must pair your app with your server.

Get started by running the server:
```
$ a2ln 8888
==> Notification server running on port 8888
                             
                             
    █▀▀▀▀▀█  █ ▄  █▀▀▀▀▀█    
    █ ███ █ ███▄▀ █ ███ █    
    █ ▀▀▀ █ ███ █ █ ▀▀▀ █    
    ▀▀▀▀▀▀▀ █ █ █ ▀▀▀▀▀▀▀    
    ▀▄██▀█▀▄ ▀  ▀ ▀▀█▀█ ▄    
     █▄█  ▀▀▄██▀█▄▀█ ▀██▄    
     ▀▀▀▀ ▀▀▄█▄▄▀   ▄ ▀      
    █▀▀▀▀▀█ ▄█▀▄██ █  █ ▄    
    █ ███ █ █ ▀▄█▀▀▀ ▄▀ ▀    
    █ ▀▀▀ █ ▀██▄ ███▀▄▀ ▄    
    ▀▀▀▀▀▀▀ ▀▀ ▀ ▀  ▀ ▀      
                             
                             
==> To pair a new device, open the Android 2 Linux Notifications app and scan this QR code or enter the following:
IP: 192.168.178.22
Port: 36513

==> Public Key: cZ3w(+qGK6QlCuUwIEW93M*Uum(Y?Y&2UteK?imZ
```
If you use a firewall, you can specify the port of the pairing server by using the `--pairing-port` flag.

Next, open the app and scan the QR code or enter the shown IP and port in the pair dialog:

<img src="https://raw.githubusercontent.com/patri9ck/a2ln-app/main/fastlane/metadata/android/en-US/images/phoneScreenshots/pair.png" width="200"/>

The server should now display the following:
```
==> New pairing request

IP: 192.168.178.33
Public Key: q(8S=6Sd6tkOaHm(.}u6m)jnC1i0pj3-SS+K9Kb*

Accept? (Yes/No): 
```

Simply type `Yes` and press enter. The public key is saved under `$HOME/.a2ln/clients/192.168.178.33.key` in this case.

To finish the pairing process, confirm the newly paired device inside the app.
