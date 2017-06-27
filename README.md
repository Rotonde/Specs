# Specifications

This is a simplistic self hosted, editable, version-controlled, platform and programing language agnostic social media experiment and tool. The idea is to share a feed of daily activity logs and interactions, that's all. You can see [my feed](http://rotonde.xxiivv.com) as an example.

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
Percentage of the day's available time dedicated to task. Float in range [0f, 1f].
#### Media
Url to attached image, audio, video.
#### Ref
Url of distant rotonde instance, followed by unixtime.
#### Text
text content of the entry.
#### Url
Attached URL of the entry.
#### Position
The entry's geoposition in decimal, not degree-hour.

### Portal
Array of subscribed rotonde instance urls, recommended limit of 30.
