[Back to Home](../../README.md) / [3.3 Infrastructure](3.3-infrastructure.md) /  **Setup Eduroam**

# Setup Eduroam
To establish a connection with the Eduroam Wlan network you need the following security configuration:
- **Security**: WPA & WPA2 Enterprise
- **Authentication**: Protected EAP (PEAP)
- **Anonymous identity**: anonymous@h-ka.de
- **CA certificate**: Select file -> Under '/etc/ssl/certs' select -> *USERTrust_RSA_Certification_Authority.pem*
- **PEAP version**: Automatic
- **Inner authentication**: MSCHAPv2
- **Username**: {yourRzHandle}@h-ka.de
- **Password**: {yourRzPassword}