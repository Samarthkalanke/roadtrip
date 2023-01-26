# Reserve a Car
Name: <input type="text" name="name" id="names">
Car: <input type="text" name="activity" id="activity">
Dates Using: <input type="text" name="description" id="description">

<script>
    function display() {
        document.getElementById("nameDisplay").innerHTML = names.value;
        document.getElementById("activityDisplay").innerHTML = activity.value;
        document.getElementById("descDisplay").innerHTML = description.value;
    }
</script>

<button onclick="display()">Enter</button>
<table id="table">
    <tr>
        <th>Name</th>
        <th>Car</th>
        <th>Dates Using</th>
    </tr>
    <tr>
        <td id="nameDisplay"></td>
        <td id="activityDisplay"></td>
        <td id="descDisplay"></td>