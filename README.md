# Wireless Monitoring, WLAN Security & Netsh

A hands-on lab exploring wireless network security for Data Security Concepts (CIT245)
at T.A. Marryshow Community College.

## Overview

This lab covers four key areas of wireless network security:

- Scanning and analysing nearby Wi-Fi networks using NirSoft WifiInfoView
- Viewing detailed WLAN security information using Vistumbler
- Configuring a wireless router securely using the TRENDnet online emulator
- Managing Wi-Fi connections and generating network reports using Windows netsh commands

## Lab Activities

### Using a Wireless Monitor Tool (WifiInfoView)
Downloaded and ran NirSoft WifiInfoView from www.nirsoft.net. Scanned for nearby
Wi-Fi networks and recorded the following information:

| Network Name | Channel | Band | Signal | Security |
|--------------|---------|------|--------|----------|
| My Network | 6 | 2.4 GHz | -58 dBm | WPA2 |
| Neighbour 5G | 44 | 5 GHz | -72 dBm | WPA2 |
| Guest WiFi | 1 | 2.4 GHz | -65 dBm | Open |

Key observations:
- Many networks clustered on channels 1, 6, and 11 causing potential interference
- Open networks broadcast data that anyone nearby can intercept
- Disabling SSID broadcast does not meaningfully improve security as tools like
  WifiInfoView can still detect hidden networks

### WLAN Security Information with Vistumbler
Downloaded and installed Vistumbler from www.vistumbler.net. Scanned nearby networks
and reviewed authentication and encryption columns.

| Field | Information |
|-------|-------------|
| BSSID (MAC) | B0:A7:B9:XX:XX:XX |
| Channel | 6 |
| Signal | 80% |
| Security | WPA2-Personal / AES |

Additional features explored:
- Graph 1 and Graph 2 views showing signal strength over time
- Audio and text-to-speech signal reporting for site surveys without screen monitoring
- Authentication and Encryption panes in the left panel organised by security type

### Configuring a Wireless Router
Used the TRENDnet online router emulator at trendnet.com/emulators to practice
secure wireless router configuration.

| Setting | Value Chosen |
|---------|-------------|
| SSID | MySecureNetwork |
| Security Mode | WPA2-PSK |
| Encryption | AES |
| Admin Password | Changed |
| WPS | Disabled |

Also explored the Guest Network settings, noting that guest networks use a separate
isolated network and can be restricted to internet access only using the WLAN Partition
and Internet Access Only options.

### Using Microsoft Windows Netsh Commands
Opened Windows Terminal (Admin) and used the following netsh wlan commands:

| Command | Purpose |
|---------|---------|
| `netsh wlan show interfaces` | View current connection details including SSID, signal and security type |
| `netsh wlan show profiles` | List all saved Wi-Fi network profiles on the device |
| `netsh wlan show profile name="[SSID]"` | View security details for a specific saved profile |
| `netsh wlan show networks` | Display all currently visible Wi-Fi networks |
| `netsh wlan disconnect` | Disconnect from the current network |
| `netsh wlan connect name=[profile] ssid=[ssid]` | Reconnect to a saved network |
| `netsh wlan add filter permission=block ssid=[ssid]` | Block a specific network |
| `netsh wlan delete filter permission=block ssid=[ssid]` | Remove a network block |
| `netsh wlan show wlanreport` | Generate a detailed HTML Wi-Fi event report |

## Key Takeaways

- Wi-Fi networks broadcast significant information publicly including SSID, BSSID,
  channel, signal strength, and security type — all visible to anyone with the right tool
- Disabling SSID broadcast is not a meaningful security control as passive scanners
  can still detect hidden networks
- WPS contains known security vulnerabilities and should be disabled on all routers
- WPA2 with AES encryption is the minimum acceptable standard for wireless security
- Netsh commands provide powerful Wi-Fi management capabilities beyond what the
  standard Windows GUI exposes

## Tools Used

| Tool | Purpose |
|------|---------|
| NirSoft WifiInfoView (nirsoft.net) | Passive Wi-Fi network scanner |
| Vistumbler (vistumbler.net) | Detailed WLAN security and signal analysis |
| TRENDnet Router Emulator (trendnet.com) | Safe wireless router configuration practice |
| Windows netsh (Command Line) | Wi-Fi connection management and reporting |

## Security Concepts Demonstrated

| Concept | Description |
|---------|-------------|
| SSID Broadcasting | Network name visible to all nearby devices even when hidden |
| WPS Vulnerability | WPS PIN brute-force weakness makes it an insecure feature |
| WPA2-PSK / AES | Current standard for strong wireless encryption |
| Guest Network Isolation | Separate network segment for visitors with restricted access |
| WLAN Filtering | Blocking specific networks from connecting via netsh |
| Wi-Fi Profiling | Saved profiles reveal historical network connections on a device |

## Environment

- OS: Windows 11
- Tools: Web browser, NirSoft WifiInfoView, Vistumbler, TRENDnet Emulator,
  Windows Terminal

## License

<strong>[&copy; 2026 Ahndre Walters](https://github.com/AhndreWalters/Wireless-Monitoring-WLAN-Security-and-Netsh/blob/main/LICENSE) · Wireless Monitoring, WLAN Security & Netsh · TAMCC Dat Security Concepts Course · College Course Assignment</strong>
