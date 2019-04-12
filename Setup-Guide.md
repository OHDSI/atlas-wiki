# ATLAS Setup Guide

The following sections detail the process for setting up Atlas and its dependencies.

## Prerequisites

### WebAPI
The first prerequisite for ATLAS is to [Install the OHDSI WebAPI](https://github.com/OHDSI/WebAPI). Installation and configuration information is available on the [WebAPI wiki](https://github.com/OHDSI/WebAPI/wiki). The ATLAS setup assumes WebAPI is avaiable and configured with one or more patient data sets converted to the OMOP Common Data Model.  

### Achilles
To use the [[Data Sources]] feature within ATLAS you must first [setup and execute ACHILLES](https://github.com/OHDSI/Achilles#getting-started) in your environment. Once you have successfully generated summary statistics, you are ready to configure ATLAS to use this information.

### NodeJS

ATLAS requires the use of Node Package Manager (npm) to obtain all of the JavaScript dependencies for the application. Please ensure that you have downloaded [NodeJS](https://nodejs.org/en/download/) which includes the npm utility which will be used during the ATLAS installation.

## ATLAS Installation

The following sections will detail how to download and ready the ATLAS code base and to configure it for your environment.

### Code Deployment
Download the [latest release of ATLAS](https://github.com/OHDSI/Atlas/releases/latest). From the root of the ATLAS folder, run the following command:

```
C:\Git\OHDSI\Atlas> npm run build
```

Then copy all of the files from the Atlas repository to your web server including the `node_modules` folder (this is required to resolve all JavaScript dependencies). Set up your webserver such that the application will be reachable via a URL such as: 

```
  http://<your_webserver>/atlas
```

### Atlas Configuration

The default configuration for ATLAS is found in the `/js/config/app.js` file. To override these application settings, create a new file in `/js/config-local.js` (example below). **Please note: the file /js/config-local.js is *not* included in the Atlas repository. This is by design so that you may have environment-specific configuration.** 

```javascript
define([], function () {
	var configLocal = {};

	configLocal.api = {
		name: 'My Organization Name',
		url: 'https://webapi.server.com/WebAPI/'
	};

	return configLocal;
});
```

In the example above, the `/js/config-local.js` overrides the corresponding ".api" property found in `/js/config/app.js` and allows for custom configuration for your environment. The same pattern can be used to override the other settings in `/js/config/app.js`.

Once this is complete, you should now be able to navigate to ATLAS from Google Chrome. 

```
  http://<your_webserver>/atlas
```

## Troubleshooting

If you are having trouble loading ATLAS, we recommend the following troubleshooting steps:

- Open [Google Chrome's developer tools](https://developers.google.com/web/tools/chrome-devtools/) (press CTRL+SHIFT+I) to reveal several tools that are useful for debugging. In the developer tools, use the [console](https://developers.google.com/web/tools/chrome-devtools/console/) to inspect any errors reported by ATLAS.
- Ensure that you can reach the OHDSI WebAPI by navigating to: `http://<your_webserver>/WebAPI/source/sources`. If you are unable to reach this endpoint, ATLAS will be unable to function properly. Additionally, if this endpoint returns an empty array, this indicates that there are no sources configured which will also prevent ATLAS from functioning.
- If there are other issues, please capture as much information as possible using the Google Chrome developer console and post them to the [OHDSI Forums](http://forums.ohdsi.org/c/developers) or [create an issue here on GitHub](https://github.com/OHDSI/Atlas/issues).

