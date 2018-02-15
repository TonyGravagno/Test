Admin Guide

[![Product Site](Common_Content/images//image_left.png)](http://www.mantisbt.org)[![Documentation Site](Common_Content/images//image_right.png)](http://www.mantisbt.org/documentation.php)

MantisBT 2.0

Admin Guide
===========

Reference for Administrators
----------------------------

### ![](./images/mantis_logo.png)

### MantisBT Development Team

`[mantisbt-dev@lists.sourceforge.net](mailto:mantisbt-dev@lists.sourceforge.net)`

Legal Notice
============

Copyright © 2016 MantisBT team. This material may only be distributed subject to the terms and conditions set forth in the GNU Free Documentation License (GFDL), V1.2 or later (the latest version is presently available at [http://www.gnu.org/licenses/fdl.txt](http://www.gnu.org/licenses/fdl.txt)).

**Abstract**

This book is targeted at MantisBT administrators, and documents the installation, upgrade, configuration, customization and administration tasks required to operate the software.

[1\. About MantisBT](#admin.about)

[1.1. What is MantisBT?](#admin.about.what)

[1.2. Who should read this manual?](#admin.about.who)

[1.3. License](#admin.about.license)

[1.4. How to get it?](#admin.about.download)

[1.5. About the Name](#admin.about.name)

[1.6. History](#admin.about.history)

[1.7. Support](#admin.about.support)

[1.8. MantisBT News](#admin.about.news)

[1.9. Versioning](#admin.about.versioning)

[2\. Installation](#admin.install)

[2.1. Overview](#admin.install.overview)

[2.2. System Requirements](#admin.install.requirements)

[2.2.1. Server Hardware Requirements](#admin.install.requirements.hardware)

[2.2.2. Server Software Requirements](#admin.install.requirements.software)

[2.2.3. Client Requirements](#admin.install.requirements.client)

[2.3. Pre-installation / upgrade tasks](#admin.install.preinstall)

[2.4. New Installation](#admin.install.new)

[2.5. Upgrading](#admin.install.upgrade)

[2.6. Configure your installation](#admin.install.config)

[2.7. Post-installation and upgrade tasks](#admin.install.postcommon)

[2.8. Post-installation tasks](#admin.install.postinstall)

[2.9. Post-upgrade tasks](#admin.install.postupgrade)

[2.10. Backups](#admin.install.backups)

[2.10.1. MySQL Backups](#admin.install.backups.mysql)

[2.11. Uninstall](#admin.install.uninstall)

[3\. User Management](#admin.user)

[3.1. Creating User Accounts](#admin.user.create)

[3.2. Enabling/Disabling User Accounts](#admin.user.enable)

[3.3. Deleting User Accounts](#admin.user.delete)

[3.4. User Signup](#admin.user.signup)

[3.5. Forgot Password and Reset Password](#admin.user.passwordreset)

[3.6. Impersonating a user](#admin.user.impersonation)

[3.7. Changing Password](#admin.user.passwordchange)

[3.8. Pruning User Accounts](#admin.user.pruning)

[3.9. Authorization and Access Levels](#admin.user.access)

[3.10. Auto Creation of Accounts on Login](#admin.user.autocreate)

[3.11. User Preferences](#admin.user.prefs)

[3.12. User Profiles](#admin.user.profiles)

[4\. Issue Lifecycle and Workflow](#admin.lifecycle)

[4.1. Issue Creation](#admin.lifecycle.create)

[4.2. Issue Statuses](#admin.lifecycle.status)

[4.3. Workflow](#admin.lifecycle.workflow)

[4.3.1. Workflow Transitions](#admin.lifecycle.workflow.transitions)

[4.3.2. Workflow Thresholds](#admin.lifecycle.workflow.thresholds)

[5\. Configuration](#admin.config)

[5.1. Introduction](#admin.config.intro)

[5.2. Database](#admin.config.database)

[5.3. Path](#admin.config.path)

[5.4. Webserver](#admin.config.webserver)

[5.5. Configuration Settings](#admin.config.settings)

[5.6. Security and Cryptography](#admin.config.security)

[5.7. Signup and Lost Password](#admin.config.signup)

[5.8. Email](#admin.config.email)

[5.9. Version](#admin.config.version)

[5.10. Language](#admin.config.language)

[5.11. Display](#admin.config.display)

[5.12. Time](#admin.config.time)

[5.13. Date](#admin.config.date)

[5.14. Time Zone](#admin.config.timezone)

[5.15. News](#admin.config.news)

[5.16. Default Preferences](#admin.config.defaults)

[5.17. Summary](#admin.config.summary)

[5.18. Bugnote](#admin.config.bugnote)

[5.19. File Upload](#admin.config.uploads)

[5.20. HTML](#admin.config.html)

[5.21. Authentication](#admin.config.auth)

[5.21.1. Global authentication parameters](#admin.config.auth.global)

[5.21.2. LDAP authentication method parameters](#admin.config.auth.ldap)

[5.22. Status Settings](#admin.config.status)

[5.23. Filters](#admin.config.filters)

[5.24. Misc](#admin.config.misc)

[5.25. Cookies](#admin.config.cookies)

[5.26. Speed Optimisation](#admin.config.speed)

[5.27. Reminders](#admin.config.reminders)

[5.28. Bug History](#admin.config.bughistory)

[5.29. Sponsorship](#admin.config.sponsorship)

[5.30. Custom Fields](#admin.config.customfields)

[5.31. My View Settings](#admin.config.myview)

[5.32. Relationship Graphs](#admin.config.relationship)

[5.33. Wiki Integration](#admin.config.wiki)

[5.34. Sub-Projects](#admin.config.subprojects)

[5.35. Field Visibility](#admin.config.fields)

[5.36. System Logging and Debugging](#admin.config.logging)

[5.37. Time Tracking](#admin.config.timetracking)

[5.38. API](#admin.config.api)

[5.38.1. Disabling the webservice API](#admin.config.api.disable)

[5.39. Anti-Spam Configuration](#admin.config.antispam)

[5.40. Due Date](#admin.config.duedate)

[5.41. User Management](#admin.config.users)

[5.42. View Page Settings](#admin.config.view)

[6\. Page descriptions](#admin.pages)

[6.1. Login page](#admin.pages.login)

[6.2. Main page](#admin.pages.main)

[6.3. View Issues page](#admin.pages.filter)

[6.4. Issue View page](#admin.pages.issueview)

[6.5. Issue Change Status page](#admin.pages.issuestatus)

[6.6. Issue Edit page](#admin.pages.issueedit)

[6.7. My Account Page](#admin.pages.account)

[6.7.1. Preferences](#admin.pages.account.prefs)

[6.7.2. Profiles](#admin.pages.account.profiles)

[6.7.3. Manage Columns](#admin.pages.account.managecolumns)

[6.7.4. API Tokens](#admin.pages.account.apitokens)

[6.8. System Management Pages](#admin.pages.manage)

[6.8.1. Manage Users](#admin.pages.manage.users)

[6.8.2. Manage Projects Page](#admin.pages.manage.projects)

[6.8.3. Manage Custom Fields](#admin.pages.manage.customfields)

[6.8.4. Manage Global Profiles](#admin.pages.manage.profiles)

[6.8.5. Manage Configuration](#admin.pages.manage.config)

[6.9. Monitor Issue](#admin.pages.monitor)

[6.10. Reopen Issue](#admin.pages.reopen)

[6.11. Delete Issue](#admin.pages.delete)

[6.12. Close Issue](#admin.pages.close)

[6.13. Assign to Me](#admin.pages.assigntome)

[6.14. Resolve Issue](#admin.pages.resolve)

[6.15. News Syndication](#admin.pages.news)

[7\. Customizing MantisBT](#admin.customize)

[7.1. Strings / Translations](#admin.customize.strings)

[7.2. Custom Fields](#admin.customize.customfields)

[7.2.1. Overview](#admin.customize.customfields.overview)

[7.2.2. Custom Field Definition](#admin.customize.customfields.definitions)

[7.2.3. Adding/Editing Custom Fields](#admin.customize.customfields.editing)

[7.2.4. Linking/Unlinking/Ordering Existing Custom Fields in Projects](#admin.customize.customfields.linking)

[7.2.5. Localizing Custom Field Names](#admin.customize.customfields.localize)

[7.2.6. Dynamic default values](#admin.customize.customfields.defaults)

[7.2.7. Dynamic values for Enumeration Custom Fields](#admin.customize.customfields.dynamic)

[7.3. Enumerations](#admin.customize.enums)

[7.4. Email Notifications](#admin.customize.email)

[7.5. Customizing Status Values](#admin.customize.status)

[7.6. Custom Functions](#admin.customize.customfuncs)

[7.6.1. Default Custom Functions](#admin.customize.customfuncs.defined)

[7.6.2. Example Custom Function Override](#admin.customize.customfuncs.example)

[8\. Authentication](#admin.auth)

[8.1. Standard Authentication](#admin.auth.standard)

[8.2. LDAP and Microsoft Active Directory](#admin.auth.ldap)

[8.3. Basic Authentication](#admin.auth.basic)

[8.4. HTTP Authentication](#admin.auth.http)

[8.5. Deprecated authentication methods](#admin.auth.deprecated)

[9\. Troubleshooting](#admin.troubleshooting)

[9.1. Application Errors](#admin.troubleshooting.errors)

[9.1.1. Error 2800 - Invalid form security token](#admin.troubleshooting.errors.2800)

[10\. Project Management](#admin.project)

[10.1. Change Log](#admin.project.changelog)

[10.2. Roadmap](#admin.project.roadmap)

[10.3. Time Tracking](#admin.project.timetracking)

[10.4. Graphs](#admin.project.graphs)

[10.5. Summary Page](#admin.project.summary)

[11\. Contributing to MantisBT](#admin.contributing)

[11.1. Talent and Time](#admin.contributing.develop)

[11.2. Recommend MantisBT to Others](#admin.contributing.share)

[11.3. Blog about MantisBT](#admin.contributing.blog)

[11.4. Integrate with MantisBT](#admin.contributing.integrate)

[A. Revision History](#appe-Admin_Guide-Revision_History)

⁠Chapter 1. About MantisBT
==========================

[1.1. What is MantisBT?](#admin.about.what)

[1.2. Who should read this manual?](#admin.about.who)

[1.3. License](#admin.about.license)

[1.4. How to get it?](#admin.about.download)

[1.5. About the Name](#admin.about.name)

[1.6. History](#admin.about.history)

[1.7. Support](#admin.about.support)

[1.8. MantisBT News](#admin.about.news)

[1.9. Versioning](#admin.about.versioning)

⁠1.1. What is MantisBT?
-----------------------

MantisBT is a web based bug tracking system that was first made available to the public in November 2000. Over time it has matured and gained a lot of popularity, and now it has become one of the most popular open source bug/issue tracking systems. MantisBT is developed in PHP, with support to multiple database backends including MySQL, MS SQL and PostgreSQL.

MantisBT, as a PHP script, can run on any operating system that is supported by PHP and has support for one of the DBMSes that are supported. MantisBT is known to run fine on Windows, Linux, OS/2, Mac OS X, System i and a variety of Unix operating systems.

⁠1.2. Who should read this manual?
----------------------------------

This manual is targeted for the person responsible for evaluating, installing and maintaining MantisBT in a company. Typically we refer to this person as the MantisBT administrator.

⁠1.3. License
-------------

MantisBT is released under the terms of [GNU General Public License (GPL)](http://www.gnu.org/copyleft/gpl.html). MantisBT is free to use and modify. It is free to redistribute as long as you abide by the distribution terms of the [GPL](http://www.gnu.org/copyleft/gpl.html).

⁠1.4. How to get it?
--------------------

MantisBT is available in several Linux distributions including: Debian, Ubuntu, Fedora, Gentoo, Frugalware and others. Hence, if you are running Linux, start by checking if your distribution has a package for MantisBT. If not, or if the package is not up-to-date with the latest MantisBT version, then you may want to download it directly from [here](http://www.mantisbt.org/download.php).

For Windows, Mac OS X and other operating systems, use the link provided above to download MantisBT. The download is compressed in tar.gz or zip format. Both formats can be unpacked using tools like [7-Zip](http://www.7-zip.org/) (in case of Windows).

Note that at any point in time there are typically two "latest" MantisBT releases that are available for download. The latest production release (stable), and the latest development release which can be an alpha or a release candidate. It is not recommended to use development releases in production specially if it is still in the alpha stage unless the administrator is familiar with PHP and is able to troubleshoot and fix any issues that may arise.

⁠1.5. About the Name
--------------------

When initially seeking to name this project Ken ran into a problem every programmer encounters. What is a good name? It has to be descriptive, unique, and not too verbose. Additionally having multiple meanings would be a nice touch. Quickly ruled out were php\*Something\* names which, incidentally, although popular, do not seem to be condoned by the PHP Group developers. Drawing inspiration from Open Source projects like Apache, Mozilla, Gnome, and so forth resulted in two eventual choices: Dragonfly and Mantis. Dragonfly was already the name of a webmail package. So the name became Mantis.

Praying Mantis are insects that feed primarily on other insects and bugs. They are extremely desirable in agriculture as they devour insects that feed on crops. They are also extremely elegant looking creatures. So, we have a name that is fairly distinctive and descriptive in multiple ways. The BT suffix stands for "Bug Tracker" and distinguishes this project from general usage of the word Mantis. However, over time the project was typically referred to as Mantis.

⁠1.6. History
-------------

Kenzaburo Ito and a friend originally created a bug tracker as an internal tool for their pet project. A search for good, free packages came up with nothing suitable so they wrote their own. After a rewrite and cleanup it was made available to the public via the GNU General Public License (GPL). The GPL was chosen partly because of his belief that development tools should be cheap or free. In 2002, Ken was joined by Jeroen Latour, Victor Boctor and Julian Fitzell to be the administrators and the core development team of MantisBT. This marks a new era in MantisBT lifetime where it is now a team project.

⁠1.7. Support
-------------

There are plenty of resources to help answer support queries. Following are the main ones:

*   [Forums](http://www.mantisbt.org/forums/) \- The forums are one of the most popular destinations for getting MantisBT support. Start off by searching the forums for your questions, if not found, then go ahead and submit a question.
    
*   [Mailing lists](http://www.mantisbt.org/mailinglists.php) \- Several lists are available, each of them with its own, specific purpose. Note that posting messages is restricted to subscribers so you will have to register before you can send messages; however, there are public archives available if you're only interested in reading.
    
*   [Gitter](https://gitter.im/mantisbt/mantisbt) is a browser-based, on-line chat that has mainly replaced the team's use of IRC. In the main chat room, you can have a live discussion with the developers and other MantisBT users. Gitter supports all modern browsers and also offers Android and iOS-based clients, as well as an [IRC bridge](https://irc.gitter.im/).
    
*   [IRC](http://www.mantisbt.org/irc.php) \- The IRC channel not very active anymore, as the developers have moved on to using Gitter for live discussions; nevertheless, the channel is still open. There are many free IRC clients: XChat (for Linux), [HexChat](http://hexchat.github.io/), [IceChat](http://www.icechat.net/) amongst others. You can also use [Web Chat](http://webchat.freenode.net/) to connect to IRC via your web browser, which may also be useful when you're behind a firewall that blocks the IRC port. The IRC channel logs are archived and made [available on the MantisBT web site](http://www.mantisbt.org/irclogs.php).
    
*   [Wiki](http://www.mantisbt.org) \- The MantisBT Wiki has information related to "How To (recipes)", FAQ, feature requirements, plugins etc.
    
*   Search - A good way for locating an answer to your question or finding more information about a topic is to search across all MantisBT website and the Internet via your favorite search engine, e.g. [Google](http://www.google.com) or [Bing](http://www.bing.com).
    

**Note**

Support questions should not be sent directly to MantisBT developers or through the MantisBT website's contact pages.

Also, our [bug tracker](http://mantisbt.org/bugs/) is reserved for reporting issues with the software, and _must not be used for support requests_.

⁠1.8. MantisBT News
-------------------

There are several ways to keep up to date with MantisBT news. These include:

*   We send release announcements and important updates to users registered on our [official bugtracker](http://www.mantisbt.org/bugs). To get onto our mailing list, users will have to signup there and verify their email address. This same account can also be used to report, monitor, and comment on issues relating to MantisBT.
    
*   [MantisBT Blog](http://www.mantisbt.org/blog/) is used to communicate announcements about new releases, topics relating to MantisBT, etc. Users are encouraged to subscribe to the RSS feed to know when new posts are posted there.
    
*   [Twitter](http://twitter.com/mantisbt) is used to notify users about up-to-date details about what is happening with MantisBT development. Twitter users are encouraged to follow "@mantisbt".
    

⁠1.9. Versioning
----------------

Our release numbering convention follows the guidelines of [Semantic Versioning](http://semver.org/). Given a version number _Major.Minor.Patch_ and an optional _Suffix_ (eg. 1.3.0-rc.1):

*   Major - Indicates a very large change in the core package. Rewrites or major milestones. API changes which are not backwards-compatible.
    
*   Minor - Introduction of new features or significant changes in functionality, in a backwards-compatible manner.
    
*   Patch - Bug fixes, maintenance and security releases.
    
*   Suffix - Optional, indicates a development release.
    
    *   a_N_ or alpha._N_ for alpha releases,
        
    *   b_N_ or beta._N_ for beta releases, or
        
    *   rc_N_ or rc._N_ for release candidates.
        
    
    Absence of suffix indicates a stable release.
    

⁠Chapter 2. Installation
========================

[2.1. Overview](#admin.install.overview)

[2.2. System Requirements](#admin.install.requirements)

[2.2.1. Server Hardware Requirements](#admin.install.requirements.hardware)

[2.2.2. Server Software Requirements](#admin.install.requirements.software)

[2.2.3. Client Requirements](#admin.install.requirements.client)

[2.3. Pre-installation / upgrade tasks](#admin.install.preinstall)

[2.4. New Installation](#admin.install.new)

[2.5. Upgrading](#admin.install.upgrade)

[2.6. Configure your installation](#admin.install.config)

[2.7. Post-installation and upgrade tasks](#admin.install.postcommon)

[2.8. Post-installation tasks](#admin.install.postinstall)

[2.9. Post-upgrade tasks](#admin.install.postupgrade)

[2.10. Backups](#admin.install.backups)

[2.10.1. MySQL Backups](#admin.install.backups.mysql)

[2.11. Uninstall](#admin.install.uninstall)

This chapter explains how to install or upgrade MantisBT.

⁠2.1. Overview
--------------

The table below contains a high-level overview of the processes. Refer to the corresponding sections for details.

New Installation

Upgrade

1.  [Section 2.2, “System Requirements”](#admin.install.requirements)
    
2.  [Section 2.3, “Pre-installation / upgrade tasks”](#admin.install.preinstall)
    
3.  [Section 2.4, “New Installation”](#admin.install.new)
    
4.  [Section 2.6, “Configure your installation”](#admin.install.config)
    
5.  [Section 2.7, “Post-installation and upgrade tasks”](#admin.install.postcommon)
    
6.  [Section 2.8, “Post-installation tasks”](#admin.install.postinstall)
    

1.  [Section 2.3, “Pre-installation / upgrade tasks”](#admin.install.preinstall)
    
2.  [Section 2.10, “Backups”](#admin.install.backups)
    
3.  Put the site down for maintenance
    
4.  [Section 2.5, “Upgrading”](#admin.install.upgrade)
    
5.  [Section 2.7, “Post-installation and upgrade tasks”](#admin.install.postcommon)
    
6.  [Section 2.9, “Post-upgrade tasks”](#admin.install.postupgrade)
    

⁠2.2. System Requirements
-------------------------

### ⁠2.2.1. Server Hardware Requirements

MantisBT has modest hardware requirements. It requires a computer that is able to run the server software (see [Section 2.2.2, “Server Software Requirements”](#admin.install.requirements.software)).

*   Server type
    
    The server can be a shared public web server or a dedicated co-located box.
    
*   CPU and Memory
    
    As for any web application, you should size your server based on the traffic on the site.
    
*   Disk
    
    The application code is less than 30 MB.
    
    The amount of disk space required for the database will vary depending on the RDBMS and the volume of data, the main driving factor being the expected number and size of attachments.
    

### ⁠2.2.2. Server Software Requirements

All of the required software is free for commercial and non-commercial use (open source). Please refer to the table in [Section 2.2.2.1, “Versions compatibility table”](#admin.install.requirements.software.versions) for minimum and recommended versions.

*   Operating System
    
    MantisBT runs on Windows, MacOS, OS/2, Linux, Solaris, the BSDs, and just about anything that supports the required server software.
    
*   Web Server
    
    MantisBT is mainly tested with [Microsoft IIS](http://www.microsoft.com/iis) and [Apache](http://www.apache.org/). However, it is expected to work with any recent web server software.
    
    File Extensions: MantisBT uses only _.php_ files. If your webserver is configured for other extensions (e.g. .PHP3, .PHTML) then you will have to request the administrator to add support for .PHP files. This should be a trivial modification. Further details can be found in the [PHP documentation](http://www.php.net/manual/en/installation.php)
    
*   [PHP](http://www.php.net/)
    
    The web server must support PHP. It can be installed as CGI or any other integration technology.
    
*   PHP extensions
    
    MantisBT is designed to work in as many environments as possible. Hence the required extensions are minimal and many of them are optional affecting only one feature.
    
    Mandatory extensions
    
    *   The extension for the RDBMS being used ( mysqli, pgsql, oci8, sqlsrv )
        
    *   _mbstring_ \- Required for Unicode (UTF-8) support.
        
    *   _Fileinfo_ \- Guesses the MIME type of attachments
        
        Without this extension, file attachment previews and downloads do not work as MantisBT won't be able to send the Content-Type header to a browser requesting an attachment.
        
        This extension is included by default from PHP version 5.3.x and above.
        
    
    Optional extensions
    
    *   _Curl_ \- required for the Twitter integration feature
        
    *   _GD_ \- required for the captcha feature
        
    
*   Database
    
    MantisBT requires a database to store its data. The supported RDBMS are:
    
    *   MySQL (or one of its forks, e.g. MariaDB)
        
    *   PostgreSQL
        
    
    Experimental support is also available for
    
    *   Microsoft SQL Server
        
    *   Oracle
        
    
    Experimental support means that manual intervention by a skilled Database Administrator may be required to complete the installation, and/or that there may be known issues or limitations when using the software. Please refer to our [Issue tracker](https://mantisbt.org/bugs/), filtering on categories _db mssql_ and _db oracle_ to find out more about those.
    
    **Note**
    
    Please note that the MantisBT development team mainly works with MySQL, so testing for other drivers is not as extensive as we mainly rely on community contributions to improve support and fix issues with other RDBMS.
    
    We therefore recommend MySQL to store your database.
    

#### ⁠2.2.2.1. Versions compatibility table

Category

Package

Minimum Version

Recommended

Comments

RDBMS

MySQL

5.5.35

5.6 or above

PHP extension: mysqli

MariaDB

5.5.35

10.x or above

PHP extension: mysqli

PostgreSQL

9.2

9.2 or later

PHP extension: pgsql

MS SQL Server

2012

2012 or later

PHP extension: sqlsrv

Oracle

11gR2

11gR2 or later

PHP extension: oci8

PHP

PHP

5.5.x

7.0 or later

See above for PHP extensions

Web Server

Apache

2.2.x

2.4.x

lighttpd

1.4.x

1.4.x

nginx

1.10.x

1.10.x

IIS

7.5

8.0

Windows Server 2008 R2 SP1 or later

Our minimum requirements are generally based on availability of support for the underlying software by their respective vendors. In some cases, we do require a specific version because we rely on a feature that is not available in older releases.

**Warning**

Running MantisBT with versions of the software components lower than the minimum requirements listed above is not supported.

### ⁠2.2.3. Client Requirements

MantisBT should run on all recent browsers in the market, including but not limited to:

*   Firefox 45 and above
    
*   Internet Explorer 10 and above
    
*   Chrome
    
*   Safari
    
*   Opera
    

⁠2.3. Pre-installation / upgrade tasks
--------------------------------------

These tasks cover the download and deployment of MantisBT, and should be performed prior to any new installation or upgrade.

1.  Download MantisBT (see [Section 1.4, “How to get it?”](#admin.about.download))
    
2.  Transfer the downloaded file to your webserver
    
    This can be done using whatever method you like best (ftp, scp, etc). You will need to telnet/ssh into the server machine for the next steps.
    
3.  Extract the release
    
    It is highly recommended to maintain a separate directory for each release. This not only avoids mismatch between versions, (files may have been added or removed) but also provides an easy path to downgrade your installation, should you need to.
    
    The usual command is (1 step):
    
    tar -xzf _filename.tar.gz_
    
    OR (2 steps):
    
    gunzip _filename.tar.gz_
    tar -xf _filename.tar_
    
    Other file archiving tools such as [7-Zip](http://www.7-zip.org/) should also be able to handle decompression of the archive.
    
    The extraction process should create a new directory like _mantisbt-1.3.x_
    
4.  Rename the directory
    
    For new installations, you may want to rename the directory just created to something simpler, e.g. _mantisbt_
    
    mv mantisbt-1.3.x mantisbt
    

⁠2.4. New Installation
----------------------

This chapter explains how to perform a new installation of MantisBT.

Start by checking [Section 2.2, “System Requirements”](#admin.install.requirements) and installing the appropriate version of required software.

Once that is done, execute the installation script. From your web browser, access

http://yoursite/mantisbt/admin/install.php

The installation procedure will go through the following steps:

1.  The script checks basic parameters for the web server
    
2.  Provide required information for the installation
    
    *   database type
        
    *   database server hostname
        
    *   user and password
        
        Required privileges: SELECT, INSERT, UPDATE, and DELETE
        
    *   high-privileged database account
        
        Additional privileges required: INDEX, CREATE, ALTER, and DROP
        
        If this account is not specified, the database user will be used.
        
    
3.  Click the _Install/Upgrade Database_ button
    
4.  The script creates the database and tables.
    
    The default Administrator user account is created at this stage, to allow the initial login and setup of MantisBT.
    
5.  The script attempts to write a basic _config_inc.php_ file to define the database connection parameters.
    
    This operation may fail if the web server's user account does not have write permissions to the directory (which is recommended for obvious security reasons). In this case, you will have to manually create the file and copy/paste the contents from the page.
    
6.  The script perform post installation checks on the system.
    
    Review and correct any errors.
    

⁠2.5. Upgrading
---------------

This chapter explains how to upgrade an existing MantisBT installation.

Start by Performing the steps described in [Section 2.3, “Pre-installation / upgrade tasks”](#admin.install.preinstall) above.

1.  Put the site down for maintenance
    
    cp mantis\_offline.php.sample mantis\_offline.php
    
    This will prevent users from using the system while the upgrade is in progress.
    
2.  Always _Backup your code, data and config files_ before upgrading !
    
    This includes your Mantis directory, your attachments, and your database. Refer to [Section 2.10, “Backups”](#admin.install.backups) for details.
    
3.  Copy the configuration files
    
    To preserve your system settings, you should copy the files listed below to subdirectory config of the new directory. You might have to copy as well other custom files such as logo, favicon, css, etc.
    
    `config_inc.php`, the _Custom Strings File_ (`custom_strings_inc.php` by default, see [Section 7.1, “Strings / Translations”](#admin.customize.strings)), `custom_constants_inc.php` and `custom_functions_inc.php`
    
4.  Execute the upgrade script. From your web browser, access
    
    http://yoursite/mantisbt-NEW/admin/install.php
    
    where _mantisbt-NEW_ is the name of the directory where the new release was extracted
    
5.  Provide required information for the upgrade
    
    *   high-privileged database account
        
        Additional privileges required: INDEX, CREATE, ALTER, and DROP
        
        If this account is not specified, the database user will be used.
        
    
6.  Click the _Install/Upgrade Database_ button
    
7.  At the end of the upgrade, review and correct any warnings or errors.
    

**Upgrading large databases**

When processing large databases from versions older than 1.2, the upgrade script may fail during the conversion of date fields, leaving the system in an inconsistent (i.e. partially updated) state.

In this case, you should simply restart the upgrade process, which will resume where it left off. Note that you may have to repeat this several times, until normal completion.

Reference: MantisBT issue [12735](http://www.mantisbt.org/bugs/view.php?id=12735).

⁠2.6. Configure your installation
---------------------------------

There are many settings that you can adjust to configure and customize MantisBT. Refer to [Chapter 5, _Configuration_](#admin.config), as well as the _config\_defaults\_inc.php_ file for in depth explanations of the available options. Check out also [Chapter 7, _Customizing MantisBT_](#admin.customize) for further options to personalize your installation.

This step is normally only required for new installations, but when upgrading you may want to review and possibly customize any new configuration options.

Open or create the file _config_inc.php_ in subfolder config in an editor and add or modify any values as required. These will override the default values.

You may want to use the provided _config_inc.php.sample_ file as a starting point.

**Warning**

you should never edit the _config\_defaults\_inc.php_ file directly, as it could cause issues with future upgrades. Always store your custom configuration in your own _config_inc.php_ file.

⁠2.7. Post-installation and upgrade tasks
-----------------------------------------

Instructions in this section are common to both new installations and upgrades, and should be applied after completing either process.

1.  Test your configuration
    
    Load up _admin/check/index.php_ to validate whether everything is setup correctly, and take corrective action as needed.
    
2.  Delete the _admin_ folder
    
    Once you have confirmed that the install or upgrade process was successful, you should delete this directory
    
    rm -r admin
    
    For security reasons, the scripts within this directory should not be freely accessible on a live MantisBT site, particularly one which is accessible via the Internet, as they can allow unauthorized people (e.g. hackers) to gain technical knowledge about the system, as well as perform administrative tasks.
    
    **Warning**
    
    Omitting this important step will leave your MantisBT instance exposed to several potentially severe attacks, e.g. [issue #23173](http://mantisbt.org/bugs/view.php?id=23173) (if [mysqli.allow\_local\_infile](http://php.net/manual/en/mysqli.configuration.php#ini.mysqli.allow-local-infile) is enabled in php.ini).
    

⁠2.8. Post-installation tasks
-----------------------------

Instructions in this section should only be applied after a new installation

1.  Login to your bugtracker
    
    Use the default Administrator account. The id and password are _administrator / root_.
    
2.  Create a new Administrator account
    
    Go to _Manage > Manage Users_ and create a new account with 'administrator' access level.
    
3.  Disable or delete the default Administrator account
    
4.  Create a new Project
    
    Go to _Manage > Manage Projects_ and create a new project
    

⁠2.9. Post-upgrade tasks
------------------------

Instructions in this section should only be applied after upgrading an existing installation.

1.  Test the new release
    
    Perform any additional testing as appropriate to ensure the new version does not introduce any regressions.
    
2.  Switch the site to the new version
    
    The commands below should be executed from the web root (or wherever the mantisbt scripts are installed) and assume that the "live" directory (old version) is named _mantisbt_ and the new release directory is _mantisbt-1.3.x_.
    
    mv mantisbt mantisbt-old
    mv mantisbt-1.3.x mantisbt
    
3.  Put the site back on line
    
    rm mantis_offline.php
    
    This should be the final step in the upgrade process, as it will let users login again.
    

⁠2.10. Backups
--------------

It is strongly recommended to backup your MantisBT database on a regular basis. The method to perform this operation depends on which RDBMS you use.

Backups are a complex subject, and the specificities of implementing and handling them for each RDBMS are beyond the scope of this document. For your convenience, the section below provides a simple method to backup MySQL databases.

You should also consider implementing backups of your MantisBT code (which includes your configs and possibly customization), as well as issue attachments (if stored on disk) and project documents.

**Warning**

You should always backup your system (code and database) before upgrading !

### ⁠2.10.1. MySQL Backups

MySQL databases are easy to backup using the _mysqldump_ command:

mysqldump -u<username> -p<password> <database name> > <output file>

To restore a backup you will need to have a clean database. Then run:

mysql -u<username> -p<password> <database name> < <input file>

You can also perform both of these tasks using [phpMyAdmin](http://www.phpmyadmin.net/)

A good idea is to make a backup script and run it regularly through cron or a task scheduler (for Windows see [WinCron](http://www.wincron.com/) ). Using the current date in the filename can prevent overwriting and make cataloguing easier.

References and useful links:

*   [mysqlhotcopy documentation](http://dev.mysql.com/doc/refman/5.1/en/mysqlhotcopy.html)
    
*   [automysqlbackup script](http://sourceforge.net/projects/automysqlbackup/)
    

⁠2.11. Uninstall
----------------

It is recommended that you make a backup in case you wish to use your data in the future. See [Section 2.10, “Backups”](#admin.install.backups) for details.

To uninstall MantisBT:

*   Delete the MantisBT directory and all files and subdirectories.
    
*   Drop all MantisBT tables from the database, these can be identified by the configured prefix for the installation. The default prefix is 'mantis'.
    
*   Remove any customizations or additions that you may have made.
    

If you have the permissions to create/drop databases and you have a specific database for MantisBT that does not contain any other data, you can drop the whole database.

⁠Chapter 3. User Management
===========================

[3.1. Creating User Accounts](#admin.user.create)

[3.2. Enabling/Disabling User Accounts](#admin.user.enable)

[3.3. Deleting User Accounts](#admin.user.delete)

[3.4. User Signup](#admin.user.signup)

[3.5. Forgot Password and Reset Password](#admin.user.passwordreset)

[3.6. Impersonating a user](#admin.user.impersonation)

[3.7. Changing Password](#admin.user.passwordchange)

[3.8. Pruning User Accounts](#admin.user.pruning)

[3.9. Authorization and Access Levels](#admin.user.access)

[3.10. Auto Creation of Accounts on Login](#admin.user.autocreate)

[3.11. User Preferences](#admin.user.prefs)

[3.12. User Profiles](#admin.user.profiles)

⁠3.1. Creating User Accounts
----------------------------

In MantisBT, there is no limit on the number of user accounts that can be created. Typically, installations with thousands of users tend to have a limited number of users that have access level above REPORTER.

By default users with ADMINISTRATOR access level have access to create new user accounts. The steps to do that are:

*   Click "Manage" on Main Menu.
    
*   Click "Manage Users" (if not selected by default).
    
*   Click "Create New Account" button just below the alphabet key.
    
*   Enter user name, email address, global access level (more details about access levels later). Other fields are optional.
    
*   Click "Create Users".
    

Creating a user triggers the following actions:

*   Creating a user in the database.
    
*   If email notifications ($g\_enable\_email_notification) is set to ON, then the user will receive an email allowing them to activate their account and set their password. Otherwise, the account will be created with a blank password.
    
*   If email notifications ($g\_enable\_email\_notification) is set to ON, users with access level about $g\_notify\_new\_user\_created\_threshold_min will get a notification that a user account has been created. Information about the user like user name and email address are provided. The IP of the user that created the account is also included.
    

When the 'Protected' flag is set on a user account, it indicates that the account is a shared account (e.g. demo account) and hence users logged using such account will not be allowed to change account preferences and profile information.

The anonymous user account specified with the $g\_anonymous\_account option will always be treated as a protected user account. When you are creating the anonymous user account, the 'Protected' flag is essentially ignored because the anonymous user is always treated as a protected user.

⁠3.2. Enabling/Disabling User Accounts
--------------------------------------

The recommended way of retiring user accounts is to disable them. Scenarios where this is useful is when a person leaves the team and it is necessary to retire their account.

Once an account is disabled the following will be enforced:

*   All currently active sessions for the account will be invalidated (i.e. automatically logged out).
    
*   It will no longer be possible login using this account.
    
*   No further email notifications will be sent to the account once it is disabled.
    
*   The user account will not show anymore in lists like "assign to", "send reminder to", etc.
    

The disabling process is totally reversible. Hence, the account can be re-enabled and all the account history will remain intact. For example, the user will still have issues reported by them, assigned to them, monitored by them, etc.

⁠3.3. Deleting User Accounts
----------------------------

Another way to retire user accounts is by deleting them. This approach is only recommended for accounts that have not been active (i.e. haven't reported issues). Once the account is deleted, any issues or actions associated with such account, will be associated with user123 (where 123 is the code of the account that was deleted). Note that associated issues or actions are not deleted.

As far as the underlying database, after the deletion of a user, records with the user id as a foreign key will have a value that no longer exists in the users table. Hence, any tools that operate directly on the database must take this into consideration.

By default administrators are the only users who can delete user accounts. They can delete accounts by clicking Manage, Manage Users, locating the user to be deleted and opening it details page, then clicking on the "Delete User" button which deletes the user.

Note that "Deleting Users" is not a reversible process. Hence, if it is required to re-add the user account, it is not possible to recreate the user account so that it gets the same ID and hence retains its history. However, manually creating a record in the users table with the same id, can possibly do that. However, this approach is not recommended or supported.

⁠3.4. User Signup
-----------------

For open source and freeware projects, it is very common to setup MantisBT so that users can signup for an account and get a REPORTER access by default (configurable by the $g\_default\_new\_account\_access\_level configuration option). The signup process can be enabled / disabled using the $g\_allow_signup configuration option, which is enabled by default.

If user signup is enabled, then it is required that $g\_send\_reset_password is ON as well, and the e-mail settings properly configured (see [Section 5.8, “Email”](#admin.config.email)).

If email notifications ($g\_enable\_email\_notification) is set to ON, users with access level about $g\_notify\_new\_user\_created\_threshold_min will get a notification that a user account has been created. Information about the user like user name, email address, IP address are included in the email notification.

⁠3.5. Forgot Password and Reset Password
----------------------------------------

It is pretty common for users to forget their password. MantisBT provides two ways to handle such scenario: "Forgot Password" and "Reset Password".

"Forgot Password" is a self service scenario where users go to the login page, figure out they don't remember their password, and then click the "Lost your password?" link. Users are then asked for their user name and email address. If correct, then they are sent an email with a link which allows them to login to MantisBT and change their password.

"Reset Password" scenario is where a user reports to the administrator that they are not able to login into MantisBT anymore. This can be due to forgetting their password and possibly user name or email address that they used when signing up. The administrator then goes to Manage, Manage Users, locates the user account and opens its details. Under the user account details, there is a "Reset Password" button which the administrator can click to reset the password and trigger an email to the user to allow them to get into MantisBT and set their password. In the case where email notifications are disabled, resetting password will set the password to an empty string.

⁠3.6. Impersonating a user
--------------------------

Administrators are able to impersonate users in order to reproduce an issue reported by a user, test their access making sure they can access the expected projects/issues/fields, or to create API tokens for service accounts that are used to grant other systems limited access to MantisBT.

⁠3.7. Changing Password
-----------------------

Users are able to change their own passwords (unless their account is "protected"). This can be done by clicking on "My Account", and then typing the new password in the "Password" and "Confirm Password" fields, then clicking "Update User". Changing the password automatically invalidates all logged in sessions and hence the user will be required to re-login. Invalidating existing sessions is very useful in the case where a user going onto a computer, logs into MantisBT and leaves the computer without logging out. By changing the password from another computer, the session on the original computer automatically becomes invalidated.

⁠3.8. Pruning User Accounts
---------------------------

The pruning function allows deleting of user accounts for accounts that have been created more than a week ago, and they never logged in. This is particularly useful for users who signed up with an invalid email or with a typo in their email address address.

The account pruning can be done by administrators by going to "Manage", "Manage Users", and clicking the "Prune Accounts" button inside the "Never Logged In" box.

⁠3.9. Authorization and Access Levels
-------------------------------------

MantisBT uses access levels to define what a user can do. Each user account has a global or default access level that is associated with it. This access level is used as the access level for such users for all actions associated with public projects as well as actions that are not related to a specific project. Users with global access level less than $g\_private\_project_threshold will not have access to private projects by default.

The default access levels shipped with MantisBT out of the box are VIEWER, REPORTER, UPDATER, DEVELOPER, MANAGER and ADMINISTRATOR. Each features has several configuration options associated with it and identifies the required access level to do certain actions. For example, viewing an issue, reporting an issue, updating an issue, adding a note, etc.

For example, in the case of reporting issues, the required access level is configurable using the $g\_report\_bug\_threshold configuration option (which is defaulted to REPORTER). So for a user to be able to report an issue against a public project, the user must have a project-specific or a global access level that is greater than or equal to REPORTER. However, in the case of reporting an issue against a private project, the user must have project specific access level (that is explicitly granted against the project) that is higher than REPORTER or have a global access level that is higher than both $g\_private\_project\_threshold and $g\_report\_bug_threshold.

Note that project specific access levels override the global access levels. For example, a user may have REPORTER as the global access level, but have a MANAGER access level to a specific project. Or a user may have MANAGER as the global access level by VIEWER access to a specific project. Access levels can be overridden for both public and private projects. However, overriding access level is not allowed for users with global access ADMINISTRATOR.

Each feature typically has multiple access control configuration options to define what access level can perform the operation. For example, adding a note may require REPORTER access level, updating it note may require DEVELOPER access level, unless the note was added by the same user.

Such threshold configuration options can be set to a single access level, which means users with such threshold and above are authorized to perform the action. The other option is to specify an array of access levels which indicates that users with the explicitly specific thresholds are allowed to execute the actions.

It is also worth mentioning that the access levels are defined by the $g\_access\_levels\_enum\_string configuration option, and it is possible to customize such list. The default value for the available access levels is '10:viewer, 25:reporter, 40:updater, 55:developer, 70:manager, 90:administrator'. The instructions about how to customize the list of access levels will be covered in the customization section.

⁠3.10. Auto Creation of Accounts on Login
-----------------------------------------

If you are using a global user directory (LDAP, Active Directory), you may want to configure MantisBT so users who already exists in the directory will be automatically authenticated and added to MantisBT.

For example, a company may setup their MantisBT installation in a way, where its staff members that are already registered in their LDAP directory, should be allowed to login into MantisBT with the same user name and password. Another option could be if MantisBT is integrated into some content management system, where it is desired to have a single registration and single sign-on experience.

In such scenarios, once a user logs in for the first time, a user account is automatically created for them, although the password verification is still done against LDAP or the main users repository.

⁠3.11. User Preferences
-----------------------

Users can fine tune the way MantisBT interacts with them by modifying their user preferences to override the defaults set by the administrator; If the administrator changes a default setting, it will not automatically cascade in the users' preferences once they have been set, so it is the users' responsibility to manage their own preferences.

The user preferences include the following:

*   _Default Project_: A user can choose the default project that is selected when the user first logs in. This can be a specific project or "All Projects". For users that only work on one project, it would make sense to set such project as the default project (rather than "All Projects"). The active project is part of the filter applied on the issues listed in the "View Issues" page. Also any newly reported issues will be associated with the active project.
    
*   _Refresh Delay_: The refresh delay is used to specify the number of seconds between auto-refreshes of the View Issues page.
    
*   _Redirect Delay_: The redirect delay is the number of seconds to wait after displaying flash messages like "Issue created successfully", and before the user gets redirected to the next page.
    
*   _Notes Sort Order_: The preference relating to how notes should be ordered when issue is viewed or in email notifications. Ascending order means that older notes are displayed first
    
*   _Email on XXX_: If unticked, then the notifications related to the corresponding event would be disabled. User can also specify the minimum issue severity of for the email to be sent.
    
    Note that the preference is only used to disable notifications that as per the administrator's configuration, this user would have qualified to receive.
    
*   _Email Notes Limit_: This preference can be used to limit the number of issue notes to be included in a email notifications. Specifying N here will cause only the latest N to be included. The value 0 means that all notes will be included.
    
*   _Language_: The preferred language of the user. This language is used by the GUI and in email notifications. Note that MantisBT uses UTF8 for encoding the data, hence the user could for example use MantisBT with a Chinese interface, while logging issue data in German.
    

⁠3.12. User Profiles
--------------------

A user profile describes an environment that used to run the software for which issues are being tracked.

When reporting issues, users can elect to enter information like platform, operating system and version manually, or they can choose from a list of available profiles.

Each user has access to all the personal profiles they create, in addition to global ones; Profile data includes "Platform", "Operating System", "OS Version", and "Additional Description".

Global profiles are typically used by the administrator to define a set of standard system settings used in their environment, which saves users the trouble of having to define them individually. The access level required to manage global profiles is configured by the $g\_manage\_global\_profile\_threshold configuration option and defaults to MANAGER.

⁠Chapter 4. Issue Lifecycle and Workflow
========================================

[4.1. Issue Creation](#admin.lifecycle.create)

[4.2. Issue Statuses](#admin.lifecycle.status)

[4.3. Workflow](#admin.lifecycle.workflow)

[4.3.1. Workflow Transitions](#admin.lifecycle.workflow.transitions)

[4.3.2. Workflow Thresholds](#admin.lifecycle.workflow.thresholds)

⁠4.1. Issue Creation
--------------------

The life cycle of an issue starts with its creation. An issue can be created via one of the following channels:

*   MantisBT Web Interface - This is where a user logs into MantisBT and reports a new issue.
    
*   SOAP API - Where an application automatically reports an issue into MantisBT using the SOAP API web services interfaces. For example, the nightly build script can automatically report an issue if the build fails.
    
*   Email - This is not supported out of the box, but there are existing MantisBT patches that would listen to emails on pre-configured email addresses and adds them to the MantisBT database.
    
*   Others - There can be several other ways to report issues. For example, applications / scripts that directly injects issues into MantisBT database (not recommended, except for one-off migration scripts), or PHP scripts that use the core MantisBT API to create new issues.
    

⁠4.2. Issue Statuses
--------------------

An important part of issue tracking is to classify issues as per their status. Each team may decide to have a different set of categorization for the status of the issues, and hence, MantisBT provides the ability to customize the list of statuses. MantisBT assumes that an issue can be in one of three stages: opened, resolved and closed. Hence, the customized statuses list will be mapped to these three stages. For example, MantisBT comes out of the box with the following statuses: new, feedback, acknowledged, confirmed, assigned, resolved and closed. In this case "new" -> "assigned" map to opened, "resolved" means resolved and "closed" means closed.

Following is the explanation of what the standard statuses that are shipped with MantisBT means.

*   New - This is the landing status for new issues. Issues stay in this status until they are assigned, acknowledged, confirmed or resolved. The next status can be "acknowledged", "confirmed", "assigned" or "resolved".
    
*   Acknowledged - This status is used by the development team to reflect their agreement to the suggested feature request. Or to agree with what the reporter is suggesting in an issue report, although they didn't yet attempt to reproduce what the reporter is referring to. The next status is typically "assigned" or "confirmed".
    
*   Confirmed - This status is typically used by the development team to mention that they agree with what the reporter is suggesting in the issue and that they have confirmed and reproduced the issue. The next status is typically "assigned".
    
*   Assigned - This status is used to reflect that the issue has been assigned to one of the team members and that such team member is actively working on the issue. The next status is typically "resolved".
    
*   Resolved - This status is used to reflect that the issue has been resolved. An issue can be resolved with one of many resolutions (customizable). For example, an issue can be resolved as "fixed", "duplicate", "won't fix", "no change required", etc. The next statuses are typically "closed" or in case of the issue being re-opened, then it would be "feedback".
    
*   Closed - This status reflects that the issue is completely closed and no further actions are required on it. It also typically hides the issue from the View Issues page. Some teams use "closed" to reflect sign-off by the reporter and others use it to reflect the fact that the fix has been released to customers.
    

⁠4.3. Workflow
--------------

Now that we have covered how an issue gets created, and what are the different statuses during the life cycle of such issues, the next step is to define the workflow. The workflow dictates the valid transitions between statuses and the user access level required of the user who triggers such transitions; in other words, how issues move from one status to another and who is authorized to trigger such transitions.

MantisBT provides the ability for teams to define their own custom workflow which works on top of their custom status (see [Section 7.5, “Customizing Status Values”](#admin.customize.status)).

### ⁠4.3.1. Workflow Transitions

By default, there is no workflow defined, which means that all states are accessible from any other, by anyone.

The "Manage > Manage Configuration > Workflow Transitions" page allows users with ADMINISTRATOR access level to do the following tasks:

*   Define the valid next statuses for each status.
    
*   Define the default next status for each status.
    
*   Define the minimum access level required for a user to transition to each status.
    
*   Define the default status for newly created issues.
    
*   Define the status at which the issue is considered resolved. Any issues a status code greater than or equal to the specified status will be considered resolved.
    
*   Define the status which is assigned to issues that are re-opened.
    
*   Define the required access level to change the workflow.
    

Note that the scope of the applied change is dependent on the selected project. If "All Projects" is selected, then the configuration is to be used as the default for all projects, unless overidden by a specific project. To configure for a specific project, switch to it via the combobox at the top right corner of the screen.

The Global ("All Projects") workflow can also be defined in the _config_inc.php_ file, as per the following example.

$g\_status\_enum\_workflow\[NEW\_\]           ='30:acknowledged,20:feedback,40:confirmed,50:assigned,80:resolved';
$g\_status\_enum_workflow\[FEEDBACK\]       ='30:acknowledged,40:confirmed,50:assigned,80:resolved';
$g\_status\_enum_workflow\[ACKNOWLEDGED\]   ='40:confirmed,20:feedback,50:assigned,80:resolved';
$g\_status\_enum_workflow\[CONFIRMED\]      ='50:assigned,20:feedback,30:acknowledged,80:resolved';
$g\_status\_enum_workflow\[ASSIGNED\]       ='80:resolved,20:feedback,30:acknowledged,40:confirmed';
$g\_status\_enum_workflow\[RESOLVED\]       ='90:closed,20:feedback,50:assigned';
$g\_status\_enum_workflow\[CLOSED\]         ='20:feedback,50:assigned';

**Note**

The workflow needs to have a path from the statuses greater than or equal to the 'resolved' state back to the 'feedback' state (see _$g\_bug\_resolved\_status\_threshold_ and _$g\_bug\_feedback_status_ under [Section 5.22, “Status Settings”](#admin.config.status)), otherwise, the re-open operation won't work.

**Note**

The first item in each list denotes the default value for this status, which will be pre-selected in the Change Status combobox in the View Issues page.

### ⁠4.3.2. Workflow Thresholds

The "Manage > Manage Configuration > Workflow Thresholds" page allows users with ADMINISTRATOR access level to define the thresholds required to do certain actions. Following is a list of such actions and what they mean:

*   Report an issue - The access levels that are allowed to report an issue.
    
*   Update an issue - The access levels that are allowed to update the header information of an issue.
    
*   Allow issue to be closed on resolved - The access levels that are allow to resolve and close an issue in one step.
    
*   Allow reporter to close issue - Indicates if reporters should be allowed to close issues reported by them.
    
*   Monitor an issue - The access levels required for a user to be able to monitor an issue. Once a user monitors an issue, the user will be included in all future email notifications relating to changes in the issue.
    
*   Handle an issue - The access levels required for a user to be shown in the list of users that can handle an issue.
    
*   Assign an issue - The access levels required for a user to be able to change the handler (i.e. assign / unassign) an issue.
    
*   Move an issue - The access levels required for a user to be able to move an issue from one project to another. (TODO: are these access levels evaluated against source or destination project?).
    
*   Delete an issue - The access levels required for a user to be able to delete an issue.
    
*   Reopen an issue - The access levels required for a user to be able to re-open a resolved or closed issue.
    
*   Allow Reporter to re-open Issue - Whether the reporter of an issue can re-open a resolved or closed issue, independent of their access level.
    
*   Status to which a reopened issue is set - This is the status to which an issue is set after it is re-opened.
    
*   Resolution to which a reopen issue is set - The resolution to set on issues that are reopened.
    
*   Status where an issue is considered resolved - The status at which an issue is considered resolved.
    
*   Status where an issue becomes readonly - Issues with such status and above are considered read-only. Read-only issues can only be modified by users with a configured access level. Read-only applies to the issue header information as well as other issue related information like relationships, attachments, notes, etc.
    
*   Update readonly issues - The access levels required for a user to be able to modify a readonly issue.
    
*   Update issue status - The access levels required for a user to be able to modify the status of an issue.
    
*   View private issues - The access levels for a user to be able to view a private issue.
    
*   Set view status (public vs. private) - The access level for a user to be able to set whether an issue is private or public, when reporting the issue. If the user reporting the issues doesn't have the required access, then the issue will be created with the default view state.
    
*   Update view status (public vs private) - The access level required for a user to be able to update the view status (i.e. public vs. private).
    
*   Show list of users monitoring issue - The access level required for a user to be able to view the list of users monitoring an issue.
    
*   Set status on assignment of handler - The access levels required for a user to be able to re-assign an issue when changing its status.
    
*   Status to set auto-assigned issues to - The status - This is the status that is set on issues that are auto assigned to users that are associated with the category that the issuer is reported under.
    
*   Limit reporter's access to their own issues - When set, reporters are only allow to view issues that they have reported.
    
*   Add notes - The access levels required for users to be able to add notes.
    
*   Update notes - The access levels required for users to be able to update issue notes.
    
*   Allow user to edit their own issue notes - A flag that indicates the ability for users to edit issue notes report by them.
    
*   Delete note - The access levels required for a user to delete a note that they may or may not have reported themselves.
    
*   View private notes - The access levels required for a user to be able to view private notes associated with an issue that they have access to view.
    
*   View Change Log - The access levels required for a user to be able to view the change log.
    
*   View Assigned To - The access levels required for a user to be able to know the handler of an issue that they have access to.
    
*   View Issue History - The access levels required for a user to be able to view the history of changes of an issue.
    
*   Send reminders - The access levels required for a user to be able to send reminders to other users relating to an issue that they have access to.
    

⁠Chapter 5. Configuration
=========================

[5.1. Introduction](#admin.config.intro)

[5.2. Database](#admin.config.database)

[5.3. Path](#admin.config.path)

[5.4. Webserver](#admin.config.webserver)

[5.5. Configuration Settings](#admin.config.settings)

[5.6. Security and Cryptography](#admin.config.security)

[5.7. Signup and Lost Password](#admin.config.signup)

[5.8. Email](#admin.config.email)

[5.9. Version](#admin.config.version)

[5.10. Language](#admin.config.language)

[5.11. Display](#admin.config.display)

[5.12. Time](#admin.config.time)

[5.13. Date](#admin.config.date)

[5.14. Time Zone](#admin.config.timezone)

[5.15. News](#admin.config.news)

[5.16. Default Preferences](#admin.config.defaults)

[5.17. Summary](#admin.config.summary)

[5.18. Bugnote](#admin.config.bugnote)

[5.19. File Upload](#admin.config.uploads)

[5.20. HTML](#admin.config.html)

[5.21. Authentication](#admin.config.auth)

[5.21.1. Global authentication parameters](#admin.config.auth.global)

[5.21.2. LDAP authentication method parameters](#admin.config.auth.ldap)

[5.22. Status Settings](#admin.config.status)

[5.23. Filters](#admin.config.filters)

[5.24. Misc](#admin.config.misc)

[5.25. Cookies](#admin.config.cookies)

[5.26. Speed Optimisation](#admin.config.speed)

[5.27. Reminders](#admin.config.reminders)

[5.28. Bug History](#admin.config.bughistory)

[5.29. Sponsorship](#admin.config.sponsorship)

[5.30. Custom Fields](#admin.config.customfields)

[5.31. My View Settings](#admin.config.myview)

[5.32. Relationship Graphs](#admin.config.relationship)

[5.33. Wiki Integration](#admin.config.wiki)

[5.34. Sub-Projects](#admin.config.subprojects)

[5.35. Field Visibility](#admin.config.fields)

[5.36. System Logging and Debugging](#admin.config.logging)

[5.37. Time Tracking](#admin.config.timetracking)

[5.38. API](#admin.config.api)

[5.38.1. Disabling the webservice API](#admin.config.api.disable)

[5.39. Anti-Spam Configuration](#admin.config.antispam)

[5.40. Due Date](#admin.config.duedate)

[5.41. User Management](#admin.config.users)

[5.42. View Page Settings](#admin.config.view)

⁠5.1. Introduction
------------------

MantisBT is highly customizable through the web interface and configuration files. Configuration options can be set globally as well as customized for a specific project or user (except for options listed in _$g\_global\_settings_, see [Section 5.5, “Configuration Settings”](#admin.config.settings)).

Configuration options can be set in _config_inc.php_ and in the _database_ (using the various manage pages). Values stored in the database take precedence over values defined in _config_inc.php_. The former can also be viewed and updated on the _Configuration Report_ page (Manage > Manage Configuration > Configuration Report).

To determine which value to use, MantisBT follows the list below, sequentially searching for the specified configuration option until a match is found.

1.  _database_: current user, current project
    
2.  _database_: current user, all projects
    
3.  _database_: all users, current project
    
4.  _database_: all users, all projects
    
5.  _config_inc.php_
    
6.  _config\_defaults\_inc.php_
    

⁠5.2. Database
--------------

The database settings must be set in order for the package to work properly. These settings should be provided to you by your system administrator or your hosting company.

$g_hostname

Host name or connection string for Database server. The default value is localhost. For MySql, this should be hostname or hostname:port (e.g. localhost:3306).

$g\_db\_username

User name to use for connecting to the database. The user needs to have read/write access to the MantisBT database. The default user name is "root".

$g\_db\_password

Password for the specified user name. The default password is empty.

$g\_database\_name

Name of database that contains MantisBT tables. The default name is 'bugtracker'.

$g\_db\_type

The supported database types are listed in the table below.

The PHP extension corresponding to the selected type must be enabled (see also [Section 2.2.2.1, “Versions compatibility table”](#admin.install.requirements.software.versions)).

RDBMS

db_type (ADOdb)

PHP extension

Comments

MySQL

mysqli

mysqli

default

PostgreSQL

pgsql

pgsql

MS SQL Server

mssqlnative

sqlsrv

Oracle

oci8

oci8

MantisBT allows administrators to configure a prefix and a suffix for its tables. This is enables multiple MantisBT installation in the same database or schema.

**Warning**

Use of long strings for these configuration options may cause issues on RDBMS restricting the size of its identifiers, such as Oracle (which imposed a maximum size of 30 characters until version 12.1; starting with 12cR2 this [limit has been increased to 128](http://docs.oracle.com/database/122/SQLRF/Database-Object-Names-and-Qualifiers.htm#SQLRF51129)).

$g\_db\_table_prefix

Specifies the prefix to be used for all table names. The default value is 'mantis'.

The prefix can be used to help make sure table names are unique. This is useful for users who are limited to a single database or schema.

$g\_db\_table_suffix

Specifies the prefix to be appended to all table names. The default value is 'table'.

The suffix can be used to help make sure table names are unique. This is useful for users who are limited to one database.

$g\_db\_table\_plugin\_prefix

Specifies the prefix to be used to differentiate tables belonging to a plugin's schema from MantisBT's base tables. The default value is 'plugin'.

Plugin table names are built using the plugin's _basename_, e.g. for a table named 'foo' in the 'Example' plugin (with default values for prefixes and suffix), the physical table name would be `mantis_plugin_Example_foo_table`.

⁠5.3. Path
----------

These path settings are important for proper linking within MantisBT. In most scenarios the default values should work fine, and you should not need to override them.

$g_path

URL to your installation as seen from the web browser; this is what you type into the URL field. Requires trailing '/' character. eg. 'http://www.example.com/mantisbt/'. In the following example https protocol is used: eg. 'https://www.example.com/mantisbt/'. MantisBT will default this to the correct value. However, in some cases it might be necessary to override the default. This is typically needed when an installation can be accessed by multiple URLs (internal vs external).

$g\_short\_path

Short web path without the domain name. This requires the trailing '/'.

$g\_absolute\_path

This is the absolute file system path to the MantisBT installation, it is defaulted to the directory where config\_defaults\_inc.php resides. Requires trailing '/' character (eg. '/usr/apache/htdocs/mantisbt/').

$g\_core\_path

This is the path to the core directory of your installation. The default value is usually OK but it is recommended that you move the 'core' directory out of your webroot. Requires trailing DIRECTORY_SEPARATOR character.

$g\_class\_path

This is the path to the classes directory which is a sub-directory of core by default. The default value is typically OK. Requires trailing DIRECTORY_SEPARATOR. character.

$g\_library\_path

This is the path to the library directory of your installation. The default value is usually OK but it is recommended that you move the 'library' directory out of your webroot. Requires trailing DIRECTORY_SEPARATOR character.

$g\_language\_path

This is the path to the language directory of your installation. The default value is usually OK but it is recommended that you move the 'language' directory out of your webroot. Requires trailing DIRECTORY_SEPARATOR character.

$g\_manual\_url

This is the url to the MantisBT online manual. Requires trailing '/' character.

⁠5.4. Webserver
---------------

$g\_session\_handler

Session handler. Possible values are as per the list below; the default is _php_.

*   _php_: PHP filesystem sessions
    
*   _adodb_: Database storage sessions
    
*   _memcached_: Memcached storage sessions
    

$g\_session\_save_path

Location where session files are stored. The default is _false_, meaning the session handler's default location will be used.

$g\_session\_validation

Use Session validation (defaults to _ON_)

**Warning**

Disabling this could be a potential security risk !

$g\_form\_security_validation

Form security validation, defaults to _ON_. This protects against [Cross-Site Request Forgery](http://en.wikipedia.org/wiki/Cross-site_request_forgery). Some proxy servers may not correctly work with this option enabled because they cache pages incorrectly.

**Warning**

Disabling this option is a security risk, it is strongly recommended to leave it ON

$g\_custom\_headers

An array of custom headers to be sent with each page.

For example, to allow your MantisBT installation to be viewed in a frame in IE6 when the frameset is not at the same hostname as the MantisBT install, you need to add a P3P header. You could try something like

$g\_custom\_headers = array( 'P3P: CP="CUR ADM"' );

in your config file, but make sure to check that your policy actually matches with what you are promising. See [MSDN](http://msdn.microsoft.com/en-us/library/ms537343.aspx) for more information.

Even though it is not recommended, you could also use this setting to disable previously sent headers. For example, assuming you didn't want to benefit from Content Security Policy (CSP), you could set:

$g\_custom\_headers = array( 'Content-Security-Policy:' );

**Warning**

Disabling CSP is a security risk, it is strongly recommended that you leave it as Mantis defines it.

⁠5.5. Configuration Settings
----------------------------

$g\_global\_settings

This option contains the list of configuration options that are used to determine if it is allowed for a specific configuration option to be saved to or loaded from the database. Configuration options that are in the list are considered global only and hence are only configurable via the config\_inc.php file and defaulted by config\_defaults_inc.php file.

$g\_public\_config_names

This option contains a list of configuration options that can be queried via SOAP API.

⁠5.6. Security and Cryptography
-------------------------------

Content Security Policy

Amongst other things, MantisBT relies on [Content Security Policy](http://en.wikipedia.org/wiki/Content_Security_Policy) (CSP), which is a [W3C candidate recommendation](http://www.w3.org/TR/CSP/) improving the system's security against [cross-site scripting (XSS)](http://en.wikipedia.org/wiki/Cross-site_scripting) and other, similar types of attacks. It is currently supported in [recent versions of many browsers](http://caniuse.com/#feat=contentsecuritypolicy).

**Note**

CSP may cause issues in certain situations (e.g. during development), or when using plugins relying on externally hosted resources such as images or scripts.

MantisBT currently does not provide any mechanism for plugins to notify the Core of 'safe' external domains. Because of that, even though it is not recommended for obvious security reasons, you may wish to disable CSP. You can do so by specifying a _Custom Header_ in your `config_inc.php` file (see [Section 5.4, “Webserver”](#admin.config.webserver)).

**Warning**

Disabling Content Security Policy is a security risk !

$g\_crypto\_master_salt

Master salt value used for cryptographic hashing throughout MantisBT. This value must be kept secret at all costs. You must generate a unique and random salt value for each installation of MantisBT you control. The minimum length of this string must be at least 16 characters.

The value you select for this salt should be a long string generated using a secure random number generator. An example for Linux systems is:

cat /dev/urandom | head -c 64 | base64

Note that the number of bits of entropy per byte of output from /dev/urandom is not 8. If you're particularly paranoid and don't mind waiting a long time, you could use /dev/random to get much closer to 8 bits of entropy per byte. Moving the mouse (if possible) while generating entropy via /dev/random will greatly improve the speed at which /dev/random produces entropy.

This setting is blank by default. MantisBT will not operate in this state. Hence you are forced to change the value of this configuration option.

**Warning**

This configuration option has a profound impact on the security of your MantisBT installation. Failure to set this configuration option correctly could lead to your MantisBT installation being compromised. Ensure that this value remains secret. Treat it with the same security that you'd treat the password to your MantisDB database.

⁠5.7. Signup and Lost Password
------------------------------

$g\_allow\_signup

Allow users to signup for their own accounts.

If ON (default), then $g\_send\_reset_password must be ON as well, and mail settings must be correctly configured (see [Section 5.8, “Email”](#admin.config.email)).

$g\_max\_failed\_login\_count

Maximum failing login attempts before the account is locked. Once locked, it's required to reset the password (lost password). Value resets to zero at each successfully login. Default is OFF.

$g\_notify\_new\_user\_created\_threshold\_min

The minimum global access level required to be notified when a new user registers via the "signup form". To pick specific access levels that are not necessarily at the higher end of access levels, use an array of access levels. Default is ADMINISTRATOR.

$g\_send\_reset_password

If ON (default), users will be sent their password when their account is created or password reset (this requires mail settings to be correctly configured).

If OFF, then the Administrator will have to provide a password when creating new accounts, and the password will be set to blank when reset.

$g\_signup\_use_captcha

TODO

$g\_system\_font_folder

TODO

$g\_lost\_password_feature

TODO

$g\_max\_lost\_password\_in\_progress\_count

TODO

⁠5.8. Email
-----------

$g\_webmaster\_email

The webmaster's e-mail address. This address is displayed in the bottom of all MantisBT pages. webmaster@example.com

$g\_from\_email

The email address to be used as the source of all emails sent by MantisBT. noreply@example.com

$g\_return\_path_email

Email address to receive bounced emails.

$g\_enable\_email_notification

Set to ON to enable email notifications, OFF to disable them. Default is ON. Note that disabling email notifications has no effect on emails generated as part of the user signup process. When set to OFF, the password reset feature is disabled. Additionally, notifications of administrators updating accounts are not sent to users.

$g\_email\_notifications_verbose

When enabled, the email notifications will include the full issue with a hint about the change type at the top, rather than using dedicated notifications that are focused on what changed. This change can be overridden in the database per user. Default is OFF.

$g\_default\_notify_flags

Associates a default notification flag with each action, to control who should be notified. The default will be used if the action is not defined in _$g\_notify\_flags_ or if the flag is not included in the specific action definition.

The list of actions include: _new_, _assigned_, _resolved_, _bugnote_, _reopened_, _closed_, _deleted_, _feedback_.

The default is:

$g\_default\_notify_flags = array(
	'reporter'      => ON,
	'handler'       => ON,
	'monitor'       => ON,
	'bugnotes'      => ON,
	'category'      => ON,
	'explicit'      => ON,
	'threshold_min' => NOBODY,
	'threshold_max' => NOBODY
);

_threshold_min_ and _threshold_max_ are used to send messages to all members of the project whose status is

*   greater than or equal to _threshold_min_, and
    
*   less than or equal to _threshold_max_.
    

Sending messages to everyone would set _threshold_min_ to ANYBODY and _threshold_max_ to NOBODY. To send to all DEVELOPERS and above, use DEVELOPER and NOBODY respectively.

$g\_notify\_flags

Defines the specific notification flags when they are different from the defaults defined in _$g\_default\_notify_flags_.

For example, the following code overrides the default by disabling notifications to bugnote authors and users monitoring the bug when submitting a new bug:

$g\_notify\_flags\['new'\] = array(
	'bugnotes' => OFF,
	'monitor' => OFF,
);

See [Section 7.4, “Email Notifications”](#admin.customize.email) for further examples of customizing the notification flags.

Available actions include:

*   _new_: a new bug has been added
    
*   _reopened_: the bug has been reopened
    
*   _deleted_: a bug has been deleted
    
*   _owner_: the bug has been assigned a new owner
    
*   _bugnote_: a bugnote has been added to a bug
    
*   _sponsor_: the sponsorship for the bug has changed (added, deleted or updated)
    
*   _relation_: a relationship for the bug has changed (added, deleted or updated)
    
*   _monitor_: a user is added to the monitor list.
    

In addition, an action can match the bug status in _$g\_status\_enum_string_. Note that spaces in the string are replaced with underscores ('_') when creating the action. Thus, using the defaults, 'feedback' would be a valid action.

$g\_email\_receive_own

This defines whether users should receive emails for their own actions. This option is defaulted to OFF, hence, users do not receive email notification for their own actions. This can be a source for confusions for users upgrading from MantisBT 0.17.x versions, since in these versions users used to get notified of their own actions.

$g\_validate\_email

Determines whether email addresses are validated.

When ON (default), validation is performed using the pattern given by the [HTML5 specification for _email_ type form input elements](http://www.w3.org/TR/html5/forms.html#valid-e-mail-address). When OFF, validation is disabled.

**Note**

Regardless of how this option is set, validation is never performed when using LDAP email (i.e. when $g\_use\_ldap_email = ON, see [Section 5.21.2, “LDAP authentication method parameters”](#admin.config.auth.ldap)), as we assume that it is handled by the directory.

$g\_check\_mx_record

Set to OFF to disable email checking. Default is OFF.

$g\_allow\_blank_email

If ON, allows the user to omit an email address field. If you allow users to create their own accounts, they must specify an email at that point, no matter what the value of this option is. Otherwise they wouldn't get their passwords.

Administrators are able to bypass this check to enable them to create special accounts like anonymous access and other service accounts that don't need notifications.

$g\_email\_login_enabled

Enable support for logging in by email and password, in addition to username and password. This will only work as long as there is a single user with the specified email address and the email address is not blank. The default value is OFF.

$g\_email\_ensure_unique

When enabled, the uniqueness of email addresses will be inforced for new users as well as updates to existing ones. Note that there can be duplicate emails before this option was turned ON. Default is ON.

$g\_limit\_email_domains

Only allow and send email to addresses in the given domain(s). This is useful as a security feature and it is also useful in cases like Sourceforge where its servers are only limited to send emails to SourceForge email addresses in order to avoid spam. $g\_limit\_email_domains = array( 'users.sourceforge.net', 'sourceforge.net' );

$g\_show\_user\_email\_threshold

This specifies the access level that is needed to have user names hyperlinked with mailto: links. The default value is NOBODY, hence, even administrators won't have this feature enabled.

$g\_phpMailer\_method

Select the method to send mail:

*   _PHPMAILER\_METHOD\_MAIL_ for use of mail() function,
    
*   _PHPMAILER\_METHOD\_SENDMAIL_ for sendmail (or postfix),
    
*   _PHPMAILER\_METHOD\_SMTP_ for SMTP,
    

Default is PHPMAILER\_METHOD\_MAIL.

$g\_smtp\_host

This option specifies the SMTP server to submit messages to. The SMTP server (MTA) then takes on the responsibility of delivering messages to their final destinations.

To use the local SMTP (if available) set this to 'localhost', otherwise use the fully qualified domain name of the remote SMTP server.

It can be either a single hostname, or multiple semicolon-delimited hostnames. You can specify for each host a port other than the default, using format: _hostname:port_ (e.g. "smtp1.example.com:25;smtp2.example.com").

Hosts will be tried in the given order.

**Note**

This is only used with _PHPMAILER\_METHOD\_SMTP_ (see $g\_phpmailer\_method).

The default is 'localhost'.

$g\_smtp\_port

The default SMTP port to use. This can be overridden individually for specific hosts. (see $g\_smtp\_host).

Typical SMTP ports are 25 and 587.

The default is 25.

$g\_smtp\_connection_mode

Allow secure connection to the SMTP server. Valid values are:

*   _'' (empty string)_: No encryption. This is the default.
    
*   _ssl_
    
*   _tls_
    

$g\_smtp\_username

SMTP Server Authentication user

Allows the use of SMTP Authentication when using a remote SMTP host.

**Note**

must be set to '' (empty string) if the SMTP host does not require authentication.

Default is ''.

$g\_smtp\_password

This is the password that is used in SMTP Authentication. Not used when $g\_smtp\_username = ''

Default is ''.

$g\_email\_dkim_enable

Enables DomainKeys Identified Mail (DKIM) Signatures (rfc6376). To successfully sign mails you need to enable DKIM and provide at least: _DKIM domain (see $g\_email\_dkim_domain)_, _DKIM private key or key file path (see $g\_email\_dkim\_private\_key\_file\_path and $g\_email\_dkim\_private\_key_string)_, _DKIM selector (see $g\_email\_dkim_selector)_, _DKIM identity (see $g\_email\_dkim_identity)_.

The default is OFF.

$g\_email\_dkim_domain

Defines domain for DomainKeys Identified Mail (DKIM) Signatures.

Typically same as the host part of the $g\_from\_email. For example example.com.

$g\_email\_dkim\_private\_key\_file\_path

Path to the private domain key to be used for DomainKeys Identified Mail (DKIM) Signatures.

If the key is specified in $g\_email\_dkim\_private\_key_string this setting will not be used.

$g\_email\_dkim\_private\_key_string

Private domain key to be used for DomainKeys Identified Mail (DKIM) Signatures.

This string should contain private key for signing. Leave empty string if you wish to load the key from the file defined with $g\_email\_dkim\_private\_key\_file\_path.

$g\_email\_dkim_selector

Selector to be used for DomainKeys Identified Mail (DKIM) Signatures.

If your domain is example.com, typically DNS TXT field should have: _host: mail.example._domainkey_, _value: v=DKIM1; t=s; n=core; k=rsa; p=\[public key\]_. In this case selector should be mail.example

$g\_email\_dkim_passphrase

Private DKIM domain key password.

Leave empty string if your private key does not have password

$g\_email\_dkim_identity

Identity to be used for DomainKeys Identified Mail (DKIM) Signatures.

This is usually the same as your g\_from\_email. For example noreply@example.com

$g\_email\_send\_using\_cronjob

Disables sending of emails as soon as an action is performed. Emails are instead queued and must be sent by running scripts/send_emails.php periodically. This script can only be executed from the CLI, not from the web interface, for security reasons.

Enabling this option can help with performance problems if large numbers of emails are generated or mail delivery is slow by not delaying page execution when sending emails.

$g\_email\_separator1

Default is str_pad('', 70, '='); This means 70 equal signs.

$g\_email\_separator2

Default is str_pad('', 70, '-'); This means 70 minus signs.

$g\_email\_padding_length

Default is 28.

MantisBT uses flags and a threshold system to generate emails on events. For each new event, email is sent to:

*   the reporter, qualified by the notify flag 'reporter' below
    
*   the handler (or Assigned to), qualified by the notify flag 'handler' below
    
*   anyone monitoring the bug, qualified by the notify flag 'monitor' below
    
*   anyone who has ever added a bugnote the bug, qualified by the notify flag 'bugnotes' below
    
*   anyone assigned to the project whose access level is greater than or equal to the notify flag 'threshold\_min' and less than or equal to the notify flag 'threshold\_max' below
    

From this list, those recipients who meet the following criteria are eliminated:

*   the originator of the change, if $g\_email\_receive_own is OFF
    
*   the recipient either no longer exists, or is disabled
    
*   the recipient has turned their email\_on\_<new status> preference OFF
    
*   the recipient has no email address entered
    

⁠5.9. Version
-------------

$g\_show\_version

Whether to show the MantisBT version at the bottom of each page or not. Default is OFF.

⁠5.10. Language
---------------

$g\_default\_language

This is the language used by default in MantisBT. This may be set to 'auto' where MantisBT will try to determine the language from the browser.

$g\_language\_choices_arr

This is to be set to an array of languages that are available for users to choose from. The default value includes all languages supported by MantisBT. The administrator can limit the languages available for users to choose from by overriding this value. For example, to support English, French and German include the following code:

$g\_language\_choices_arr = array( 'english', 'french', 'german' );

Of course, administrators can also add their own languages by translating the strings and creating their own language files. You are encouraged to share any translation work that you do with the MantisBT team. This will ensure that the newly created language file is maintained with future MantisBT releases.All language files reside in the lang/ folder. They are all named according to the following pattern: strings_<language>.txt.

$g\_fallback\_language

This is the language used if MantisBT cannot determine the language from the browser. It defaults to 'english'.As of 0.19.0, this may be set to 'auto' where MantisBT will try to determine the language from the browser.

**Note**

If a string does not exist in the active language, the English string is used instead.

⁠5.11. Display
--------------

$g\_font\_family

Name of the google font family for the browser to use. For all available fonts, see: [fonts.google.com](https://fonts.google.com/) .

$g\_font\_family_choices

Google font family list offered to the user to chose from. Font files are fetched from google servers.

$g\_font\_family\_choices\_local

This is a small subset of _$g\_font\_family_choices_ in which font files are part of MantisBT installation.

$g\_window\_title

This is the browser window title (<TITLE> tag).

$g\_search\_title

This is used as prefix to describe Browser Search entries, and must be short enough so that when inserted into the 'opensearch\_XXX\_short' language string, the resulting text is 16 characters or less, to be compliant with the limit for the ShortName element as defined in the [OpenSearch specification](http://www.opensearch.org/Specifications/OpenSearch/1.1) .

Defaults to the value of $g\_window\_title.

$g\_favicon\_image

Path to the favorites icon relative to MantisBT root folder This icon should be of _image/x-icon_ MIME type, and its size 16x16 pixels. It is also used to decorate OpenSearch Browser search entries. (default 'images/favicon.ico').

$g\_logo\_image

Path to the logo image relative to MantisBT root folder (default 'images/mantis_logo.gif').

$g\_logo\_url

The default URL to be associated with the logo. By default this is set to $g\_default\_home_page (which defaults to My View page). Clicking on the logo from any page in the bug tracker will navigate to the URL specified in this configuration option.

$g\_show\_project\_menu\_bar

This option specifies whether to add menu at the top of the page which includes links to all the projects. The default value is OFF.

$g\_show\_assigned_names

When a bug is assigned then replace the word "assigned" with the name of the developer in parenthesis. Default is ON.

$g\_show\_priority_text

Specifies whether to show priority as text (ON) or icon (OFF) in the view all bugs page. Default is OFF (icon).

$g\_priority\_significant_threshold

Define the priority level at which a bug becomes significant. Significant bugs are displayed with emphasis. Set this value to -1 to disable the feature. The default value is HIGH.

$g\_severity\_significant_threshold

Define the severity level at which a bug becomes significant. Significant bugs are displayed with emphasis. Set this value to -1 to disable the feature. The default value is MAJOR.

$g\_view\_issues\_page\_columns

This configuration option is used to select the columns to be included in the View Issues page and in which order. If one of the column is not accessible to the logged in user, or corresponds to a disabled feature, then it will be automatically removed from the list at runtime. Hence, the same column list may show a different set of columns based on the logged in user, the currently selected project and enabled features (e.g. sponsorship_total is only shown if the sponsorship feature is enabled).

The supported columns are: selection, edit, id, project\_id, reporter\_id, handler\_id, priority, reproducibility, projection, eta, resolution, fixed\_in\_version, view\_state, os, os\_build, build (for product build), platform, version, date\_submitted, attachment\_count, category, sponsorship\_total, severity, status, last\_updated, summary, bugnotes\_count, description, steps\_to\_reproduce, additional\_info. As for custom fields they can be referenced by adding a 'custom\_' to their name (e.g. xyz would be custom_xyz).

By default the following columns are selected: selection, edit, priority, id, sponsorship\_total, bugnotes\_count, attachment\_count, category\_id, severity, status, last_updated, summary.

$g\_print\_issues\_page\_columns

This configuration option is used to select the columns to be included in the Print Issues page and in which order. See $g\_view\_issues\_page\_columns for more details about the supported fields.

By default the following columns are selected: selection, priority, id, sponsorship\_total, bugnotes\_count, attachment\_count, category\_id, severity, status, last_updated, summary

$g\_csv\_columns

This configuration option is used to select the columns to be included in the CSV export and in which order. See $g\_view\_issues\_page\_columns for more details about the supported fields.

By default the following columns are selected: id, project\_id, reporter\_id, handler\_id, priority, severity, reproducibility, version, build, projection, category\_id, date\_submitted, eta, os, os\_build, platform, view\_state, last\_updated, summary, status, resolution, fixed\_in\_version, duplicate_id.

$g\_excel\_columns

This configuration option is used to select the columns to be included in the CSV export and in which order. See $g\_view\_issues\_page\_columns for more details about the supported fields.

By default the following columns are selected: id, project\_id, reporter\_id, handler\_id, priority, severity, reproducibility, version, build, projection, category\_id, date\_submitted, eta, os, os\_build, platform, view\_state, last\_updated, summary, status, resolution, fixed\_in\_version, duplicate_id.

$g\_show\_bug\_project\_links

Show project links when in All Projects mode. Default is ON.

$g\_show\_product_version

This controls display of the product version in the report, view, update and print issue pages. This flag also applies to other product version related fields like product build, fixed in version, and target version. Valid values are ON, OFF, and AUTO. ON for always displayed, AUTO for displayed when project has versions defined, and OFF for always OFF. The default value is AUTO.

$g\_show\_version\_dates\_threshold

The access level threshold at which users will see the date of release for product versions. Dates will be shown next to the product version, target version and fixed in version fields. Set this threshold to NOBODY to disable the feature. Default value is NOBODY.

$g\_show\_realname

This control will replace the user's userid with their realname. If it is set to ON, and the real name field has been populated, the replacement will occur. It defaults to OFF.

$g\_show\_avatar

Show the users' avatar

In addition to enabling this configuration option it is necessary to install an avatar plugin like the [Gravatar](http://www.gravatar.com) plugin which is bundled out of the box.

$g\_show\_avatar_threshold

The threshold of users for which MantisBT should show the avatar (default DEVELOPER). Note that the threshold is related to the user for whom the avatar is being shown, rather than the user who is currently logged in.

⁠5.12. Time
-----------

$g\_cookie\_time_length

Time for long lived cookie to live in seconds. It is also used as the default for permanent logins if $g\_allow\_permanent_cookie is enabled and selected. Default is 1 year.

$g\_allow\_permanent_cookie

Allow users to opt for a 'permanent' cookie when logging in. Controls the display of the 'Remember my login in this browser' checkbox on the login page. See $g\_cookie\_time_length.

$g\_wait\_time

Time to delay between page redirects (in seconds). Users can override this setting in their user preferences. Default is 2 seconds.

$g\_long\_process_timeout

This timeout is used by pages which does time consuming operations like upgrading the database. The default value of 0 disables timeout. Note that this timeout is specified in seconds.

⁠5.13. Date
-----------

These variables control how the date is displayed. The default is [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) formatting.

Please refer to the [PHP manual](http://www.php.net/manual/en/function.date.php#refsect1-function.date-parameters) for details on available formatting options.

$g\_short\_date_format

This format is used in the bug listing pages (eg: View Bugs). Default is `Y-m-d`.

$g\_normal\_date_format

This format is used in the view/update bug pages, bug notes, manage section, and news section. Default is `Y-m-d H:i`.

$g\_complete\_date_format

This format is used on the top of each page (current time) and the emails that are sent out. Default is `Y-m-d H:i T`.

$g\_datetime\_picker_format

This format is used with the datetime picker widget. Default is `Y-MM-DD H:m`.

**Note**

The formatting convention for the DateTime picker is different from the one used for the other date settings described above; see [Moment.js documention](http://momentjs.com/docs/#/displaying/format/) for details.

**Warning**

This format needs to match the one defined in _$g\_normal\_date_format_. Inconsistencies between these two settings, e.g. using different date ordering (DMY, MDY or YMD) or displaying the month as a number vs a word or abbreviation, may result in unexpected behavior such as an invalid interpretation of the date by the DateTime picker widget, or errors trying to save a modified date.

⁠5.14. Time Zone
----------------

$g\_default\_timezone

Default timezone to use in MantisBT. This configuration is normally initialized when installing Mantis. It should be set to one of the values specified in the [List of Supported Timezones](http://php.net/timezones).

If this config is left blank, the timezone will be initialized by calling function [date\_default\_timezone_get()](http://php.net/date-default-timezone-get), which will fall back to _UTC_ if unable to determine the timezone.

Correct configuration of this variable can be confirmed by running the administration checks. Users can override the default timezone under user their preferences.

**Note**

Note that this function's behavior was modified in PHP 5.4.0.

⁠5.15. News
-----------

These options are used to control the query that selects the news entries to be displayed.

$g\_news\_enabled

Indicates whether the news feature should be enabled or disabled. The default is OFF. The news feature is deprecated in favor of being moved to a plugin.

$g\_news\_limit_method

Limit the news entry that are displayed by number of entries (BY\_LIMIT) or by date (BY\_DATE). The default is BY_LIMIT.

$g\_news\_view_limit

The limit for the number of news entries to be displayed. This option is only used if $g\_news\_limit\_method is set to BY\_LIMIT.

$g\_news\_view\_limit\_days

Specifies the number of dates after which the news are not displayed. This option is only used if $g\_news\_limit\_method is set to BY\_DATE.

$g\_private\_news_threshold

Specifies the access level required to view private news. The default is DEVELOPER.

⁠5.16. Default Preferences
--------------------------

$g\_default\_new\_account\_access_level

This is the default access level users are given when their account is created by email. The default access level is REPORTER. Look in constant_inc.php for other values.

$g\_default\_project\_view\_status

The default viewing status for new projects (VS\_PUBLIC or VS\_PRIVATE). The default is VS_PUBLIC.

$g\_default\_bug\_view\_status

The default viewing status for the new bug (VS\_PUBLIC or VS\_PRIVATE). The default is VS_PUBLIC.

$g\_default\_bugnote\_view\_status

The default viewing status for the new bugnote (VS\_PUBLIC or VS\_PRIVATE). The default is VS_PUBLIC.

$g\_timeline\_view_threshold

Threshold for viewing timeline information. Use NOBODY to turn it off. If the timeline is turned off, the other widgets are displayed in a two column view. The default is VIEWER.

$g\_default\_reminder\_view\_status

The default viewing status for the new reminders (VS\_PUBLIC or VS\_PRIVATE). The default is VS_PUBLIC.

$g\_reminder\_receive_threshold

The minimum access level for a user to show up in the reminder user picker. Note that this is the access level for the project for which the issue belongs. The default is DEVELOPER.

$g\_default\_bug_resolution

The resolution for a newly created issue. The default is OPEN. Look in constant_inc.php for other values.

$g\_default\_bug_severity

The severity for a newly created issue. The default is MINOR. Look in constant_inc.php for other values.

$g\_default\_bug_priority

The priority for a newly created issue. The default is NORMAL. Look in constant_inc.php for other values.

$g\_default\_bug_reproducibility

The reproducibility for a newly created issue. The default is REPRODUCIBILITY\_HAVENOTTRIED. Look in constant\_inc.php for other values.

$g\_default\_bug_projection

The projection for a newly created issue. The default is PROJECTION\_NONE. Look in constant\_inc.php for other values.

$g\_default\_bug_eta

The ETA for a newly created issue. The default is ETA\_NONE. Look in constant\_inc.php for other values.

$g\_default\_category\_for\_moves

Default global category to be used when an issue is moved from a project to another that doesn't have a category with a matching name. The default is 1 which is the "General" category that is created in the default database.

$g\_default\_limit_view

Number of bugs to show in the View Bugs page. The default value is 50.

$g\_default\_show_changed

Highlight bugs that have changed during the last N hours. The default value is 6.

$g\_hide\_status_default

Controls which issues will be displayed in the View Issues page. Default value is CLOSED, implying that all issues at "closed" or higher state will not be shown.

$g\_min\_refresh_delay

This is the delay between automatic refreshes of the View Issues page in minutes. Make sure refresh delay in user preferences isn't too short. If a users set their preferences to be lower then it is bumped back up to this minimum value. The default value is 10 minutes.

These settings are used as the default values for preferences for new users. Each user can override these settings through the user preferences form. Default language is set to default site language ($g\_default\_language).

$g\_default\_refresh_delay

Default page refresh delay (in minutes). This is for the bug listing pages. Default value is 30 minutes.

$g\_default\_redirect_delay

Default delay before a user is redirected to a page after being prompted by a message (eg: operational successful). Default value is 2 seconds.

$g\_default\_bugnote_order

This controls the time order in which bug notes are displayed. It can be either ASC (oldest first, the default) or DESC (newest first).

$g\_default\_email\_on\_new$g\_default\_email\_on\_assigned$g\_default\_email\_on\_feedback$g\_default\_email\_on\_resolved$g\_default\_email\_on\_closed

Default user preferences to enable receiving emails when a bug is set to the corresponding status. This option only has an effect if users have the required access level to receive such emails. Default value is ON.

$g\_default\_email\_on\_reopened

Default user preferences to enable receiving emails when bugs are re-opened. Default value is ON.

$g\_default\_email\_on\_bugnote

Default user preferences to enable receiving emails when bugnotes are added to bugs. Default value is ON.

$g\_default\_email\_on\_status$g\_default\_email\_on\_priority

Default user preferences to enable receiving emails when status or priority is changed. Default is ON. Note that this option is not implemented.

$g\_default\_email\_on\_new\_minimum\_severity$g\_default\_email\_on\_assigned\_minimum\_severity$g\_default\_email\_on\_feedback\_minimum\_severity$g\_default\_email\_on\_resolved\_minimum\_severity$g\_default\_email\_on\_closed\_minimum\_severity$g\_default\_email\_on\_reopened\_minimum\_severity$g\_default\_email\_on\_bugnote\_minimum\_severity

Default user preferences to enable filtering based on issue severity. These correspond to the email\_on\_<status> settings. Default is 'any'.

$g\_default\_email\_on\_bugnote\_minimum\_severity

Default user preference to enable filtering based on issue severity. These corresponds to the email\_on\_bugnote setting. Default is 'any'.

$g\_default\_email\_on\_status\_minimum\_severity$g\_default\_email\_on\_priority\_minimum\_severity

Default user preferences to enable filtering based on issue severity. These correspond to the email\_on\_status and email\_on\_priority settings. Default is 'any'. Note that this option is not yet implemented.

See also: [Section 7.4, “Email Notifications”](#admin.customize.email)

⁠5.17. Summary
--------------

These are the settings that are used to configuration options related to the Summary page. This page contains statistics about the bugs in MantisBT.

$g\_reporter\_summary_limit

Limit how many reporters to show in the summary page. This is useful when there are dozens or hundreds of reporters. The default value is 10.

$g\_date\_partitions

An array of date lengths to count bugs by (in days) for the summary by date. The default is to count for 1, 2, 3, 7, 30, 60, 90, 180, and 365.

$g\_summary\_category\_include\_project

Specifies whether category names should be preceded by project names (eg: \[Project\] Category) when the summary page is viewed for all projects. This is useful in the case where category names are common across projects. The default is OFF.

$g\_view\_summary_threshold

Specifies the access level required to view the summary page. Default is MANAGER.

$g\_severity\_multipliers

An array of multipliers which are used to determine the effectiveness of reporters based on the severity of bugs. Higher multipliers will result in an increase in reporter effectiveness. The default multipliers are:

$g\_severity\_multipliers = array ( FEATURE => 1,
                                  TRIVIAL => 2,
                                  TEXT => 3,
                                  TWEAK => 2,
                                  MINOR => 5,
                                  MAJOR => 8,
                                  CRASH => 8,
                                  BLOCK => 10 );

The keys of the array are severity constants from constant\_inc.php or from custom\_constants_inc.php if you have custom severities defined. The values are integers, typically in the range of 0 to 10. If you would like for a severity to not count towards effectiveness, set the value to 0 for that severity.

$g\_resolution\_multipliers

An array of multipliers which are used to determine the effectiveness of reporters based on the resolution of bugs. Higher multipliers will result in a decrease in reporter effectiveness. The only resolutions that need to be defined here are those which match or exceed $g\_bug\_resolution\_not\_fixed_threshold. The default multipliers are:

$g\_resolution\_multipliers = array( UNABLE\_TO\_REPRODUCE => 2,
                                   NOT_FIXABLE => 1,
                                   DUPLICATE => 3,
                                   NOT\_A\_BUG => 5,
                                   SUSPENDED => 1,
                                   WONT_FIX => 1 );

The keys of the array are resolution constants from constant\_inc.php or from custom\_constants_inc.php if you have custom resolutions defined. Resolutions not included here will be assumed to have a multiplier value of 0. The values are integers, typically in the range of 0 to 10. If you would like for a resolution to not count towards effectiveness, set the value to 0 for that resolution or remove it from the array completely. Note that these resolution multipliers are stacked on top of the severity multipliers. Therefore by default, a user reporting many duplicate bugs at severity level BLOCK will be far worse off than a user reporting many duplicate bugs at severity level FEATURE.

⁠5.18. Bugnote
--------------

$g\_bugnote\_order

Order to use for sorting bugnotes by submit date. Possible values include ASC for ascending and DESC for descending order. The default value is ASC.

⁠5.19. File Upload
------------------

MantisBT allows users to upload file attachments and associate them with bugs as well as projects. Bug attachments / project documents can be uploaded to the webserver or database. When bugs are uploaded to the webserver they are uploaded to the path that is configured in the project properties. In case of problems getting the file upload feature to work, check the following resources: [PHP Manual](http://www.php.net/manual/en/features.file-upload.php) .

$g\_allow\_file_upload

Whether to allow/disallow uploading of attachments. Default value is ON.

$g\_file\_upload_method

Specify the location for uploading attachments. In case of DISK methods you need to provide the webserver with write access rights to the configured upload path (configured in the project) and temporary upload path (used by PHP).

Values: DISK or DATABASE

Default: DATABASE

$g\_dropzone\_enabled

Whether to enable/disable drag and drop zone for uploading of attachments. Default value is ON.

$g\_file\_upload\_max\_num

Maximum number of files that can be uploaded simultaneously. Default value is 10.

$g\_max\_file_size

Maximum file size that can be uploaded. Default value is about 5MB. The maximum size is also affected by the PHP options post\_max\_size (default 8MB), upload\_max\_filesize (default 2MB) and memory_limit (default 128MB) specified in php.ini.

$g\_allowed\_files

Files that are allowed. Separate items by commas. eg. "zip,bmp,gif,jpg,txt" If $g\_allowed\_files is filled in NO other file types will be allowed. If empty it will assume any files are accepted that pass the $g\_disallowed\_files list.

$g\_disallowed\_files

Files that are not allowed. Separate items by commas. eg. "php,php3,phtml,html,class,java,exe,pl" $g\_disallowed\_files takes precedence over $g\_allowed\_files. It is recommended to disable all extensions that can be executed by your server.

$g\_preview\_attachments\_inline\_max_size

This limit applies to previewing of image / text attachments. If the attachment size is smaller than the specified value, the attachment is previewed with the issue details. The previewing can be disabled by setting this configuration to 0. The default value is 256 * 1024 (256KB).

$g\_fileinfo\_magic\_db\_file

Specify the filename of the magic database file. This is used by PHP 5.3.0 (or earlier versions with the fileinfo PECL extension) to guess what the MIME type of a file is. Usually it is safe to leave this setting as the default (blank) as PHP is usually able to find this file by itself.

$g\_file\_download\_xsendfile\_enabled

Enable support for sending files to users via a more efficient X-Sendfile method. HTTP server software supporting this technique includes Lighttpd, Cherokee, Apache with mod\_xsendfile and nginx. You may need to set the proceeding file\_download\_xsendfile\_header_name option to suit the server you are using.

$g\_file\_download\_xsendfile\_header_name

The name of the X-Sendfile header to use. Each server tends to implement this functionality in a slightly different way and thus the naming conventions for the header differ between each server. Lighttpd from v1.5, Apache with mod_xsendfile and Cherokee web servers use X-Sendfile. nginx uses X-Accel-Redirect and Lighttpd v1.4 uses X-LIGHTTPD-send-file.

⁠5.20. HTML
-----------

$g\_html\_make_links

This flag controls whether www URLs and email addresses are automatically converted into clickable links as well as where the www links open when clicked. The options are:

*   _OFF_ \- do not convert URLs or emails
    
*   _LINKS\_SAME\_WINDOW_ \- convert to links that open in current tab/window. NOTE: for backwards-compatibility, this is equivalent to _ON_.
    
*   _LINKS\_NEW\_WINDOW_ \- convert to links that open in a new tab/window
    

Default is _LINKS\_SAME\_WINDOW_.

$g\_html\_valid_tags

This is the list of HTML tags that are allowed.Do NOT include href or img tags here.Do NOT include tags that have parameters (eg. )The HTML code is allowed to enter the database as is. The $g\_allow\_href_tags does not have to be enabled to make URL links. The package will automatically hyperlink properly formatted URLs eg. http://blah.blah/ or mailto://me@more.com/

$g\_bottom\_include_page

Specifies a file to be included at the bottom of each page. It can be used e.g. for company branding, to include Google Analytics script, etc.

$g\_top\_include_page

Specifies a file to be included at the top of each page. It can be used e.g. for company branding.

If a file is supplied, the logo specified by `$g_logo_image` (see [Section 5.11, “Display”](#admin.config.display)) will not be shown, and the include file will have to handle display of the logo. To do so you can use the `html_print_logo()` API function, which will display the logo with an URL link if one has been specified in `$g_logo_url`

Example top include PHP file with logo and centered page title:

<div id="banner" style="display: flex; align-items: center;">
	<div style="width: 10%;">
		<?php html\_print\_logo(); ?>
	</div>

	<div class="center">
		<span class="pagetitle">
			<?php global $g\_window\_title; echo $g\_window\_title; ?>
		</span>
	</div>

	<div style="width: 10%;">
	</div>
</div>

$g\_css\_include_file

Set this to point to the CSS file of your choice.

$g\_css\_rtl\_include\_file

Set this to point to the RTL CSS file of your choice.

$g\_cdn\_enabled

A flag that indicates whether to use CDN (content delivery networks) for loading javascript libraries and their associated CSS. This improves performance for loading MantisBT pages. This can be disabled if it is desired that MantisBT doesn't reach out outside corporate network. Default OFF.

$g\_main\_menu\_custom\_options

This option will add custom options to the main menu. It is an array of arrays listing the caption, access level required, and the link to be executed. For example:

$g\_main\_menu\_custom\_options = array(
    array( 
        'title'        => 'My Link',
        'access_level' => MANAGER,
        'url'          => 'my_link.php',
        'icon'         => 'fa-plug'
    ),
    array( 
        'title'        => 'My Link2',
        'access_level' => ADMINISTRATOR,
        'url'          => 'my_link2.php',
        'icon'         => 'fa-plug'
    )
);

Note that if the caption is found in the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings)) it will be replaced by the corresponding translated string. Options will only be added to the menu if the current logged in user has the appropriate access level.

Use icons from [Font Awesome](http://fontawesome.io/icons/). Add "fa-" prefix to icon name.

Access level is an optional field, and no check will be done if it is not set. Icon is an optional field, and 'fa-plug' will be used if it is not set.

⁠5.21. Authentication
---------------------

### ⁠5.21.1. Global authentication parameters

$g\_login\_method

Specifies which method will be used to authenticate. It should be one of the following values (defaults to _MD5_):

*   MD5 - user's password is stored as a hash in the database
    
*   LDAP - authenticates against an LDAP (or Active Directory) server
    
*   BASIC_AUTH
    
*   HTTP_AUTH
    

In addition, the following deprecated values are supported for backwards-compatibility, and should no longer be used:

*   PLAIN - password is stored in plain, unencrypted text in the database
    
*   CRYPT
    
*   CRYPT\_FULL\_SALT
    

Note: you may not be able to easily switch encryption methods, so this should be carefully chosen at install time. However, MantisBT will attempt to "fall back" to older methods if possible.

$g_reauthentication

Determines whether MantisBT will require the user to re-authenticate before granting access to the Admin areas after timeout expiration. Defaults to _ON_

$g\_reauthentication\_expiry

Duration of the reauthentication timeout, in seconds. Defaults to 5 minutes.

### ⁠5.21.2. LDAP authentication method parameters

The parameters below are only used if $g\_login\_method (see above) is set to LDAP.

$g\_ldap\_server

Specifies the LDAP or Active Directory server to connect to, and must be provided as an URI

The protocol is optional, can be one of _ldap_ or _ldaps_, and defaults to _ldap_.

The port number is optional, and defaults to _389_. If this doesn't work, try using one of the following standard port numbers: 636 (ldaps); for Active Directory Global Catalog forest-wide search, use 3268 (ldap) or 3269 (ldaps)

Examples of valid URI:

ldap.example.com
ldap.example.com:3268
ldap://ldap.example.com/
ldaps://ldap.example.com:3269/

$g\_ldap\_root_dn

The root distinguished name for LDAP searches. For example, "dc=example, dc=com".

$g\_ldap\_organization

LDAP search filter for the organization, for example, "(organizationname=*Traffic)". Defaults to _''_.

$g\_ldap\_protocol_version

The LDAP Protocol Version. If 0, then the protocol version is not set. Defaults to _0_.

For Active Directory use protocol version 3.

$g\_ldap\_network_timeout

Duration of the timeout for TCP connection to the LDAP server (in seconds). Defaults to _0_ (infinite).

Set this to a low value when the hostname defined in $g\_ldap\_server resolves to multiple IP addresses, allowing rapid failover to the next available LDAP server.

$g\_ldap\_follow_referrals

Determines whether the LDAP library automatically follows referrals returned by LDAP servers or not. This maps to LDAP\_OPT\_REFERRALS ldap library option. Defaults to _ON_.

For Active Directory, this should be set to OFF.

$g\_ldap\_bind_dn

The distinguished name of the service account to use for binding to the LDAP server. For example, 'CN=ldap,OU=Administrators,DC=example,DC=com'.

$g\_ldap\_bind_passwd

The password for the service account used to establish the connection to the LDAP server.

$g\_ldap\_uid_field

The LDAP field for username. Defaults to _uid_.

For Active Directory, set to _sAMAccountName_.

$g\_ldap\_realname_field

The LDAP field for the user's real name (i.e. common name). Defaults to _cn_.

$g\_use\_ldap_realname

Use the realname specified in LDAP (ON) rather than the one stored in the database (OFF). Defaults to _OFF_.

Note that MantisBT will update the database with the data retrieved from LDAP when ON.

$g\_use\_ldap_email

Use the email address specified in LDAP (ON) rather than the one stored in the database (OFF). Defaults to _OFF_.

Note that MantisBT will update the database with the data retrieved from LDAP when ON.

$g\_ldap\_simulation\_file\_path

This configuration option allows replacing the ldap server with a comma-delimited text file for development or testing purposes.

The LDAP simulation file format is as follows:

*   One line per user
    
*   Each line has 4 comma-delimited fields
    
    *   username
        
    *   realname
        
    *   e-mail
        
    *   password
        
    
*   Any extra fields are ignored
    

**Warning**

On production systems, this option should be set to '' (This is the default).

$g\_ldap\_port

_Deprecated since MantisBT release 1.2.0a1._

The LDAP server port number should be defined as part of the URI in $g\_ldap\_server instead (see above).

⁠5.22. Status Settings
----------------------

$g\_bug\_submit_status

Status to assign to the bug when submitted. Default value is NEW_.

$g\_bug\_assigned_status

Status to assign to the bug when assigned. Default value is ASSIGNED.

$g\_bug\_reopen_status

Status to assign to the bug when reopened. Default value is FEEDBACK.

$g\_bug\_feedback_status

Status to assign to the bug when feedback is required from the issue reporter. Once the reporter adds a note the status moves back from feedback to $g\_bug\_assigned\_status or $g\_bug\_submit\_status based on whether the bug assigned or not.

$g\_reassign\_on_feedback

When a note is added to a bug currently in $g\_bug\_feedback\_status, and the note author is the bug's reporter, this option will automatically set the bug status to $g\_bug\_submit\_status or $g\_bug\_assigned_status if the bug is assigned to a developer. Default value is ON.

$g\_bug\_duplicate_resolution

Default resolution to assign to a bug when it is resolved as being a duplicate of another issue. Default value is DUPLICATE.

$g\_bug\_reopen_resolution

Resolution to assign to the bug when reopened. Default value is REOPENED.

$g\_auto\_set\_status\_to_assigned

Automatically set status to $g\_bug\_assigned_status whenever a bug is assigned to a person. Installations where assigned status is to be used when the defect is in progress, rather than just put in a person's queue should set it to OFF. Default is ON. For the status change to be effective, these conditions must be met:

*   Bug has no handler, and a new handler is selected
    
*   The assignment is not part of a explicit status change
    
*   Current bug status is lower than defined "assigned" status
    
*   "Assigned" status is reachable by workflow configuration
    

If the conditions are not met, the assignment is still made, but status will not be modified.

$g\_bug\_resolved\_status\_threshold

Bug is resolved, ready to be closed or reopened. In some custom installations a bug maybe considered as resolved when it is moved to a custom (FIXED OR TESTED) status.

$g\_bug\_resolution\_fixed\_threshold

Threshold resolution which denotes that a bug has been resolved and successfully fixed by developers. Resolutions above and including this threshold and below $g\_bug\_resolution\_not\_fixed_threshold are considered to be resolved successfully. Default value is FIXED.

$g\_bug\_resolution\_not\_fixed_threshold

Threshold resolution which denotes that a bug has been resolved without being successfully fixed by developers. Resolutions above this threshold are considered to be resolved in an unsuccessful way. Default value is UNABLE\_TO\_REPRODUCE.

$g\_bug\_readonly\_status\_threshold $g\_update\_readonly\_bug\_threshold

Bug becomes readonly if its status is >= $g\_bug\_readonly\_status\_threshold. The bug becomes read/write again if re-opened and its status becomes less than this threshold. The default is RESOLVED. Once the bug becomes readonly, a user with an access level greater than or equal to $g\_update\_readonly\_bug\_threshold can still edit the bug.

$g\_status\_enum_workflow

'status\_enum\_workflow' defines the workflow, and reflects a simple 2-dimensional matrix. For each existing status, you define which statuses you can go to from that status, e.g. from NEW_ you might list statuses '10:new,20:feedback,30:acknowledged' but not higher ones.The default is no workflow, where all states are accessible from any others.

$g\_report\_bug_threshold

This is the access level required to open a bug. The default is REPORTER.

$g\_update\_bug_threshold

This is the access level generally required to update the content of a bug. The default is UPDATER.

$g\_handle\_bug_threshold

This is the access level generally required to be access level needed to be listed in the assign to field. The default is DEVELOPER. If a more restrictive setting can be determined from $g\_set\_status_threshold, it will be used.

$g\_update\_bug\_status\_threshold $g\_set\_status_threshold

These settings control the access level required to promote a bug to a new status once the bug is opened.$g\_set\_status\_threshold is an array indexed by the status value that allows a distinct setting for each status. It defaults to blank.If the appropriate status is not defined above, $g\_update\_bug\_status_threshold is used instead. The default is DEVELOPER.

$g\_bugnote\_user\_edit\_threshold

Threshold at which a user can edit his/her own bugnotes. The default value is equal to the configuration setting $g\_update\_bugnote_threshold.

$g\_bugnote\_user\_delete\_threshold

Threshold at which a user can delete his/her own bugnotes. The default value is equal to the configuration setting $g\_delete\_bugnote_threshold.

$g\_bugnote\_user\_change\_view\_state\_threshold

Threshold at which a user can change the view status of his/her own bugnotes. The default value is equal to the configuration setting $g\_change\_view\_status\_threshold.

$g\_allow\_reporter_close

If set, the bug reporter is allowed to close their own bugs, regardless of their access level. The default is OFF.

$g\_allow\_reporter_reopen

If set, the bug reporter is allowed to reopen their own bugs once resolved, regardless of their access level. This allows the reporter to disagree with the resolution. The default is ON.

$g\_allow\_parent\_of\_unresolved\_to\_close

If set, no check is performed on the status of a bug's children, which allows the parent to be closed whether or not the children have been resolved. The default is OFF.

See also: [Section 7.5, “Customizing Status Values”](#admin.customize.status)

⁠5.23. Filters
--------------

$g\_filter\_by\_custom\_fields

Show custom fields in the filter dialog and use these in filtering. Defaults to ON.

$g\_filter\_custom\_fields\_per_row

The number of filter fields to display per row. The default is 8.

$g\_view\_filters = SIMPLE_DEFAULT;

Controls the display of the filter pages. Possible values are:

*   SIMPLE_ONLY - only allow use of simple view
    
*   ADVANCED_ONLY - only allow use of advanced view (allows multiple value selections)
    
*   SIMPLE_DEFAULT - defaults to simple view, but shows a link for advanced
    
*   ADVANCED_DEFAULT - defaults to advanced view, but shows a link for simple
    

$g\_use\_dynamic_filters = ON;

This switch enables the use of AJAX to dynamically load and create filter form controls upon request. This method will reduce the amount of data that needs to be transferred upon each page load dealing with filters and thus will result in speed improvements and bandwidth reduction.

$g\_create\_permalink_threshold

The threshold required for users to be able to create permalinks (default DEVELOPER). To turn this feature off use NOBODY.

$g\_create\_short_url

The service to use to create a short URL. The %s will be replaced by the long URL. By default http://www.tinyurl service is used to shorten URLs.

⁠5.24. Misc
-----------

$g\_user\_login\_valid\_regex

The regular expression to use when validating new user login names. The default regular expression allows a-z, A-Z, 0-9, +, -, dot, space and underscore. If you change this, you may want to update the ERROR\_USER\_NAME_INVALID string in the language files to explain the rules you are using on your site.

See [Wikipedia](http://en.wikipedia.org/wiki/Regular_Expression) for more details about regular expressions. For testing regular expressions, use [Rubular](http://rubular.com/).

$g\_monitor\_bug_threshold

Access level needed to monitor bugs. The default value is REPORTER.

$g\_monitor\_add\_others\_bug_threshold

Access level needed to add other users to the list of users monitoring a bug. The default value is DEVELOPER.

$g\_monitor\_delete\_others\_bug_threshold

Access level needed to delete other users from the list of users monitoring a bug. The default value is DEVELOPER.

$g\_limit\_reporters

Limit reporters to only viewing bugs that they report.

$g\_allow\_reporter_close

Allow reporters to close the bugs they reported.

$g\_delete\_bug_threshold

Allow the specified access level and above to delete bugs.

$g\_bug\_move\_access\_level

Allow the specified access level and above to move bugs between projects.

$g\_allow\_account_delete

Allow users to delete their own accounts.

$g\_allow\_anonymous_login

Enable anonymous access to Mantis. You must also specify $g\_anonymous\_account as the account which anonymous users will browse Mantis with. The default setting is OFF.

$g\_anonymous\_account

Define the account which anonymous users will assume when using Mantis. This account is considered by Mantis to be protected from modification. In other words, this account can only be modified by users with an access level equal to or higher than $g\_manage\_user_threshold. Anonymous users will not be able to adjust preferences or change account settings like normal users can.

You will need to create a new account to use for this $g\_anonymous\_account setting. When creating the account you should specify a password, email address and so forth in the same way you'd create any other account. It is suggested that the access level for this account be set to VIEWER or some other read only level.

The anonymous user account will not receive standard notifications and can not monitor issues.

The default setting is blank/undefined. You only need to define this setting when $g\_allow\_anonymous_login is set to ON.

$g\_bug\_link_tag

If a number follows this tag it will create a link to a bug. Default is '#'.

*   '#': a link would be #45
    
*   'bug:' a link would be bug:98
    

$g\_bugnote\_link_tag

If a number follows this tag it will create a link to a bug note. Default is '~'.

*   '~': a link would be ~45
    
*   'bugnote:' a link would be bugnote:98
    

$g\_enable\_project_documentation

Specifies whether to enable support for project documents or not. Default is OFF. This feature is deprecated and is expected to be moved to a plugin in the future.

$g\_admin\_site_threshold

Threshold at which a user is considered to be a site administrator. These users have the highest level of access to your Mantis installation. This access level is required to change key Mantis settings (such as server paths) and perform other administrative duties. You may need to change this value from the default of ADMINISTRATOR if you have defined a new access level to replace the default ADMINISTRATOR level in constant_inc.php.

**Warning**

This is a potentially dangerous configuration option. Users at or above this threshold value will have permission to all aspects of Mantis including the admin/ directory. With this access level, users can damage your installation of Mantis, destroy your database or have elevated access to your server.

DO NOT CHANGE THIS VALUE UNLESS YOU ABSOLUTELY KNOW WHAT YOU'RE DOING. BE VERY CAREFUL WITH CHANGING THIS CONFIGURATION VALUE FROM THE DEFAULT SETTING.

$g\_manage\_configuration_threshold

The threshold required for users to be able to manage configuration of a project. This includes workflow, email notifications, columns to view, and others. Default is MANAGER.

$g\_view\_configuration_threshold

Threshold for users to view the raw system configurations as stored in the database. The default value is ADMINISTRATOR.

$g\_set\_configuration_threshold

Threshold for users to set the system configurations generically via MantisBT web interface. The default value is ADMINISTRATOR.

**Warning**

Users who have access to set configuration via the interface MUST be trusted. This is due to the fact that these users can leverage the interface to _inject PHP code_ into the system, which is a potential security risk.

⁠5.25. Cookies
--------------

$g\_cookie\_path

Specifies the path under which a cookie is visible.

All scripts in this directory and its sub-directories will be able to access MantisBT cookies.

Default value is '/'. It is recommended to set this to the actual MantisBT path.

$g\_cookie\_domain

The domain that the MantisBT cookies are available to.

$g\_cookie\_prefix

Prefix for all MantisBT cookies

This should be an identifier which does not include spaces or periods, and should be unique per MantisBT installation, especially if $g\_cookie\_path is not restricting the cookies' scope to the actual MantisBT directory.

It applies to the cookies listed below. Their actual names are calculated by prepending the prefix, and it is not expected for the user to need to change these.

*   $g\_string\_cookie
    
*   $g\_project\_cookie
    
*   $g\_view\_all_cookie
    
*   $g\_manage\_users_cookie
    
    Stores the filter criteria for the Manage Users page
    
*   $g\_manage\_config_cookie
    
    Stores the filter criteria for the Manage Config Report page
    
*   $g\_logout\_cookie
    
*   $g\_bug\_list_cookie
    

⁠5.26. Speed Optimisation
-------------------------

$g\_compress\_html

This option is used to enable buffering/compression of HTML output if the user's browser supports it. Default value is ON. This option will be ignored in the following scenarios:

*   If php.ini has zlib.output_compression enabled.
    
*   If php.ini has output_handler set to a handler.
    
*   If PHP does not include the zlib extension (PHP 4.3.0 and later include zlib extension by default).
    

You can check the loaded modules in your PHP by running "php -m" on the command line, or by using php_info() command in a php script.

$g\_use\_persistent_connections

Use persistent database connections, setting this to ON will open the database once per connection, rather than once per page. There might be some scalability issues here and that is why it is defaulted to OFF.

⁠5.27. Reminders
----------------

Sending reminders is a feature where a user can notify / remind other users about a bug. In the past, only selected users like the managers, or developers would get notified about bugs. However, these people can not invite other people (through MantisBT) to look at or monitor these bugs.

This feature is useful if the Manager needs to get feedback from testers / requirements team about a certain bug. It avoid needing this person to do this manual outside MantisBT. It also records the history of such reminders.

$g\_store\_reminders

Specifies if reminders should be stored as bugnotes. The bugnote will still reflect that it is a reminder and list the names of users that got it. Default is ON.

$g\_reminder\_recipients\_monitor\_bug

Specifies if users who receive reminders about a bug, should be automatically added to the monitor list of that bug. Default is ON.

$g\_mentions\_enabled

Enables or disables the @ mentions feature. Default is ON. When a user is @ mentioned in an issue or a note, they receive an email notification to get their attention. Users can be @ mentioned using their username and not realname.

This feature works with fields like summary, description, additional info, steps to reproduce and notes.

$g\_mentions\_tag

The tag to use for prefixing mentions. Default is '@'.

⁠5.28. Bug History
------------------

Bug history is a feature where MantisBT tracks all modifications that are made to bugs. These include everything starting from its creation, till it is closed. For each change, the bug history will record the time stamp, user who made the change, field that changed, old value, and new value.

Independent of the these settings, MantisBT will always track the changes to a bug and add them to its history.

$g\_history\_default_visible

Make the bug history visible by default. If this option is not enabled, then the user will have to click on the Bug History link to see the bug history. Default is ON.

$g\_history\_order

Show bug history entries in ascending or descending order. Default value is 'ASC'.

⁠5.29. Sponsorship
------------------

$g\_enable\_sponsorship

enable/disable the whole issue sponsorship feature. The default os OFF.

$g\_sponsorship\_currency

The currency string used for all sponsorships. The default is 'US$'.

$g\_minimum\_sponsorship_amount

The minimum sponsorship amount that can be entered. If the user enters a value less than this, an error will be flagged. The default is 5.

$g\_view\_sponsorship\_total\_threshold

The access level threshold needed to view the total sponsorship for an issue by all users. The default is VIEWER.

$g\_view\_sponsorship\_details\_threshold

The access level threshold needed to view the details of the sponsorship (i.e., who will donate what) for an issue by all users. The default is VIEWER.

$g\_sponsor\_threshold

The access level threshold needed to allow user to sponsor issues. The default is REPORTER. Note that sponsoring user must have their email set in their profile.

$g\_handle\_sponsored\_bugs\_threshold

The access level required to be able to handle sponsored issues. The default is DEVELOPER.

$g\_assign\_sponsored\_bugs\_threshold

The access level required to be able to assign a sponsored issue to a user with access level greater or equal to 'handle\_sponsored\_bugs_threshold'. The default is MANAGER.

⁠5.30. Custom Fields
--------------------

$g\_manage\_custom\_fields\_threshold

Access level needed to manage custom fields. The default is ADMINISTRATOR.

$g\_custom\_field\_link\_threshold

Access level needed to link a custom field to a project. The default is MANAGER.

$$g\_custom\_field\_edit\_after_create

This flag determines whether to start editing a custom field immediately after creating it, or return to the definition list. The default is ON (edit the custom field after creating).

⁠5.31. My View Settings
-----------------------

$g\_my\_view_boxes

This is an array of values defining the order that the boxes to be shown. A box that is not to be shown can have its value set to 0. The default is:

$g\_my\_view_boxes = array( 'assigned' => '1',
                          'unassigned' => '2',
                          'reported' => '3',
                          'resolved' => '4',
                          'recent_mod' => '5',
                          'monitored' => '6'
                   );

If you want to change the definition, copy the default value and apply the changes.

$g\_my\_view\_bug\_count

Number of bugs shown in each box. The default is 10.

$g\_default\_home_page

Default page to transfer to after Login or Set Project. The default is 'my\_view\_page.php'. An alternative would be 'view\_all\_bugs\_page.php' or 'main\_page.php'.

⁠5.32. Relationship Graphs
--------------------------

$g\_relationship\_graph_enable

This enables the relationship graphs feature where issues are represented by nodes and relationships as links between such nodes. Possible values are ON or OFF. Default is OFF.

This feature requires installing [GraphViz](http://www.research.att.com/sw/tools/graphviz/) (all OSes except Windows) or [WinGraphviz](http://home.so-net.net.tw/oodtsen/wingraphviz/) (only Windows). Refer to the notes near the top of core/graphviz\_api.php and core/relationship\_graph_api.php for more information.

$g\_relationship\_graph_fontname

Font name and size, as required by Graphviz. If Graphviz fails to run for you, you are probably using a font name that gd PHP extension can't find. On Linux, try the name of the font file without the extension. The default value is 'Arial'.

$g\_relationship\_graph_fontsize

Font size, default is 8.

$g\_relationship\_graph_orientation

Default dependency orientation. If you have issues with lots of children or parents, leave as 'horizontal', otherwise, if you have lots of "chained" issue dependencies, change to 'vertical'. Default is 'horizontal'.

$g\_relationship\_graph\_max\_depth

Max depth for relation graphs. This only affects relationship graphs, dependency graphs are drawn to the full depth. The default value is 2.

$g\_relationship\_graph\_view\_on_click

If set to ON, clicking on an issue on the relationship graph will open the bug view page for that issue, otherwise, will navigate to the relationship graph for that issue.

$g\_dot\_tool

The full path for the dot tool. The webserver must have execute permission to this program in order to generate relationship graphs. This configuration option is not relevant for Windows. The default value is '/usr/bin/dot'.

$g\_neato\_tool

The full path for the neato tool. The webserver must have execute permission to this program in order to generate relationship graphs. This configuration option is not relevant for Windows. The default value is '/usr/bin/neato'.

⁠5.33. Wiki Integration
-----------------------

$g\_wiki\_enable

Set to ON to enable Wiki integration. Defaults to OFF.

$g\_wiki\_engine

The following Wiki Engine values are supported:

*   _dokuwiki_: [DokuWiki](https://www.dokuwiki.org/)
    
*   _mediawiki_: [MediaWiki](https://www.mediawiki.org/)
    
*   _twiki_: [TWiki](http://twiki.org/)
    
*   _wikka_: [WikkaWiki](http://wikkawiki.org/)
    
*   _xwiki_: [XWiki](http://www.xwiki.org/)
    

$g\_wiki\_root_namespace

Wiki namespace to be used as root for all pages relating to this MantisBT installation.

$g\_wiki\_engine_url

URL under which the wiki engine is hosted.

Must be on the same server as MantisBT, requires a trailing '/'.

If left empty (default), the URL is derived from the global MantisBT path ($g_path, see [Section 5.3, “Path”](#admin.config.path)), replacing the URL's path component by the wiki engine string (i.e. if $g\_path = 'http://example.com/mantis/' and $g\_wiki_engine = 'dokuwiki', the wiki URL will be 'http://example.com/dokuwiki/').

⁠5.34. Sub-Projects
-------------------

$g\_subprojects\_enabled

Whether sub-projects feature should be enabled. Before turning this flag OFF, make sure all sub-projects are moved to top level projects, otherwise they won't be accessible. The default value is ON.

$g\_subprojects\_inherit_versions

Whether sub-projects should inherit versions from parent projects. For project X which is a sub-project of A and B, it will have versions from X, A and B. The default value is ON.

$g\_subprojects\_inherit_categories

Whether sub-projects should inherit categories from parent projects. For project X which is a sub-project of A and B, it will have categories from X, A and B. The default value is ON.

⁠5.35. Field Visibility
-----------------------

$g\_enable\_eta

Enable or disable usage of 'ETA' field. Default value is OFF.

$g\_enable\_projection

Enable or disable usage of 'Projection' field. Default value is OFF.

$g\_enable\_product_build

Enable or disable usage of 'Product Build' field. Default is OFF.

$g\_bug\_report\_page\_fields

An array of optional fields to show on the bug report page.

The following optional fields are allowed: additional\_info, attachments, category\_id, due\_date, handler, os, os\_version, platform, priority, product\_build, product\_version, reproducibility, resolution, severity, status, steps\_to\_reproduce, tags, target\_version, view\_state.

The summary and description fields are always shown and do not need to be listed in this option. Fields not listed above cannot be shown on the bug report page. Visibility of custom fields is handled via the Manage => Manage Custom Fields administrator page.

This setting can be set on a per-project basis by using the Manage => Manage Configuration administrator page.

$g\_bug\_view\_page\_fields

An array of optional fields to show on the bug view page.

The following optional fields are allowed: additional\_info, attachments, category\_id, date\_submitted, description, due\_date, eta, fixed\_in\_version, handler, id, last\_updated, os, os\_version, platform, priority, product\_build, product\_version, project, projection, reporter, reproducibility, resolution, severity, status, steps\_to\_reproduce, summary, tags, target\_version, view\_state.

Fields not listed above cannot be shown on the bug view page. Visibility of custom fields is handled via the Manage => Manage Custom Fields administrator page.

This setting can be set on a per-project basis by using the Manage => Manage Configuration administrator page.

$g\_bug\_update\_page\_fields

An array of optional fields to show on the bug update page.

The following optional fields are allowed: additional\_info, category\_id, date\_submitted, description, due\_date, eta, fixed\_in\_version, handler, id, last\_updated, os, os\_version, platform, priority, product\_build, product\_version, project, projection, reporter, reproducibility, resolution, severity, status, steps\_to\_reproduce, summary, target\_version, view\_state.

Fields not listed above cannot be shown on the bug update page. Visibility of custom fields is handled via the Manage => Manage Custom Fields administrator page.

This setting can be set on a per-project basis by using the Manage => Manage Configuration administrator page.

$g\_bug\_change\_status\_page_fields

An array of optional fields to show on the bug change status page. This only changes the visibility of fields shown below the form used for updating the status of an issue.

The following optional fields are allowed: additional\_info, attachments, category\_id, date\_submitted, description, due\_date, eta, fixed\_in\_version, handler, id, last\_updated, os, os\_version, platform, priority, product\_build, product\_version, project, projection, reporter, reproducibility, resolution, severity, status, steps\_to\_reproduce, summary, tags, target\_version, view\_state.

Fields not listed above cannot be shown on the bug change status page. Visibility of custom fields is handled via the Manage => Manage Custom Fields administrator page (use the same settings as the bug view page).

This setting can be set on a per-project basis by using the Manage => Manage Configuration administrator page.

⁠5.36. System Logging and Debugging
-----------------------------------

This section describes settings which can be used to troubleshoot MantisBT operations as well as assist during development.

$g\_show\_timer

Time page loads. The page execution timer shows at the bottom of each page.

Default is OFF.

$g\_show\_memory_usage

Show memory usage for each page load in the footer.

Default is OFF.

$g\_debug\_email

Used for debugging e-mail notifications. When it is '', the emails are sent normally. If set to an e-mail address, all messages are sent to it, with the original recipients (To, Cc, Bcc) included in the message body.

Default is ''.

$g\_show\_queries_count

Shows the total number/unique number of queries executed to serve the page.

Default is OFF.

$g\_display\_errors

Errors Display Method. Defines what [errors](http://php.net/errorfunc.constants) are displayed and how. Available options are:

DISPLAY\_ERROR\_HALT

Stop and display the error message (including variables and backtrace if _$g\_show\_detailed_errors_ is ON).

DISPLAY\_ERROR\_INLINE

Display a one line error and continue execution.

DISPLAY\_ERROR\_NONE

Suppress the error (no display). This is the default behavior for unspecified [errors constants](http://php.net/errorfunc.constants).

The default settings, recommended for use in production will only display and exit on errors and suppress warninga and notices.

Recommended `config_inc.php` settings for developers:

$g\_display\_errors = array(
	E\_USER\_WARNING => DISPLAY\_ERROR\_HALT,
	E\_WARNING      => DISPLAY\_ERROR_HALT,
	E\_ALL          => DISPLAY\_ERROR_INLINE,
);

**Note**

The system automatically sets _$g\_display\_errors_ to the above recommended development values when the server's name is _localhost_.

Less intrusive settings, recommended for testing purposes:

$g\_display\_errors = array(
	E\_USER\_WARNING => DISPLAY\_ERROR\_INLINE,
	E\_WARNING      => DISPLAY\_ERROR_INLINE,
);

**Warning**

`E_USER_ERROR` should _always_ be set to `DISPLAY_ERROR_HALT`. Using any other value will cause program execution to continue despite the error, which may lead to data integrity issues and/or cause MantisBT to function incorrectly.

$g\_show\_detailed_errors

Shows a list of variables and their values whenever an error is triggered. Only applies to error types configured to `DISPLAY_ERROR_HALT` in _$g\_display\_errors_.

Default is OFF.

**Warning**

Setting this to ON is a potential security hazard, as it can expose sensitive information. Only enable this setting for debugging purposes when you really need it.

$g\_stop\_on_errors

Debug messages. If this option is turned OFF, page redirects will function if a non-fatal error occurs. For debugging purposes, you can set this to ON so that any non-fatal error will prevent page redirection, allowing you to see the errors.

Default is OFF.

**Note**

This should only be turned on when debugging.

$g\_log\_level

The system logging interface is used to extract detailed debugging information for the MantisBT system. It can also serve as an audit trail for users' actions.

This controls the type of logging information recorded. Refer to _$g\_log\_destination_ for details on where to save the logs.

The available log channels are:

LOG_NONE

Disable logging

LOG_AJAX

logs AJAX events

LOG_DATABASE

logs database events and executed SQL queries

LOG_EMAIL

logs issue id, message type and recipients for all emails sent

LOG\_EMAIL\_VERBOSE

Enables extra logging for troubleshooting internals of email queuing and sending.

LOG\_EMAIL\_RECIPIENT

logs the details of email recipient determination. Each user id is listed as well as why they are added, or deleted from the recipient list

LOG_FILTERING

logs filter operations

LOG_LDAP

logs the details of LDAP operations

LOG_WEBSERVICE

logs the details of Web Services operations (e.g. SOAP API)

LOG_PLUGIN

Enables logging from plugins.

LOG_ALL

combines all of the above log levels

Default is LOG_NONE.

**Note**

Multiple log channels can be combined using [PHP bitwise operators](http://php.net/language.operators.bitwise) , e.g.

$g\_log\_level = LOG\_EMAIL | LOG\_EMAIL_RECIPIENT;

or

$g\_log\_level = LOG\_ALL & ~LOG\_DATABASE;

$g\_log\_destination

Specifies where the log data goes. The following five options are available:

''

The empty string means [default PHP error log settings](http://php.net/error_log)

'none'

Don't output the logs, but would still trigger EVENT_LOG plugin event.

'file'

Log to a specific file, specified as an absolute path, e.g. `'file:/var/log/mantis.log'` (Unix) or `'file:c:/temp/mantisbt.log'` (Windows)

**Note**

This file must be writable by the web server running MantisBT.

'firebug'

make use of Firefox [Firebug Add-on](http://getfirebug.com/). If user is not running firefox, this options falls back to the default php error log settings.

'page'

Display log output at bottom of the page. See also _$g\_show\_log_threshold_ to restrict who can see log data.

Default is '' (empty string).

$g\_show\_log_threshold

Indicates the access level required for a user to see the log output (if _$g\_log\_destination_ is 'page').

Default is ADMINISTRATOR.

**Note**

This threshold is compared against the user's _global access level_ rather than the one from the currently active project.

⁠5.37. Time Tracking
--------------------

$g\_time\_tracking_enabled

Turns Time Tracking features ON or OFF - Default is OFF

$g\_time\_tracking\_without\_note

Allow time tracking to be recorded without writing some text in the associated bugnote - Default is ON

$g\_time\_tracking\_with\_billing

Adds calculation links to workout how much time has been spent between a particular time frame. Currently it will allow you to enter a cost/hour and will work out some billing information. This will become more extensive in the future. Currently it is more of a proof of concept.

$g\_time\_tracking\_billing\_rate

Default billing rate per hour - Default is 0

$g\_time\_tracking_stopwatch

Instead of a text field turning this option on places a stopwatch on the page with **Start/Stop** and **Reset** buttons next to it. A bit gimmicky, but who cares.

$g\_time\_tracking\_view\_threshold

Access level required to view time tracking information - Default DEVELOPER.

$g\_time\_tracking\_edit\_threshold

Access level required to add/edit time tracking information (If you give a user $g\_time\_tracking\_edit\_threshold you must give them $g\_time\_tracking\_view\_threshold as well) - Default DEVELOPER.

$g\_time\_tracking\_reporting\_threshold

Access level required to run reports (not completed yet) - Default MANAGER.

⁠5.38. API
----------

MantisBT exposes a webservice API which allows remote clients to interact with MantisBT and perform many of the usual tasks, such as reporting issues, running filtered searches and retrieving attachments.

The SOAP API is enabled by default and available at `/api/soap/mantisconnect.php` below the MantisBT root. A WSDL file which describes the web service is available at `/api/soap/mantisconnect.php?wsdl` below the MantisBT root.

The REST API is experimental and is disabled by default. A Swagger sandbox and documentation for REST API is available at `/api/rest/swagger/` below the MantisBT root.

The following options are used to control the behaviour of the MantisBT SOAP API:

$g\_webservice\_readonly\_access\_level_threshold

Minimum global access level required to access webservice for readonly operations.

$g\_webservice\_readwrite\_access\_level_threshold

Minimum global access level required to access webservice for read/write operations.

$g\_webservice\_admin\_access\_level_threshold

Minimum global access level required to access the administrator webservices.

$g\_webservice\_specify\_reporter\_on\_add\_access\_level\_threshold

Minimum project access level required for caller to be able to specify reporter when adding issues or issue notes. Defaults to DEVELOPER.

$g\_webservice\_rest_enabled

Whether the REST API is enabled or not. Note that this flag only impacts API Token based auth. Hence, even if the API is disabled, it can still be used from the Web UI using cookie based authentication. Default ON.

### ⁠5.38.1. Disabling the webservice API

If you wish to temporarily disable the webservice API it is sufficient to set the specific access thresholds to NOBODY:

`$g_webservice_readonly_access_level_threshold = $g_webservice_readwrite_access_level_threshold = $g_webservice_admin_access_level_threshold = NOBODY;`

While the SOAP API will still be accessible, it will not allow users to retrieve or modify data.

⁠5.39. Anti-Spam Configuration
------------------------------

$g\_antispam\_max\_event\_count

Max number of events to allow for users with default access level (see $g\_default\_new\_account\_access_level) when signup is enabled. Use 0 for no limit. Default is 10.

$g\_antispam\_time\_window\_in_seconds

Time window to enforce max events within. Default is 3600 seconds (1 hour).

⁠5.40. Due Date
---------------

$g\_due\_date\_update\_threshold

Threshold to update due date submitted. Default is NOBODY.

$g\_due\_date\_view\_threshold

Threshold to see due date. Default is NOBODY.

$g\_due\_date_default

Default due date value for newly submitted issues: Empty string for no due date set. Related date that is accepted by [strtotime()](http://php.net/manual/en/function.strtotime.php), e.g. 'today' or '+2 days'. Default is ''.

⁠5.41. User Management
----------------------

$g\_impersonate\_user_threshold

The threshold for a user to be able to impersonate another user, or NOBODY to disable impersonation. Default ADMINISTRATOR.

$g\_manage\_user_threshold

The threshold for a user to manage user accounts. Default ADMINISTRATOR.

⁠5.42. View Page Settings
-------------------------

$g\_issue\_activity\_note\_attachments\_seconds\_threshold

If a user submits a note with an attachments (with the specified # of seconds) the attachment is linked to the note. Or 0 for disabling this feature.

⁠Chapter 6. Page descriptions
=============================

[6.1. Login page](#admin.pages.login)

[6.2. Main page](#admin.pages.main)

[6.3. View Issues page](#admin.pages.filter)

[6.4. Issue View page](#admin.pages.issueview)

[6.5. Issue Change Status page](#admin.pages.issuestatus)

[6.6. Issue Edit page](#admin.pages.issueedit)

[6.7. My Account Page](#admin.pages.account)

[6.7.1. Preferences](#admin.pages.account.prefs)

[6.7.2. Profiles](#admin.pages.account.profiles)

[6.7.3. Manage Columns](#admin.pages.account.managecolumns)

[6.7.4. API Tokens](#admin.pages.account.apitokens)

[6.8. System Management Pages](#admin.pages.manage)

[6.8.1. Manage Users](#admin.pages.manage.users)

[6.8.2. Manage Projects Page](#admin.pages.manage.projects)

[6.8.3. Manage Custom Fields](#admin.pages.manage.customfields)

[6.8.4. Manage Global Profiles](#admin.pages.manage.profiles)

[6.8.5. Manage Configuration](#admin.pages.manage.config)

[6.9. Monitor Issue](#admin.pages.monitor)

[6.10. Reopen Issue](#admin.pages.reopen)

[6.11. Delete Issue](#admin.pages.delete)

[6.12. Close Issue](#admin.pages.close)

[6.13. Assign to Me](#admin.pages.assigntome)

[6.14. Resolve Issue](#admin.pages.resolve)

[6.15. News Syndication](#admin.pages.news)

⁠6.1. Login page
----------------

Just enter your username and password and hit the login button. There is also a Save Login checkbox to have the package remember that you are logged in between browser sessions. You will have to have cookies enabled to login.If the account doesn't exist, the account is disabled, or the password is incorrect then you will remain at the login page. An error message will be displayed.The administrator may allow users to sign up for their own accounts. If so, a link to Signup for your own account will be available.The administrator may also have anonymous login allowed. Anonymous users will be logged in under a common account.You will be allowed to select a project to work in after logging in. You can make a project your default selection from the Select Project screen or from your Account Options.SignupHere you can signup for a new account. You must supply a valid email address and select a unique username. Your randomly generated password will be emailed to your email account. If MantisBT is setup so that the email password is not to be emailed, newly generated accounts will have an empty password.

⁠6.2. Main page
---------------

This is the first page you see upon logging in. It shows you the latest news updates for the bugtracker. This is a simple news module (based off of work by Scott Roberts) and is to keep users abreast of changes in the bugtracker or project. Some news postings are specific to projects and others are global across the entire bugtracker. This is set at the time of posting in the Edit News section.The number of news posts is controlled by a global variable. When the number of posts is more than the limit, a link to show "older news" is displayed at the bottom. Similarly a "newer news" is displayed when you have clicked on "older news".There is an Archives option at the bottom of the page to view all listings.ArchivesA title/date/poster listing of ALL past news articles will be listed here. Clicking on the link will bring up the specified article. This listing will also only display items that are either global or specific to the selected project.

⁠6.3. View Issues page
----------------------

Here we can view the issue listings. The page has a set of viewing filters at the top and the issues are listed below.FiltersThe filters control the behavior of the issues list. The filters are saved between browsing sessions but do not currently save sort order or direction.If the number of issues exceeds the "Show" count in the filter a set of navigation to go to "First", "Last", "Previous", "Next" and specific page numbers are added.The Search field will look for simple keyword matches in the summary, description, steps to reproduce, additional information, issue id, or issue text id fields. It does not search through issue notes. Issue List - The issues are listed in a table and the attributes are listed in the following order: priority, id, number of issue notes, category, severity, status, last updated, and summary. Each (except for number of issue notes) can be clicked on to sort by that column. Clicking again will reverse the direction of the sort. The default is to sort by last modification time, where the last modified issue appears at the top. The issue id is a link that leads to a more detailed report about the issue. You can also add issue notes here. The number in the issue note count column will be bold if an issue note has been added in the specified time frame. The addition of an issue note will make the issue note link of the issue appear in the unvisited state. The text in the "Severity" column will be bold if the severity is major, crash, or block and the issue not resolved. The text in the "Updated" column will be bold if the issue has changed in the last "Changed(hrs)" field which is specified in the viewing filters. Each table row is color coded according to the issue status. The colors can be customised through MantisBT configuration pages (see [Chapter 5, _Configuration_](#admin.config) for details). Severities block - prevents further work/progress from being made crash - crashes the application or blocking, major - major issue, minor - minor issue, tweak - needs tweaking, text - error in the text, trivial - being nit picky, feature - requesting new feature - Status new - new issue, feedback - issue requires more information from reporter, acknowledged - issue has been looked at but not confirmed or assigned, confirmed - confirmed and reproducible (typically set by an Updater or other Developer), assigned - assigned to a Developer, resolved - issue should be fixed, waiting on confirmation of fix, closed - issue is closed, Moving the mouse over the status text will show the resolution as a title. This is rendered by some browsers as a bubble and in others as a status line text.

⁠6.4. Issue View page
---------------------

Here is the simple listing of the issue report. Most of the fields are self-explanatory. "Assigned To" will contain the developer assigned to handle the issue. Priority is fully functional but currently does nothing of importance. Duplicate ID is used when an issue is a duplicate of another. It links to the duplicate issue which allows users to read up on the original issue report. Below the issue report is a set of buttons that a user can select to work on the issue.

*   Update Issue - brings up a page to edit all aspects of the issue
    
*   Assign to - in conjunction with the dropdown list next top the button, this is a shortcut to change the assignment of an issue
    
*   Change Status to - in conjunction with the dropdown list next top the button, this is a shortcut to change the status of an issue. Another page (Change Status) will be presented to allow the user to add notes or change relevant information
    
*   Monitor / Unmonitor Issue - allows the user to monitor any additions to the issue by email
    
*   Create Clone - create a copy of the current issue. This presents the user with a new issue reporting form with all of the information in the current issue filled in. Upon submission, a new issue, related to the current issue, will be created.
    
*   Reopen Issue - Allows the user to re-open a resolved issue
    
*   Move Issue - allows the user to move the issue to another project
    
*   Delete Issue - Allows the user to delete the issue permanently. It is recommended against deleting issues unless the entry is frivolous. Instead issues should be set to resolved and an appropriate resolution category chosen.
    

A panel is provided to view and update the sponsorship of an issue.Another panel is provided to view, delete and add relationships for an issue. Issues can have a parent/child relationship, where the user is warned about resolving a parent issue before all of the children are resolved. A peer relationship is also possible.Below this, there may be a form for uploading file attachments. The Administrator needs to configure the bugtracker to handle file uploads. If uploading to disk is selected, each project needs to set its own upload path. Issue notes are shown at the bottom of the issue report. A panel to add issue notes is also shown.

⁠6.5. Issue Change Status page
------------------------------

This page is used to change the status of an issue. A user can add an issue note to describe the reason for change.In addition, the following fields may be displayed for update:

*   Resolution and Duplicate ID - for issues being resolved or closed
    
*   Issue Handler (Assigned to)
    
*   any Custom Fields that are to be visible on update or resolution
    
*   Fixed in Version - for issues being resolved
    
*   Close Immediately - to immediately close a resolved issue
    

⁠6.6. Issue Edit page
---------------------

The layout of this page resembles the Simple Issue View page, but here you can update various issue fields. The Reporter, Category, Severity, and Reproducibility fields are editable but shouldn't be unless there is a gross mis-categorization.Also modifiable are the Assigned To, Priority, Projection, ETA, Resolution, and Duplicate ID fields.As per version 0.18.0, the user can also add an issue note as part of an issue update.

⁠6.7. My Account Page
---------------------

This page changes user alterable parameters for the system. These selections are user specific. This allows the user to change their password, username, real name and email address. It also reports the user's access levels on the current project and default access level used for public projects.

### ⁠6.7.1. Preferences

This sets the following information:

*   Default project
    
*   whether the pages used for reporting, viewing, and updating are the simple or advanced views
    
*   the delay in minutes between refreshes of the view all issues page
    
*   the delay in seconds when redirecting from a confirmation page to the display page
    
*   the time order in which notes will be sorted
    
*   whether to filter email messages based on type of message and severity
    
*   the number of notes to append to notification emails
    
*   the default language for the system. The additional setting of "auto" will use the browser's default language for the system.
    

### ⁠6.7.2. Profiles

Profiles are shortcuts to define the values for Platform, OS, and version. This page allows you to define and edit personal shortcuts.

### ⁠6.7.3. Manage Columns

Provides the ability to select the fields to be displayed in View Issues, Print Issues, CSV and Excel exports. The changes apply to the currently selected projects or All Projects for setting the defaults. It is also possible to copy such settings from/to other projects.

### ⁠6.7.4. API Tokens

Provides the ability to generate and revoke tokens that can be used by applications and services to access MantisBT via its APIs. This page also provides information about the creation and last used timestamps for such tokens.

⁠6.8. System Management Pages
-----------------------------

A number of pages exist under the "Manage" link. These will only be visible to those who have an appropriate access level.

### ⁠6.8.1. Manage Users

This page allow an administrator to manage the users in the system.It essentially supplies a list of users defined in the system. The user names are linked to a page where you can change the user's name, access level, and projects to which they are assigned. You can also reset their passwords through this page.At the top, there is also a list of new users (who have created an account in the last week), and accounts where the user has yet to log in.New users are created using the "Create User" link above the list of existing users. Note that the username must be unique in the system. Further, note that the user's real name (as displayed on the screen) cannot match another user's user name.

### ⁠6.8.2. Manage Projects Page

This page allows the user to manage the projects listed in the system.Each project is listed along with a link to manage that specific project. The specific project pages allow the user to change:

*   the project name
    
*   the project description
    
*   its status
    
*   whether the project is public or private. Private projects are only visible to users who are assigned to it or users who have the access level to automatically have access to private projects (eg: administrators).
    
*   file directory used to store attachments for issues and documents associated with the project. This folder is located on the webserver, it can be absolute path or path relative to the main MantisBT folder. Note that this is only used if the files are stored on disk.
    
*   common subprojects. These are other projects who can be considered a sub-project of this one. They can be shared amongst multiple projects. For example, a "documentation" project may be shared amongst several development projects.
    
*   project categories. These are used to sub-divide the issues stored in the system.
    
*   project versions. These are used to create ChangeLog reports and can be used to filter issues. They are used for both the Found In and Fixed In versions.
    
*   Custom Fields linked to this project
    
*   Users linked to this project. Here is the place where a user's access level may be upgraded or downgraded depending on their particular role in the project.
    

### ⁠6.8.3. Manage Custom Fields

This page is the base point for managing custom fields. It lists the custom fields defined in the system. There is also a place to enter a new field name to create a new field.The "Edit" links take you to a page where you can define the details of a custom field. These include it's name, type, value, and display information. On the edit page, the following information is defined to control the custom field:

*   name
    
*   type. Possible values are listed below.
    
*   Value constraints (Possible values, default value, regular expression, minimum length, maximum length).
    
*   Access (who can read and write the field based on their access level).
    
*   Display control (where the field will show up and must be filled in
    

All fields are compared in length to be greater than or equal to the minimum length, and less than or equal to the minimum length, unless these values are 0. If the values are 0, the check is skipped. All fields are also compared against the regular expression. If the value matches the expression, then the value is stored. For example, the expression "^-?(\[0-9\])*$" can be used to constrain an integer.The table below describes the field types and the value constraints.

Type

Field Contents

Value Constraints

String

text string up to 255 characters

Numeric

an integer

Float

a floating point number

Enumeration

one of a list of text strings

Enter the list of text strings separated by "|" (pipe character) in the Possible Values field. The Default value should match one of these strings as well. This will be displayed as a dropdown menu.

Email

an email address string up to 255 characters

When displayed, the value will also be encapsulated in a mailto: reference.

Checkbox

zero or more of a list of text strings

Enter the list of text strings separated by "|" (pipe character) in the Possible Values field. The Default value should match one of these strings as well. This will be displayed as a list of text strings with a checkbox beside them.

List

one of a list of text strings

Enter the list of text strings separated by "|" (pipe character) in the Possible Values field. The Default value should match one of these strings as well. This will be displayed as a multi-line dropdown menu.

Multiselection List

zero or more of a list of text strings

Enter the list of text strings separated by "|" (pipe character) in the Possible Values field. The Default value should match one of these strings as well. This will be displayed as a multi-line dropdown menu.

Date

text string defining a date

This is displayed as a set of dropdown menus for day, month, and year. Defaults should be defined in yyyy-mm-dd format.

The display entries are used as follows:

Entry

Meaning

Display Only On Advanced Page

If checked, the field will NOT be shown on the simple issue displays

Display When Reporting Issues

If checked, the field will be shown on the report issues displays

Display When Updating Issues

If checked, the field will NOT be shown on the update issue and change status displays

Display When Resolving Issues

If checked, the field will NOT be shown on the update issue displays and change status displays, if the new status is resolved.

Display When Closing Issues

If checked, the field will NOT be shown on the update issue displays and change status displays, if the new status is closed.

Required On Report

If checked, the field must be filled in on the issue reports.

Required On Update

If checked, the field must be filled in on the update issue and change status displays.

Required On Resolve

If checked, the field must be filled in on the update issue and change status displays, if the new status is resolved.

Required On Close

If checked, the field must be filled in on the update issue and change status displays, if the new status is closed.

Notes on Display

*   Be careful not to set both a required attribute and show only on advanced display. It may be possible to trigger a validation error that the user cannot recover from (i.e., field is not filled in).
    

### ⁠6.8.4. Manage Global Profiles

This page allows the definition of global profiles accessible to all users of the system. It is similar to the user definition of a profile consisting of Platform, OS and Version.

### ⁠6.8.5. Manage Configuration

This set of pages control the configuration of the MantisBT system. Note that the configuration items displayed may be on a project by project basis.These pages serve two purposes. First, they will display the settings for the particular aspects of the system. If authorized, they will allow a user to change the parameters. They also have settings for what access level is required to change these settings ON A PROJECT basis. In general, this should be left alone, but administrators may want to delegate some of these settings to managers.

#### ⁠6.8.5.1. Workflow Thresholds

This page covers the adjustment of the settings for many of the workflow related parameters. For most of these, the fields are self explanatory and relate to a similarly named setting in the configuration file. At the right of each row is a selector that allows the administrator to lower the access level required to change the particular parameter.The values changeable on this page are:

Issues

Title

Variable

Description

Report an Issue

$g\_report\_bug_threshold

threshold to report an issue

Status to which a new issue is set

$g\_bug\_submit_status

status issue is set to when submitted

Update an Issue

$g\_update\_bug_threshold

threshold to update an issue

Allow Reporter to close an issue

$g\_allow\_reporter_close

allow reporter to close issues they reported

Monitor an issue

$g\_monitor\_bug_threshold

threshold to monitor an issue

Handle Issue

$g\_handle\_bug_threshold

threshold to handle (be assigned) an issue

Assign Issue

$g\_update\_bug\_assign\_threshold

threshold to be in the assign to list

Move Issue

$g\_move\_bug_threshold

threshold to move an issue to another project. This setting is for all projects.

Delete Issue

$g\_delete\_bug_threshold

threshold to delete an issue

Reopen Issue

$g\_reopen\_bug_threshold

threshold to reopen an issue

Allow reporter to reopen Issue

$g\_allow\_reporter_reopen

allow reporter to reopen issues they reported

Status to which a reopened Issue is set

$g\_bug\_reopen_status

status issue is set to when reopened

Resolution to which a reopened Issue is set

$g\_bug\_reopen_resolution

resolution issue is set to when reopened

Status where an issue is considered resolved

$g\_bug\_resolved\_status\_threshold

status where bug is resolved

Status where an issue becomes read-only

$g\_bug\_readonly\_status\_threshold

status where bug is read-only (see update\_readonly\_bug_threshold)

Update readonly issue

$g\_update\_readonly\_bug\_threshold

threshold to update an issue marked as read-only

Update Issue Status

$g\_update\_bug\_status\_threshold

threshold to update an issue's status

View Private Issues

$g\_private\_bug_threshold

threshold to view a private issue

Set View Status

$g\_set\_view\_status\_threshold

threshold to set an issue to Private/Public

Update View Status

$g\_change\_view\_status\_threshold

threshold needed to update the view status while updating an issue or an issue note

Show list of users monitoring issue

$g\_show\_monitor\_list\_threshold

threshold to see who is monitoring an issue

Set status on assignment of handler

$g\_auto\_set\_status\_to_assigned

change status when an issue is assigned

Status to set auto-assigned issues to

$g\_bug\_assigned_status

status to use when an issue is auto-assigned

Limit reporter's access to their own issues

$g\_limit\_reporters

reporters can see only issues they reported. This setting is for all projects.

Notes

Title

Variable

Description

Add Notes

$g\_add\_bugnote_threshold

threshold to add an issue note

Update Others' Notes

$g\_update\_bugnote_threshold

threshold at which a user can edit issue notes created by other users

Update Own Notes

$g\_bugnote\_user\_edit\_threshold

threshold at which a user can edit issue notes created by themselves

Delete Others' Notes

$g\_delete\_bugnote_threshold

threshold at which a user can delete issue notes created by other users

Delete Own Notes

$g\_bugnote\_user\_delete\_threshold

threshold at which a user can delete issue notes created by themselves

View private notes

$g\_private\_bugnote_threshold

threshold to view a private issue note

Change view state of own notes

$g\_bugnote\_user\_change\_view\_state\_threshold

threshold at which a user can change the view state of issue notes created by themselves

Others

Title

Variable

Description

View Change Log

$g\_view\_changelog_threshold

threshold to view the changelog

View Assigned To

$g\_view\_handler_threshold

threshold to see who is handling an issue

View Issue History

$g\_view\_history_threshold

threshold to view the issue history

Send Reminders

$g\_bug\_reminder_threshold

threshold to send a reminder

#### ⁠6.8.5.2. Workflow Transitions

This page covers the status workflow. For most of these, the fields are self explanatory and relate to a similarly named setting in the configuration file. At the right of each row is a selector that allows the administrator to lower the access level required to change the particular parameter.The values changeable on this page are:

⁠

**Table 6.1. Issues**

Title

Variable

Description

Status to which a new issue is set

$g\_bug\_submit_status

status issue is set to when submitted

Status where an issue is considered resolved

$g\_bug\_resolved\_status\_threshold

status where issue is resolved

Status to which a reopened Issue is set

$g\_bug\_reopen_status

status issue is set to when reopened

The matrix that follows has checkmarks where the transitions are allowed from the status on the left edge to the status listed across the top. This corresponds to the $g\_enum\_workflow array.At the bottom, there is a list of access levels that are required to change the status to the value listed across the top. This can be used, for instance, to restrict those who can close an issue to a specific level, say a manager. This corresponds to the $g\_set\_status\_threshold array and the $g\_report\_bug\_threshold setting.

#### ⁠6.8.5.3. Email Notifications

This page sets the system defaults for sending emails on issue related events. MantisBT uses flags and a threshold system to generate emails on events. For each new event, email is sent to:

*   the reporter
    
*   the handler (or Assigned to)
    
*   anyone monitoring the issue
    
*   anyone who has ever added a issue note the issue
    
*   anyone assigned to the project whose access level matches a range
    

From this list, those recipients who meet the following criteria are eliminated:

*   the originator of the change, if $g\_email\_receive_own is OFF
    
*   the recipient either no longer exists, or is disabled
    
*   the recipient has turned their email\_on\_<new status> preference OFF
    
*   the recipient has no email address entered
    

The matrix on this page selects who will receive messages for each of the events listed down the left hand side. The first four columns correspond to the first four points listed above. The next columns correspond to the access levels defined. Note that because a minimum and maximum threshold are used, a discontinuous selection is not allowed.

⁠6.9. Monitor Issue
-------------------

The monitor issues feature allows users to subscribe to certain issues and hence get copied on all notification emails that are sent for these issues.Depending on the configuration, sending a reminder to a user about an issue can add this issue to the user's list of monitored issues. Users who reported the issue or are assigned the issue typically don't need to monitor the issue to get the notifications. This is because by default they get notified on changes related to the issue anyway. However, administrators can change the configuration to disable notifications to reporters or handlers in specific scenarios.

⁠6.10. Reopen Issue
-------------------

Re-open issue button is visible in the issue view pages if the user has the appropriate access level and the issue is resolved/closed. Re-opening a issue will allow users to enter issue notes for the re-opening reason. The issue will automatically be put into the Feedback status.

⁠6.11. Delete Issue
-------------------

The delete issues button appears on the issue view pages for the users who have the appropriate access level. This allows you to delete an existing issue. This should only be used on frivolous or test issues. A confirmation screen will prompt you if you really want to delete the issue. Updaters, Developers, Managers, and Administrators can remove issues (you can also configure this).

⁠6.12. Close Issue
------------------

This is a button that appears on the issue view pages for users that are authorized to close issues. Depending on the configuration, users may be able to close issues without having to resolve them first, or may be able to only close resolved issues. After the button is clicked, the user is redirected to a page where an issue note maybe added.

⁠6.13. Assign to Me
-------------------

This button appears in the issue view pages in case of users with access level that is equal to handle\_bug\_threshold or higher. When this button is clicked the issue is assigned to the user.

⁠6.14. Resolve Issue
--------------------

This option on the View Issues page allows you to resolve the issue. It will lead you to a page where you can set the resolution state and a duplicate id (if applicable). After choosing that the user can choose to enter an issue note detailing the reason for the closure. The issue is then set to the Resolved state. The reporter should check off on the issue by using the Close Issue button.

⁠6.15. News Syndication
-----------------------

MantisBT supports news syndication using RSS v2.0 protocol. MantisBT also supports authenticated news feeds for private projects or installations where anonymous access is not enabled. Authenticated feeds takes a user name and a key token that are used to authenticate the user and generate the feed results in the context of the user's access rights (i.e. the same as what the user would see if they were to logged into MantisBT).To get access to the News RSS as anonymous user, visit the following page: http://www.example.com/mantisbt/news_rss.php While a user is logged in, the RSS links provided in the UI will always provide links to the authenticated feeds, if no user is logged in (i.e. anonymous), then anonymous links will be provided.

⁠Chapter 7. Customizing MantisBT
================================

[7.1. Strings / Translations](#admin.customize.strings)

[7.2. Custom Fields](#admin.customize.customfields)

[7.2.1. Overview](#admin.customize.customfields.overview)

[7.2.2. Custom Field Definition](#admin.customize.customfields.definitions)

[7.2.3. Adding/Editing Custom Fields](#admin.customize.customfields.editing)

[7.2.4. Linking/Unlinking/Ordering Existing Custom Fields in Projects](#admin.customize.customfields.linking)

[7.2.5. Localizing Custom Field Names](#admin.customize.customfields.localize)

[7.2.6. Dynamic default values](#admin.customize.customfields.defaults)

[7.2.7. Dynamic values for Enumeration Custom Fields](#admin.customize.customfields.dynamic)

[7.3. Enumerations](#admin.customize.enums)

[7.4. Email Notifications](#admin.customize.email)

[7.5. Customizing Status Values](#admin.customize.status)

[7.6. Custom Functions](#admin.customize.customfuncs)

[7.6.1. Default Custom Functions](#admin.customize.customfuncs.defined)

[7.6.2. Example Custom Function Override](#admin.customize.customfuncs.example)

⁠7.1. Strings / Translations
----------------------------

All strings used in MantisBT, including those defined in plugins, can be customized or translated differently. This is achieved by overriding them in the `Custom Strings File` (in config/custom\_strings\_inc.php), which is automatically detected and included by MantisBT code.

Defining custom strings here provides a simple upgrade path, and avoids having to re-do the changes when upgrading to the next release.

**Note**

The standard MantisBT language strings are sometimes reused in different contexts. If you are planning to override some strings to meet your specific requirements, make sure to analyze where they are used to avoids unexpected issues.

Two formats are supported within this file:

New Format

Define a _$s\_custom\_messages_ array as follows:

$s\_custom\_messages = array( LANG => array( CODE => STRING, ... ) );

Legacy Format

One variable per string

$s_CODE = STRING;

Where

*   LANG = language code, as defined in _$g\_language\_choices_arr_ (see [Section 5.10, “Language”](#admin.config.language))
    
*   CODE = string code, as called by lang_get() function.
    
*   STRING = string value / translation
    

**Note**

Mixing old and new formats within the file is not supported.

**Warning**

NEVER call _lang\_get\_current()_ from the _Custom Strings File_, as doing so will reset the active_language, causing the code to return incorrect translations if the default language is different from English. Always use the _$g\_active\_language_ global variable instead.

⁠7.2. Custom Fields
-------------------

### ⁠7.2.1. Overview

Different teams typically like to capture different information as users report issues, in some cases, the data required is even different from one project to another. Hence, MantisBT provides the ability for managers and administrators to define custom fields as way to extend MantisBT to deal with information that is specific to their teams or their projects. The aim is for this to keep MantisBT native fields to a minimum. Following are some facts about the implementation of custom fields in MantisBT:

*   Custom fields are defined system wide.
    
*   Custom fields can be linked to multiple projects.
    
*   The sequence of displaying custom fields can be different per project.
    
*   Custom fields must be defined by users with access level ADMINISTRATOR.
    
*   Custom fields can be linked to projects by users with access level MANAGER or above (by default, this can be configurable).
    
*   Number of custom fields is not restricted.
    
*   Users can define filters that include custom fields.
    
*   Custom fields can be included in View Issues, Print Issues, and CSV exports.
    
*   Enumeration custom fields can have a set of static values or values that are calculated dynamically based on a custom function.
    

### ⁠7.2.2. Custom Field Definition

The definition of a custom field includes the following logical attributes:

*   Caption variable name. This value is supplied to the lang_get() API; it is therefore mandatory to set this to a [valid PHP identifier](http://php.net/language.variables.basics.php) (i.e. only letters, numbers and underscores; no spaces) if you intend to translate the field label (see [Section 7.2.5, “Localizing Custom Field Names”](#admin.customize.customfields.localize)).
    
    **Note**
    
    If the specified variable is not found in the language files or in the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings)), then it will be displayed as-is.
    
*   Custom field type (string, numeric, float, enumeration, email, checkbox, radio, list, multi-selection list, date).
    
    Type 'string' is used for strings of up to 255 characters.
    
    Type 'numeric' is used for numerical integer values.
    
    Type 'float' is used for real (float / double) numbers.
    
    Type 'enumeration' is used when a user selects one entry from a list. The user interface for such type is a combo-box.
    
    Type 'email' is used for storing email addresses.
    
    Type 'checkbox' is like enumeration but the list is shown as checkboxes and the user is allowed to tick more than one selection. The default value and the possible value can contain multiple values like 'RED|YELLOW|BLUE' (without the single quote).
    
    Type 'radio' is like enumeration but the list is shown as radio buttons and the user is allowed to tick on of the options. The possible values can be 'RED|YELLOW|BLUE', where the default value can be 'YELLOW'. Note that the default value can't contain multiple values.
    
    Type 'list' is like enumeration but the list is shown as a list box where the user is only allowed to select one option. The possible values can be 'RED|YELLOW|BLUE', where the default value can be 'YELLOW'. Note that the default value can't contain multiple values.
    
    Type 'multi-selection list' is like enumeration but the list is shown as a list box where the user is allowed to select multiple options. The possible values can be 'RED|YELLOW|BLUE', where the default value can be 'RED|BLUE'. Note that in this case the default value contains multiple values.
    
    Type 'date' is for date values. The default value can be empty, or {tomorrow}, {yesterday}, {next week}, {last week}, {+3 days}, {-2 days}.
    
*   Enumeration possible values (eg: RED|YELLOW|BLUE). Use the pipe ('|') character to separate possible values for an enumeration. One of the possible values can be an empty string. The set of possible values can also be calculated at runtime. For example, "=versions" would automatically resolve into all the versions defined for the current project.
    
*   Default value - see details above for a sample default value for each type.
    
*   Minimum/maximum length for the custom field value (use 0 to disable). Note that these metrics are not really relevant to custom fields that are based on an enumeration of possible values.
    
*   Regular expression to use for validating user input (use [PCRE syntax](http://www.php.net/manual/en/reference.pcre.pattern.syntax.php)).
    
*   Read Access level: Minimum access level for users to be able to see the value of the custom field.
    
*   Write Access level: Minimum access level for users to be able to edit the value of the custom field.
    
*   Display when reporting issues? - If this custom field should be shown on the Report Issue page.
    
*   Display when updating issues? - If this custom field should be shown on the Update Issue page.
    
*   Display when resolving issues? - If this custom field should be shown when resolving an issue. For example, a "root cause" custom field would make sense to set when resolving the issue.
    
*   Display when closing issues? - If this custom field should be shown when closing an issue.
    
*   Required on Report - If this custom field is a mandatory field on the Report Issue page.
    
*   Required on Update - If this custom field is a mandatory field on the Update Issue page.
    
*   Required on Resolve - If this custom field is a mandatory field when resolving an issue.
    
*   Required on Close - If this custom field is a mandatory field when closing an issue.
    

All custom fields are currently saved to a field of type VARCHAR(255) in the database. However, in future releases, it is possible to support custom fields of different types (eg: memo, file).

If the value of a custom field for a certain defect is not found, the default value is assumed.

### ⁠7.2.3. Adding/Editing Custom Fields

*   The logged in user needs $g\_manage\_custom\_fields\_threshold access level.
    
*   Select "Manage" from the main menu.
    
*   Select "Manage Custom Fields" from the management menu.
    
*   In case of edit, click on the name of an existing custom field to edit its information.
    
*   In case of adding a new one, enter the name of the new custom field then click "New Custom Field".
    

**Note**

Added custom fields will not show up in any of the issues until the added custom field is linked to the appropriate projects.

### ⁠7.2.4. Linking/Unlinking/Ordering Existing Custom Fields in Projects

*   The logged in user needs to have access level that is greater than or equal to $g\_custom\_field\_link\_threshold and $g\_manage\_project_threshold.
    
*   Select "Manage" from the main menu.
    
*   Select "Manage Projects".
    
*   Select the name of the project to manage.
    
*   Scroll down to the "Custom Fields" box.
    
*   Select the field to add from the list, then click "Add This Existing Custom Field".
    
*   To change the order of the custom fields, edit the "Sequence" value and click update. Custom fields with smaller values are displayed first.
    
*   To unlink a custom field, click on "Remove" link next to the field. Unlinking a custom field will not delete the values that are associated with the issues for this field. These values are only deleted if the custom field definition is removed (not unlinked!) from the database. This is useful if you decide to re-link the custom field. These values may also re-appear if issues are moved to another project which has this field linked.
    

Moving Issues

When an issue is moved from one project to another, custom fields that are not defined for the new project are not deleted. These fields will re-appear with their correct values if the issue is moved back to the original project, or if these custom fields are linked to the new project.

### ⁠7.2.5. Localizing Custom Field Names

It is possible to localize the custom fields' labels. This can be done as follows:

1.  Define the custom field (see [Section 7.2.2, “Custom Field Definition”](#admin.customize.customfields.definitions)), keeping in mind that its name must be a [valid PHP identifier](http://php.net/language.variables.basics.php).
    
    As an example, we will use _my\_start\_date_ for a custom field of type "Date", storing the date when work on an issue was initiated.
    
2.  Set the localization strings
    
    *   In the main MantisBT directory, locate and edit the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings)), create it if it does not exist.
        
    *   Localize the custom field's label _my\_start\_date_ by adding the following code
        
        <?php
        switch( $g\_active\_language ) {
        	case 'french':
        		$s\_my\_start_date = 'Date de début';
        		break;
        
        	default:
        		# Default language, as defined in config/config_inc.php
        		# ($g\_default\_language, English in this case)
        		$s\_my\_start_date = 'Start Date';
        		break;
        }
        
    

**Note**

Had we decided to use _start_date_ as the custom field's name, then it would not have been necessary to modify the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings)), since MantisBT would have used the existing, already localized string from the standard language files. To check for standard strings, inspect `lang/strings_english.txt`.

### ⁠7.2.6. Dynamic default values

#### ⁠7.2.6.1. Dynamic defaults for Date fields

Custom fields of type date can be defaulted to either specific or relative dates. Typically, relative dates is the scenario that makes sense in most of the cases.

The format for specific dates is an integer which indicates the number of seconds since the [Unix Epoch](http://en.wikipedia.org/wiki/Unix_time) (January 1 1970 00:00:00 UTC), which is the format consumed by the PHP [date()](http://www.php.net/date) method.

The relative scenario expects default values like {tomorrow}, {yesterday}, {+2 days}, {-3 days}, {next week}, etc. The curly brackets indicate that this is a logical value which is then evaluated using the PHP [strtotime()](http://www.php.net/strtotime) function.

### ⁠7.2.7. Dynamic values for Enumeration Custom Fields

As discussed earlier, one of the possible types of a custom field is "enumeration". This type of custom field allows the user to select one value from a provided list of possible values. The standard way of defining such custom fields is to provide a '|' separated list of possible values. However, this approach has two limitations: the list is static, and the maximum length of the list must be no longer than 255 characters. Hence, the need for the ability to construct the list of possible values dynamically.

#### ⁠7.2.7.1. Dynamic possible values included by default

MantisBT ships with some dynamic possible values, these include the following:

*   =categories - a list of categories defined in the current project (or the project to which the issue belongs).
    
*   =versions - a list of all versions defined in the current project (or the project to which the issue belongs).
    
*   =future_versions - a list of all versions that belong to the current project with released flag set to false.
    
*   =released_versions - a list of all versions that belong to the current project with released flag set to true.
    

**Note**

The '=' before the name of the dynamic list of options is used to tell MantisBT that this is a dynamic list, rather than a static list with just one option.

#### ⁠7.2.7.2. Defining Custom Dynamic Possible Values

If the user selects =versions, the actual custom function that is executed is custom\_function\_\*\_enum\_versions(). The reason why the "enum_" is not included is to have a fixed prefix for all custom functions used for this purpose and protect against users using custom functions that were not intended for this purpose. For example, you don't want the user to use custom\_function\_\*\_issue\_delete_notify() which may be overridden by the web master to delete associated data in other databases.

Following is a sample custom function that is used to populate a field with the categories belonging to the currently selected project:

\# --------------------
\# Construct an enumeration for all categories for the current project.
\# The enumeration will be empty if current project is ALL PROJECTS.
\# Enumerations format is: "abc|lmn|xyz"
\# To use this in a custom field type "=categories" in the possible values field.
function custom\_function\_override\_enum\_categories() {
    $t\_categories = category\_get\_all\_rows( helper\_get\_current_project() );

    $t_enum = array();
    foreach( $t\_categories as $t\_category ) {
        $t\_enum\[\] = $t\_category\['category'\];
    }

    $t\_possible\_values = implode( '|', $t_enum );

    return $t\_possible\_values;
}

Notice the following:

*   The custom function doesn't take any parameters.
    
*   The custom function returns the possible values in the format (A|B|C).
    
*   The custom function uses the current project.
    
*   The custom function builds on top of the already existing APIs.
    

To define your own function \\u201c=mine\\u201d, you will have to define it with the following signature:

\# --------------------
\# To use this in a custom field type "=mine" in the possible values field.
function custom\_function\_override\_enum\_mine() {
    $t_enum = array();

    :

    $t\_possible\_values = implode( '|', $t_enum );

    return $t\_possible\_values;
}

Notice "override" in the function name. This is because this method is defined by the MantisBT administrator/webmaster and not part of the MantisBT source. It is OK to override a method that doesn't exist.

As usual, when MantisBT is upgraded to future releases, the custom functions will not be overwritten. The difference between the "default" implementation and the "override" implementation is explained in more details in the custom functions section.

⁠7.3. Enumerations
------------------

Enumerations are used in MantisBT to represent a set of possible values for an attribute. Enumerations are used for access levels, severities, priorities, project statuses, project view state, reproducibility, resolution, ETA, and projection. MantisBT provides the administrator with the flexibility of altering the values in these enumerations. The rest of this topic explains how enumerations work, and then how they can be customised.

How do enumerations work?

`core/constant_inc.php` defines the constants that correspond to those in the enumeration. These are useful to refer to these enumerations in the configs and the code.

define( 'VIEWER', 10 );
define( 'REPORTER', 25 );
define( 'UPDATER',  40 );
define( 'DEVELOPER', 55 );
define( 'MANAGER', 70 );
define( 'ADMINISTRATOR', 90 );

`config_defaults_inc.php` includes the defaults for the enumerations. The configuration options that are defaulted here are used in specifying which enumerations are active and should be used in MantisBT.

$g\_access\_levels\_enum\_string =
	'10:viewer,25:reporter,40:updater,55:developer,70:manager,90:administrator';

**Note**

The strings included in the enumerations here are just for documentation purposes, they are not actually shown to the user (due to the need for localisation). Hence, if an entry in this enumeration is not found in the corresponding localised string (i.e. 70:manager), then it will be printed to the user as @70@.

The Language Files (e.g. `lang/strings_german.txt`) provide the localised strings (German in this case) for enumerations. But again, the _master list_ is the enumeration in the configs themselves, the ones in the language files are just used for finding the localised equivalent for an entry. Hence, if a user changes the config to have only two types of users developers and administrators, then only those will be prompted to the users even if the enumerations in the language files still includes the full list.

$s\_access\_levels\_enum\_string =
	'10:Betrachter,25:Reporter,40:Updater,55:Entwickler,70:Manager,90:Administrator';

How can they be customised?

Let say we want to remove access level "Updater" and add access level "Senior Developer".

The file `config/custom_constants_inc.php` is supported for the exclusive purpose of allowing administrators to define their own constants while maintaining a simple upgrade path for future releases of MantisBT. Note that this file is not distributed with MantisBT and you will need to create it if you need such customisation. In our example, we need to define a constant for the new access level.

define( 'SENIOR_DEVELOPER', 60 );

In `config/config_inc.php`

// Remove Updater and add Senior Developer
$g\_access\_levels\_enum\_string =
	'10:viewer,25:reporter,55:developer,60:senior_developer,70:manager,90:administrator';

// Give access to Senior developers to create/delete custom field.
$g\_manage\_custom\_fields\_threshold = SENIOR_DEVELOPER;

Update the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings))

$s\_access\_levels\_enum\_string =
	'10:Betrachter,25:Reporter,40:Updater,55:Entwickler,60:Senior Developer,70:Manager,90:Administrator';

**Note**

We don't need to remove the _Updater_ entry from the localisation file if the current language is 'English'.

Conclusion

We have covered how enumerations work in general, and how to customise one of them. If you are interested in customising other enumerations, a good starting point would be to go to _MantisBT Enum Strings_ section in `config_defaults_inc.php`. This section defines all enumerations that are used by MantisBT.

⁠7.4. Email Notifications
-------------------------

See [Section 5.8, “Email”](#admin.config.email) in the Configuration section.

Examples:

*   Notify only managers of new issues.
    
    $g\_notify\_flags\['new'\] = array(
    	'threshold_min' => MANAGER,
    	'threshold_max' => MANAGER,
    );
    
*   Notify Developers and managers of all project events, except, exclude developers from the 'closed' events.
    
    $g\_default\_notify_flags = array(
    	'threshold_min' => DEVELOPER,
    	'threshold_max' => MANAGER,
    );
    $g\_notify\_flags\['closed'\] = array(
    	'threshold_min' => MANAGER,
    	'threshold_max' => MANAGER,
    );
    
*   Exclude those who contributed issue notes from getting messages about other changes in the issue.
    
    $g\_default\_notify_flags\['bugnotes'\] = OFF;
    
*   Exclude those monitoring issues from seeing the 'closed' message
    
    $g\_notify\_flags\['closed'\]\['monitor'\] = OFF;
    
*   Only notify developers when issue notes are added.
    
    $g\_notify\_flags\['bugnote'\] = array(
    	'threshold_min' => DEVELOPER,
    	'threshold_max' => DEVELOPER,
    );
    
*   Notify managers of changes in sponsorship.
    
    $g\_notify\_flags\['sponsor'\] = array(
    	'threshold_min' => MANAGER,
    	'threshold_max' => MANAGER,
    );
    
*   Notify originator and managers of changes in ownership ("Assigned To:").
    
    $g\_notify\_flags\['owner'\] = array(
    	'threshold_min' => MANAGER,
    	'threshold_max' => MANAGER,
    	'reporter'      => ON,
    );
    
*   I'm paranoid about mail. Only send information on issues to those involved in them. Don't send mail people already know about. Also send new issue notifications to managers so they can screen them.
    
    $g\_email\_receive_own = OFF;
    $g\_default\_notify_flags = array(
    	'reporter'      => ON,
    	'handler'       => ON,
    	'monitor'       => ON,
    	'bugnotes'      => ON,
    	'category'      => ON,
    	'threshold_min' => NOBODY,
    	'threshold_max' => NOBODY
    );
    $g\_notify\_flags\['new'\] = array(
    	'threshold_min' => MANAGER,
    	'threshold_max' => MANAGER,
    );
    
*   How do I replace the $g\_to\_email configuration variable to log all messages to an email logger.
    
    You will need to create a dummy user with the appropriate access level for the notices you want to log. Once this user is added to projects, they will receive mail using the appropriate rules.
    

⁠7.5. Customizing Status Values
-------------------------------

This section describes how to add a custom status.

1.  Define a constant to map the new status to.
    
    In subfolder config, locate and edit file _custom\_constants\_inc.php_; (create it if it does not exist)
    
    <?php
    	# Custom status code
    	define( 'TESTING', 60 );
    
2.  Define the new status in the enumeration, as well as the corresponding color code.
    
    In subfolder config, edit your _config_inc.php_
    
    \# Revised enum string with new 'testing' status
    $g\_status\_enum_string = '10:new,20:feedback,30:acknowledged,40:confirmed,50:assigned,_60:testing,_80:resolved,90:closed';
    
    \# Status color additions
    $g\_status\_colors\['_testing_'\] = '#ACE7AE';
    
    Note that the key in the $g\_status\_colors array must be equal to the value defined for the new status code in $g\_status\_enum_string.
    
3.  Define the required translation strings for the new status, for each language used in the installation.
    
    *   _s\_status\_enum_string_: status codes translation (refer to the original language strings for standard values)
        
    *   _s\_XXXX\_bug_title_: title displayed in the change status page
        
    *   _s\_XXXX\_bug_button_: label for the submit button in the change status page
        
    *   _s\_email\_notification\_title\_for\_status\_bug_XXXX_: title for notification e-mails
        
    
    where XXXX is the name of the new status as it was defined in _g\_status\_enum_string_ above. If XXXX contains spaces, they should be replaced by underscores in the language strings names (e.g. for '35:pending user', use '$s\_pending\_user\_bug\_button')
    
    In subfolder config, locate and edit the _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings)), create it if it does not exist
    
    <?php
    \# Translation for Custom Status Code: _testing_
    switch( $g\_active\_language ) {
    
    	case 'french':
    		$s\_status\_enum_string = '10:nouveau,20:commentaire,30:accepté,40:confirmé,50:affecté,60:à tester,80:résolu,90:fermé';
    
    		$s\_testing\_bug_title = 'Mettre le bogue en test';
    		$s\_testing\_bug_button = 'A tester';
    
    		$s\_email\_notification\_title\_for\_status\_bug_testing = 'Le bogue suivant est prêt à être TESTE.';
    		break;
    
    	default: # english
    		$s\_status\_enum_string = '10:new,20:feedback,30:acknowledged,40:confirmed,50:assigned,60:testing,80:resolved,90:closed';
    
    		$s\_testing\_bug_title = 'Mark issue Ready for Testing';
    		$s\_testing\_bug_button = 'Ready for Testing';
    
    		$s\_email\_notification\_title\_for\_status\_bug_testing = 'The following issue is ready for TESTING.';
    		break;
    }
    
4.  Add the new status to the workflow as required.
    
    This can either be done from the Manage Workflow Transitions page (see [Section 4.3.1, “Workflow Transitions”](#admin.lifecycle.workflow.transitions)) or by manually editing _config_inc.php_ as per the example below:
    
    $g\_status\_enum\_workflow\[NEW\_\]         ='30:acknowledged,20:feedback,40:confirmed,50:assigned,80:resolved';
    $g\_status\_enum_workflow\[FEEDBACK\]     ='30:acknowledged,40:confirmed,50:assigned,80:resolved';
    $g\_status\_enum_workflow\[ACKNOWLEDGED\] ='40:confirmed,20:feedback,50:assigned,80:resolved';
    $g\_status\_enum_workflow\[CONFIRMED\]    ='50:assigned,20:feedback,30:acknowledged,80:resolved';
    $g\_status\_enum_workflow\[ASSIGNED\]     ='60:testing,20:feedback,30:acknowledged,40:confirmed,80:resolved';
    $g\_status\_enum_workflow\[TESTING\]      ='80:resolved,20:feedback,50:assigned';
    $g\_status\_enum_workflow\[RESOLVED\]     ='90:closed,20:feedback,50:assigned';
    $g\_status\_enum_workflow\[CLOSED\]       ='20:feedback,50:assigned';
    
5.  Check and update existing workflow configurations
    
    If you do not perform this step and have existing workflow definitions, it will not be possible to transition to and from your new status.
    
    Go to the Workflow Transitions page (manage\_config\_workflow_page.php), and update the workflow as appropriate. Make sure that you have picked the correct Project in the selection list).
    
    Hint: to identify whether you have any workflows that should be updated, open the Manage Configuration Report page (adm\_config\_report.php) and filter on 'All Users', \[any\] project and config option = 'status\_enum\_workflow'. All of the listed projects should be reviewed to eventually include transitions to and from the newly added states.
    

⁠7.6. Custom Functions
----------------------

Custom functions are used to extend the functionality of MantisBT by integrating user-written functions into the issue processing at strategic places. This allows the system administrator to change the functionality without touching MantisBT's core.

Default Custom Functions are defined in the API file `core/custom_function_api.php` , and are named _custom\_function\_default\_descriptive\_name_, where _descriptive_name_ describes the particular function. See [Section 7.6.1, “Default Custom Functions”](#admin.customize.customfuncs.defined) for a description of the specific functions.

User versions of these functions (overrides) are named like _custom\_function\_override\_descriptive\_name_, and placed in a file called `custom_functions_inc.php` that must be saved in MantisBT's config directory. In normal processing, the system will look for override functions and execute them instead of the provided default functions.

The simplest way to create a custom function is to copy the default one from the api to your override file (`custom_functions_inc.php`), and rename it (i.e. replacing 'default' by 'override'). The specific functionality you need can then be coded into the override function.

### ⁠7.6.1. Default Custom Functions

Refer to `core/custom_functions_api.php` for further details.

Custom Function Name

Description

Return value

custom\_function\_default\_auth\_can\_change\_password()

Determines whether MantisBT can update the password

True if yes, False if not

custom\_function\_default\_changelog\_include\_issue( $p\_issue_id )

Determines whether the specified issue should be included in the Changelog or not.

True to include, False to exclude

custom\_function\_default\_changelog\_print\_issue( $p\_issue\_id, $p\_issue_level = 0 )

Prints one entry in the Changelog

None

custom\_function\_default\_enum\_categories()

Build a list of all categories for the current project

Enumeration, delimited by "|"

custom\_function\_default\_enum\_future_versions()

Build a list of all future versions for the current project

Enumeration, delimited by "|"

custom\_function\_default\_enum\_released_versions()

Build a list of all released versions for the current project

Enumeration, delimited by "|"

custom\_function\_default\_enum\_versions()

Build a list of all versions for the current project

Enumeration, delimited by "|"

custom\_function\_default\_format\_issue\_summary( $p\_issue\_id, $p\_context = 0 )

Format the bug summary

Formatted string

custom\_function\_default\_get\_columns\_to\_view( $p\_columns\_target = COLUMNS\_TARGET\_VIEW\_PAGE, $p\_user_id = null )

Defines which columns should be displayed

Array of the column names

custom\_function\_default\_issue\_create\_notify( $p\_issue_id )

Notify after an issue has been created

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_issue\_create\_validate( $p\_new\_issue\_data )

Validate field settings before creating an issue

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_issue\_delete\_notify( $p\_issue_data )

Notify after an issue has been deleted

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_issue\_delete\_validate( $p\_issue_id )

Validate field settings before deleting an issue

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_issue\_update\_notify( $p\_issue_id )

Notify after an issue has been updated

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_issue\_update\_validate( $p\_issue\_id, $p\_new\_issue\_data, $p\_bugnote\_text )

Validate field issue data before updating

In case of invalid data, this function should call trigger_error()

custom\_function\_default\_print\_bug\_view\_page\_custom\_buttons( $p\_bug\_id )

Prints the custom buttons on the current view page

None

custom\_function\_default\_print\_column\_title( $p\_column, $p\_columns\_target = COLUMNS\_TARGET\_VIEW\_PAGE, array $p\_sort_properties = null )

Print a column's title based on its name

None

custom\_function\_default\_print\_column\_value( $p\_column, $p\_bug, $p\_columns\_target = COLUMNS\_TARGET\_VIEW\_PAGE )

Print a column's value based on its name

None

custom\_function\_default\_roadmap\_include\_issue( $p\_issue_id )

Determines whether the specified issue should be included in the Roadmap or not.

True to include, False to exclude

custom\_function\_default\_roadmap\_print\_issue( $p\_issue\_id, $p\_issue_level = 0 )

Prints one entry in the Roadmap

None

### ⁠7.6.2. Example Custom Function Override

The following function is used to validate an issue before it is resolved.

<?php

/\*\*
 \* Hook to validate Validate field settings before resolving
 \* verify that the resolution is not set to OPEN
 \* verify that the fixed in version is set (if versions of the product exist)
 */
function custom\_function\_override\_issue\_update\_validate( $p\_issue\_id, $p\_bug\_data, $p\_bugnote_text ) {
	if( $p\_bug\_data->status == RESOLVED ) {
		if( $p\_bug\_data->resolution == OPEN ) {
			error_parameters( 'the resolution cannot be open to resolve the issue' );
			trigger\_error( ERROR\_VALIDATE_FAILURE, ERROR );
		}
		$t\_version\_count = count( version\_get\_all\_rows( $p\_bug\_data->project\_id ) );
		if( ( $t\_version\_count > 0 ) && ( $p\_bug\_data->fixed\_in\_version == '' ) ) {
			error_parameters( 'fixed in version must be set to resolve the issue' );
			trigger\_error( ERROR\_VALIDATE_FAILURE, ERROR );
		}
	}
}

?>

The errors will also need to be defined, by modifying the following files

*   `custom_constants_inc.php`
    
    define( 'ERROR\_VALIDATE\_FAILURE', 2000 );
    
*   _Custom Strings File_ (see [Section 7.1, “Strings / Translations”](#admin.customize.strings))
    
    $MANTIS\_ERROR\['ERROR\_VALIDATE_FAILURE'\] = 'This change cannot be made because %s';
    

⁠Chapter 8. Authentication
==========================

[8.1. Standard Authentication](#admin.auth.standard)

[8.2. LDAP and Microsoft Active Directory](#admin.auth.ldap)

[8.3. Basic Authentication](#admin.auth.basic)

[8.4. HTTP Authentication](#admin.auth.http)

[8.5. Deprecated authentication methods](#admin.auth.deprecated)

MantisBT supports several authentication methods out of the box. In addition, there is work in progress relating to supporting authentication plug-ins. Once these are implemented, authentication against any protocol or repository of user names and passwords will be possible without having to touch MantisBT core code.

It is important to note that MantisBT does not yet support hybrid authentication scenarios. For example, internal staff authenticating against LDAP while customers authenticate against the MantisBT database with MD5 hash.

See $g\_login\_method in [Section 5.21.1, “Global authentication parameters”](#admin.config.auth.global) for more details about how to configure MantisBT to use one of these authentication techniques.

⁠8.1. Standard Authentication
-----------------------------

With Standard login method, MantisBT users are authenticated against records in the MantisBT database, where the passwords are stored as a hash.

Note: while technically unlimited, the password's length is arbitrarily restricted to 1024 characters (PASSWORD\_MAX\_SIZE\_BEFORE\_HASH constant).

Values for $g\_login\_method:

*   _[MD5](http://en.wikipedia.org/wiki/MD5)_ is the default - and recommended - method
    
*   Support for additional methods (e.g. [SHA-1](http://en.wikipedia.org/wiki/SHA-1)) could be added in the future
    

⁠8.2. LDAP and Microsoft Active Directory
-----------------------------------------

Value for $g\_login\_method: _LDAP_

Authentication is made against an [LDAP](http://en.wikipedia.org/wiki/LDAP) or [Active Directory](http://en.wikipedia.org/wiki/Active_Directory) server.

The LDAP parameters should be setup as explained in [Section 5.21.2, “LDAP authentication method parameters”](#admin.config.auth.ldap).

An MD5 hash of the user's password will be stored in the database upon successful login, allowing fall-back to Standard Authentication when the LDAP server is not available.

The user's ID and password is checked against the Directory; if the credentials are valid, then the user is allowed to login and their user account in MantisBT is created automatically.

⁠8.3. Basic Authentication
--------------------------

Value for $g\_login\_method: _BASIC_AUTH_

When MantisBT is configured to use basic auth, it automatically detects the logged in user and checks if they are already registered in MantisBT, if not, then a new account is automatically created for the username.

The password length is limited to the size of the underlying database field (DB\_FIELD\_SIZE_PASSWORD constant), currently 32 characters.

⁠8.4. HTTP Authentication
-------------------------

Value for $g\_login\_method: _HTTP_AUTH_

TODO

The password length is limited to the size of the underlying database field (DB\_FIELD\_SIZE_PASSWORD constant), currently 32 characters.

⁠8.5. Deprecated authentication methods
---------------------------------------

The following methods of authentication are deprecated, and supported for backwards-compatibility reasons only. It is strongly recommended to update MantisBT installations relying on these to use [Section 8.1, “Standard Authentication”](#admin.auth.standard) instead.

Deprecated values for $g\_login\_method:

*   CRYPT
    
*   CRYPT\_FULL\_SALT
    
*   PLAIN
    

With CRYPT-based methods, the password's length is limited as per Standard Authentication. With PLAIN, its size is restricted as for Basic Authentication.

⁠Chapter 9. Troubleshooting
===========================

[9.1. Application Errors](#admin.troubleshooting.errors)

[9.1.1. Error 2800 - Invalid form security token](#admin.troubleshooting.errors.2800)

This chapter provides the Administrator with additional information related to Application Errors and common problems in MantisBT.

Useful additional reference information and support may also be found on the [MantisBT website](http://www.mantisbt.org/), more specifically the [Forums](http://www.mantisbt.org/forums/) and the [Bugtracker](http://www.mantisbt.org/bugs/).

⁠9.1. Application Errors
------------------------

Additional information about MantisBT common errors.

### ⁠9.1.1. Error 2800 - Invalid form security token

This error may only occur when Form Validation is enabled with $g\_form\_security_validation = ON (see [Section 5.4, “Webserver”](#admin.config.webserver)). There are several known cases that could trigger it:

*   Multiple submissions of a form by clicking on the submit button several times (user error)
    
*   Invalid or unauthorized submission of a form, e.g. by hand-crafting the URL (CSRF attack)
    
*   Expired PHP session
    

In the first two instances, MantisBT's behavior is by design, and the response as expected. For expired sessions however, the user is impacted by system behavior, which could not only cause confusion, but also potential loss of submitted form data. What happens is driven by several php.ini configuration settings:

*   The ratio [session.gc_probability](http://php.net/session.gc-probability) divided by [session.gc_divisor](http://php.net/session.gc-divisor), which determines the probability that the garbage collection process will start when a session is initialized.
    
*   [session.gc_maxlifetime](http://php.net/session.gc-maxlifetime) which specifies (as the name does not indicate) the _minimum_ validity of session data.
    

With PHP default values, sessions created more than 1440 seconds (24 minutes) ago have a 1% chance to be invalidated each time a new session is initialized. This explains the seemingly random occurrence of this error.

Unfortunately, this problem cannot be fixed without a major rework of the way sessions and form security are handled in MantisBT.

As a workaround, the Administrator can

*   Increase the value of [session.gc_maxlifetime](http://php.net/session.gc-maxlifetime)
    
*   Set $g\_form\_security_validation = OFF. _Note that for security reasons, it is strongly recommended not to do this._
    

Users may also install local tools to avoid loss of form data, e.g. [Lazarus Form Recovery](http://lazarus.interclue.com/) add-on for Firefox.

Further references and reading:

*   MantisBT issues [12381](http://www.mantisbt.org/bugs/view.php?id=12381), [12492](http://www.mantisbt.org/bugs/view.php?id=12492), [13106](http://www.mantisbt.org/bugs/view.php?id=13106), [13246](http://www.mantisbt.org/bugs/view.php?id=13246)
    

⁠Chapter 10. Project Management
===============================

[10.1. Change Log](#admin.project.changelog)

[10.2. Roadmap](#admin.project.roadmap)

[10.3. Time Tracking](#admin.project.timetracking)

[10.4. Graphs](#admin.project.graphs)

[10.5. Summary Page](#admin.project.summary)

This section covers the project management features of MantisBT. This includes features like change log, roadmap, time tracking, reporting and others.

⁠10.1. Change Log
-----------------

MantisBT doesn't just track the status of issues, it also relates issues to versions. Each project can have several versions, which are marked with attributes like released and obsolete. Users typically report issues against released issues and developers typically fix issues in not released versions. With every new release comes question like: what's new? what has been fixed? Customers wonder if the new release is of interest to them and whether they should take an upgrade. Well, the change log is specifically tailored to answer these kind of questions.

In order for an issue to show up in the change log, it has to satisfy certain criteria. The criteria is that the issue has to be resolved with a 'fixed' resolution and has to have the 'fixed\_in\_version' field set. Users sometimes wonder why resolved or closed issues don't show up in the change log, and the answer is that the 'fixed\_in\_version' field is not set. Without the 'fixed\_in\_version', it is not possible for MantisBT to include the issues in the appropriate section of the changelog. Note that it is possible to set the 'fixed\_in\_version' for multiple issues using the 'Update Fixed in Version' group action on the View Issues page (just below the issues list). This option is only available when the selected project is not 'All Projects'. Once a version is marked as obsolete, it is now longer included in the change log.

MantisBT also provides the ability to customize the criteria used for an issue to be included in the change log. For example, for installations that use a custom set of resolutions, it is possible to select multiple resolutions as valid candidates for the change log. This can be done using custom functions (see custom functions documentation for more details). The custom function below overrides the MantisBT default behavior to include issues with both FIXED and IMPLEMENTED (a custom resolution) resolutions in the change log.

​<?php
​\# --------------------
​\# Checks the provided bug and determines whether it should be included in the changelog
​\# or not.
​\# returns true: to include, false: to exclude.
​function custom\_function\_override\_changelog\_include_issue( $p\_issue\_id ) {
​    $t_issue = bug_get( $p\_issue\_id );
​
​    return ( ( $t_issue->resolution == FIXED || $t_issue->resolution == IMPLEMENTED ) &&
​        ( $t_issue->status >= config_get( 'bug\_resolved\_status_threshold' ) ) );
​}

MantisBT also provides the ability to customize the details to include from the issue and in what format. This can be done using the following custom function.

​
​<?php
​\# --------------------
​\# Prints one entry in the changelog.
​function custom\_function\_override\_changelog\_print_issue( $p\_issue\_id, $p\_issue\_level = 0 ) {
​    $t_bug = bug_get( $p\_issue\_id );
​
​    if( $t_bug->category_id ) {
​        $t\_category\_name = category\_get\_name( $t_bug->category_id );
​    } else {
​        $t\_category\_name = '';
​    }
​
​    $t_category = is_blank( $t\_category\_name ) ? '' : '&lt;b&gt;\[' . $t\_category\_name . '\]&lt;/b&gt; ';
​    echo str_pad( '', $p\_issue\_level \* 6, '&#160;' ), '\- ', string\_get\_bug\_view\_link( $p\_issue\_id ), ': ', $t_category, string\_display\_line_links( $t_bug->summary );
​
​    if( $t_bug->handler_id != 0 ) {
​        echo ' (', prepare\_user\_name( $t_bug->handler_id ), ')';
​    }
​
​    echo ' \- ', get\_enum\_element( 'status', $t_bug->status ), '.&lt;br /&gt;';
​}

By combining both customization features, it is also possible to do more advanced customization scenarios. For example, users can add a 'ChangelogSummary' custom field and include all issues that have such field in the change log. Through customizing what information being included for a qualifying issue, users can also include the 'ChangelogSummary' text rather than the native summary field.

In some cases, users know that they fixed an issue and that the fix will be included in the next release, however, they don't know yet the name of the release. In such case, the recommended approach is to always have a version defined that corresponds to the next release, which is typically called 'Next Release'. Once the release is cut and has a concrete name, then 'Next Release' can be renamed to the appropriate name and a new 'Next Release' can then be created. For teams that manage releases from multiple branches for the same project, then more than one next release can be possible. For example, 'Next Dev Release' and 'Next Stable Release'.

Another common requirement is to be able to link to the change log of a specific project from the project's main website. There is a variety of ways to do that:

*   To link to the changelog of version "ver1" of project "myproject":
    
    http://www.example.com/mantisbt/changelog_page.php?project=myproject&version=ver1
    
*   To link to the changelog of all non-obsolete versions of project 'myproject':
    
    http://www.example.com/mantisbt/changelog_page.php?project=myproject
    
*   To link to the changelog of project with id 1. The project id can be figured out by going to the management page for the project and getting the value of project_id field form the URL.
    
    http://www.example.com/mantisbt/changelog\_page.php?project\_id=1
    
*   To link to the changelog of version with id 1. The version id is unique across all projects and hence in this case it is not necessary to include the project id/name. The version id can be figured out by going to the manage project page and editing the required version. The version_id will be included in the URL.
    
    http://www.example.com/mantisbt/changelog\_page.php?version\_id=1
    

Another approach is to go to the project page and from there users can get to multiple other locations relating to the project include the change log. This can be done by a URL like the following:

http://www.example.com/mantisbt/project\_page.php?project\_id=1

It is possible to customize the access level required for viewing the change log page. This can be done using the $g\_view\_changelog_threshold configuration option.

⁠10.2. Roadmap
--------------

One of the very important scenarios in project management is where the project managers (or team leads) triage the issues to set their priorities, target version, and possibly assign the issues to specific developers or take other actions on the issue. By setting the target version of an issue to a version that is not yet released, the issue shows up on the project roadmap, providing user with information about when to expect the issues to be resolved. The roadmap page has a section for each release showing information like planned issues, issues done and percentage of issues completed. Issues that are fixed in a specific version, but didn't have the target\_version field set, will not show up in the roadmap. This allows the ability to control the issues that are significant enough to show in the roadmap, while all resolved fields can be found in the change log. Note that it is possible to set the 'target\_version' for multiple issues using the 'Update Target Version' group action that is available through the View Issues page (below the issues list). This option is only available when the current project is not 'All Projects'. Although it is not a typical scenario, it is worth mentioning that once a version is marked as obsolete, it is not included in the roadmap.

Note that the roadmap only includes future versions, once a version is marked as released, it no longer is included in the roadmap. For information about such releases, the change log feature should be used. For an issue to be shown on the roadmap, it has to have the target version set. It does not matter whether the feature is resolved or not. Resolved features will be decorated with a strikethrough and will be counted as done.

MantisBT provides the ability to customize the criteria for issues to show up on the roadmap. The default criteria is that the issue has to belong to a version that is not yet released and that the issues is not a duplicate. However, such criteria can be customized by using custom functions as below.

​
​<?php
​\# --------------------
​\# Checks the provided bug and determines whether it should be included in the roadmap or not.
​\# returns true: to include, false: to exclude.
​function custom\_function\_override\_roadmap\_include_issue( $p\_issue\_id ) {
​    return ( true );
​}

It is also possible to customize the details included about an issues and the presentation of such details. This can be done through the following custom function:

​
​<?php
​\# --------------------
​\# Prints one entry in the roadmap.
​function custom\_function\_override\_roadmap\_print_issue( $p\_issue\_id, $p\_issue\_level = 0 ) {
​    $t_bug = bug_get( $p\_issue\_id );
​
​    if( bug\_is\_resolved( $p\_issue\_id ) ) {
​        $t\_strike\_start = '&lt;strike&gt;';
​        $t\_strike\_end = '&lt;/strike&gt;';
​    } else {
​        $t\_strike\_start = $t\_strike\_end = '';
​    }
​
​    if( $t_bug->category_id ) {
​        $t\_category\_name = category\_get\_name( $t_bug->category_id );
​    } else {
​        $t\_category\_name = '';
​    }
​
​    $t_category = is_blank( $t\_category\_name ) ? '' : '&lt;b&gt;\[' . $t\_category\_name . '\]&lt;/b&gt; ';
​
​    echo str_pad( '', $p\_issue\_level \* 6, '&#160;' ), '\- ', $t\_strike\_start, string\_get\_bug\_view\_link( $p\_issue\_id ), ': ', $t_category, string\_display\_line_links( $t_bug->summary );
​
​    if( $t_bug->handler_id != 0 ) {
​        echo ' (', prepare\_user\_name( $t_bug->handler_id ), ')';
​    }
​
​    echo ' \- ', get\_enum\_element( 'status', $t_bug->status ), $t\_strike\_end, '.&lt;br /&gt;';
​}

Some teams manage different branches for each of their projects (e.g. development and maintenance branches). As part of triaging the issue, they may decide that an issue should be targeted to multiple branches. Hence, frequently the request comes up to be able to target a single issue to multiple releases. The current MantisBT approach is that an issues represents an implementation or a fix for an issue on a specific branch. Since sometimes applying and verifying a fix to the two branches does not happen at the same time and in some cases the approach for fixing an issue is different based on the branch. Hence, the way to manage such scenario is to have the main issue for the initial fix and have related issues which capture the work relating to applying the fix to other branches. The issues for porting the fix can contain any discussions relating to progress, reflect the appropriate status and can go through the standard workflow process independent of the original issues.

Another common requirement is to be able to link to the roadmap of a specific project from the project's main website. There is a variety of ways to do that:

*   To link to the roadmap of version "ver1" of project "myproject":
    
    http://www.example.com/mantisbt/roadmap_page.php?project=myproject&version=ver1
    
*   To link to the roadmap of all non-obsolete versions of project 'myproject':
    
    http://www.example.com/mantisbt/roadmap_page.php?project=myproject
    
*   To link to the roadmap of project with id 1. The project id can be figured out by going to the management page for the project and getting the value of project_id field form the URL.
    
    http://www.example.com/mantisbt/roadmap\_page.php?project\_id=1
    
*   To link to the roadmap of version with id 1. The version id is unique across all projects and hence in this case it is not necessary to include the project id/name. The version id can be figured out by going to the manage project page and editing the required version. The version_id will be included in the URL.
    
    http://www.example.com/mantisbt/roadmap\_page.php?version\_id=1
    

Another approach is to go to the project page and from there users can get to multiple other locations relating to the project include the roadmap. This can be done by a URL like the following:

http://www.example.com/mantisbt/project\_page.php?project\_id=1

The access level required to view and modify the roadmap can be configured through $g\_roadmap\_view\_threshold and $g\_roadmap\_update\_threshold respectively. Modifying the roadmap is the ability to set the target versions for issues. Users who have such access can set the target versions while reporting new issues or by updating existing issues.

⁠10.3. Time Tracking
--------------------

To activate the Time Tracking feature you have to set the configuration option "time\_tracking\_enabled" to ON. To activating the Time Tracking you can :

*   Static solution : change the variable '$g\_time\_tracking\_enabled' in the configuration file 'config\_defaults_inc.php', this will change the configuration for all the MantisBT instance ;
    
*   Dynamic and "project by project" solution : Use the administration page "Manage Configuration" and set the variable 'time\_tracking\_enabled' to '1' for which user and which project of you choice.
    

All Time Tracking configuration options are described in the configuration section off this guide.

⁠10.4. Graphs
-------------

Assigned to me: TODO

Release Delta: TODO

Category: TODO

Severity: TODO

Severity / Status: TODO

Daily Delta: TODO

Reported by Me: TODO

⁠10.5. Summary Page
-------------------

By Status: TODO

By Severity: TODO

By Category: TODO

Time Stats for Resolved Issues (days): TODO

Developer Status: TODO

Reporter by Resolution: TODO

Developer by Resolution: TODO

By Date: TODO

Most Active: TODO

Longest Open: TODO

By Resolution: TODO

By Priority: TODO

Reporter Status: TODO

Reporter Effectiveness: TODO

⁠Chapter 11. Contributing to MantisBT
=====================================

[11.1. Talent and Time](#admin.contributing.develop)

[11.2. Recommend MantisBT to Others](#admin.contributing.share)

[11.3. Blog about MantisBT](#admin.contributing.blog)

[11.4. Integrate with MantisBT](#admin.contributing.integrate)

⁠11.1. Talent and Time
----------------------

One of the greatest ways to contribute to MantisBT is to contribute your talent and time. For MantisBT to keep growing we need such support in all areas related to the software development cycle. This includes: business analysts, developers, web designers, graphics designers, technical writers, globalization developers, translators, testers, super users, packagers and active users. If you would like to contribute in any of these capacities please contact us through the "Contact Us" page.

⁠11.2. Recommend MantisBT to Others
-----------------------------------

It feels great when we get feedback from the user community about how MantisBT boosted their productivity, and benefited their organization. A lot of the feedback I get is via email, some on mailing lists, and some on forums. I would encourage such users to blog about it, tell their friends about MantisBT, and recommend MantisBT to other organizations. MantisBT is driven by it's community, the greater the community, the greater the ideas, the greater of a product it becomes.

⁠11.3. Blog about MantisBT
--------------------------

If you have a blog, then talk about MantisBT, review it's features and help us spread the word. A lot of users also like to blog about how they customized MantisBT to fit their needs or to integrate with other tools that they use in their work environment.

⁠11.4. Integrate with MantisBT
------------------------------

If you have a product that can be integrated with MantisBT to provide value for MantisBT users, that would be a great place to contribute and benefit both your project's and the MantisBT community.

A great example in this area are integrations with content management systems (e.g. *Nuke, Xoops), project management (PHPProjekt), and TestLink for Test Management. MantisBT can easily be integrated with projects in any programming language whether it is hosted on the same webserver or anywhere else in the world. This can be achieved through its SOAP API and MantisConnect client libraries. MantisConnect comes with client libraries and samples in languages like PHP, .NET, Java and Cocoa.

⁠Appendix A. Revision History
=============================

**Revision History**

Revision 2.11-0

Tue Feb 6 2018

Victor Boctor

Release 2.11.0

Revision 2.10-0

Sat Dec 30 2017

Victor Boctor

Release 2.10.0

Revision 2.9-0

Sun Dec 3 2017

Victor Boctor

Release 2.9.0

Revision 2.8-0

Sat Oct 28 2017

Victor Boctor

Release 2.8.0

Revision 2.7-0

Sun Oct 8 2017

Victor Boctor

Release 2.7.0

Revision 2.6-0

Sun Sep 3 2017

Victor Boctor

Release 2.6.0

Revision 2.5-1

Sat Jun 17 2017

Victor Boctor

Release 2.5.1

Revision 2.5-0

Sun Jun 4 2017

Victor Boctor

Release 2.5.0

Revision 2.4-1

Sat May 20 2017

Victor Boctor

Release 2.4.1

Revision 2.4-0

Sun Apr 30 2017

Victor Boctor

Release 2.4.0

Revision 2.3-3

Sun Apr 30 2017

Victor Boctor

Release 2.3.2

Revision 2.3-2

Sun Apr 17 2017

Victor Boctor

Release 2.3.1

Revision 2.3-1

Fri Mar 31 2017

Victor Boctor

Release 2.3.0

Revision 2.2-3

Wed Mar 22 2017

Damien Regad

Release 2.2.2

Revision 2.2-2

Sun Mar 12 2017

Victor Boctor

Release 2.2.1

Revision 2.2-1

Sun Feb 26 2017

Victor Boctor

Release 2.2.0

Revision 2.1-2

Sun Feb 26 2017

Victor Boctor

Release 2.1.1

Revision 2.1-1

Tue Jan 31 2017

Victor Boctor

Release 2.1.0

Revision 2.0-2

Fri Dec 30 2016

Victor Boctor

Release 2.0.0

Revision 2.0-1

Sat Nov 26 2016

Damien Regad

Release 2.0.0-rc.2
