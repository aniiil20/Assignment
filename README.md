# Assignment
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,   
 initial-scale=1.0">
  <title>Your Brand Name</title>   

  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    </header>
  <main>
    <section class="hero">
      <div class="weather-widget">
        </div>
    </section>
    </main>
  <footer>
    
    </footer>
  <script src="script.js"></script>
</body>
</html>
<div class="weather-widget">
  <h3>Weather in Bengaluru</h3>
  <p id="weather-description"></p>
  <p id="weather-temp"></p>
  <img id="weather-icon" src="" alt="Weather Icon">
</div>
const apiKey = "YOUR_API_KEY";
const location = "Bengaluru";

fetch(`https://api.openweathermap.org/data/2.5/weather?q=${location}&appid=${apiKey}`)
  .then(response => response.json())
  .then(data => {
    const weather = data.weather[0];   

    const temp = Math.floor(data.main.temp - 273.15); // Convert Kelvin to Celsius
    document.getElementById("weather-description").textContent = weather.description;
    document.getElementById("weather-temp").textContent = `${temp}°C`;
    document.getElementById("weather-icon").src = `http://openweathermap.org/img/wn/${weather.icon}@2x.png`;
  });
