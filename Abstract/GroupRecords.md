# General informations

A group record contain various kind of informations accessible based on ACL.

Here you will find all general informations useful to interact with group infos. A dedicated API documentation will exist to explain how to access. This page is only focussed on the goal of each data.

For each group, informations available are:
* direct member;
* nested groups;
* all members.

The last one is an optional computed value use to flatten the group inheritence. Inheritence is something hard to compute when it's time to work with group and ACL. The server will provide raw info and do the work to provide computed info, letting to the consumer code use the choice to use the most useful value depending on the usecase.

In term of access level, there is three kind of access right:
* can see all details;
* know that the group exist but doesn't see the details;
* don't know that the group exist.

## Generic Group Informations

Generic group informations contain all basic informations related to the group iself.

|    Information     |     Nature    |     Usage     |
| ------------------ | ------------- | ------------- |
| Common Name        | String        | Common name for the group  |
| Description        | String        | Description for this group  |
| Photo              | URL to PNG    | Official group picture |
| Short Name         | String        | A really short name for quick access, could be used for the e-mail too. Must be unique across users and groups |
| Principal Name     | String        | In a form of an e-mail, address, should be use as the common ID for most services. Domain name used should be dedicated to the IT services and be different from the e-mail domain (like group@corp.example.com). It's recommended to use the shortname as ID. |
| E-mail             | String        | E-mail address used as mailling list for this group. |
| Numeric Unique ID  | Integer       | An incremental numeric ID starting from 1789 here for system who need id. Modern software should not use this kind of ID |
| Globally Unique ID | String        | An UUID used as globally unique ID that should be used by every software nowadays to uniquely identify an identity |
| Creation Date      | Date          | Date of initial account creation |
| Modification Date  | Date          | Date of last account change |


## Recorded Informations

Informations directly stored into the group record

|    Information     |      Nature     |     Usage     |
| ------------------ | --------------- | ------------- |
| Direct Members     | Array of String | Array of GUID representing the members. Memebers are users only |
| Nested Groups      | Array of String | Array of GUID representing the nested groups (first level only). |

## Computed Informations

Informations computed by the server for the consumer code. Should be skiped by default and could be provided based on a header option in the HTTP request (most advanced system like an operating system already know how to do this job, only third part softwares have issue with this).

|    Information     |      Nature     |     Usage     |
| ------------------ | --------------- | ------------- |
| All Members        | Array of String | Array of GUID representing all the members. |

## App Centric Informations

App centric informations are organized by bundle ID, root object must be a dict, everything under is free form JSON compatible.
