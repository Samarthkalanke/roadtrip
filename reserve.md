![](/images/car.gif)

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
<<<<<<< HEAD:suggest.md
        document.getElementById("goinDisplay").innerHTML = description.value;
    }
    const url

    function carlists{

        var cars = ["Honda Civic", "Honda Lamborghini", "Toyota", "Honda Odyssey", "Tesla Model S","Tesla Model X", "Tesla Model 3", "Tesla Model Y", "Porche", "Volkswagen"];

        var license_plates = ["7WFV926","NSC709","6LVA210","64758P2","CT2K3A","55827T","JSX8090","8EPJ872","5NLF823","7ZDU842"];

        var booked = [
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
            [-1,-1,-1,-1,-1];
        ];

<<form>

    <input type="car">
    <input type="license plate">

</form>>

<button type="button">Book a Reservation!</button>

=======
        document.getElementById("goinDisplay").innerHTML = going.value;
>>>>>>> af4ba1404285654925411d0da7b9ea3121d78289:reserve.md
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
