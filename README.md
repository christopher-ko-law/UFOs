# UFOs

## Overview of the Project

This UFO sightings websites allows users to view sightings in a HTML table format. The users are allowed to filter by Date, City, State,Country and Shape. The table will populate dynamically when the filters are filled out.

## Results

### Using the Search Functionality

The following filters can be applied to the dataset:
* Date
* City
* State
* Country
* Shape

These filters can either be applied together or separately in any combination.

These filters are normally found on the left side of the screen and look like below:

![Filters](/analysis/filters.png)


### Filtering by Date

Enter a date in the format of mm/dd/yyyy. Do not enter any leading zeros. 
Examples:
* 1/13/2010 will return results.
* 01/12/2010 will not return any results.

At this moment in time, the dataset only has entries from 1/1/2010 to 1/13/2020.

### Filtering by City

Enter the full name of a city. The city name must spelt correctly.

### Filtering by State 

Enter the abbrievated name of a state. The state name must match a name in the United States. The dataset only contains data from the United States. All entries are converted to lower case, so this is not case sensitive.

### Filtering by Country

Enter the abbrievated name of a country. At this point in time, the only valid country is US. All entries are converted to lower case, so this is not case sensitive.

### Filtering by Shape

This is the shape as depicted by the observer. Possible inputs are:
| Filters | | | | | |
| --- | --- | --- | --- | --- | --- |
| circle | light | triangle | unknown | fireball | formation | 
| other | sphere | disk | chevron | rectangle | cross |
| flash | changing | oval | cigar | teardrop | cylinder |

### Example

Here is an output when the following filters are applied:<br>
**Date:** 1/10/2010<br>
**State:** ca<br>

![Sample](/analysis/filter_sample.png)

## Summary

### Drawbacks
While functionality has been increased, there are still a few drawbacks to this design:
* The Date input field is not restricted to dates only. As well, in the JS code, we do not convert the input and data into a proper datetime object and compare thte two. As the a result, if the user is unfamiliar with the current format, the date field will not be properly used.
* Users do not know what the correct search terms for shape are. This may lead to frustrating expereiences when no data is populated as they would be searching for terms that do not exist.

### Additional Recommendation for Further Development

For further development, there are many paths we can take. I will be focusing on the frontend improvements and will be not be discussing backend improvements, such as using MongoDB, API calls, and separating frontend and backend access (in terms of how data.js is updated).

* **Date Picker** - We can implement a date picker for this field:<br>
https://bootstrap-datepicker.readthedocs.io/en/latest/<Br>
This would require the addition of jQuery to be added and would make our site a bit heavier, but this functionality would allow us to remove date format input inconsistencies from the end users. The JS code in app.js could then be updated to take this into account.

* **Pagination** - 
When new data is added to the data.js file, there may be a time where there are too many entries in the table to display neatly. One option to fix this issue in the front end is to add pagination:<br>
https://getbootstrap.com/docs/4.0/components/pagination/<br>
Note: the above page only shows how to add pagination links to to the page (html/css). <br>The JS code in app.js would need to be updated to only display a certain number of results. Then, as the next page number is clicked, the current HTML table would need to be cleared, and the next range of results would be displayed (based on page number).<br>
IE  - On page 1, display results 1-50. On page 2, display results 51 - 100, etc.

* **Export to CSV** - 
Some users may want to export the table into a CSV format. Once can use this code as a template to achieve that effect: <br>
https://stackoverflow.com/questions/50257068/converting-a-collection-of-objects-to-csv-with-keys-as-headers-and-values<br>

