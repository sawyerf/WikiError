# Android

## ApkTool
### INSTALL_PARSE_FAILED_NO_CERTIFICATESAPK (2020/03/05)
#### Error Message:
```
Installation did not succeed.
The application could not be installed: INSTALL_PARSE_FAILED_NO_CERTIFICATES
APK signature verification failed.
Retry
```
#### Solution
```
keytool -genkey -v -keystore <mykeystore> -alias <alias> -sigalg MD5withRSA -keyalg RSA -keysize 2048 -validity 10000
jarsigner -verbose -sigalg MD5withRSA -digestalg SHA1 -keystore <mykeystore> <name.apk> <alias>
```
