![](/images/TESK-1.png)

<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      th, td {
        padding: 8px;
      }
    </style>
    <script>
      function loadCars() {
        document.getElementById('table').innerHTML = 'Loading...';
        const options = {
          method: 'GET',
          headers: {
            'x-rapidapi-host': 'car-data.p.rapidapi.com',
            'x-rapidapi-key':'31c2c9240dmshb093261393c2f95p1ac6bajsn3bf7b947282a' // This is the api key pulling from backend notebook from rapid api
          }
        }; //This is the part where it fetchs data from api key above
        fetch('https://car-data.p.rapidapi.com/cars?limit=10&page=0', options)
          .then(res => {
            if (!res.ok) {
              throw new Error('Failed to fetch data');
            }
            return res.json();
          }) //these are the buttons for the reserve and find a car
          .then(data => {
            let output = '<table><tr><th>View Car</th><th>Make</th><th>Model</th><th>Year</th><th>Review Car</td></tr>';
            for (let i = 0; i < 10; i++) {
              output += '<tr>' +
                '<td><a href="/cars"><button>View Car</button></a></td>' +
                '<td>' + data[i].make + '</td>' +
                '<td>' + data[i].model + '</td>' +
                '<td>' + data[i].year + '</td>' +
                '<td><a href="/review"><button>Review Car</button></a></td>' +
                '</tr>'; // this is the making of the table and displays the api onto a table of rows and columns.
            }
            output += '</table>';
            document.getElementById('table').innerHTML = output;
          })
          .catch(error => {
            document.getElementById('table').innerHTML = 'Error: ' + error.message;
          });
      }
    </script>
  </head>
  <body onload="loadCars()">
    <div id="table"></div>
  </body>
</html>   
 
# Add a car

Name: <input type="text" name="name" id="names">

<script>
    function display() {
        document.getElementById("nameDisplay").innerHTML = names.value;
    }
</script> 

<button onclick="display()">Enter</button>

<table id="table">
    <tr>
        <th>Name</th>
    </tr>
    <tr>
        <td id="nameDisplay"></td>
    </tr>
</table>

