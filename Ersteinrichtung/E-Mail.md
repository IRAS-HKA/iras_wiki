# <a href="/README.md"><img src="/iras_logo.png" alt="iras_logo" width="95" style="vertical-align:middle"> Wiki </a>

## Zertifikat für Verschlüsselung erstellen - Achtung: Aktuell nicht möglich
--> Zitat Hr. Quint: "Die Folge ist, dass wir (wie alle anderen Wissenschaftseinrichtungen europaweit) ab dem 10.01. keine Zertifikate erneuern/neu erstellen können."
1. [RZ-Flyer](https://www.h-ka.de/securedl/sdl-eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE3NDI4OTA5ODEsImV4cCI6MTc0Mjk4MDk4MSwidXNlciI6MzQ3MjIsImdyb3VwcyI6WzAsLTIsMTY0Niw0NTE1NCw0NTIwNF0sImZpbGUiOiJmaWxlYWRtaW4vSG9jaHNjaHVsZV9LYXJsc3J1aGVfSEtBL19pbnRlcm4vSEtBX0JFLVJaX0ZseWVyX1plcnRpZmlrYXRlXzA3MjAyNC5wZGYiLCJwYWdlIjo0ODI0fQ.EvXX7a-vQ3gl2t0OwhrfJ6Dc1Ht9N1eIyg7GThNmCIk/HKA_BE-RZ_Flyer_Zertifikate_072024.pdf)
2. Anmeldung mit RZ-Zugangsdaten an https://cert-manager.com/customer/DFN/idp/clientgeant via Shibboleth IDP. Kein Papier mehr nötig!
3. Wahl der Parameter
   - Certificate Profile := "GEANT Personal Certificate"
   - Gültigkeitsdauer:= 365 oder 720 Tage
   - Generierungsmethode:="Key Generation"
   - Key-Type := "RSA-4096"
5. Abholen des Zertifikats via Download direkt im Browser. Import wie gewohnt.

## E-Mail Signatur erstellen
1. [Vorlage für E-Mail-Signatur](https://www.h-ka.de/intern/mitarbeitende/organisieren/hochschulweite-prozesse/prozesse-corporate-design-corporate-identity?ADMCMD_simUser=1646#c48591) kopieren und mit persönlichen Angaben überschreiben
2. Signatur im E-Mail Client automatisch in Nachrichten einfügen: Einstellungen ➝ Optionen ➝ E-Mail ➝ Layout ➝ E-Mail-Signatur


## Zweifaktorauthentifizierung
### Einrichten mit Authenticator App
1. [https://mfa.h-ka.de](https://mfa.h-ka.de)
2. Enroll Token
3. Set **NO** PIN/Password
4. Click on created token in the "All tokens" tab
5. Enter one toke from app to: "Enter first OTP value"
6. Wait for app to create new token and enter to: "Enter second OTP value"
7. Click Resync Token
8. Done.

### Email Anmelden mit Token
- https://owa.h-ka.de
- Token aus Authenticator app
- Wenn PIN/Password vergeben wurde muss es **immer vor** dem Token eingegeben werden

### Nach Fehlanmeldung zurücksetzen
1. Token ist nach 10 Fehlversuchen gesperrt
2. [https://mfa.h-ka.de](https://mfa.h-ka.de)
3. Auf Fehlercounter klicken zum resetten
