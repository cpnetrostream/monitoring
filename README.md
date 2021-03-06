# StreamTest.net Monitoring API  

**StreamTest.net Monitoring** lets you easily create, list, update, delete. Plus enable and disable your streamtest monitors. Any stream on your streamtest dashboard can also be enabled and disable through the API.


## Features

* Create a new monitor
* List all the monitors on your account
* Enable or Disable your monitors
* Access your monitors thumbnail image
* Initiate a new thumbnail to be generated

## Requirements
You'll need a streamtest API token. (Talk to your account rep)

## Usage

If you have an account with StreamTest.net, you probably love their monitoring service and wish you could control it all with an API call. Well this is the beginning of that API documentation.

## Examples

**Get all monitors on your account:**
```
GET https://streamtest-tools.azurewebsites.net/api/GetMonitors
Content-Type: application/json
token: ####(get from streamtest account rep)####
```
* Returns a JSON formatted list of all monitors on your account:
`string id`
`string name`
`string stage`
`string thumbnail_url`



**Enable or Disable monitoring of a stream:**
```
POST https://streamtest-tools.azurewebsites.net/api/SetMonitor
token: ####(get from streamtest account rep)####
Content-Type: application/json


HTTP Body
{
"monitor_id":"dca2eb6b-e138-4156-87a6-ae10b08dba54"
,"enabled":"false"
}
```
* Returns a JSON formatted response 
`string id `
`string name `
`string stage `

* Stage returns enabled or disabled

**Add a new Stream to be monitored**
```
POST https://streamtest-tools.azurewebsites.net/api/AddMonitor
token: ####(get from streamtest account rep)####
Content-Type: application/json

HTTP Body
{
"monitor_url":"rtmp://streamserver.com/stream/live"
,"enabled":"false"
,"monitor_location":"US-WEST"
,"alert_enable":"true"
,"alert_type":"sms"
,"alert_address":"555-222-1212"
,"probe_interval":"60"
}
```
* Returns a JSON formatted response 
