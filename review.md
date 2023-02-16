# Rate your experience 
Name: <input type="text" name="name" id="names">
Car: <input type="text" name="activity" id="activity">
Write a review : <input type="text" name="write" id="license">


<script>
    function display() {
        document.getElementById("nameDisplay").innerHTML = names.value;
        document.getElementById("activityDisplay").innerHTML = activity.value;
        document.getElementById("licDisplay").innerHTML = license.value;
        document.getElementById("starDisplay").innerHTML = star.value
    }
</script>

<button onclick="display()">Enter</button>
<table id="table">
    <tr>
        <th>Name</th>
        <th>Car</th>
        <th>Write a review</th>
        <th>Stars/5</th>
    </tr>
    <tr>
        <td id="nameDisplay"></td>
        <td id="activityDisplay"></td>
        <td id="licDisplay"></td>
        <td id="starDisplay"></td>
    </tr>
</table>

# Rate out of 5 stars your overall experience 
<div class="rating">
  <input type="radio" id="star5" name="rating" value="5 stars" class="star">
  <label for="star5"></label>
  <input type="radio" id="star4" name="rating" value="4 stars" class="star">
  <label for="star4"></label>
  <input type="radio" id="star3" name="rating" value="3 stars" class="star">
  <label for="star3"></label>
  <input type="radio" id="star2" name="rating" value="2 stars" class="star">
  <label for="star2"></label>
  <input type="radio" id="star1" name="rating" value="1 star" class="star">
  <label for="star1"></label>
</div>


