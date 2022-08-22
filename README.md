# UFOs

## Overview
In this repository is code that takes Javascript UFO sighting data and puts it into an HTML table on a website.  It then allows for user input to filter the data by date, city, state, country, and shape of the UFO.


## Results
### Page layout
- Underneath the banner of this website is a short article intrducing the page.  This is just information and is not interactable.
- There are two sections underneath the article: a Filter Search form on the left and the data table on the right.

#### FILTER SEARCH FORM 
This section is made of five fields the user can enter information into with placeholders hinting how the text should be entered in order to properly filter the table to the right.  Unfiltered fields show as a dark grey text and fields with user input are shown in black text.

![filter_search](https://user-images.githubusercontent.com/102555125/186039636-663e406c-d77e-4bf8-bf1f-f82d45024e79.png)


#### DATA TABLE
This section, by default, shows the entire data set and will filter down according to the criteria entered in the boxes in the Filter Search form.  It will clear out filter criteria and display the whole dataset upon visiting the page for the first time, refreshing the whole page, clicking on the "UFO Sightings" text at the very top of the page, or deleting input and pressing the enter key.

![unfiltered_table](https://user-images.githubusercontent.com/102555125/186039665-11a1fe87-8d8f-4667-8e74-7abe36bdbe39.png)


#### WORKING WITH THE FILTERS
- In order to filter the information in the table, criteria must be entered in exactly the same way as the placeholder text: everything in lower case and the date in a format that doesn't use leading zeroes on the month or day.  
- Not all filters need to be filled in as this table filters one at a time, triggered by pressing enter or tabbing through the fields after entering the criteria, or clicking into a new field.  The table will filter further by each individual criteria as you move to another field.  
- All filters are limited to one criteria so multiple cannot be searched for at the same time (for example: you can search for circle or light individually, but not circle AND light).

![filtered_table](https://user-images.githubusercontent.com/102555125/186039675-f1473a90-4e9b-437e-b294-23371057e22b.png)




## Summary
One drawback of this design is that it is very sensitive to how a user inputs the search criteria and assumes the user knows how to use this form.  If a user inputs "CA" instead of "ca" or "01/10/2010" instead of "1/10/2010" the filter will not recognize it and return a blank table (see image below).  This could be frustrating for a user and lead them to believe that there is no data for their search criteria.  There is also no recognizable filter button or directions to press Enter or Tab after entering the criteria.  This could cause a user to just sit there after entering their criteria, confused as to why nothing is happening.
![case_sensitive](https://user-images.githubusercontent.com/102555125/186039708-0126770a-616f-4f45-99aa-e6de9c5f069c.png)

Another drawback is the lack of ability for the user to contact the writer of the section explaining the data.  The very last sentence of the article reads, "Dig through the data yourself, and let us know what you see."  This implies that reactions and comments are welcomed, yet there is nowhere on the website to leave a comment or contact the writer.

A third drawback is the limits to what the user can enter.  They can enter one search criteria at a time for each section.  They are unable to see all of the sigtings for California and Arizona in the same table, as the table is unable to handle multiple search criteria for the same type.

### Solutions
- The code will need to be refactored to either ignore case or convert user input to lower case so that a wider range of inputs yeilds the results desired.
-  The code will also need to be refactored for more variety in datetime entries.  The script needs to be able to recognize that 1/1/10 is the same as 01/01/2010 and 1/01/10 and any other variety of datetime entry.
- I would also suggest adding the filter button back in, which was removed during refactoring to include additional search criteria.  It is more intuitive for users to click a button to trigger the filtering than pressing Enter or Tab in each of the input fields.
- A best-case-scenario would be coding the search boxes to accept standard search language using AND/OR/WILDCARDS/ETC.  This would give the user the freedom to see the data from multiple states, cities, etc in one table, allowing for much deeper analysis.
-  At the very least, and the least desirable of solutions, there needs to be directions on exactly how to enter search criteria so that this filter is not frustrating for the user.  Frustrated users don't re-visit websites and they will go elsewhere to meet their needs.
- Another update I would like to see would be a comments section or contact information.  This could also be accomplished using a form with specific questions.  If this were included, more data analysis could be conducted on the results of the forms sent back.
