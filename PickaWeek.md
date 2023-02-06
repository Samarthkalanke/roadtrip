# Pick some dates to come Join us on our trip
<script>
// create a table to display the calendar
var calendarTable = document.createElement("table");

// create a table row for each month
for (var month = 0; month < 12; month++) {
  var monthRow = document.createElement("tr");
  var monthName = document.createElement("td");
  monthName.innerHTML = getMonthName(month);
  monthRow.appendChild(monthName);

  // determine the number of days in the month
  var daysInMonth = new Date(2022, month + 1, 0).getDate();

  // create a table cell for each day in the month
  for (var day = 1; day <= daysInMonth; day++) {
    var dayCell = document.createElement("td");
    var dayTextBox = document.createElement("input");
    dayTextBox.type = "text";
    dayTextBox.value = day;
    dayCell.appendChild(dayTextBox);
    monthRow.appendChild(dayCell);
  }

  calendarTable.appendChild(monthRow);
}

document.body.appendChild(calendarTable);

// function to return the name of a month based on its number
function getMonthName(month) {
  var monthNames = ["January", "February", "March", "April", "May", "June",
    "July", "August", "September", "October", "November", "December"
  ];
  return monthNames[month];
}
