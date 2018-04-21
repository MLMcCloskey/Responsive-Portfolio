
$(document).ready(function() {
  //enable GetWeather button if disabled//
  var Geo={};
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(success,error);
    }
    else {
      alert('Geolocation is not available');
    }

    function error() {
      alert("Sorry you couldn't be located");
    }

    function success(position){
      Geo_lat = position.coords.latitude;
      Geo_lon = position.coords.longitude;
      console.log(Geo_lat,Geo_lon);
      $("#homeButtons").on("click", "#weatherBtn", getData)

  // $("#weatherBtn").attr("enabled", true);
  // //location tracking for local weather//
  // if (google.loader.ClientLocation)
  // {
  //   Geo_lat = google.loader.ClientLocation.latitude;
  //   Geo_lon = google.loader.ClientLocation.longitude;
  //   //   //onclick run getData function to make AJAX WeatherAPI calls//
  //   $("#GetWeather").on("click", getData)

  // }
  // else {
  //   alert('Geolocation is not available');
  // }
  
  // Run getData function to make ajax call
  function getData() {
    // $("#weatherBtn").attr("disabled", true);

    $("#homeButtons").empty();
    $("#homeButtons").prepend(homeBtn+"<br>");

    $.ajax({
      url: "http://api.wunderground.com/api/2c13cbda3d02efb1/forecast7day/geolookup/conditions/q/"+ Geo_lat + "," + Geo_lon +".json",
      dataType: "jsonp",
      success: function (parsed_json) {
        var location = parsed_json['current_observation']['observation_location']['city'];
        var loc_html = ("Location:  " + location)
        // Make location box visible
        $("#homeButtons").append(loc_html).css("opacity", "1")

        // create table head
        $(".table").prepend("<thead><tr><th>Day</th><th>Temperature</th><th>Weather</th><th>Wind speed</th><th>Humidity</th></tr></thead>");

        // Get current weather and 3 day weather forecast
        for (i=0; i<=3; i++) {
          var fcast_day = parsed_json['forecast']['simpleforecast']['forecastday'][i]['date']['weekday_short'];
          var fcast_hi = parsed_json['forecast']['simpleforecast']['forecastday'][i]['high']['fahrenheit'];
          var fcast_con = parsed_json['forecast']['simpleforecast']['forecastday'][i]['conditions'];
          var fcast_wnd = parsed_json['forecast']['simpleforecast']['forecastday'][i]['avewind']['mph'];
          var fcast_hum = parsed_json['forecast']['simpleforecast']['forecastday'][i]['avehumidity'];
          console.log(fcast_day,fcast_hi,fcast_con,fcast_wnd,fcast_hum);
          // Get reference to existing tbody element, create a new table row element
          var tBody = $("tbody");
          var tRow = $("<tr>");
          // Methods run on jQuery selectors return the selector they we run on
          // This is why we can create and save a reference to a td in the same statement we update its text
          var fcast_dayTd = $("<td>").text(fcast_day);
          var fcast_hiTd = $("<td>").text(fcast_hi +"°F");
          var fcast_conTd = $("<td>").text(fcast_con);
          var fcast_wndTd = $("<td>").text(fcast_wnd +" mph");
          var fcast_humTd = $("<td>").text(fcast_hum +"%");

          // Append the newly created table data to the table row
          tRow.append(fcast_dayTd, fcast_hiTd, fcast_conTd, fcast_wndTd, fcast_humTd);
          // Append the table row to the table body
          tBody.append(tRow);
          // if (fcast_conTd 
          // switch (expr) {
          //  case 'Thunderstorm':
          //  $(this).append("assets/images/if_flash-cloud.png");
          //   break;
          //   case 'clear':
          //   $(this)
          // }
          // }
          $("#table td:nth-child(5)").each(function () {
        if (parseInt($(this).text()) > 50) {
            $(this).parent("tr").css("background-color", "yellow");
        }
    });
        }

      }
    });
  }
}
});
