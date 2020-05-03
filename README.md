Represents the weather forecast for one day.

| Element | Description | Type | Notes |
|---- | --- | --- | --- |
| date | Date of the forecast | string | Format is YYYY-MM-DD |
| description | Text description of the weather | string | Valid values: sunny, overcast, partly cloudy, raining, and snowing |
| maxTemp | High temperature | number | In degrees Celsius |
| minTemp | Low temperature | number | In degrees Celsius |
| windSpeed | Wind speed | number | In kilometers per hour |
| danger | true if the weather conditions are dangerous; otherwise, false. | Boolean | |
```json
{
  "date": "2015-09-01",
  "description": "sunny",
  "maxTemp": 22,
  "minTemp": 20,
  "windSpeed": 12,
  "danger": false
}
```

Represents the weather forecast for multiple days.

| Element | Description | Type | Notes |
| --- | --- | --- | --- |
| longitude | Longitude of the location where the forecast takes place | number |  |
| latitude | Latitude of the location where the forecast takes place | number |  |
| forecast | Daily forecast | array of daily forecast objects |  |
| &nbsp; &nbsp; date | Date of the forecast | string | Format is YYYY-MM-DD|
| &nbsp; &nbsp; description | Text description of the weather | string | Valid values: sunny, overcast, partly cloudy, raining, and snowing |
| &nbsp; &nbsp; maxTemp | High temperature | number | In degrees Celsius |
| &nbsp; &nbsp; minTemp | Low temperature | number | In degrees Celsius |
| &nbsp; &nbsp; windSpeed | Wind speed | number | In kilometers per hour |
| &nbsp; &nbsp; danger | true if the weather conditions are dangerous; otherwise, false. | Boolean | |
```json
{
  "longitude": 47.60,
  "latitude": 122.33,
  "forecasts": [
    {
      "date": "2015-09-01",
      "description": "sunny",
      "maxTemp": 22,
      "minTemp": 20,
      "windSpeed": 12,
      "danger": false
    },
    {
      "date": "2015-09-02",
      "description": "overcast",
      "maxTemp": 21,
      "minTemp": 17,
      "windSpeed": 15,
      "danger": false
    },
    {
      "date": "2015-09-03",
      "description": "raining",
      "maxTemp": 20,
      "minTemp": 18,
      "windSpeed": 13,
      "danger": false
    }
  ]
}
```

Represents a request for a meeting in a calendar.

| Element | Description | Type | Required | Notes |
|---- | --- | --- | --- | --- |
| meeting | Top level | meeting data object | Required | |
| &nbsp; &nbsp; time | When meeting starts.  | string | Required | Format is YYYY-MM-DD HH:MM:SS. Timezone is GMT. |
| &nbsp; &nbsp; duration | How long meeting lasts | number | Required | In minutes |
| &nbsp; &nbsp; description | Description of the meeting | string | Required | |
| &nbsp; &nbsp; location | Location of the meeting | number | Optional | Default is an empty string |
| &nbsp; &nbsp; reminder | How many minutes before the meeting a reminder event should take place | number | Optional | Default is 10 minutes |
| &nbsp; &nbsp; invitees | List of email address of people to invite to the meeting | array of string | Optional | The strings should be valid email addresses. Default is an empty array. |

```json
{
  "meeting" : {
    "time": "2015-09-01 10:00",
    "duration": 60,
    "description": "2016 Strategic Planning Meeting",
    "location": "Building 23, Room 206",
    "reminder": 15,
    "invitees": ["michael@example.com", "thelma@example.com",
      "david@example.com", "leon@example.com"]
  }
}
```


