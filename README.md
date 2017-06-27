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
    "avatar":"http://wiki.xxiivv.com/public.oscean/media/brand/logo.devine.lu.linvega.png"
  },
  "feed":
  [
    {
      "time":"1497499200",
      "ref":"rotonde.monochromatic.co 1496203200",
      "text":"Nice work Ian!"
    },
    {
      "time":"1497326400",
      "media":"http://wiki.xxiivv.com/public.oscean/media/diary/339.jpg",
      "text":"Worked on the Rotonde specs.",
      "focus": 0.2,
      "url":"http://xxiivv.com/index.htm"
    }
  ],
  "portal":
  [
    "rotonde.cblgh.org",
    "rotonde.monochromatic.co",
    "rotonde.brennan.pizza/feed.json",
    "rotonde.anxl.faith",
    "rotonde.electricgecko.de",
    "rotonde.attilam.com"
  ]
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
#### Focus
Percentage of the day's available time dedicated to task. Float in range [0, 1].
#### Media
Url to attached image, audio, video.
#### Ref
Url of distant rotonde instance, followed by unixtime.
#### Text
Text content of the entry.
#### Url
Attached URL of the entry.
#### Position
The entry's geoposition in decimal, not degree-hour.

### Portal
Array of subscribed rotonde instance urls, recommended limit of 30.
