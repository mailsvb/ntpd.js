# ntpd.js
flexible NTP server for testing purposes written for node.js

feature list:

 * define linux timestamp as initial reference to be sent in an NTP reply or let NTP server sent the most recent timestamp
 * define error state
 * define server version
 * define server mode
 * define stratum
 * define delay
 * define dispersion

Example for sending NTP replies based on an initial timestamp provided on start

```javascript
const TimeServer = require('./ntpd.js');

var server = new TimeServer("1220580245", "0", "4", "4", "1", "0.9900", "0.9900");

server.on('data', function(output) {
	console.log(output);
});
```

If you want to get the most recent timestamp of the system

```javascript
var server = new TimeServer("", "0", "4", "4", "1", "0.9900", "0.9900");
```