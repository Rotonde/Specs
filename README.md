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
      },
      {
        "message": "I'm excited for this!",
        "timestamp": 1508373135785,
        "target": "dat://60f134e8fb243fbf4a0f8a252cc9aa09bdcf4ecac2efbcb8455aa01c8a04b4b0/index.html",
        "ref": "17",
        "quote": {
          "message": "Have also been scrounging a complex set of arena channels that get at some of the ecosystem that exists around rotonde that I'll share shortly",
         "timestamp": 1508371261682
    },
      {
        "message": "psst!",
        "timestamp": 1508381644692,
        "target": "dat://c1ae9f8b1b10a0df968a157c8b35cd8b32266c657d3aa767751895568146bed4/",
        "whisper": true
    }

},
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
&nbsp;&nbsp; `whisper` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; indicates that the target is the sole intended recipient. if it exists its value is set to true  
&nbsp;&nbsp; `quote` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; contains a `message`. used for replying to, as well as sharing of, a message someone else posted   
&nbsp;&nbsp; `ref` _optional_  
&nbsp;&nbsp; &nbsp;&nbsp; identifies a message, currently only used for rotonde's quotes/re-entries   
#### `dat` the dat url to your rotonde portal
#### `site` a string with a link to a website
