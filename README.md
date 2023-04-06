# adobe-login-nightmare
A simple NodeJS module that works with Nightmare (Webdriver) to login to any Adobe service.

## Install for NodeJS
```css
npm install adobe-login-nightmare
```

## Dependencies
- <a href="https://github.com/evancgassman/adobe-fetch-verify">adobe-fetch-verify</a>

## Usage and Functions
```
login(nightmareInstance, username, password, settingsOBJ);
```

## Supported Services:
| Service | Supported | Last Tested Date |
| ------------- | ------------- |  ------------- | 
| Adobe Stock  | Yes ✔️ | (4/5/2023) | 
| Adobe Color  | Yes ✔️ | (4/5/2023) | 
| Adobe Fonts  | No ❌ | ------------- | 
| Adobe Acrobat Pro  | No ❌ | ------------- | 
| Adobe Express  | No ❌ | ------------- | 
| Mixamo  | No ❌ | ------------- | 
| Frame.io  | No ❌ | ------------- | 
| Behance | No ❌ | ------------- | 

In the future, I plan to add supported services as needed, but I am a busy man.<br>
❤️ If you require any assistance, feel free to join <a href="https://discord.gg/y6UywbeB3U">my support Discord!</a>!<br>
💙 If you would love to support me as an independent developer and have the means necessary, check out https://ko-fi.com/evangassman! Anything is appreciated! 

## Example with Annotations
```js
const adobeLoginNightmare = require("adobe-login-nightmare");
const Nightmare = require('nightmare');
const nightmareClient = Nightmare();

async function mainHandler() {

    let settingsOBJ = {
        "verifyType": "IMAP",
        "imapPassword": "imapPassword",
        "service": "Adobe Stock"
    };

    await adobeLoginNightmare.login(nightmareClient, "adobeUsername", "adobePassword", settingsOBJ);

}

mainHandler();
```
**Due to security reasons, Adobe will send a verification code via email when trying to login with this software. In order for this code to be gathered by this package, it is recommended that you set a custom IMAP password. <a href="https://github.com/evancgassman/adobe-fetch-verify/blob/main/README.md#important-notes-and-support">For more information check out this link</a>**.
