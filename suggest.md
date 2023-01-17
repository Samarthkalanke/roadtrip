# Suggest an Activity
Name: <input type="text" name="name" id="name">
Activity: <input type="text" name="activity" id="activity">
Description: <input type="text" name="description" id="description">

<script>
    function display() {
        document.getElementById("nameDisplay").innerHTML = name
        document.getElementById("activityDisplay").innerHTML = activity
        document.getElementById("descDisplay").innerHTML = description
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
</table>