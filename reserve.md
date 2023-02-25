![](/images/car.gif)

# Reserve a Car
Name: <input type="text" name="name" id="names"> <br><br>
Car: <input type="text" name="activity" id="activity"> <br><br>
License Plate: <input type="text" name="description" id="license"> <br><br>
Dates Using: <input type="text" name="description" id="description"><br><br>
Where are you going:<input type="text" name="going" id="going"><br><br>
<html>
<head>
<script>
    window.googleDocCallback = function () { return true; };
      function loadCars() {
        document.getElementById('table').innerHTML = 'Loading...';
        const options = { 
          method: 'GET', 
          headers: { 
            'x-rapidapi-host': 'car-data.p.rapidapi.com', 
            'x-rapidapi-key':'31c2c9240dmshb093261393c2f95p1ac6bajsn3bf7b947282a' 
          } 
        };
        fetch('https://car-data.p.rapidapi.com/cars?limit=10&page=0', options)
          .then(res => {
            if (!res.ok) {
              throw new Error('Failed to fetch data');
            }
            return res.json();
          })
          .then(data => {
            let output = '<table><tr><th>Make</th><th>Model</th><th>Year</th></tr>';
            for (let i = 0; i < 10; i++) {
              output += '<tr>' +
                '<td>' + data[i].make + '</td>' +
                '<td>' + data[i].model + '</td>' +
                '<td>' + data[i].year + '</td>' +
                '</tr>';
            }
            output += '</table>';
            document.getElementById('table').innerHTML = output;
          })
          .catch(error => {
            document.getElementById('table').innerHTML = 'Error: ' + error.message;
          });
    }
    function GetSheets(){
    let SHEET_ID = '16dzb_zqTXIXj4QQSZSCthwOaVbIypr1FfPpV58N6VcI'
    let SHEET_TITLE = 'Sheet1'
    let SHEET_RANGE = 'A1:D11'
    let FULL_URL = ('https://docs.google.com/spreadsheets/d/' + SHEET_ID + '/gviz/tq?sheet=' + SHEET_TITLE + '&range=' + SHEET_RANGE);
    fetch(FULL_URL)
    .then(response => response.text())
    .then(rep => {
        let data = JSON.parse(rep.substr(47).slice(0,-2));
        let Car_name_title = document.getELementByID('Car_name_title');
        let Liscense_Plate_title = document.getElementByID('Liscense_Plate_title');
        let Person_Reserve_title = document.getElementByID('Person_Reserve_title');
        let Date_Reserve_title = document.getElementByID('Date_Reserve_title');
        let Car_avaliablity_title = document.getElementByID('Car_avaliablity_title');
        let City_title = document.getElementByID('City_title');
        let Carsdetails = document.getElementByID('Carsdetails');
        let length = data.table.rows.lenght-1;
        Car_name_title.innerHTML = data.table.rows[0].c[0].v;
        Liscense_Plate_title.innerHTML = data.table.rows[0].c[1].v;
        Person_Reserve_title.innerHTML = data.table.rows[0].c[2].v;
        Date_Reserve_title.innerHTML = data.table.rows[0].c[3].v;
        Car_avaliablity_title.innerHTML = data.table.rows[0].c[4].v;
        City_title.innerHTML = data.table.rows[0].c[5].v;
        for(let i = 1;i<length;i++){
            let NewBoxCar = document.createElement('div');
            NewBoxCar.id = ("box"+i);
            NewBoxCar.className = "Some_Style";
            Car_name.append(NewBoxCar);
            NewBoxCar.innerHTML = data.table.rows[i].c[0].v;
            let NewBoxLisc = document.createElement('div');
            NewBoxLisc.id = ("box"+i);
            NewBoxLisc.className = "Some_Style";
            Liscense_Plate.append(NewBoxLisc);
            NewBoxLisc.innerHTML = data.table.rows[i].c[1].v;
            let NewBoxPer = document.createElement('div');
            NewBoxPer.id = ("box"+i);
            NewBoxPer.className = "Some_Style";
            Person_Reserve.append(NewBoxPer);
            NewBoxPer.innerHTML = data.table.rows[i].c[2].v;
            let NewBoxDat = document.createElement('div');
            NewBoxDat.id = ("box"+i);
            NewBoxDat.className = "Some_Style";
            Date_Reserve.append(NewBoxDat);
            NewBoxDat.innerHTML = data.table.rows[i].c[3].v;
            let NewBoxAva = document.createElement('div');
            NewBoxAva.id = ("box"+i);
            NewBoxAva.className = "Some_Style";
            Car_avaliablity.append(NewBoxAva);
            NewBoxAva.innerHTML = data.table.rows[i].c[4].v;
            let NewBoxCity = document.createElement('div');
            NewBoxCity.id = ("box"+i);
            NewBoxCity.className = "Some_Style";
            City.append(NewBoxCity);
            NewBoxCity.innerHTML = data.table.rows[i].c[5].v;
        }
    }) 
    }
    function mydisplay() {
        console.log("comes in display");
        document.getElementById("nameDisplay").innerHTML = names.value;
        document.getElementById("activityDisplay").innerHTML = activity.value;
        document.getElementById("licDisplay").innerHTML = license.value;
        document.getElementById("descDisplay").innerHTML = description.value;
        document.getElementById("goinDisplay").innerHTML = going.value;
    }
    function carlists (){
        var cars = ["Honda Civic", "Honda Lamborghini", "Toyota", "Honda Odyssey", "Tesla Model S","Tesla Model X", "Tesla Model 3", "Tesla Model Y", "Porche", "Volkswagen"];
        var license_plates = ["7WFV926","NSC709","6LVA210","64758P2","CT2K3A","55827T","JSX8090","8EPJ872","5NLF823","7ZDU842"];
        var booked = [
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
            [-1,-1,-1,-1,-1],
        ];
    }
</script>
</head>

<body onload="loadCars(); GetSheets();">
    <div id="table"></div>

<form>

<div id="Carstitle">
    <div id="Car_name_title"></div>
    <div id="Liscense_Plate_title"></div>
    <div id="Person_Reserve_title"></div>
    <div id="Date_Reserve_title"></div>
    <div id="Car_avaliablity_title"></div>
    <div id="City_title"></div>
</div>

<div id="Carsdetails">
    <div id="Car_name"></div>
    <div id="Liscense_Plate"></div>
    <div id="Person_Reserve"></div>
    <div id="Date_Reserve"></div>
    <div id="Car_avaliablity"></div>
    <div id="City"></div>
</div>


<button onclick="mydisplay()">Reserve</button>


<table id="table2">
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
    </tr>
</table>

</body>
</html>