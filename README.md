# fbt

## Installation

**Prerequisites**
 - Git ([how to install](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))
 - Node.js ([how to install](https://docs.npmjs.com/getting-started/installing-node))

**Clone repository**
```
git clone https://github.com/sqren/fb-sleep-stats.git
```

**Configuration**

Open the source code folder:
```
cd fbt
```

Copy the default config file:
```
cp config/default.json config/development.json
```

Update the following values in `config/development.json`
 - "c_user": [your numeric Facebook user id](https://lookup-id.com/)
 -  "xs": xs value from Facebook cookie
 - "appId": Facebook App Id  Refer to below:

appID was cancelled setup own app id to use:

-    Open https://developers.facebook.com/apps
-    Click "Add a new app"
-    Choose "Website"
-    Click through the setup guide
-    In "Dashboard" copy "App ID" to config/development.json config
-    Choose "Settings" in left-hand menu
-    App Domains: "localhost"
-    Site Url: "localhost:3000"

Remember to run npm run webpack after updating the app id

*Make sure there are no trailing tabs or spaces in the config file!*

**Install dependencies**
```
npm install
```

**Build browser dependencies**
```
npm run webpack
```

## Starting

You need to have two processes running simultaneously: the scraper and the web-server. Therefore, you must run the following two commands in separate windows/tabs.

**Start scraping**

*This will run continuously, polling Facebook every 10 minutes. Keep it running for as long as you want to track sleep.*
```
npm run scrape
```

**Start server**
```
npm start
```

See the result in the browser: [http://localhost:3000](http://localhost:3000)
