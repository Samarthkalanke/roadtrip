![](images/wafflehouse.jpeg)

## Planned Meals
> On the Road, we will have three meals a day and will be filled with nutrients and also some desserts. Each meal will have to be eaten by a certain time or they will be nonaviable anymore. 

### Monday Dinner
> Ceaser Salad, hamburgers with bacon ( condiments included ), Ice Cream Drumsticks for Dessert.
 
### Tuesday Breakfast (Anytime before 10am)
> Homemade waffles and pancakes with syrup ( chocolate chips too ) and side of bacon.

### Tuesday Lunch
> Make lunch at dinning room.  Pack and Go.  Eat outside or at your housing, pick up trash and leave no mess in dinning hall or grounds.

### Tuesday Dinner
> Ground beef hard shell Tacos with cheese, sourcream, and lettuce. Choice of rootbeer or Coke.

### Wednesday Breakfast (Anytime before 10am)
> Choice of eating Chick-Fila Breakfest or Waffle house.
### Wednesday Lunch
> Homemade Sandwhich's included with condiments or choice of eating at the truck stop and get some snacks.

### Wednesday Dinner
> Lobster served with rice and salmon and were eating in the RV. No messes please.

### Thursday Breakfast (Anytime Before 10am)
Your on Your own!!!
### Thursday Lunch
> We are getting KFC for lunch!!!!!!
### Thursday Dinner
> This is the last nght, we are going buffet style, make sure to clean up after yourself, Person with most food eaten wins 20$, Good luck.


<html>
<body>

<h2>Find Closest Food Choices from the trip</h2>

<input type="button" onclick="alert('closest waffle house is 5 Hours and 4 Minutes or 352 Miles away')" value="Waffle house">

</body>
</html>


<html>
<body>

<h2></h2>

<input type="button" onclick="alert('closest KFC is 13 Minutes or 5.3 Miles away')" value="KFC">

</body>
</html>

<html>
<body>

<h2></h2>

<input type="button" onclick="alert('closest Chick-Fil-A is 4 Minutes or 0.6 Miles away')" value="Chick-Fil-A">

</body>
</html>


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