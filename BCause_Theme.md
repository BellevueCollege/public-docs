<span id="bcause"></span>
# BCause
---

- [Project Plan](#project-plan)
  - [Statement of need](#statement-of-need)
  - [Problem](#problem)
  - [Goal](#goal)
- [Statement of intent](#statement-of-intent)
  - [Title](#title)
  - [Stakeholders](#stakeholders)
  - [Expected scope/scale/size](#expected-scopescalesize)
- [Current status](#current-status)
  - [Requirements](#requirements)
  - [Roadmap](#roadmap)
- [Vision/Goal](#visiongoal)
- [Requirements](#requirements)
  - [Design needs](#design-needs)
  - [Column options](#column-options)
  - [Navigation options](#navigation-options)
  - [Page Templates](#page-templates)
  - [Aside](#aside)
  - [Widget areas:](#widget-areas)
- [Commons / StudentWeb Thenes](#commons--studentweb-thenes)
- [Technical Requirements for Theme](#technical-requirements-for-theme)
- [Plugins - Home Grown](#plugins---home-grown)
  - [Official site plugin](#official-site-plugin)
  - [SEO Components - for official sites](#seo-components---for-official-sites)
  - [Analytics](#analytics)
  - [Social Media Connection plugin](#social-media-connection-plugin)
  - [Student Web Club Activation plugin](#student-web-club-activation-plugin)
- [Plugins - 3rd Party (purchase/use](#plugins---3rd-party-purchaseuse)
  - [Slider](#slider)
  - [Social Media](#social-media)
  - [Events](#events)
  - [Tables](#tables)
  - [Contact Forms](#contact-forms)
- [Commons/Studentweb Unique Needs](#commonsstudentweb-unique-needs)
- [Functionality](#functionality)
  - [Potential functionality built into theme](#potential-functionality-built-into-theme)
- [Performance Plugins/tools to consider](#performance-pluginstools-to-consider)
- [Documentation Plan](#documentation-plan)
- [Project members](#project-members)
- [Projects this interfaces with](#projects-this-interfaces-with)

<span id="project-plan"></span>
## Project Plan

<span id="statement-of-need"></span>
#### Statement of need

The college needs a simpler way to manage web site content.

<span id="problem"></span>
#### Problem

The large majority of web content managers are using Dreamweaver to create/edit web pages. The software requires moderate technical knowledge which is a barrier for some content managers.

<span id="goal"></span>
#### Goal

Create a content management system to enable content managers across campus an easy to use method to publish and edit information.

<span id="statement-of-intent"></span>
### Statement of intent 

<span id="title"></span>
#### Title

BCause Framework

<span id="stakeholders"></span>
#### Stakeholders 

Campus web managers, DevCom, students, Institutional Advancement

<span id="expected-scopescalesize"></span>
#### Expected scope/scale/size

This system will be the foundation for which future college web sites are built. 

<span id="current-status"></span>
### Current status 
In active development

<span id="requirements"></span>
### Requirements 
?

<span id="roadmap"></span>
### Roadmap

First iteration will require greatest ramp up. Once version 1 is delivered, the expectation is to release regular iterations/improvements.

<span id="visiongoal"></span>
## Vision/Goal

ATTENTION, GOAL CHANGED!!!  NEEDS to be EDITED

BCause Theme is a theme we will be developing because we can.  It is an uber-flexible theme for our informal websites [Studentweb](https://wikiwiki.bellevuecollege.edu/wiki/Studentweb) and [Sites+](https://wikiwiki.bellevuecollege.edu/wiki/Sites%2B).  It will be the default theme in these environments

Potentially, this theme could be used for Affiliate websites

<span id="requirements"></span>
## Requirements

Develop theme for branded college websites with 2 major design options

<span id="design-needs"></span>
#### Design needs
* responsive, 2 step 

Styles
* Homesite brand  - sites that carry the main look/feel of the college home page, including main navigation + footer
* BC-Lite brand - For department websites - 
* Potentially allow for different schemes, particularly for top navigation colors

Other
- move search box into id bar, redesign id bar
- tweak college header
- tweak phat footer

<span id="column-options"></span>
#### Column options
* no column
* left column
* right colunm 
(no 3 column, instead, allow for an 'aside' space within the content)

<span id="navigation-options"></span>
#### Navigation options
* Top navigation (not 'designed' for homesite brand
* Left Navigation 
* No navigation

<span id="page-templates"></span>
#### Page Templates
* Create a page template that generates navigations based of "ancestor" 
* Design navigation pages for
* homesite nav pages
* for other nav pages

<span id="aside"></span>
#### Aside
Display a box floated right within the content space if:
* content is added in the aside box.  
* widget added on the "Aside widget area"

<span id="widget-areas"></span>
#### Widget areas:
* Aside (this widget area is after aside content added on a page
* Sidebar (if there is a sidenav, it shows up after navigation)
* 3 footer asides

<span id="commons--studentweb-thenes"></span>
## Commons / StudentWeb Thenes 
* purchase 4-7 themes for those, instead woothemes / elegantthemes


<span id="technical-requirements-for-theme"></span>
## Technical Requirements for Theme
Allow for:

* Base CSS
* custom css to be used with tiny-MCE advanced plugin
* Look & Feel is stripped down version of [Btheme](https://wikiwiki.bellevuecollege.edu/index.php?title=Btheme&action=edit&redlink=1).  No college logo/footer (that is added via a plugin
* Allow for color scheme switching, such as color / font packages
* Allow for layout options. 
* Sitewide layout options
* Top nav and/or sidenav
* home page layouts
* home page settings: Home page blog/site/combo? (future?)
* Allow for user to upload logo / banner to site. Default, text based
* Responsive
* widget areas (define/etc)
* Navigation
* choose what navigation you want Top/Side  (or top primary with side secondary nav)
* Default to top with wp_list_pages.
* If appearance > menu defined, show it.
* Give option to have top or side navigation or both.
* If both top & side, side navigation lists children of parent page.
* If both top & side on home page, ignore side nav.
* Allow for custom wp menu in side nav on home page.

<span id="plugins---home-grown"></span>
## Plugins - Home Grown

<span id="official-site-plugin"></span>
#### Official site plugin 
* strip design control form BCause down
* allow for site to look like homesite or more generic website
* homesite includes college-wide nav and thick footer w/ legal links
* stripped-down official site includes narrow identity bar and legal links  (maybe id bar uses drawer)
* extra options for dept. footers (tie into maps, etc)
* Class Schedule shortcode functionality to connect with class schedule data
* course descriptions
* quarterly schedule info by class or by subject [allow for tabs as quarter?]
* class details info
* Staff CPT funcitonality (future iteration?) -> or may be based on ODS/Active Directory data
* College-wide search + site search --> on sites that don't use main college nav
* photo of bulding/office ""You are here"
* widget with info about office hours

<span id="seo-components---for-official-sites"></span>
#### SEO Components - for official sites
Simple home-grown multisite-friendly plugin to improve SEO by improving control of page titles and keywords in WP sites. 
* Adds a metabox with  2 custom fields to all pages/posts
* 1st: add meta keywords
* 2nd: custom page title
* Default page title on all pages is: "[page-title] | [name-of-site]" (except for home page)
* Adds an options page for the plugin with one field - "institution name".   On multi-site installs, the settings are controlled centrally.
* if institution name is filled. The title tag for the home page of all sites changes to:  "[name-of-site] @ [institution-name]" 
* if institution name is not filled, the title tag for the home page becomes "[name-of-site] - [site-description]"

<span id="analytics"></span>
#### Analytics
Custom plugin to create our own way to handle analytics that is multi-site friendly
* Network admin has ability to set up multiple GA tracking codes the way BC handles it
* allow individual sites to add their own GA tracking code
* track 404 errors
* allow sites to turn on methods for tracking specific options (global nav/footer/docs/etc)

<span id="social-media-connection-plugin"></span>
#### Social Media Connection plugin
Create custom social media plugin that:
* uses sprites for social media stuff
* Allows for multiple icon pacs
* generates a widget that conforms to area it shows in (sidebar of footer)
* horizontal/vertical layout options

<span id="student-web-club-activation-plugin"></span>
#### Student Web Club Activation plugin

These could be achieved via multiple plugins, but could be one plugin
* allow for students to charter a club via studentweb process.  Once chartered, if club site doesn't already exist, give them the option to create a site
* At the end of every academic year, uncharter all clubs.  Display a message on all sites saying that the club is not chartered any longer. Provide a way to allow students to re-charter club from site
* Display system-wide disclaimer on footer - including info on student code
* Differentiate Club sites from Program sites.  Program sites never become inactive.

<span id="plugins---3rd-party-purchaseuse"></span>
## Plugins - 3rd Party (purchase/use

<span id="slider"></span>
#### Slider

* Plugin that creates CPT
* Fields for title, content, image, url, expiry
* need design work done
* Optional for version 1 - Setup multiple options for slider styles in plugin settings

<span id="social-media"></span>
#### Social Media

* Social Sharing (existing plugins)
* Display Twitter feed/tweets (existing plugins?)
* Display Flickr Stream (exisint plugins?)
* Linking to Social Media Sites (plugin widget)

<span id="events"></span>
#### Events

* pushed to next version of BCause
* fallback to My Calendar on a site-per-site basis

<span id="tables"></span>
#### Tables

* TinyMCE to generate tables (CSS to default styles)
* Use jQuery to add column sorting functionality as it comes up.
* Other tables plugin for more complex+ accessible tables

<span id="contact-forms"></span>
#### Contact Forms

* Gravity Forms (spam reducing settings?)
* Way to interact with ODS data after authentication (future version)

<span id="commonsstudentweb-unique-needs"></span>
## Commons/Studentweb Unique Needs

* <span style="background:#0d9f08; padding: 5px;">Custom CSS</span>
* <span style="background:#0d9f08; padding: 5px;">Scheme Switcher</span>
* Disclaimer

<span id="functionality"></span>
## Functionality (may be done via plugins in [Studentweb](https://wikiwiki.bellevuecollege.edu/wiki/Studentweb) and [Sites+](https://wikiwiki.bellevuecollege.edu/wiki/Sites%2B)/[Commons](Commons.md)

<span id="potential-functionality-built-into-theme"></span>
#### Potential functionality built into theme

* Defaults to CMS site not blog (or option to easily switch from blog to site
* Needs to be designed to handle blog/cms off the bat

<span id="performance-pluginstools-to-consider"></span>
## Performance Plugins/tools to consider
* WP Minify
* Caching?
* LESS

<span id="documentation-plan"></span>
## Documentation Plan
* Create a public space for documenting project 
* technical documentation (how-to)
* Rationale/explanation about this plan over dreamweaver + what it means to web managers
* Framework specs 
* style guide | global look and feel
* component library
* Info for outside developers to work in our infrastructure 
* upgrade process (expectations)

<span id="project-members"></span>
## Project members
* Juan - UX/Design Guru
* Erik - WP/Dev Guru

<span id="projects-this-interfaces-with"></span>
## Projects this interfaces with
* [Studentweb](https://wikiwiki.bellevuecollege.edu/wiki/Studentweb)
* [Sites+](https://wikiwiki.bellevuecollege.edu/wiki/Sites%2B)
* [WordPress](https://wikiwiki.bellevuecollege.edu/wiki/WordPress)
* [Commons](Commons.md)

