# Our Vehicle

![](images/rv.Png)

We will be driving the Winnebago View, one of the best RVs the market has to offer. We felt this was the right choice for the trip based on the picture above, where we felt the need to experience the road trippin' experience for ourselves as we saw how much the people in the picture were enjoying it. As mentioned in the schedule, we plan on dumping the brand new vehicle into the Scioto River in Columbus before hijacking a plane back to San Diego.

## Additional Information
[From Winnebago's site](https://www.winnebago.com/models/product/motorhomes/class-c/view)

From Winnebago: "Showcasing boundless freedom combined with upscale comfort, the View® is designed to create memories that last lifetimes. With luxurious details and features throughout, the View’s industry-leading amenities promise an unparalleled Class C experience. And with the dependable diesel-powered Sprinter chassis, you can stay in control, even off-grid."

As you can see, this is the perfect vehicle for our trip. We can't wait to have the time of our lives with this vehicle every step of the way.

<html>
  <head>
    <script>
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
    </script>
  </head>
  <body onload="loadCars()">
    <div id="table"></div>
  </body>
</html>

