# Suggest an Activity
Name: <input type="text" name="name" id="names">
Activity: <input type="text" name="activity" id="activity">
Description: <input type="text" name="description" id="description">

<script>
    function display() {
        document.getElementById("names").value;
        document.getElementById("activity").value;
        document.getElementById("description").value;
        document.getElementById("nameDisplay").innerHTML = names.value;
        document.getElementById("activityDisplay").innerHTML = activity.value;
        document.getElementById("descDisplay").innerHTML = description.value;
    }
</script>

<button onclick="display()">Enter</button>
<table>
    <tr>
        <th>Name</th>
        <th>Activity</th>
        <th>Description</th>
    </tr>
    <tr>
        <td id="nameDisplay"></td>
        <td id="activityDisplay"></td>
        <td id="descDisplay"></td>