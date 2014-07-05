Template Strings
---
```
       var buildFlightUrl = function({flightType,departure }) {
          
                  return `http://flights.com/${flightType}/date/${departure}`
          
              }
          
       console.log(buildFlightUrl({flightType:'roundTrip', departure: '2014-07-16'}));
       //http://flights.com/roundTrip/date/2014-07-16 
```