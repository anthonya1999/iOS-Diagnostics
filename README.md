This is a simple Python script that allows your phone to connect to mitmproxy and run iOS Diagnostics with the ticket number "123456".

Note: Your Mac and iDevice MUST be connected to the same network.


# To Configure:

1.) Install mitmproxy by running this command in terminal:

```
sudo easy_install pip
```

2.) And then:
```
sudo pip install mitmproxy
```

After mitmproxy has been installed, change the directory to where you put the diags.py file, and run:
```
mitmdump -e -s diags.py
```

On your iDevice, go to Settings --> Wi-Fi, and click on the i or blue arrow, depending on which software version you are running, and scroll down to "HTTP Proxy". Then click on "Manual". Now, on your Mac, go to your Network Preferences. Enter the IP (IPv4) Address of your Mac into the "Server" field on your iDevice. And enter 8080 for the port.

In Safari on your iDevice, navigate to "http://mitm.it". Click the Apple icon and install the profile. Go back to your browser, and type in "diags://". Once that has loaded, enter "123456" for the ticket number. Click quick test for the device logs, and click on extended test for power usage information + device logs. The information will be compressed in tar.gz format in the directory where you are running the script from.