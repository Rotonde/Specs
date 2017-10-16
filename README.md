# Specifications

Rotonde is a decentralized social network built upon on [dat](https://datproject.org) & [beaker](https://beakerbrowser.com).

### The JSON structure for the Rotonde API. 

In the root directory of the dat there should be a file called `portal.json`. Its contents has the following structure.
```
{
  "name": "cblgh",
  "desc": "the p2p web is here",
  "port": [
    "dat://2f21e3c122ef0f2555d3a99497710cd875c7b0383f998a2d37c02c042d598485/",
    "dat://7f2ef715c36b6cd226102192ba220c73384c32e4beb49601fb3f5bba4719e0c5/",
    "dat://223e4ab259fe5c8d622b52025be869f11a726091772f14ab3603d7182442c6eb"
    ]
  "feed": [
      {
        "message": "welcome to rotonde 2.0", 
        "timestamp": 1507846364271
      },
      {
        "message": "check https://cblgh.org/rotonde.html for a list of portals to follow", 
        "media": "webpage-img.png",
        "timestamp": 1507846314271
      },
      {
        "message": "@neauoire woah that's cool", 
        "target": "dat://2f21e3c122ef0f2555d3a99497710cd875c7b0383f998a2d37c02c042d598485/",
        "timestamp": 1507846214271
      },

      {
        "message": "dat is so cooool, thanks https://datproject.org & https://beakerbrowser.com !", 
        "timestamp": 1507846194271
        "editstamp": 1507846216271
      }
  ],
  "dat": "dat://7f2ef715c36b6cd226102192ba220c73384c32e4beb49601fb3f5bba4719e0c5",
  "site": "https://cblgh.org"
}
```

#### `name` your display name
#### `desc` a description for you & your portal
#### `port` an array of rotonde portals
#### `feed` a list of json objects, containing the following attributes
&nbsp;&nbsp; `message` _required_   
&nbsp;&nbsp; &nbsp;&nbsp; a string  
&nbsp;&nbsp; `timestamp` _required_  
&nbsp;&nbsp; &nbsp;&nbsp; an int representing the unix time the message was posted  
&nbsp;&nbsp; `editstamp` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; an int representing the unix time of the edit  
&nbsp;&nbsp; `target` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; the destination portal for your message, basically a reply  
&nbsp;&nbsp; `media` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; the name of a media file (.jpg, .png, .gif), relative to the dat's /media/content folder  
