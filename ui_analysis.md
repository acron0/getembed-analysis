# getembed UI Analysis
by Antony Woods  
antony@teamwoods.org

## Introduction
An analysis of 'getembed's user interface will attempt to yield a series of improvements
that can be made. The focus of these improvements will be:
  * making the site more visually pleasing
  * making the site more intuitive to use and navigate
  * drawing out the key information points and highlighting them

### Questions and Assumptions
Without a principle understanding of the 'getembed' site, there are some immediate
questions that would usually have been asked. In absence of the answers, some assumptions
will be made and the recommended improvements will be based upon them.

#### Questions
  * Who is the primary user of the site?
    * What is their story?
    * Which information is most important to them?
  * Is there a primary form-factor or device?
    * Will this be predominantly accessed on mobile? Desktop? Kiosk?
    * If there is a primary device, are there bandwidth constraints?
  * What is the skill-level of the average site user?
    * Do we expect tech-savvy, or complete-novice, or average ability?

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
### Equipment
The analysis was performed with the following equipment:
  * **Device** Laptop
  * **OS** Windows 8.1
  * **Resolution** 3840x2160
  * **Browser** Chrome 43

### Impressions

Link: https://www.getembed.com/app#c94a2f01d89708fb406fed83665ccb1c36e441a5,25fdad74c3736e60b0257ac3f06e2726577dc1f0,c8f8611712da3686830343b0b7d70f88e2eba47d

![Page](https://raw.githubusercontent.com/acron0/getembed-analysis/master/resources/page.png)

#### Landing/Overview

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

#### Profiles

Selected from the tab navigation on the page, this section presents a large table. The
columns are vaguely named 'planned', 'pre' and 'post' and don't offer much information.
The table rows are grouped by headings that are clearly marked. A lot of the cells are
empty. The table is quite long and in order to reach the bottom scrolling is required. The
row groups are not sorted alphabetically.

#### Devices

This section presents another table. It's unclear to a layman what a 'device' is, but by
looking at the table it seems to represent a collection of devices
