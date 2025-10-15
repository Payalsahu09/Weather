☀️ Simple Weather App

A simple and responsive Weather Application built using HTML, CSS, and JavaScript.
It allows users to search for any city and instantly get real-time weather information such as temperature, humidity, and weather conditions, using the OpenWeatherMap API.

✨ Features

✅ Get real-time weather data for any city 🌎
✅ Displays temperature, weather condition, humidity, and wind speed 🌤️
✅ Responsive and mobile-friendly UI 📱
✅ Uses OpenWeatherMap API for accurate data 🌡️
✅ Displays weather icons dynamically ☁️
✅ Simple, clean, and beginner-friendly code 🧩

🧩 Tech Stack

HTML5 — Structure of the web page

CSS3 — Styling and layout

JavaScript (ES6) — Fetching and displaying weather data dynamically

OpenWeatherMap API — Source of live weather data

🚀 Getting Started
1️⃣ Clone the repository
git clone https://github.com/Payalsahu09/Weather.git
cd weather-app

2️⃣ Open in your browser

Simply open the index.html file in your preferred browser.
No additional installation required!

🔑 Get Your API Key

This app uses the OpenWeatherMap API to fetch live weather data.

Go to OpenWeatherMap

Sign up for a free account

Generate your API Key

Replace the YOUR_API_KEY placeholder in your JavaScript file with your actual key:

const apiKey = "YOUR_API_KEY";

💻 Example Code (Main Script)
const apiKey = "YOUR_API_KEY";
const searchBox = document.querySelector(".search input");
const searchBtn = document.querySelector(".search button");
const weatherIcon = document.querySelector(".weather-icon");

async function checkWeather(city) {
  const response = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${apiKey}`
  );

  if (response.status === 404) {
    document.querySelector(".error").style.display = "block";
    document.querySelector(".weather").style.display = "none";
  } else {
    const data = await response.json();

    document.querySelector(".city").innerHTML = data.name;
    document.querySelector(".temp").innerHTML = Math.round(data.main.temp) + "°C";
    document.querySelector(".humidity").innerHTML = data.main.humidity + "%";
    document.querySelector(".wind").innerHTML = data.wind.speed + " km/h";

    // Change icon based on weather
    if (data.weather[0].main === "Clouds") {
      weatherIcon.src = "images/clouds.png";
    } else if (data.weather[0].main === "Clear") {
      weatherIcon.src = "images/clear.png";
    } else if (data.weather[0].main === "Rain") {
      weatherIcon.src = "images/rain.png";
    } else if (data.weather[0].main === "Drizzle") {
      weatherIcon.src = "images/drizzle.png";
    } else if (data.weather[0].main === "Mist") {
      weatherIcon.src = "images/mist.png";
    }

    document.querySelector(".weather").style.display = "block";
    document.querySelector(".error").style.display = "none";
  }
}

searchBtn.addEventListener("click", () => {
  checkWeather(searchBox.value);
});

📁 Folder Structure
weather-app/
│
├── index.html          # Main HTML file
├── style.css           # Styling for the app
├── script.js           # JavaScript logic
└── /images/            # Weather icons (clouds, clear, rain, etc.)

🌦️ Example Output

Search: “New York”

Displays:

City: New York  
Temperature: 18°C  
Humidity: 73%  
Wind Speed: 4.6 km/h  
Weather: Cloudy ☁️  

🎨 UI Preview

💡 Future Enhancements

🗺️ Add auto-location detection using Geolocation API

🕐 Show 5-day forecast

🌙 Add dark/light theme toggle

🔔 Add error messages for invalid inputs or network issues

🧾 License

This project is licensed under the MIT License — feel free to use, modify, and share.
