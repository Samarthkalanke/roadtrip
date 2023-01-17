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
        const password_length = 12;
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