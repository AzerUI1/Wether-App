<h1 align="center">Learn Weather 🌤️💻</h1>
<p align="center">
  <img src="https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif" alt="Weather App Animation" width="400">
</p>

---

<h2>📌 Project Overview</h2>
<p>
This project is a **modern, ultra-beautiful single-page weather app** built with HTML, CSS, and JavaScript. 
It allows users to enter any city and instantly see **current weather, temperature, humidity, wind speed, and a weather icon**, with **glassmorphism design, gradient background, and animations**.
</p>

<p>Key features of this app include:</p>
<ul>
  <li>Real-time weather data using the <strong>OpenWeatherMap API</strong></li>
  <li>Responsive and interactive UI with animations</li>
  <li>Hover effects and fade-in animations for smooth experience</li>
  <li>Fully frontend — no backend required</li>
</ul>

---

<h2>🛠 Features</h2>
<ul>
  <li>✅ Glassmorphism weather card with blur and shadows</li>
  <li>✅ Gradient animated background with decorative circles</li>
  <li>✅ Input for city names and "Get Weather" button</li>
  <li>✅ Displays temperature, weather description, humidity, wind speed, and icon</li>
  <li>✅ Fade-in animation when page loads</li>
  <li>✅ Hover animations on card and button</li>
</ul>

---

<h2>📁 Project Structure</h2>
<pre>
Learn-Weather/
│
├─ index.html       # Main HTML file with structure, CSS, and JS
├─ weather.png      # App icon / screenshot
├─ .gitignore
├─ LICENSE
└─ README.md        # This file
</pre>

---

<h2>⚙️ How It Works</h2>
<p>The app follows a **basic frontend workflow**:</p>
<ol>
  <li>User enters a city name in the input box</li>
  <li>Clicking "Get Weather" triggers JavaScript function <code>getWeather()</code></li>
  <li>JS <code>fetch</code> sends a request to <strong>OpenWeatherMap API</strong></li>
  <li>API returns JSON data with temperature, humidity, wind, and weather info</li>
  <li>JS updates HTML elements dynamically to display weather data</li>
  <li>User sees the fully updated weather card instantly</li>
</ol>

<p>Example JavaScript snippet:</p>
<pre><code class="language-javascript">
const apiKey = 'YOUR_API_KEY';

function getWeather() {
  const city = document.getElementById('cityInput').value;
  if(!city) return alert('Please enter a city name');

  fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)
    .then(res => {
      if(!res.ok) throw new Error('City not found');
      return res.json();
    })
    .then(data => {
      document.getElementById('city').textContent = data.name + ', ' + data.sys.country;
      document.getElementById('temp').textContent = Math.round(data.main.temp) + '°C';
      document.getElementById('desc').textContent = data.weather[0].description;
      document.getElementById('humidity').textContent = 'Humidity: ' + data.main.humidity + '%';
      document.getElementById('wind').textContent = 'Wind: ' + data.wind.speed + ' m/s';
      document.getElementById('icon').src = `https://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`;
    })
    .catch(err => alert(err.message));
}
</code></pre>

---

<h2>💡 How HTML, CSS & JS Work Together</h2>
<ul>
  <li><strong>HTML:</strong> Provides the page structure and elements like input, button, and weather card</li>
  <li><strong>CSS:</strong> Styles the page with gradients, blur effects, animations, hover effects, and responsive layout</li>
  <li><strong>JavaScript:</strong> Handles user interaction, API calls, JSON parsing, and DOM updates</li>
</ul>

---

<h2>🌤️ How the API Works</h2>
<p>We use the <strong>OpenWeatherMap API</strong>:</p>
<ol>
  <li>JavaScript <code>fetch</code> sends a GET request:
    <pre><code>https://api.openweathermap.org/data/2.5/weather?q=CityName&appid=API_KEY&units=metric</code></pre>
  </li>
  <li>API returns JSON like:
<pre><code>{
  "main": { "temp": 28, "humidity": 70 },
  "weather": [{ "description": "clear sky", "icon": "01d" }],
  "wind": { "speed": 3.5 },
  "sys": { "country": "AZ" },
  "name": "Baku"
}</code></pre>
  </li>
  <li>JS parses JSON and updates HTML elements with dynamic content</li>
</ol>

---

<h2>📸 Screenshots & Demo</h2>
<p align="center">
  <img src="weather.png" alt="Weather App Screenshot" width="350">
</p>
<p align="center">
  <img src="https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif" alt="Weather App Animation" width="400">
</p>

---

<h2>🛠️ How to Run Locally</h2>
<ol>
  <li>Clone the repository:
    <pre><code>git clone https://github.com/AzerAslanov/Learn-Weather.git</code></pre>
  </li>
  <li>Open <code>index.html</code> in any modern browser</li>
  <li>Enter a city name and click **Get Weather**</li>
</ol>

---

<h2>📚 References</h2>
<ul>
  <li><a href="https://openweathermap.org/api">OpenWeatherMap API Documentation</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/HTML">HTML5 Documentation</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS">CSS3 Documentation</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript">JavaScript Documentation</a></li>
</ul>

---

<p align="center">Made with ❤️ and 🌤️ by Azer Aslanov</p>
