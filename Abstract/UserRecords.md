# General informations

A user identity contain various kind of informations with access rules based on the requester identity and location (managed computer or not).

Here you will find all general informations useful to interact with user data. A dedicated API documentation will exist to explain how to access. This page is only focussed on the goal of each data.

For each user identity, informations are organized by scope. A scope is always linked to an access rules.

Planned scopes are:
* Generic Account Informations;
* Organization Directory Informations;
* Human Resources Informations;
* Authentication Informations;
* App Centric Informations;

In a more generic way, accounts are never deleted. The software does not allow this action in most admin UI. From management point of view, removing accounts does not make sense and lead the organization to a lack of traceability. The recommended scenario is to disable accounts.

## Generic Account Informations

Generic account informations contain all basic informations related to the identity from a computer point of view.

|    Information     |     Nature    |     Usage     |
| ------------------ | ------------- | ------------- |
| Given Name         | String        | First name or equivalent  |
| Surname            | String        | Last name or equivalent  |
| Photo              | URL to PNG    | Official user picture |
| Display Name       | String        | Name to show in most display field (system UI, mail sender's description, etc.)  |
| Short Name         | String        | A really short name for quick access and home folder (like a trichar or generated identifier). Must be unique across users and groups. |
| Principal Name     | String        | In a form of an e-mail, address, should be use as the common login name for most services. Domain name used should be dedicated to the IT services and be different from the e-mail domain (like user@corp.example.com). Must be unique across users and groups. |
| Numeric Unique ID  | Integer       | An incremental numeric ID starting from 1789 here for system who need id. Modern software should not use this kind of ID. Must be unique. |
| Globally Unique ID | String        | An UUID used as globally unique ID that should be used by every software nowadays to uniquely identify an identity. Must be unique. |
| Creation Date      | Date          | Date of initial account creation |
| Modification Date  | Date          | Date of last account change |
| Deactivation Date  | Date          | After this date, accounts are inaccessible. Deactivated account has this field set to January First, 1970 |


## Organization Directory Informations

This scope contain all informations related to the internal directory for the organization using EasyLogin. In term of personal data protection, this scope does not contain anything personal. It's only organization related informations and should not be under any kind of regulation in most countries.

|    Information     |      Nature     |     Usage     |
| ------------------ | --------------- | ------------- |
| e-mail             | String          | Main e-mail address that should be used everywhere |
| e-mail aliases     | Array of String | Other organization's related e-mail address that could identify this user |
| Address            | String          | Office address, free form without city, postal code and country |
| Postal Code        | String          | Office address, Postal Code, ZIP Code, or anything close to |
| City               | String          | Office address, City names (with state if needed) |
| Country            | String          | Office address, Country name |
| Phone              | String          | Direct line, with extension if needed (like +33123456789,100), should be the only public phone field for company using correct phone service provider |
| Mobile Phone       | String          | Mobile phone number |
| Internal Phone     | String          | Internal only phone number (like 100) |

## Human Resources Informations

This scope contain all informations related to the user outside the company, dedicated to HR usage. In term of personal data protection, this scope contain only personal and sensitive informations. In most countries, this scope will be protected by local laws.

|    Information     |     Nature    |     Usage     |
| ------------------ | ------------- | ------------- |
| Full Name          | String        | Full string containing the complete user identity according to the country usage (like all names in right orders, birth name and maiden name, etc.) |
| Common Name        | String        | Common but formal user designation according to the country usage (like First name LAST NAME) |
| Address            | String        | Home address, free form without city, postal code and country |
| Postal Code        | String        | Home address, Postal Code, ZIP Code, or anything close to |
| City               | String        | Home address, City name (with state if needed) |
| Country            | String        | Home address, Country name |
| SSN                | String        | Social Security number |
| Birth date         | Date          | Birth date if available |
| Principal Phone    | String        | Principal personal phone number |
| Secondary Phone    | String        | Secondary personal phone number |

## Authentication Informations

Authentication informations contain all informations needed to challenge the user to prove who he or she claim to be.

That could be a hash, a PBFDK string, a public certificate, a pre computed DIGEST hash and challenge.

## App Centric Informations

App centric informations are organized by bundle ID, root object must be a dict, everything under is free form JSON compatible.
