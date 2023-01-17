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
    color: #fff;
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
<h1>Countdown Clock</h1>
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
  
var deadline = new Date("feb 14, 2023 18:59:45").getTime();
  
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

# Basic Information and Route

![](images/columbus.jpg)

We will be taking a road trip up to Columbus, Ohio. The trip will take 4 days.

### Route
![](images/route.jpg)

We plan on going through the midwest, making many stops and exploring new territory, and having a lot of fun! We will go on multiple interstate highways, including I-15, I-70, I-76, I-80, and finally I-74 into Columbus

## Schedule

| Day | Plan |
| --- | --- |
| Monday | We will eat breakfast and lunch at home, leaving mid-afternoon as we begin our drive and spend the night in Vegas |
| Tuesday | We will maybe sleep in after a late and eventful night in Vegas and continue our trip, driving through most of day, and plan to spend the night somewhere in the mountains of Colorado, enjoying the scenery |
| Wednesday | We will make our way out of the rockies and into the midwest as we traverse through Nebraska and Iowa, enjoying the culture. We will stop in Omaha or Des Moines, depending on circumstances such as time and our current mood. |
| Thursday | We will continue the homestretch into Columbus enjoying the culture of beloved Ohio. Possible activities include attending a basketball game at The Ohio State University, gun range, doing other random fun stuff. We will then ditch the RV and sneak on a plane back home. |

# Sign up to come along on the Trip

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