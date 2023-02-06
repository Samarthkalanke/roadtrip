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
    <meta charset="UTF-8">
    <style>
      .cars {
        display: flex;
        flex-wrap: wrap;
      }
      .car {
        width: calc(33.33% - 20px);
        margin: 10px;
        text-align: center;
      }
    </style>
    <title>Car Rental Service</title>
  </head>
  <body>
    <h1>Car Rental Service</h1>
    <div class="cars">
      <!-- List of cars will be inserted here using JavaScript -->
    </div>
    <script>
      // Array of 10 cars
      const cars = [
        { name: "Toyota Camry", image: "toyatacamry.jpg" },
        { name: "Honda Civic", image: "civic.jpg" },
        { name: "Chevy Impala", image: "chevy.jpg" },
        { name: "Ford Mustang", image: "ford.jpg" },
        { name: "Nissan Altima", image: "nissan.jpg" },
        { name: "Tesla Model S", image: "tesla.jpg" },
        { name: "BMW 5 Series", image: "bmw.jpg" },
        { name: "Audi A6", image: "audi.jpg" },
        { name: "Mercedes-Benz E-Class", image: "e class.jpg" },
        { name: "Jaguar XF", image: "jag.jpg" }
      ];
      
      // Get the car list element
      const carList = document.querySelector(".cars");
      
      // Loop through the cars array
      for (const car of cars) {
        // Create a new element for each car
        const item = document.createElement("div");
        item.classList.add("car");
        item.innerHTML = `
          <h2>${car.name}</h2>
          <img src="${car.image}" alt="${car.name}" width="100%">
        `;
        
        // Append the car element to the car list
        carList.appendChild(item);
      }
    </script>
  </body>
</html>