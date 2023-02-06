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

<style>
  table {
    width: 100%;
  }
  table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
    text-align: center;
    padding: 10px;
  }
  th {
    background-color: lightgray;
  }
  .carImage {
    width: 100px;
    height: 100px;
  }
</style>

<table id="rentalCars">
  <tr>
    <th>Car Name</th>
    <th>Make</th>
    <th>Model</th>
    <th>Year</th>
    <th>Image</th>
  </tr>
  <tr>
    <td>Car 1</td>
    <td>Toyota</td>
    <td>Camry</td>
    <td>2021</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 1 Image">
    </td>
  </tr>
  <tr>
    <td>Car 2</td>
    <td>Honda</td>
    <td>Accord</td>
    <td>2022</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 2 Image">
    </td>
  </tr>
  <tr>
    <td>Car 3</td>
    <td>Tesla</td>
    <td>Model 3</td>
    <td>2022</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 3 Image">
    </td>
  </tr>
  <tr>
    <td>Car 4</td>
    <td>Nissan</td>
    <td>Altima</td>
    <td>2021</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 4 Image">
    </td>
  </tr>
  <tr>
    <td>Car 5</td>
    <td>Ford</td>
    <td>Mustang</td>
    <td>2022</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 5 Image">
    </td>
  </tr>
  <tr>
    <td>Car 6</td>
    <td>Chevrolet</td>
    <td>Camaro</td>
    <td>2021</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 6 Image">
    </td>
  </tr>
  <tr>
    <td>Car 7</td>
    <td>BMW</td>
    <td>3 Series</td>
    <td>2022</td>
    <td>
      <img class="carImage" src="https://via.placeholder.com/100x100" alt="Car 6 Image">
    </td>


<html>
  <head>
    <meta charset="UTF-8">
    <title>Car Rental Service</title>
  </head>
  <body>
    <h1>Car Rental Service</h1>
    <ul id="car-list">
      <!-- List of cars will be inserted here using JavaScript -->
    </ul>
    <script>
      // Array of 10 cars
      const cars = [
        { name: "2023 Toyota Camry", image: "toyatacamry.jpg" },
        { name: "2023 Honda Civic", image: "civic.jpg" },
        { name: "2022 Chevrolet Impala", image: "chevy.jpg" },
        { name: "2023 Ford Mustang", image: "ford.jpg" },
        { name: "2022 Nissan Altima", image: "nissan.png" },
        { name: "2019 Tesla Model S", image: "tesla.jpg" },
        { name: "2023 BMW 5 Series", image: "bmw.jpg" },
        { name: "2023 Audi A6", image: "audi.jpg" },
        { name: "2020 Mercedes-Benz E-Class", image: "e class.jpg" },
        { name: "2022 Jaguar XF", image: "jag.jpg" }
      ];
      
      // Get the list element
      const carList = document.getElementById("car-list");
      
      // Loop through the cars array
      for (const car of cars) {
        // Create a new list item for each car
        const item = document.createElement("li");
        item.innerHTML = `
          <h2>${car.name}</h2>
          <img src="${car.image}" alt="${car.name}">
        `;
        
        // Append the list item to the car list
        carList.appendChild(item);
      }
    </script>
  </body>
</html>

<form action="create_User()">
    <p><label>
        Name:
        <input type="text" name="name" id="name" required>
    </label></p>
    <p><label>
        Password:
        <input type="password" name="password" id="password" required>
    </label></p>
    <p><label>
        Phone:
        <input type="tel" name="phone_num" id="phone_num"
            pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
            placeholder="858-111-0938">
    </label></p>
    <p><label>
        Email:
        <input type="email">   
    </label></p>
    <p>
        <button>Sign up</button>
    </p>
</form>

# Click here to Generate Password
<script>
    function generatePassword() {
        const password_length = 9;
        const characters = ["a", "b", "c", "d", "e", "1", "2", "3", "4", "5"];
        let password = "";

        for (let index = 0; index < password_length; index++) {
        password += characters[Math.floor(Math.random() * characters.length)];
        }
        document.getElementById("element").innerHTML = password
    }
</script>

<button onclick="generatePassword()">Generate Password</button>
<p id="element">