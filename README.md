# UFO Sighting - JavaScript and DOM Manipulation

## Table of Contents
* [Objective](#Objective)
* [Technologies](#Technologies)
* [Visualization](#Visualization)

# Objective | Create Automated Table with Multiple Category Search Function
* Using the UFO dataset provided in the form of an array of JavaScript objects, write code that appends a table to an HTMl page and then adds new rows of data for each UFO sighting.

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


# Technologies
* HTML5
* CSS
* Javascript

# Visualization

<img src="website_screenshot.png" width=100% align=center>

- - -

### Dataset

* [UFO Sightings Data](StarterCode/static/js/data.js)
