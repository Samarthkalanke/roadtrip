

<form action="javascript:login_user()">
    <p><label>
        User ID:
        <input type="text" name="uid" id="uid" required>
    </label></p>
    <p><label>
        Password:
        <input type="password" name="password" id="password" required>
    </label></p>
    <p><button>Login</button></p>
    <p id="message"></p>
</form>

<script>
    // URL for deployment
    var url = "https://flask.nighthawkcodingsociety.com"
    // Comment out next line for local testing
    //url = "http://localhost:8086"
    // Authenticate endpoint
    const login_url = url + '/api/users/authenticate';


    function login_user(){
        // Set body to include login data
        const body = {
            uid: document.getElementById("uid").value,
            password: document.getElementById("password").value,
        };

        // Set Headers to support cross origin
        const requestOptions = {
            method: 'POST',
            mode: 'cors', // no-cors, *cors, same-origin
            cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
            // credentials: 'include', // include, *same-origin, omit
            body: JSON.stringify(body),
            headers: {
                "content-type": "application/json",
            },
        };

        // Fetch JWT
        fetch(login_url, requestOptions)
        .then(response => {
            // trap error response from Web API
            if (response.status !== 200) {
                const message = 'Login error: ' + response.status + " " + response.statusText;
                document.getElementById("message").innerHTML = message;
                localStorage.removeItem("uid");
                localStorage.removeItem("visitor");
                return;
            }
            // Valid response will contain json data
            response.json().then(data => {
                const message = 'Login success: ' + data.name;
                document.getElementById("message").innerHTML = message;
                localStorage.setItem("uid", data.uid);
                localStorage.setItem("visitor", data.name);
            })
        })
    }


</script>