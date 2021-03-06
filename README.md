[![Build Status](https://travis-ci.org/karmats/gocd-monitor.svg?branch=master)](https://travis-ci.org/karmats/gocd-monitor)
[![Dependencies](https://david-dm.org/karmats/gocd-monitor.svg)](https://david-dm.org/karmats/gocd-monitor)
[![Code Climate](https://codeclimate.com/github/karmats/gocd-monitor/badges/gpa.svg)](https://codeclimate.com/github/karmats/gocd-monitor)

# Go cd monitor
Build monitor for Go cd build server https://www.go.cd/
#### Pipeline status
* Blue - Pipeline is building
* Green - Pipeline build passed
* Red - Pipeline has failed
* Yellow - Pipeline has been paused

![Pipelines](https://github.com/karmats/gocd-monitor/blob/gh-pages/images/pipelines.png?raw=true)

#### Pipeline attributes
![Pipeline explanation](https://github.com/karmats/gocd-monitor/blob/gh-pages/images/pipeline-expl.png?raw=true)

## Setup
Open app-config.js and change the three lines
```   
// Url for your go server
goServerUrl: 'https://ci.example.com',
// Go user to use for communication with go server
goUser: 'xxx',
// Password for go user
goPassword: 'xxx',
  ```
Open a terminal and enter
```
npm install
npm start
```
Go to `http://localhost:3000`

Enjoy :)

## Configuration
Go to `http://localhost:3000?admin` and click the settings button in the bottom-right corner to open the configuration dialog.
* Sort Order - Sort pipelines by status or latest build time
* Filter Pipelines - Disable/enable pipelines to retrieve from go server
![Configuration img](https://github.com/karmats/gocd-monitor/blob/gh-pages/images/configuration.png?raw=true)

## How it works
The server polls your defined go server every `goPollingInterval` seconds. The results are then reported to the client using [socket.io](http://socket.io/). The pipelines are refreshed once every day.

## Development
To run the application in development mode, open a terminal and enter `npm run dev-start`. The server and client will be rebuilt when a js or jsx-file changes.
To run tests, enter `npm test`.
