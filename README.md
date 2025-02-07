# Weather App ☀️

## Description 
This Weather App allows users to check real-time weather conditions for any city in the world. It uses the OpenWeatherMap API to fetch and display weather information, including temperature, humidity, wind speed, and an appropriate weather icon.

## Features 
- 📊 Search for current weather information by city name.
- ☀️ Display temperature, humidity, wind speed, and weather conditions.
- ⚠️ Error handling for invalid city names.
- 🌍 Real-time weather icons for different weather conditions (clouds, clear, rain, snow, etc.).
- ⏳ Enter key press to trigger search for weather.

## Demo 
Link - https://harjotrocks.com/javascript/weather-app/

## Technologies Used 
- **🔄 HTML**: Markup structure of the app.
- **🔢 CSS**: Styling and layout design.
- **🔧 JavaScript**: Logic and API integration.
- **🌐 OpenWeatherMap API**: Fetching real-time weather data.

## How to Use 
1. 💾 Clone the repository or download the project files.
2. 💻 Open `index.html` in a web browser.
3. 🔍 Enter a city name in the search bar.
4. ⏭ Click the **Search** button or press the **Enter** key.
5. ☁️ View the weather details for the entered city.

## Code Explanation 
### 🔄 HTML 
- Contains input fields for city search and displays weather information.
- Displays error messages when a user enters an invalid city name.

### 🔢 CSS 
- Styles the weather card layout.
- Aligns weather information and icons for better user experience.

### 🔧 JavaScript 
- Fetches weather data from OpenWeatherMap API using the city name.
- Handles API responses to display relevant weather information.
- Dynamically updates the UI with temperature, humidity, and weather icons.
- Error handling to manage invalid city searches.

#### Key Functions:
- **checkWeather(city)**: Fetches and displays weather data for a given city.
- **Event Listeners**:
  - Click event on search button to fetch data.
  - Key press event for **Enter** key to initiate search.

### Sample Code
```javascript
const apiKey = "your-api-key-here";
const apiUrl = "https://api.openweathermap.org/data/2.5/weather?units=metric&q=";

async function checkWeather(city) {
    const response = await fetch(apiUrl + city + `&appid=${apiKey}`);
    if (response.status == 404) {
        document.querySelector(".error").style.display = "block";
        document.querySelector(".weather").style.display = "none";
    } else {
        var data = await response.json();
        document.querySelector(".city").innerHTML = data.name;
        document.querySelector(".temp").innerHTML = Math.round(data.main.temp) + "°C";
        document.querySelector(".humidity").innerHTML = data.main.humidity + "%";
        document.querySelector(".wind").innerHTML = data.wind.speed + " km/h";
    }
}
```

## Improvements 
- 🌐 Add support for location-based weather.
- 🔐 Implement a secure way to hide API keys.
- 🔧 Improve UI/UX with animations and enhanced error messages.
- ⏳ Show weather forecasts for multiple days.
