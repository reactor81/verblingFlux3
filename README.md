# Verbling Flux/React Challenge 3

## Version 3 - WebRTC Video Addon

### Background

This version has a WebRTC Video chat addon. Multiple users can open the page on different tabs / computers and have video+audio chat - in addition to the Firebase text chat addon from verblingFlux2 repo.

I noticed the verbling/webrtc-lib repository and saw the Twilio library there. In my previous job, we briefly looked at the Twilio site, as well as OpenTok, and Temasys / Skylink.. We decided not to use a WebRTC BaaS/PaaS and created our own, including SIP, TURN and STUN servers. My responsibility was handling the entire web client portion - working with the JSSIP client library, setting up and connecting the media streams, creating mute audio/video buttons, etc. I also did a little bit of packet debugging with wireshark. 

To keep this Verbling Flux Demo simple to startup and run, I decided not to create all that infrastructure - and used a WebRTC cloud service isntead. It seems like Twilio has something in beta, but since I do not have access to that, I decided to look at Skylink. This was my first time looking at Skylink/Temasys code. It was refreshingly simple!

The Skylink API uses CORS and requires me to pick a domain name that will host the client app. I have whitelisted 'localhost' for the API key currently used in this demo. As a result file:// does not work, and a localhost web server was required. I created a very simple express.js server that does nothing but server the index.html file for me at http://localhost:5000/submissions/verbling/index.html .

### Features

#### WebRTC Video/Audio Chat



### Run

1) Ensure that you have cloned repo into the proper subfolder of the server. e.g. on Windows 7, c:\verblingserver\submissions\verbling if the server is located at c:\verblingserver\server

2) run 'npm install' to install express web server (only needed to server static file from localhost, a SkyLink/Temasys CORS requirement, see webserver.js)

3) run 'npm run webserver' to start webserver

4) navigate to http://localhost:5000 in Chrome (Chrome on Windows 7 tested, no other WebRTC enabled browsers were tested..).

### Build

install: npm install

build: npm run build

watch: npm run watch

### Usage

Try opening in multiple tabs or multiple computers. Notice onDisconnect and on connect updates happening. Chat by typing into the black box. 

### Author

Created by Daniel Guillamot - 2015-10-26