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
login(username, password, settingsOBJ);
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
const adobeVerify = require("adobe-login-nightmare");

async function mainHandler() {
    let options = {
        searchFlag: 'ALL',
        subSearchFlag: 'SINCE',
        subSearchFlagValue: new Date(),
        returnTimestamp: true,
        limit: 15
    };

    let codeList = await adobeVerify.fetch("example@gmail.com", "wgg3g2hh2h", options);
    console.log(codeList); 
    /*
      This will log an array of objects containing the properties "timestamp" and "code".
      Example: [{code: "243631", timestamp: [ 'Thu, 23 Mar 2023 21:22:04 +0000' ]}, {code: "638211", timestamp: [ 'Thu, 21 Mar 2023 21:22:04 +0000' ]}]
    */
}

mainHandler();
```
