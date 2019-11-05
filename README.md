# Project 1 - National Park Search

    - Group Project

### Technologies Used

- HTML
- CSS
- Javascript
- JS

### API

- [National Parks API](https://www.nps.gov/subjects/developer/api-documentation.htm)

- [Open Weather MAP](https://openweathermap.org/api)

### Problems During Project Implementation

- Sliding down only one option at a time (Solution: Javascript code using Jquery which handled it)

```
// code example

$(".card_content")
    .not($(this)
    .next())
    .slideUp("slow");
 $(this).next()
    .slideToggle("slow");
```

- We decided to display weather for parks but coordinates format that parks had and coordinates that weather map api supports were different (Solution: Using javascript string and array logic we were able to get the format we wanted)

    ```
    //code example

    var lat = availableCoordinates.slice(
      0,
      availableCoordinates.lastIndexOf(",")
    );
    var splitLat = lat.substring(
      lat.lastIndexOf(":") + 1,
      lat.lastIndexOf(".")
    );
    console.log("lat = " + splitLat);
    var long = availableCoordinates.slice(
      availableCoordinates.lastIndexOf(",") + 1
    );
    var splitLong = long.substring(
      long.lastIndexOf(":") + 1,
      long.lastIndexOf(".")
    );
    console.log("long = " + splitLong);

    //weather query url
    var weatherQueryUrl =
      "https://api.openweathermap.org/data/2.5/weather?lat=" +
      splitLat +
      "&lon=" +
      splitLong +
      "&appid=" +
      weatherApiKey;
    ```

- Setting up favorite buttons and make it working without repeating or having any possible bugs (Solution: Using javascript arrays - I could write a code that made it possible)