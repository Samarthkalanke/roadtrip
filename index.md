<html>
<head>
<style>
body{
    text-align: center;
  font-family: sans-serif;
  font-weight: 100;
}
h1{
  color: #396;
  font-weight: 100;
  font-size: 40px;
  margin: 40px 0px 20px;
}
 #clockdiv{
    font-family: sans-serif;
    color: #100f14;
    display: inline-block;
    font-weight: 100;
    text-align: center;
    font-size: 30px;
}
#clockdiv > div{
    padding: 10px;
    border-radius: 3px;
    display: inline-block;
}
#clockdiv div > span{
    padding: 15px;
    border-radius: 3px;
    display: inline-block;
}
smalltext{
    padding-top: 5px;
    font-size: 16px;
}
</style>
</head>
<body>
<h1>Countdown to Road Trip!!!</h1>
<div id="clockdiv">
  <div>
    <span class="days" id="day"></span>
    <div class="smalltext">Days</div>
  </div>
  <div>
    <span class="hours" id="hour"></span>
    <div class="smalltext">Hours</div>
  </div>
  <div>
    <span class="minutes" id="minute"></span>
    <div class="smalltext">Minutes</div>
  </div>
  <div>
    <span class="seconds" id="second"></span>
    <div class="smalltext">Seconds</div>
  </div>
</div>
  
<p id="demo"></p>
  
<script>
  
var deadline = new Date("feb 16, 2023 19:00:00").getTime();
  
var x = setInterval(function() {
  
var now = new Date().getTime();
var t = deadline - now;
var days = Math.floor(t / (1000 * 60 * 60 * 24));
var hours = Math.floor((t%(1000 * 60 * 60 * 24))/(1000 * 60 * 60));
var minutes = Math.floor((t % (1000 * 60 * 60)) / (1000 * 60));
var seconds = Math.floor((t % (1000 * 60)) / 1000);
document.getElementById("day").innerHTML =days ;
document.getElementById("hour").innerHTML =hours;
document.getElementById("minute").innerHTML = minutes; 
document.getElementById("second").innerHTML =seconds; 
if (t < 0) {
        clearInterval(x);
        document.getElementById("demo").innerHTML = "TIME UP";
        document.getElementById("day").innerHTML ='0';
        document.getElementById("hour").innerHTML ='0';
        document.getElementById("minute").innerHTML ='0' ; 
        document.getElementById("second").innerHTML = '0'; }
}, 1000);
</script>
</body>
</html>


<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      th, td {
        padding: 8px;
      }
    </style>
    <script>
      function loadCars() {
        document.getElementById('table').innerHTML = 'Loading...';
        const options = {
          method: 'GET',
          headers: {
            'x-rapidapi-host': 'car-data.p.rapidapi.com',
            'x-rapidapi-key':'31c2c9240dmshb093261393c2f95p1ac6bajsn3bf7b947282a'
          }
        };
        fetch('https://car-data.p.rapidapi.com/cars?limit=10&page=0', options)
          .then(res => {
            if (!res.ok) {
              throw new Error('Failed to fetch data');
            }
            return res.json();
          })
          .then(data => {
            let output = '<table><tr><th></th><th>Make</th><th>Model</th><th>Year</th></tr>';
            for (let i = 0; i < 10; i++) {
              output += '<tr>' +
                '<td><a href="/cars"><button>View Car</button></a></td>' +
                '<td>' + data[i].make + '</td>' +
                '<td>' + data[i].model + '</td>' +
                '<td>' + data[i].year + '</td>' +
                '</tr>';
            }
            output += '</table>';
            document.getElementById('table').innerHTML = output;
          })
          .catch(error => {
            document.getElementById('table').innerHTML = 'Error: ' + error.message;
          });
      }
    </script>
  </head>
  <body onload="loadCars()">
    <div id="table"></div>
  </body>
</html>
