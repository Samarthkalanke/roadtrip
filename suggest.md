# Suggest an Activity
Name: <input type="text" name="name" id="name">
Activity: <input type="text" name="name" id="activity">
Description: <input type="text" name="name" id="description">
<button id="button">Enter</button>
<table>
    <tr>
        <th>Name</th>
        <th>Activity</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><script>document.querySelector("button").onclick = function displayName() {
        document.getElementById("name").InnerHTML = name}</script></td>
        <td><script>document.querySelector("button").onclick = function displayActivity() {
        document.getElementById("activity").InnerHTML = activity}</script></td>
        <td><script>document.querySelector("button").onclick = function displayDescription() {
        document.getElementById("description").InnerHTML = description}</script></td>
</table>