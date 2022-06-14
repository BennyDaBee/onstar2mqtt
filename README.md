# onstar2mqtt
A service that utilizes the [OnStarJS](https://github.com/samrum/OnStarJS) library to expose OnStar data to MQTT topics.

This Fork is for Gas Vehicles. 

There is no affiliation with this project and GM, Chevrolet nor OnStar. In fact, it would be nice if they'd even respond to development requests so we wouldn't have to reverse engineer their API.

## Running
Collect the following information:
1. [Generate](https://www.uuidgenerator.net/version4) a v4 uuid for the device ID
1. OnStar login: username, password, PIN
1. Your car's VIN. Easily found in the monthly OnStar diagnostic emails.
1. MQTT server information: hostname, username, password
    1. If using TLS, define `MQTT_PORT` and `MQTT_TLS=true`

### Install on Ubuntu
I know this works for Ubuntu.  
`git pull https://www.github.com/BennyDaBee/onstar2mqtt`  
After it pulls, move to the onstar2mqtt directory.  
`npm install`  
This will install all the dependencies.  
The way I do things is not best practice, but I do edit the index.js in src with my credentials for MQTT and Onstar.  

### Node.js
It's a typical node.js application, define the same environment values as described in the docker sections and run with:
`npm run start`. Currently, this is only tested with Node.js 12.x.

### Home Assistant configuration templates
MQTT auto discovery is enabled. For further integrations and screenshots see [HA-MQTT.md](HA-MQTT.md).

## Development
### Install Dependencies
`npm install`
### Running
`npm run start`
### Testing
`npm run test`
### Coverage
`npm run coverage`
### Releases
`npm version [major|minor|patch] -m "Version %s" && git push --follow-tags`

Publish the release on GitHub to trigger a release build (ie, update 'latest' docker tag).
