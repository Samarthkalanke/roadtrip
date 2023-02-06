# Live Weather in Destinations
## Columbus
<script>
function fetchColumbus() {
    const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': '4abcb54450msh7468dfd72294e89p18fbaajsn6d4200063b39',
		'X-RapidAPI-Host': 'yahoo-weather5.p.rapidapi.com'
	}
    };

    fetch('https://yahoo-weather5.p.rapidapi.com/weather?location=Columbus&format=json&u=f', options)
	    .then(response => response.json())
	    .then(response => console.log(response))
	    .catch(err => console.error(err));

    document.getElementById("columbus_weather").innerHTML = response.condition
}
</script>

<button onclick="fetchColumbus()">Columbus Weather</button>
<p id="columbus_weather">