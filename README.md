# Specifications

Rotonde is a self-hosted, platform and programming language agnostic social media experiment. Its purpose is simply to share feeds of daily activity logs between its members. See [this feed](http://rotonde.xxiivv.com) for an example.

You may browse [the custom clients](https://github.com/Rotonde) for inspiration.

## Answer
### The JSON structure for the Rotonde API. 

The answer is the minimum required structure for the data answered by rotonde calls.

```
{
  "profile":
  {
    "name":"Devine Lu Linvega",
    "location":"Huahine",
    "position":"-16.812254, -150.989524",
    "color":"#72dec2",
    "glyph": "M240,240 l0,-90 a-90,-90 0 0,0 -90,-90 l-90,0 l0,90 a90,90 0 0,0 90,90 l60,0 l0,-90 a-60,-60 0 0,0 -60,-60 l-60,0 l0,60 a60,60 0 0,0 60,60 l30,0 l0,-60 a-30,-30 0 0,0 -30,-30 l-30,0 l0,30 a30,30 0 0,0 30,30",
    "avatar":"http://wiki.xxiivv.com/public.oscean/media/brand/logo.devine.lu.linvega.png"
  },
  "feed":[
    {
      "time":"1497499200",
      "text":"Worked on Rotonde specs.",
      "data":
      {
        "topic":"Rotonde",
        "task":"Development",
        "focus":0.5,
        "sleep":0.3
      }
    },
    {
      "time":"1496326400",
      "media":"http://wiki.xxiivv.com/public.oscean/media/diary/339.jpg",
      "text":"Worked on the Rotonde specs.",
      "url":"http://xxiivv.com/index.htm",
      "data":
      {
        "topic": "Rotonde",
        "task": "Research",
        "focus":0.6,
        "sleep":0.6,
        "nutrition":0.7
      }
    }
  ],
  "portal":
  [
    "rotonde.cblgh.org",
    "rotonde.monochromatic.co",
    "brennan-ltkmn.hashbase.io",
    "rotonde.anxl.faith",
    "rotonde.electricgecko.de",
    "rotonde.attilam.com"
  ],
  "meta": {
    "version": "0.0.1",
    "canonical": "rotonde.xxiivv.com",
    "aliases": [
      "xxiivv.com/rotonde",
      "162.243.128.238",
      "oldrotonde.xxiivv.com"
    ],
    "options": [
      {
        "id": "Bradshaw/RotondeArchive",
        "spec": "https://github.com/Bradshaw/RotondeArchive",
        "data": {
          "path": "/archive/$page"
        }
      }
    ]
  }
}
```

### Profile
Profile information.
#### Name
Your display name.
#### Location
Current location.
#### Position
Current geoposition in decimal, not degree-hour.
#### Color
Hex value for display highlights.
#### Avatar*
A url to an image.
#### Glyph*
A single SVG path stroke data, created on a canvas of 300x300.

### Feed
Array of Entries, recommended limit of 30.
#### Time
Unixtime.
#### Media
Url to attached image, audio, video.
#### Text
Text content of the entry.
#### Url
Attached URL of the entry.
#### Position
The entry's geoposition in decimal, not degree-hour.

### Feed > Data
Feed data in the format of a string key, and a value, typically a float or a string.
#### Topic(Example) 
The entry's topic.
#### Task(Example) 
The topic's task type.
#### Focus(Example)
Float between 0 and 1, of the day's available time dedicated to task.
#### Nutrition(Example)
Float between 0 and 1, of the daily nutritional goal.
#### Sleep(Example)
Float between 0 and 1, of the daily sleep time goal.
#### Exercise(Example)
Float between 0 and 1, of the daily exercise goal.

### Portal
Array of subscribed rotonde instance urls, recommended limit of 30.

### Meta (Optional)
Information about the rotonde instance
#### Version
A [semver 2.0.0](semver.org) formatted string, describing the version of the Rotonde API being used.   
When omitted, the latest stable version is assumed
#### canonical
The canonical url of this rotonde instance. Clients should use this when sharing this instance and including in a Portal
#### aliases
Other urls which also serve this rotonde instance
#### Options
Array of optional modules this instance implements
##### Options > Id
The name of the optional feature
##### Options > Spec
Url to a human-readable spec for implementers
##### Options > Data
Free-form object containing any data the optional feature needs to work
