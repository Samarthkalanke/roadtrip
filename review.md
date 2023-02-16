# Rate your experience 
Name: <input type="text" name="name" id="names">
Car: <input type="text" name="activity" id="activity">
Write a review : <input type="text" name="write" id="license">
Stars: <input type="number" name="stars" id="stars">

<script>
    function display() {
        document.getElementById("nameDisplay").innerHTML = names.value;
        document.getElementById("activityDisplay").innerHTML = activity.value;
        document.getElementById("licDisplay").innerHTML = license.value;
        document.getElementById("descDisplay").innerHTML = description.value;
        document.getElementById("goinDisplay").innerHTML = going.value;
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

