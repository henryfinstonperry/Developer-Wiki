# **Code Snippets**

## **Countdown Timer**

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Countdown Timer</title>
<style>
  #countdown {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  .countdown-item {
    text-align: center;
  }
</style>
</head>
<body>

<h1>Countdown Timer</h1>
<div id="countdown">
  <div id="days" class="countdown-item">
    <div id="days-number"></div>
    <div>Days</div>
  </div>
  <div id="hours" class="countdown-item">
    <div id="hours-number"></div>
    <div>Hours</div>
  </div>
  <div id="minutes" class="countdown-item">
    <div id="minutes-number"></div>
    <div>Minutes</div>
  </div>
  <div id="seconds" class="countdown-item">
    <div id="seconds-number"></div>
    <div>Seconds</div>
  </div>
</div>

<script>
// Set the date we're counting down to
var countDownDate = new Date("August 31, 2024 23:59:00").getTime();

// Update the countdown every 1 second
var x = setInterval(function() {

  // Get the current date and time
  var now = new Date().getTime();
    
  // Calculate the remaining time
  var distance = countDownDate - now;
    
  // Calculate days, hours, minutes, and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);
    
  // Display the countdown
  document.getElementById("days-number").innerHTML = days;
  document.getElementById("hours-number").innerHTML = hours;
  document.getElementById("minutes-number").innerHTML = minutes;
  document.getElementById("seconds-number").innerHTML = seconds;
    
  // If the countdown is over, display a message
  if (distance < 0) {
    clearInterval(x);
    document.getElementById("countdown").innerHTML = "EXPIRED";
  }
}, 1000);
</script>

</body>
</html>
```

## **Fundraising Thermometer**

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fundraising Thermometer</title>
<style>
  #thermometer-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px auto;
  }
  #thermometer {
    width: 400px;
    height: 100px;
    border: 2px solid black;
    position: relative;
    border-radius: 50px; /* Rounded corners */
    overflow: hidden; /* Hide overflow content */
  }
  #mercury {
    width: 0%;
    height: 100%;
    background-color: red;
    transition: width 0.5s ease;
    border-radius: 50px; /* Rounded corners */
  }
  #numbers {
    display: flex;
    justify-content: space-between;
    width: 400px;
    margin-top: 10px;
    font-size: 14px;
  }
</style>
</head>
<body>

<h1 style="text-align: center;">Fundraising Thermometer</h1>
<div id="thermometer-container">
  <div id="thermometer">
    <div id="mercury"></div>
  </div>
</div>
<div id="numbers">
  <div id="raised">$50,000</div>
  <div id="goal">$200,000</div>
</div>

<script>
// Set the fundraising goal
var goal = 200000;

// Function to update the thermometer
function updateThermometer(amountRaised) {
  var percentage = (amountRaised / goal) * 100;
  document.getElementById("mercury").style.width = percentage + "%";
}

// Example: simulate fundraising progress
var amountRaised = 50000; // Example amount raised
updateThermometer(amountRaised); // Update the thermometer

// You can call updateThermometer(amount) with the actual amount raised to update the thermometer dynamically.
</script>

</body>
</html>
```

## **Percentage of Time Passed** (for use with Thermometer)

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Percentage of Time Passed</title>
</head>
<body>

<h1>Percentage of Time Passed</h1>

<script>
// Set the target end date (August 31, 2024, 11:59 PM)
var endDate = new Date("August 31, 2024 23:59:00").getTime();

// Get the current date and time
var now = new Date().getTime();

// Calculate the difference in milliseconds between now and the end date
var timeDifference = endDate - now;

// Calculate the total time difference between the start and end dates (in milliseconds)
var totalDifference = endDate - new Date("January 1, 2024").getTime();

// Calculate the percentage of time passed
var percentagePassed = ((totalDifference - timeDifference) / totalDifference) * 100;

// Round the percentage to two decimal places
percentagePassed = Math.round(percentagePassed * 100) / 100;

// Display the percentage of time passed
console.log("Percentage of time passed: " + percentagePassed + "%");

// You can use the percentagePassed variable to display or use the percentage as needed.
</script>

</body>
</html>
```
