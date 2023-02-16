# Reserve a Car
Name: <input type="text" name="name" id="names">
Car: <input type="text" name="activity" id="activity">
License Plate: <input type="text" name="description" id="license">
Dates Using: <input type="text" name="description" id="description">
Where are you going:<input type="text" name="going" id="going">

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
        <th>License Plate</th>
        <th>Dates Using</th>
        <th>City</th>
    </tr>
    <tr>
        <td id="nameDisplay"></td>
        <td id="activityDisplay"></td>
        <td id="licDisplay"></td>
        <td id="descDisplay"></td>
        <td id="goinDisplay"></td>
