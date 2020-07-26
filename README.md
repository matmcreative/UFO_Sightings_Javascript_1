# UFO Sighting - JavaScript and DOM Manipulation

## Table of Contents
* [Objective](#Objective)
* [Technologies](#Technologies)
* [Visualization](#Visualization)

# Objective | Create Automated Table with Multiple Category Search Function
* Using the UFO dataset provided in the form of an array of JavaScript objects, write code that appends a table to an HTMl page and then adds new rows of data for each UFO sighting.
* Using multiple `input` tags and/or select dropdowns, write JavaScript code so the user can to set multiple filters and search for UFO sightings.

### Objective 1: Automatic Table and Date Search

* Using the UFO dataset provided in the form of an array of JavaScript objects, write code that appends a table to your HTML page and then adds new rows of data for each UFO sighting.

```
// loop through data and append rows to the table body
tableData.forEach(function(ufo){
    var row = tbody.append("tr");
    // use append method to insert table data for each row
    Object.entries(ufo).forEach(function([key,value]){
        //console.log(key, value)
        // use append to insert a cell for each value
        // use text to insert data to each cell
        var cell = row.append("td").text(value);
    });
});
```
* Columns: `date/time`, `city`, `state`, `country`, `shape`, and `comment`.

* Use a date form in HTML document and write JavaScript code that will listen for events and search through the `date/time` column to find rows that match user input.

```
button.on("click", function(){
    // select the input element and get the html node
    var inputElement = d3.select(".form-control");
    // get the value property of the input element
    var inputDate = inputElement.property("value");
    //console.log(inputDate)
    // filter data for the date value to get data that is searched for
    var filteredData = tableData.filter(ufo => ufo.datetime === inputDate);
    //console.log(filteredData);

    // select the table body to insert table rows and cells
    var tbody = d3.select("tbody")
    // clean the table body to insert selected date values
    tbody.html("");
```
### Objective 2: Multiple Search Categories

* Using multiple `input` tags and/or select dropdowns, write JavaScript code so the user can to set multiple filters and search for UFO sightings using the following criteria based on the table columns:
  1. `date/time`
  2. `city`
  3. `state`
  4. `country`
  5. `shape`

```
button.on("click", function(){
    // select the input element for date and get the html node
    var dateElement = d3.select("#datetime");
    // get the value property of the input element
    var inputDate = dateElement.property("value");
    
    // select the input element for city and get the value info
    var cityElement = d3.select("#city");
    var inputCity = cityElement.property("value");

    // select the input element for state and get the value info
    var stateElement = d3.select("#state");
    var inputState = stateElement.property("value");

    // select the input element for country and get the value info
    var countryElement = d3.select("#country");
    var inputCountry = countryElement.property("value");

    //select the input element for shape and get the value info
    var shapeElement = d3.select("#shape");
    var inputShape = shapeElement.property("value");

    // create a variable for filtered data
    var filteredData = tableData;

    // use filterData function to filter data for the search criterias
    filteredData = filterData(filteredData, 'datetime', inputDate);
    filteredData = filterData(filteredData, 'city', inputCity);
    filteredData = filterData(filteredData, 'state', inputState);
    filteredData = filterData(filteredData, 'country', inputCountry);
    filteredData = filterData(filteredData, 'shape', inputShape);
```

# Technologies
* HTML5
* CSS
* Javascript

# Visualization

<img src="website_screenshot.png" width=100% align=center>

- - -

### Dataset

* [UFO Sightings Data](StarterCode/static/js/data.js)
