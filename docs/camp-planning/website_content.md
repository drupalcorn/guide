


## Overview
The website is the primary source of information about the camp. All other mentions of the camp on other websites, social media, emails, stickers, and other marketing materials will reference the camp website for the canonical source of information about DrupalCorn.

It is important that the website is updated as soon as information is available and reflects the DrupalCorn [Identity and Brand](../../identity). 

## Teaser/Splash Site
In order to get information out as early as possible and to help recruit sponsors, we sometimes publish a static site with basic information about dates, venue, and information about sponsoring. This may be replaced with a full-featured Drupal site at later time.

## Registration
Registration is usually done through Eventbrite. Eventbrite offers an embeddable widget that can be placed on a registration page. Actually integrating Eventbrite with the Drupal site can be difficult, so that's optional. Any call-to-action for registration (such as in the a news item, or a page listing trainings) should link to the registration page that the embed widget is displayed.

## Basic Pages
There are a few generic pages that we normally have on the site. 

* **About** - General information about DrupalCorn. [Example](http://2018.drupalcorn.org/about/index.html)
* **Location(s)** - A list of all the venues for the camp. Address, maps, and pictures of all the places. A list of transportation options in the area (public transit, taxi, shuttles, airport information). [Example](http://2018.drupalcorn.org/venue/index.html)
* **Lodging** - Information about the hotel blocks reserved for DrupalCorn along with address, deadlines, parking, WiFi and other basic information. Pictures would be nice too. [Example](http://2018.drupalcorn.org/lodging/index.html)
* **Policies/CoC** - Review the policies every year. Considering we have this handbook, it may be good to link to the handbook pages about our policies. The Code of Conduct also usually lives here. A link to this page should also be on every page of the site. [Example](http://2018.drupalcorn.org/policies/index.html)
* **Sponsor Opportunities** - Information for potential sponsors. Explain the demographics of DrupalCorn and describe what sponsor levels or opportunities we offer. This page is important to get published as soon as possible. [Example](http://2018.drupalcorn.org/sponsor/index.html).

A basic page could also have a timeslot field so a page can be added to the schedule view.

## Sponsors
A content type for sponsors so that we can display our sponsorships across the site. Usual fields are the following:

* **Name** - Could be the title field. The name of the sponsor
* **Type** - Term reference for what type of sponsor they are, eg: Gold, Silver, Platinum, Badge, Party, Sprint, In-Kind, etc.
* **URL** - The URL the sponsor would like us to send people to.
* **Description** - Could be the body field. About a paragraph about the the sponsor and what they do. Call-to-action, if any.
* **Logo** - Image field to hold a high resolution jpg or png of the sponsor's logo.
* **People** - If we're ambitious, we could relate users/presenters with sponsors so that their sessions can be featured on their sponsor page.

Sponsors are usually listed on a sponsor listing page with just their logo linked to the node, grouped by Type. [Example](http://2018.drupalcorn.org/sponsors/index.html). Platinum sponsors can also be displayed in a block that is displayed on all pages of the site.

## Sessions
Sessions can be proposed by registered users on the site. This way presenters will have the ability to edit and update their own session nodes as needed. The following are fields that we like to use.

* **Title** - Title of the talk. Keep it below 128 characters for YouTube limitations.
* **Presenter(s)** - Multivalue entity reference to Users.
* **Short Description** - Plaintext short description of the session suitable for a tweet or teaser on the schedule view
* **Full Description** - WYSIWYG area (possibly body field) with a full description of the session
* **Track** - Term reference
* **Experience Level** - Term reference
* **Video** - A video field that links the session recording.

The following fields we may ask for to help us make decisions and put together a schedule:

* **Timeslot** - Term reference, field should not be available to edit by non-admin users.
* **Previously Presented?** - Has this presentation been presented at this or other camps?
* **Schedule Preference** - Are there any limitations in time that we need to be aware about. Eg. only available on Saturday or Friday morning, etc.

## Schedule
**Timeslot**

Each "item" in the schedule will need a timeslot. This could be a taxonomy vocabulary. We define time slot terms for when events can happen. For example "Thursday 8am to 9am", and "Thursday 9am to noon", etc. As a taxonomy term, we can weight the terms in chronological order and later display associated nodes/entities grouped by time slots on a schedule view. There could also be separate fields for Start Time, End Time, and Day, which may be put together with auto entity label.

**Schedule View**

A list of of nodes grouped by timeslot. In order for this view to work, the nodes in the view should have a shared timeslot field.  Node types that might show up in this view are Session, or Page (which could be training, lunch, registration, etc.). Nodes that don't have a timeslot can be filtered by excluding nodes where timeslot is NULL.

This view could also have exposed filters for things like track/tags, day. It should be easy for us to default the exposed filters to the current day.

## Users
To make updates to sesion nodes easier, we like to have session nodes owned by a presenter so they can update/revise as needed. We like to collect and display the following information on the users (all optional)

* Name
* Title
* Company/Organization
* Drupal.org Username: links
* Biography
* Profile picture

We can also use entity relationships to attach sessions and sponsorships.

## Other Considerations

