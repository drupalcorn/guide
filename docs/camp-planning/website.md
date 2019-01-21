
## Hosting

We have accounts at Pantheon and Acquia. Both have been donated for community use. Recent years we have been using Pantheon. Access to these accounts is managed by the core committee.

As part of any hosting, we are required to acknowledge it on our website. Usually in the footer.

    <a href="https://pantheon.io/">Powered by Pantheon</a>

Managing hosting is the responsibility of the core committee. Developing the site and the site content is the responsibility of the camp committee.

## Archive Sites

After every camp and enough time has passed that we don't need to be updating the site, we will "flatten" the site into static files so that we don't have to keep up with security updates and can use basic hosting.

To archive a site we first remove any ajax or forms that require interaction with Drupal. These features will not work after the site is flattened. Some examples of interactive items could be webforms or views that use ajax for filters or display.

When the site is ready to be flattened, we use a product called [Site Sucker](https://ricks-apps.com/osx/sitesucker/) to crawl the site and generate the static files. These files are then uploaded to our static hosting at [460 Design](http://www.460design.net/), provided gratis by emeritus core committee member Hans Hoerschelman.

## DNS

DNS hosting is done through [Namecheap](https://www.namecheap.com/) and is managed by the core committee. The following is how we usually have DNS set up.

***.drupalcorn.org** - URL Redirect to `http://[year].drupalcorn.org`

> By default any request for `*.drupalcorn.org` that isn't otherwise
> defined will redirect to the most recent year. This record will need
> to be updated when we go live with a new year's site.

**@.drupalcorn.org** - URL Redirect to `http://[year].drupalcorn.org`

> By default any request for `drupalcorn.org` (without any subdomain)
> will redirect to the most recent year. This record will need to be
> updated when we go live with a new year's site. [Learn a bit about the
> difference between `*` and
> `@`](https://www.namecheap.com/support/knowledgebase/article.aspx/320/2237/what-is-a-catchall-wildcard-subdomain).

**[current year].drupalcorn.org** - CNAME to hosting provider.

> The current site (e.g. `2018.drupalcorn.org`) will be hosted at
> whatever our hosting provider is.

**www.[current year].drupalcorn.org** - URL Redirect to `http://[current year].drupalcorn.org`.

> We redirect all our `www` requests to the no-www requests. So,
> `www.2018.drupalcorn.org` redirects to `2018.drupalcorn.org`. This may
> be done at the hosting provider, but doing it here means we only need
> to update one record when it's time to change hosting after
> flattening.

**[year].drupalcorn.org** - CNAME to `static.drupalcorn.org`.

> Archived sites go to our static hosting, which is defined by
> `static.drupalcorn.org`.

**static.drupalcorn.org** - CNAME to `server4.460host.com`.

> `static.drupalcorn.org` is a CNAME to our static hosting service.
> Currently `server4.460host.com`. If this should ever change, we only
> need to update this record to change all the archived sites.

**calendar/docs/mail.drupalcorn.org** - CNAME to ghs.google.com.

> We have a grandfathered free Google Apps account. These are CNAMEs so
> drupalcorn.org accounts have access to calendar docs and email web
> services.

**@.drupalcorn.org** - MX for Gmail mail servers.

> We use Google Apps with a free grandfathered account. MX records route
> mail to where it's supposed to go.

**@.drupalcorn.org** - TXT record for Google verification and SPF records.

> SPF and Google site verification information.
