HTML (index.html)
<title>Current Date and Time</title>
<script src="script.js"></script>
CSS (style.css)
body { font-family: Arial, sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; background-color: #f4f4f4; text-align: center; }

#date-time { font-size: 32px; font-weight: bold; color: #333; }

#date { font-size: 24px; margin-bottom: 10px; }

#time { font-size: 48px; color: #333; }

JavaScript (script.js)
function updateDateTime() { const now = new Date();

// Get current time in HH:mm:ss format
const hours = String(now.getHours()).padStart(2, '0');
const minutes = String(now.getMinutes()).padStart(2, '0');
const seconds = String(now.getSeconds()).padStart(2, '0');
const currentTime = `${hours}:${minutes}:${seconds}`;

// Get current date and day
const daysOfWeek = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
const dayOfWeek = daysOfWeek[now.getDay()];
const date = now.toLocaleDateString(); // Format: MM/DD/YYYY

document.getElementById('date').textContent = `${dayOfWeek}, ${date}`;
document.getElementById('time').textContent = currentTime;
}

setInterval(updateDateTime, 1000);

updateDateTime();
