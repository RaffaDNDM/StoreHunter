# StoreHunter
The script will retrieve the list of all the mobile applications having access to mobile stores developer console.

Having valid App Store Connect credentials, the script will retrieve all the information about the apps:
- _**App Name:**_ Application common name
- _**Bundle ID:**_ Application bundle ID
- _**App ID:**_ Application number ID 
- _**Version:**_ Application version 
- _**Status:**_ Application development status
- _**Is Watch Only:**_ Is the application only for watches?
- _**Downlodable:**_ Is the application downloadable?
- _**Date:**_ Creation date of the last application version
- _**Is public?:**_ Is the application publicly available on App Store to users?
- _**Release History URL:**_ URL of the release history for an application
- _**App Store URL:**_ URL of the application on the public App Store

Having valid Play Store Console credentials, the script will retrieve all the information about the apps:
- _**Account ID:**_ Account ID of the user used to access the Developer Console
- _**Web ID:**_ Application number ID used in Developer Console
- _**App Name:**_ Application common name 
- _**App ID:**_ Application ID 
- _**Status:**_ Application development status
- _**Date:**_ Creation date of the last application version
- _**Is public?:**_ Is the application publicly available on Play Store to users?
- _**Release History URL:**_ URL of the release history for the an application
- _**Play Store URL:**_ URL of the application on the public Play Store

---

## Installation
```bash
pip install -r requirements.txt
```

---

## Execution
```bash
python3 store_hunter.py [--apple] [--google] [--timeout <seconds>] [--debug] [--help]
```
You can specify two modalities:
- `--apple`: to retrieve information about mobile application from the App Store Connect account
- `--google`: to retrieve information about mobile application from the Play Store Console account

Other options:
- `--timeout <seconds>`: to specify timeout in seconds for the login phase (default: 60s)
- `--debug`: debug mode
- `--help`: help command

### App Store Connect
If you specify `--apple` a new Chrome Window will be open using Selenium and you have 60 seconds to login into the App Store Connect using valid credentials.

![App Store Login](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-aab35b09fcc89bf2c4e67a097e62c5e45c41fb89%2Fapp_login.png?alt=media)

![App Store OTP](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-e740623b72c077d194c44aeb4b22c773277ead3b%2Fapp_otp.png?alt=media)

![App Store Trust](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-0e10334d88f0460abd6c33884e52b482729f4d16%2Fapp_trust.png?alt=media)

![App Store Connect](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-37026def8b7db844f5f1aea2accdd9bda281c147%2Fapp_store_connect.png?alt=media)

Then the script will retreive information of the apps that the account can access to in its console and will output in a CSV file (`YYYYMMDD__AppStore.csv`).

### Play Store Console
If you specify `--google` a new Chrome Window will be open using Selenium and you have 60 seconds to login into the Play Store Developer Console using valid credentials.

![Play Store Login](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-3ac7bd180358bfacd08f541a3f44e755447d2e53%2Fplay_login.png?alt=media)

![Play Store Company](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-dd6be3b7dcec794e0cf3501eb2fedfc5abcc275e%2Fplay_company.png?alt=media)

![Play Store Developer Console](https://3928478158-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FhjMjdRXwO33Lfo7uCpl6%2Fuploads%2Fgit-blob-38106365f59bb41eabe84ee5527ca4e7100461d0%2Fplay_developer_console.png?alt=media)

Then the script will retreive information of the apps that the account can access to in its console and will output in a CSV file (`YYYYMMDD__PlayStore.csv`).
