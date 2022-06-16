## Library Name: 
**Smart Watch One**
## Library Version:
**1.0.0**

## Library Release Date:
03-06-2022

## Library Overview (Description):
 Watch Design for fetching Date & Weather 

## GitHub link:

## Screenshot of the Library:

![Watch_Design_One](https://user-images.githubusercontent.com/72146802/170127385-8829af76-6be5-41bb-bc7c-73337749f0d5.png)


## Library Feature1:
 Fetching Date
## Description:
 It is an API key which fetchs real-time Date, Day. 
## Code Snippet:

       fetchDate: function () {
        const date = new Date();
        this.date_d = (String(date.getDate()))
        this.date_m = (String(date.getMonth() + 1))
        const dayOfWeek = (date.getDay())
        const month = (date.getMonth())

        var days = ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];
        this.date_w = days[dayOfWeek];

        var months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
        this.date_m = months[month];
    }

## Screenshot:
![image](https://user-images.githubusercontent.com/72146802/171700215-ab0208ff-c617-47cb-9390-321497cbe7c8.png)


## Library Feature2:
Weather API
## Description:
API Key which gives the user real-time weather for a particular location.
## Code Snippet:
       fetchWeather: function () {
        var dataw = JSON.stringify(item);
        let weather_api_input = JSON.parse(dataw);
        let data;
        fetch.fetch({
            url: "https://api.openweathermap.org/data/2.5/weather?lat=" + weather_api_input[0].latitude + "&lon=" + weather_api_input[0].longitude + "&appid=" + weather_api_input[0].api_key,
            responseType: "json",
            method: 'GET',
            success: function (resp) {
                data = JSON.stringify(resp);
                console.info('Weather data fetch success. Resp: ' + data);
            },
            fail: function (data, code) {
                console.log("fail data: " + JSON.stringify(data) + " fail code: " + code);
            },
            complete: () => {
                const { main } = data.weather[0];
                this.weather = main;
                this.weather_description = main;
            }
        })
    }

## Screenshot:

![image](https://user-images.githubusercontent.com/72146802/171700797-544e7405-81e0-4056-913e-6fc95b55e211.png)


## Advanced feature that could be implemented in Future in this library:
Features like Sliding bar which can calculate Calories-Burned, Heart Rate, Blood Oxygen Levels, Amount of Food Intake.

## Conclusion:
Smart Watch One can be used to get real-time weather, date and day.

## Code Contribution
If you find any problems during usage, you can submit an Issue to us. Of course, we also welcome you to send us PR.

## Open source License
This project is based on Apache License 2.0 ，please enjoy and participate in open source freely
