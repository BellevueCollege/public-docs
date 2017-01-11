<span id="google-custom-search"></span>
# Google Custom Search

<span id="contents"></span>
- [Google Custom Search](#google-custom-search)
- [Contents](#contents)
- [Overview](#overview)
- [Alterante solutions](#alterante-solutions)
- [Technologies](#technologies)
  - [Administrative Dashboard](#administrative-dashboard)
  - [How it works](#how-it-works)
  - [Considerations in implementation](#considerations-in-implementation)

<span id="overview"></span>
## Overview

Google Custom Search is being used to handle public search on the Bellevue College website as an interim solution while we decide on and implement a more permanent solution.

<span id="alterante-solutions"></span>
## Alterante solutions

Alternate solutions being discussed include:

* SOLR
* SharePoint
* Google Search Appliance

<span id="technologies"></span>
## Technologies

[Google Custom Search](http://www.google.com/cse/all)

<span id="administrative-dashboard"></span>
#### Administrative Dashboard

Log into the [Google Custom Search](http://www.google.com/cse/all) using the BC webmaster google account.

<span id="how-it-works"></span>
#### How it works

* We simply add a javascript file on the page where we want custom search to appear. We chose http://bellevuecollege.edu/search/

<span id="considerations-in-implementation"></span>
#### Considerations in implementation

* Use same querystring for search as we had before to ensure that search didn't break globally.
* Integration with Google Analytics for search tracking
* styling tweaks (google custom search generates tables, which we style globally, we had to unstyle them)
* ```<Noscript>``` alternative that points to a google hosted URL.