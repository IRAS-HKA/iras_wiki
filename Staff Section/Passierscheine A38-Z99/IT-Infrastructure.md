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


## Zweifaktorauthentifizierung
#### Einrichten mit Authenticator App
1. [https://mfa.h-ka.de](https://mfa.h-ka.de)
2. Enroll Token
3. Set **NO** PIN/Password
4. Click on created token in the "All tokens" tab
5. Enter one toke from app to: "Enter first OTP value"
6. Wait for app to create new token and enter to: "Enter second OTP value"
7. Click Resync Token
8. Done.

#### Email Anmelden mit Token
- https://owa.h-ka.de
- Token aus Authenticator app
- Wenn PIN/Password vergeben wurde muss es **immer vor** dem Token eingegeben werden

#### Nach Fehlanmeldung zurücksetzen
1. Token ist nach 10 Fehlversuchen gesperrt
2. [https://mfa.h-ka.de](https://mfa.h-ka.de)
3. Auf Fehlercounter klicken zum resetten
