---
title: Ad Blocker Mitigation
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Summary

Public reports ( [link](https://backlinko.com/ad-blockers-users), [link2](https://www.statista.com/topics/3201/ad-blocking/#topicOverview) ) indicate up to 50% of web browser ad blocker usage, varying by country, device type and demographic.

Ad blockers browser extensions not only block banner ads but may also block JavaScript tags hosted on third-party domains, which may include Redfast, effectively disabling Redfast platform functionality.

In order to mitigate the potential loss of reach, Redfast customers who are on an Enterprise tier or have opted for the add-on may have the Redfast tag and associated API traffic handled on client browsers via a subdomain of the top level domain utilized by the web application. By configuring traffic to occur via subdomain, ad blocker extensions no longer disable the Redfast platform. With this setup Redfast will otherwise continue to host the necessary files, including the deployment of periodic updates as needed. This change is enabled purely with a DNS update.

Here are the steps required to enable this functionality:

## Update DNS

Once a subdomain has been agreed upon, your Redfast customer success manager will provide instructions for your I.T. team to provision the new subdomain via CNAME entries in your DNS configuration.

## Update Tags

Once the DNS configuration has been updated and validated, the tag manager should be updated to reflect the new subdomain.

Old tag: `<script src="https://[appID].redfastlabs.com/assets/redfast.js" async></script>`

New tag: `<script src="https://[subdomain].yourcompany.com/assets/redfast.js" async></script>`
