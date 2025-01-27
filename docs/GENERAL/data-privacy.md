---
title: Data Privacy and Security
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
By default, Redfast does not collect or process end-user information besides session timestamps. Redfast does not collect or store end-user IP addresses. Redfast tracking only collects and processes information that you designate. These items can be disabled or modified at any time. Redfast is a transient processing platform with a 90-day default lookback window. This duration may be further modified if desired.

## IP Address

Redfast never stores the end user's IP address. Location targeting is possible via one-way hashed integration with a locally hosted copy of the [MaxMind's GeoIP database](https://www.maxmind.com/en/geoip-databases). The IP address is never shared outside of Redfast's internal services.

## Cookies

Redfast does not utilize cookies in its platform operations, unless directed by a customer to do so on a first party basis.

## Email Address

Redfast does not utilize the end user's email address to operate the service. **Email addresses may only be imported explicitly at your option.** See [importing custom traits](user-traits) for more information.

Certain third party connectors may require the end user email address for proper operation. For example, in order to initiate a [Sendgrid](https://www.sendgrid.com/) email campaign to the end user in response to a prompt rendered within Redfast, Sendgrid requires the end user's email be sent in an encrypted form using their API.

## End User Privacy

Redfast takes end user privacy seriously and does not share end user information provided by our customers to any third party, nor does Redfast aggregate third party data against customer end user data. Where applicable, Redfast utilizes identifiers recommended by device platforms (i.e. IDFV for Apple and Instance ID for Android) as utilized within customer apps. Hardware and network identifiers like MAC address and IP address are never used for identification purposes.

## SOC2 Type II

Redfast has achieved the System and Organization Controls (SOC) 2 Type II compliance via audit by a trusted AICPA firm to validate the company's internal controls with respect to information security. This includes a detailed review of internal controls including policies, procedures, and infrastructure regarding data security, firewall configurations, change management, logical access, backup management, business continuity and disaster recovery, security incident response, and other critical areas of the business.

Customers on a Growth or Enterprise plan may reach out to their customer success manager to obtain a copy of the report.

## GDPR / CCPA Compliance

See the Redfast [Privacy Policy](https://www.redfast.com/privacy)for information on GDPR and CCPA compliance.

## Suppression List

A customer may inform Redfast of user IDs that have opted out of further data processing. In this case, Redfast will immediately cease processing any information it receives associated with those user IDs.

## Data Retention

On an ongoing basis, Redfast will retain end-user usage data no longer than ninety days past the latest activity encountered by that end user unless extended lookback has been enabled. For customers who request the extended lookback feature, data is retained for one year. For end users that have been added to the Suppression List, Redfast will not retain any history of the end user's usage.

## API Access

Any direct integration with third party systems that you configure within Redfast should be secured with a developer specific API key assigned to Redfast. Redfast uses publicly or privately supplied documentation with these APIs to establish communications between the systems. An alternative to API access for 1-Click actions is redirecting the user to an existing screen within your app to perform the desired action. However this will come with an adverse impact to conversion rate.

## Apple App Store

In December 2020, Apple introduced new requirements for app developers to outline their apps' data collection and usage policy. The following specifies data collected by Redfast.

Data collected by default: 

* Identifiers: Redfast does not create a user identifier. A User ID created by your system is passed on to the Redfast SDK. Please note that your system may be using Apple's IDFV identifier and passing that to the Redfast SDK. Consult with your engineer for specific details. 
* Usage Data: Session related information. Optionally, additional user events that you elect to be tracked using Redfast.
