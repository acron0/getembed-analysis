# getembed UI Analysis
by Antony Woods  
antony@teamwoods.org

## Introduction
An analysis of 'getembed's user interface will attempt to yield a series of improvements
that can be made. The focus of these improvements will be:
  * making the site more visually pleasing
  * making the site more intuitive to use and navigate
  * drawing out the key information points and highlighting them

## Questions and Assumptions
Without a principle understanding of the 'getembed' site, there are some immediate
questions that would usually have been asked. In absence of the answers, some assumptions
will be made and the recommended improvements will be based on them.

### Questions
  * Who is the primary user of the site?
    * What is their story?
    * Which information is most important to them?
  * Is there a primary form-factor or device?
    * Will this be predominantly accessed on mobile? Desktop? Kiosk?
    * If there is a primary device, are there bandwidth constraints?
  * What is the skill-level of the average site user?
    * Do we expect tech-savvy, complete novice or average ability?

As an example of why there might be a difference, knowing the motives behind the
primary user of 'getembed' sie allows us to prioritise the information that is displayed
and the way in which it is presented. In any situation where the answers to these
questions are unavailable, assumptions must be made.

### Assumptions
The following assumptions have been made regarding the intended user and form-factor.
  * The site is predominantly viewed on desktop computers/laptops.
    * For now, there will be no recommendations for a mobile experience.
  * The site user is of average-ability, but with a high-level understanding of the data
  being presented by the site, such as sensor readings and what impact they have.
  * Possibly a civil servant, but some one who understands the building trade enough
    that the data doesn't need 'dumbing down' too much.
    * They will use 'getembed' in an investigatory manner, i.e. to locate and find 
    information on a single property within a project and programme.

## Analysis
The analysis will focus on the 'Main' part of the site, omitting the 'Compare' and
'Property Map' sections, for now.
#### Equipment
The analysis was performed with the following equipment:
  * **Device** Laptop
  * **OS** Windows 8.1
  * **Resolution** 3840x2160
  * **Browser** Chrome 43

Link: https://www.getembed.com/app#c94a2f01d89708fb406fed83665ccb1c36e441a5,25fdad74c3736e60b0257ac3f06e2726577dc1f0,c8f8611712da3686830343b0b7d70f88e2eba47d

![Page](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/page.png)

### Landing/Overview

The current site is bereft of any styling, other than a a vanilla Bootstrap theme. It
appears flat and unbalanced. Its clear that it is presenting information regarding a 
single property - this is made obvious by the titling and overview fields. There is a
picture of the property but without visual anchors it looks quite 'floaty' on the right
side of the page. There are icons used to indicate 'Technologies', however there is no
visible key, no ALT attribute for the icons and they are unfamiliar enough to be more
confusing than informative.

At a guess, the icons *could* indicate access, solar power, air conditioning and
insulation.

Below the photo is a list of 'Documents'. There is a single document for this property
although it's unclear what the document is about. There is a link to the document which
looks like an unformatted filename. The word 'Public' floats to the right of the link but
it's unclear what that means.

The information fields in the Overview appear to extend below the fold so in order
to view these the page must be scrolled. A lot of the fields are simply blank and it's
unclear whether they are blank because the information is/was unavailable or because they
perhaps don't apply to this property. The large, wordy sections at the end of the 
information fields don't seem relevant to the property to which they are connected.

Scrolling up reveals two large tables titled 'Projects' and 'Programmes' but the
information they contain seems mainly irrelevant to the selected property.

In the menu bar, to the far right is the logged-in user's emali address, but it is not a
link (to a profile page or similar), nor is it a drop-down to further features as is
conventional.

### Profiles

Selected from the tab navigation on the page, this section presents a large table. The
columns are vaguely named 'planned', 'pre' ad 'post' and don't offer much information.
The table rows are grouped by headings that are clearly marked. A lot of the cells are
empty. The table is quite long and in order to reach the bottom scrolling is required. The
row groups are not sorted alphabetically.

### Devices

This section presents another table. It's unclear to a layman what a 'device' is, but by
analysing the table it seems to represent a collection of devices. The information in this
section is cryptic. The 'Unique Description' and 'Device ID' fields appear to contain
UIDs. The former field posses the ability to sort the table, although this is irrelevant
as the UIDs appear random. 

It is not obvious that clicking on a row reveals more information - the subtle visual
highlight is not enough. Upon clicking a row, the page scrolls to the base of the table
where a new section has appeared which gives further information about the device
and its sensors. In some instances, both the table and device details have blank
fields.

### Datasets

This section is completely empty.

### Sensor Charts

This section displays a table of sensors. Like the Devices section, the rows are 
selectable although this is not immediately obvious. The Type column is sortable,
although 'type' seems like a miscategorisation as they are infact human-readable
names/IDs. Below the table is a 'Chart Data' button, two text input boxes 
containing date ('dd/mm/yyyy') placeholders but there is no obvious relationship between
the inputs. There are links below the buttons which adjust the date once input. Clicking 
the input reveals similar functionality inside the widget, as well as a date picker.

Unlike the preceeding sections, clicking a row does not immediately display new data.
Clicking a row does automatically input date information into the date text boxes. This
information reflects the 'Event' dates in the row of the specified sensor. Clicking the
'Chart Data' button displays a line chart of sensor data between the two dates.

It's not obvious, but you can select multiple rows before pressing 'Chart Data' to see the
respective line charts overlayed. An obscure error message is displayed (often out of
sight) if you attempt to pick rows that would span more than two unit types.

### Raw Sensor Data

Using a very similar table to the 'Sensor Charts' section, this section allows you to 
select sensors (using row selection, as per other sections) and a date (as long as it
falls within the event date range) to see raw sensor data at regular time intervals. 
Selecting a sensor with a blank date range, or selecting a date outside a range yields
no results and does not alert the user of their error. There are icons (rather than text
links as in 'Sensor Charts' section) to control the date input widget, including the same 
inline controls as in the 'Sensor Charts' section.

## Improvements

There are a number of functional *and* cosmetic changes that can be made in order to
address the issues with this page.

### General

  1. The URL for the page is unconventional and confusing. It is recommended that URLs are
  'intelligible for humans' [(1)](https://support.google.com/webmasters/answer/76329?hl=en).
  A better pattern would be  
  `https://www.getembed.com/app/<programme_slug>/<project_slug>/<property_id>`

  2. Rather than include the 'Project' and 'Programme' selection tables on the page, they
  should be hidden away with [breadcrumbs](http://www.smashingmagazine.com/2009/03/17/breadcrumbs-in-web-design-examples-and-best-practices/) 
  as the hierarchy (Programme > Project > Property) facilitates this type of feature. 
  Simultaneously, it allows each level to have a dedicted page so they are less cluttered
  and more targetted.

  3. A lack of branding and style consistency leaves the UI very flat and uninviting. The
  typefaces and syling (light-green with green bold) from `https://www.getembed.com/`
  would be enough to start making the inside pages more appealing.  

  4. On the menu bar, replace the user's email address with a 'Profile'
  drop-down (via text or an icon), which would contain functions such as 'Edit Profile', 
  'Logout' etc. Remove 'Logout' from the menu bar. This approach is far more conventional
  and familiar to users.

  5. The navigation tabs (Overview, Profiles etc) should use the appropriate 'Hand' cursor
  so that they are not confusing.

  6. Ideally, either the navigation tabs should be sticky (at the top, beneath the main
  menu) or there should be a sticky icon which returns you to the property section (rather
  than the top of the page) so that you can return to the navigation tabs quickly.

  7. Change the name of the "Main" link on the main menu navigation to something more
  appropriate such as 'Property Search'

### Overview

  1. Although we assume the photo is not a critical piece of information (unlike a site
  like RightMove or Zoopla, where it definitely would be) it makes a good visual anchor
  for balance on the right side of the page. It should be larger, more prominent and the
  key pieces of property information should wrap it. Also, using a UI that is similar to
  that of a well-known property site will likely feel familiar to users, making them more
  at ease whilst trying to navigate.

  2. All of the information fields in Overview should appear above the fold. There are
  couple of reasons:  

     a. An 'overview' should be just that; concise, brief, succinct. Extraneous
     information such as the wordy project descriptions should be hidden by widgets,
     confined to breakouts or removed entirely.  

     b. When a user first encounters the Overview section, they have not yet used the
     property tab navigation. If they are forced or encouraged to scroll it out of view,
     they may find it confusing or difficult to then move to other sections.

  3. Avoid blank information fields. Either omit the field or use an '*Unavailable*'
  placeholder. Blank fields are confusing.

  4. The Technology icons need a key. This could be inline but breakouts are also popular,
  with links like "What do these icons mean?". At the very least, the icons should have
  ALT text.

  5. The Documents section should replace the listed documents filename with either an
  appropriate description (i.e. Project Final Report) or an icon which informs of the
  filetype. Simultaneously, the 'Public' label needs clarification such as becoming "This
  document is public" or "This document is confidential" etc.

  6. Opening a document in the Documents section should open in a new tab or breakout 
  rather than replacing the current window location.

### Profiles

  1. Each of the headed 'row groups' should be collapsible and be collapsed by default.
  There should be instructions so that it's clear the headers can be interacted with.
  There is an overwhelming amount of information in this table and it can afford to be
  hidden so that users can select just the information they need.

  2. The table should be alphabetically sortable by row group names. Currently there is no
  sorting on this table and no obvious to the order of the row groups, making it difficult
  to quickly navigate to any particular group.

  3. More appropriate column headers should be used in conjunction with an explanation as 
  to what they mean. The current column headers are too vague.

  4. If the purpose of the table is to compare ('diff') the changes between one column to
  another then coloured row values could be used to indicate a change. For example,
  columns with the same value use the same colour but columns with a differing value use a
  different colour.

### Devices

  1. The ability to select rows needs to be made more obvious: 

     a. The grey highlight is too subtle.
     b. The cursor should change to 'Hand' when hovering.

  2. The "Unique Description" and "Device ID" columns seem like niche information points.
  Either hide these values using ellipsis (click/hover to reveal), move them to the
  details section or remove them entirely.

  3. The units in the 'Device Details' pane (and any units on other sections) should be 
  fully expanded and not just shorthand, i.e. use "Amps" not "A", "Watts per hour" not
  "Wh".

  4. "Header Rows" and "Calculated Field" columns are blank on every row, so remove them.

  5. Allow the user to sort the table on the "Sensor Types" and "No. of Sensors" columns.

  6. Sit the device table and details section side by side, rather than stacked. This
  allows the user better overall control as they don't have to continuously scroll to
  view the selected device.

### Sensor Charts

  1. Similarly to in the Devices section, the ability to toggle a row needs to be made
  more obvious: 

     a. Provide an explanation at the top of the section which mentions toggling rows,
     displaying the graph and the constraints that are in place.
     b. The grey highlight is too subtle.
     c. The cursor should change to 'Hand' when hovering.

  2. The "Description" and "Device ID" columns seem like niche information points. Either 
  hide these values using ellipsis (click/hover to reveal) or remove them entirely.

  3. "Location" and "Status" columns are blank on every row, so remove them.

  4. Under most circumstances, do not require the user to press "Chart Data" in order to
  fetch the data and generate the chart. It should be performed automatically and 
  asynchronously as soon as an additional row is selected. A 'Refresh' button (or icon)
  could be used for if a user adjusts the date fields.

  5. There needs to be more focus on the date inputs and their relationship. They are 
  currently unlabled.

  6. The "+1" links below the date inputs duplicate functionality that exists inside the
  date input widgets themselves and should be removed.

  ```
  NOTE: This control does not appear to work in all browsers. Consider replacing it with
  one that does.
  ```
  ![Date input browser comparisson](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/date-input.png)
  
  7. Rather than display an error message when you try to select multiple rows that
  collectively span more than two units, proactively disallow the user from selecting bad
  rows by 'disabling' them; no more cursor change, grey highlight. This, together with a
  decent explanation at the top of the page, *prevents* bad behaviour entirely rather than
  punishes it.

  8. Allow the user to sort the table on the "Types", "Unit" and two "Event" columns.

  9. Sit the sensor table and graph side by side, rather than stacked. This allows the
  user better overall control as they don't have to continuously scroll to select
  different rows to compare.

### Raw Sensor Data

  1. The "Description" and "Device ID" columns seem like niche information points. Either 
  hide these values using ellipsis (click/hover to reveal) or remove them entirely.

  2. "Location" and "Status" columns are blank on every row, so remove them.

  3. Sensors without any value in the Event columns cannot fetch data and therefore should
  not be included in the table. 

  4. See comments on 'Devices' and 'Sensor Charts' sections regarding the ability to select
  rows in a table as they apply here too.

  5. Under most circumstances, do not require the user to press "Get Data" in order to
  fetch the data. It should be performed automatically and asynchronously as soon as an a
  row is selected. A 'Refresh' button (or icon) could be used for if a user adjusts the
  date field.

  6. See comments in 'Sensor Charts' section regarding date input widget and external 
  controls.

  7. Sit the sensor table and data table side by side, rather than stacked, and provide a
  scrollable area for the data table so that a large number of results doesn't severly
  affect the height of the page.

## Examples

Some concept examples which illustrate the key points made above.

### Overview

![Overview Example](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/mockup-overview.png)

### Profiles

![Profiles Example](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/mockup-profiles.png)

### Devices

![Devices Example](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/mockup-devices.png)

### Sensor Charts

![Sensor Charts Example](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/mockup-sensor_charts.png)

### Raw Sensor Data

![Raw Sensor Data Example](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/mockup-raw_sensor_data.png)

## Conclusion

There are clearly a fair number of improvements that can be made to this site's UI. It's
true to say that most of the changes are about enforcing convention and 'tidying' rather
than discussing better ways for presenting data. With a deeper context, it's very likely
that even more could be done to improve the functionality of the site, but this is a
fair start.