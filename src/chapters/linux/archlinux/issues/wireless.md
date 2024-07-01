# Wireless

If you are on an Arch Live USB, you can configure your wireless connection this way:

Get an interactive prompt:
```bash
iwctl
```

Get some help:
```bash
iwctl help
```

List all Wi-Fi devices:
```bash
iwctl station list
```

If the device or its corresponding adapter is turned off, turn it on:
```bash
iwctl station device set-property Powered on
iwctl station adapter set-property Powered on
```

Scan for networks (note that this command will not output anything):
```bash
iwctl station device scan
```

List all available networks:
```bash
iwctl station device get-networks
```

Connect to a network:
```bash
iwctl station device connect SSID
```
