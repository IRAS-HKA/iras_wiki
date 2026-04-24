# <a href="/README.md"><img src="/iras_logo.png" alt="iras_logo" width="95" style="vertical-align:middle"> Wiki </a>

## Setup HsKA-8021x
- Username: {yourRzHandle}@iras-wlan.h-ka.de
- Password: {yourRzPassword}

## Setup Eduroam
To establish a connection with the Eduroam Wlan network you need the following security configuration:
- **Security**: WPA & WPA2 Enterprise
- **Authentication**: Protected EAP (PEAP)
- **Anonymous identity**: anonymous@h-ka.de
- **CA certificate**: Select file -> Under '/etc/ssl/certs' select -> *USERTrust_RSA_Certification_Authority.pem*
- **PEAP version**: Automatic
- **Inner authentication**: MSCHAPv2
- **Username**: {yourRzHandle}@h-ka.de
- **Password**: {yourRzPassword}