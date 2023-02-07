# Find a Car that's Right for You

<p>How many miles are planning on driving?</p>
<input type="radio" id="0-200" value="a1" name="q1">
<label for="0-200">0-200</label><br>
<input type="radio" id="200-400" value="a2" name="q1">
<label for="200-400">200-400</label><br>
<input type="radio" id="400-600" value="a3" name="q1">
<label for="400-600">400-600</label><br>
<input type="radio" id="600+" value="a4" name="q1">
<label for="600+">600+</label><br>

<p>How much money are you willing to pay per day?</p>
<input type="radio" id="0-20" value="a1" name="q2">
<label for="0-20">$0-20</label><br>
<input type="radio" id="20-50" value="a2" name="q2">
<label for="20-50">$20-50</label><br>
<input type="radio" id="50-80" value="a3" name="q2">
<label for="50-80">$50-80</label><br>
<input type="radio" id="80+" value="a4" name="q2">
<label for="80-100">$80+</label><br>

<p>How nice do you want your car to be?</p>
<input type="radio" id="decent" value="a1" name="q3">
<label for="decent">Decent Condition</label><br>
<input type="radio" id="premium" value="a2" name="q3">
<label for="premium">Premium</label><br>
<input type="radio" id="luxury" value="a3" name="q3">
<label for="luxury">Luxury</label><br>
<input type="radio" id="billionaire" value="a4" name="q3">
<label for="billionaire">Billionaire Status</label><br>

<script>
   function survey() {
    function calculateAnswers{
        var a1score = 0;
        var a2score = 0;
        var a3score = 0;
        var a4score = 0;

        var userAnswers = document.getElementsByType("radio");
        for (i=0; i<userAnswers.length; i++) {
        if (userAnswers[i].checked) {
            if (userAnswers[i].value) == "a1" {
                a1score = a1score + 1;
            }
            if (userAnswers[i].value) == "a2" {
                a2score = a2score + 1;
            }
            if (userAnswers[i].value) == "a3" {
                a3score = a3score + 1;
            }
            if (userAnswers[i].value) == "a4" {
                a4score = a4score + 1;
            }
       } 
      }
    }
   var maxScore = Math.max(a1score, a2score, a3score, a4score);
   var result = document.getElementById("result")
   if (a1score == maxScore) {
    result.innerHTML = "A1 Max test"
   }
   if (a2score == maxScore) {
    result.innerHTML = "A2 Max Test"
   }
   if (a3score == maxScore) {
    result.innerHTML = "A3 Max Test"
   }
   if (a4score == maxScore) {
    result.innerHTML = "A4 Max Test"
   }
}
</script>

<button onclick="survey()">Submit Answers</button>

<p id="result"></p>

# 2020 Honda Accord

![](images/honda.jpg)

<p><b>Price:</b> $35 per day</p>
<p><b>Gas Mileage:</b> 38 miles per gallon</p>

<button>Reserve</button>

## Review this car 

<input type="text"> /5 <textarea>