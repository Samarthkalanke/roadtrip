<script>
// Get the current year
var currentYear = new Date().getFullYear();

// Create the table element
var calendar = document.createElement("table");
calendar.id = 'calendar';

// Create the header row
var headerRow = document.createElement("tr");

// Create the header cells
var headerCells = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
for (var i = 0; i < headerCells.length; i++) {
  var headerCell = document.createElement("th");
  headerCell.innerHTML = headerCells[i];
  headerRow.appendChild(headerCell);
}

// Add the header row to the table
calendar.appendChild(headerRow);

// Create the calendar rows
for (var month = 0; month < 12; month++) {
  var firstDay = new Date(currentYear, month, 1);
  var daysInMonth = new Date(currentYear, month + 1, 0).getDate();
  var firstDayOfWeek = firstDay.getDay();
  var dayCount = 1;

  // Create the rows of the month
  for (var row = 0; row < 6; row++) {
    var calendarRow = document.createElement("tr");
    for (var col = 0; col < 7; col++) {
      var calendarCell = document.createElement("td");
      if (row === 0 && col < firstDayOfWeek) {
        calendarCell.innerHTML = "";
      } else if (dayCount > daysInMonth) {
        calendarCell.innerHTML = "";
      } else {
        calendarCell.innerHTML = dayCount;
        dayCount++;
      }
      calendarRow.appendChild(calendarCell);
    }
    calendar.appendChild(calendarRow);
  }
}

// Add the calendar to the document
document.body.appendChild(calendar);

// Add click event to each cell of the calendar
document.getElementById("calendar").addEventListener("click", function(e) {
  if (e.target && e.target.nodeName == "TD") {
    var day = e.target.textContent;
    var month = e.target.parentNode.parentNode.parentNode.rowIndex;
    var year = currentYear;
    alert(`You clicked on day: ${day} of month: ${month} of year: ${year}`);
  }
});
