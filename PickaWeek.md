<div id="calendar">
  <div id="calendar-header">
    <button id="prev-month"><<</button>
    <h2 id="month-year"></h2>
    <button id="next-month">>></button>
  </div>
  <table>
    <thead>
      <tr>
        <th>Sun</th>
        <th>Mon</th>
        <th>Tue</th>
        <th>Wed</th>
        <th>Thu</th>
        <th>Fri</th>
        <th>Sat</th>
      </tr>
    </thead>
    <tbody id="calendar-body"></tbody>
  </table>
</div>

<script>
  // Get current date
  var date = new Date();
  var currentMonth = date.getMonth();
  var currentYear = date.getFullYear();

  // Get the first day of the month
  var firstDay = new Date(currentYear, currentMonth, 1);
  var startingDay = firstDay.getDay();

  // Get the number of days in the month
  var monthLength = new Date(currentYear, currentMonth + 1, 0).getDate();

  // Create the table body
  var calendarBody = document.getElementById("calendar-body");
  var row = document.createElement("tr");
  var day = 1;

  // Create the calendar
  for (var i = 0; i < 6; i++) {
    var row = document.createElement("tr");

    for (var j = 0; j < 7; j++) {
      if (i === 0 && j < startingDay) {
        var cell = document.createElement("td");
        var cellText = document.createTextNode("");
        cell.appendChild(cellText);
        row.appendChild(cell);
      } else if (day > monthLength) {
        break;
      } else {
        var cell = document.createElement("td");
        var cellText = document.createTextNode(day);
        if (day === date.getDate() && currentMonth === date.getMonth() && currentYear === date.getFullYear()) {
          cell.classList.add("current-day");
        }
        cell.appendChild(cellText);
        row.appendChild(cell);
        day++;
      }
    }

    calendarBody.appendChild(row);
  }

  // Display current month and year
  var monthYear = document.getElementById("month-year");
  var months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
  monthYear.innerHTML = months[currentMonth] + " " + currentYear;

  // Function to go to next month
  var nextMonth = document.getElementById("next-month");
  nextMonth.addEventListener("click", function() {
    currentYear = (currentMonth === 11) ? currentYear + 1 : currentYear;
    currentMonth = (currentMonth + 1) % 12;
    createCalendar(currentMonth
