---
title: "A Friendly Guide to OpenMRS"
date: 2018-01-12T09:12:02+07:00
categories: ["OpenMRS"]
tags: ["openmrs", "outreach", "documentation"]
cover:
  image: /img/about-openmrs/openmrs_atlas_2018.png
  caption: Hospitals and clinics [using OpenMRS](https://atlas.openmrs.org/) as of January, 2018
  style: full
---

When *Academic Model for Prevention and Treatment of HIV/AIDS* (AMPATH) systems were overloaded with patient data back in February 2004, *two men* from the Regenstrief Institute in Indianapolis, United States were invited to analyze the site for improvements to the patient data model. Having visited Kenya, they realized that a new, robust system needed to be built - one that supports a wider range of patients with an optimized data model - and soon becomes the worldwide health care organization we know today as **OpenMRS**.

## About OpenMRS

[OpenMRS](http://openmrs.org/) is an organization with a clear goal: to provide a robust, scalable, user-driven open electronic medical record system for the planet, tackling the severe conditions experienced by patients in developing countries. We have a vision to provide the best means of recording patient data with the lowest cost possible: a **free** and open source software.

As a representative of the OpenMRS community, I'd like to say OpenMRS is being developed by people like **you** - someone who cares for health care delivery in the world, regardless of costs and materials involved.

## OpenMRS Today

*OpenMRS community, from [openmrs.org](http://openmrs.org)*
![](http://openmrs.org/wp-content/uploads/2011/12/296587_10150306947211362_319313176361_8201304_1488260688_n.jpeg)

As of 2018, OpenMRS has a large [range of modules](http://addons.openmrs.org/) tailored to each implementation; has released over **66** OpenMRS [Platform versions](https://wiki.openmrs.org/x/xgLpAw) and **18** [Reference Application versions](https://wiki.openmrs.org/x/xALpAw); and more importantly, OpenMRS has **thousands** of Internet-connected community members actively contributing to the [codebase](https://github.com/openmrs/).

OpenMRS community works hard to ensure that real places where OpenMRS systems are implemented operates well under control, bug-free and open to customize its functionalities.

### Our Demo Application

Go ahead and preview our OpenMRS web application:

>**http://demo.openmrs.org/**

![Login page of the Refapp](/img/about-openmrs/refapp_login.png)

You will need a test username and a password. [This Wiki page](https://wiki.openmrs.org/display/docs/Reference+Application+2.7.0#ReferenceApplication2.7.0-TryItOut!) provides you the credentials.

```
Username: admin
Password: Admin123
```

Next, choose a location and click `Login`.

![Refapp home page](/img/about-openmrs/refapp_home.png)

Alright, now that you are viewing our live demo web app, you might be wondering what our application consists of.

What you are seeing is the OpenMRS **Reference Application** (commonly known as the *Refapp*). It is essentially an Electronic Medical Record (EMR) software, and one can freely make modifications suited to their needs.

The Refapp is built from a collection of chosen modules. Each module depends on one another to function, and each module functions as a part of an EMR. For example, the *Appointment Scheduling* module provides the function of scheduling patient check-ups or visits with a provider, the *Registration App* module allows new patients to be registered and stored in the server, and the *UI Framework* module builds the entire user interface through a set of common rules or traits.

Thus, the *Appointment Scheduling* and *Registration App* module depends on the *UI Framework* module to be able to create the module's user interface.

>See [this Wiki page](https://wiki.openmrs.org/display/RES/Release+Notes+2.7.0#ReleaseNotes2.7.0-IncludedModules) for the list of modules built for Reference Application 2.7.

### Preview our Android client

![Android client screenshots](/img/about-openmrs/android_client_1.png)

>At https://play.google.com/store/apps/details?id=org.openmrs.mobile

Our **Android client** essentially covers most functionalities of the web application. Providers are able to interact with the server with great mobility - such as capturing biometric data, registering new patients, and so forth. All of these operations are run on Android phones, effectively speeding up the process.

The [Android client](https://wiki.openmrs.org/x/nABtB) can be used in locations where computers and the Internet is out of reach, as it **supports offline** operations as well. When the provider or user *does* access the Internet, he/she will be able to sync the data to an OpenMRS server.

>For an in-depth tutorial of using the mobile app, view our complete [**user guide**](https://openmrs.github.io/openmrs-android-client-user-guide/) for the Android client.

#### [Servers](https://wiki.openmrs.org/x/-oO8Bg)

Now, the test server I have shown to you at [demo.openmrs.org](http://demo.openmrs.org/) is actually running the latest *stable* release of the Refapp. What I am saying, is that [demo.openmrs.org](http://demo.openmrs.org/) will not likely change until a new major version is released (this will be the Refapp 2.8 on April 2018).

If you would like to see the latest code changes for the Refapp (a.k.a. the nightly build), it is available especially for Quality Assurance testing at **http://qa-refapp.openmrs.org/**

After reading about how different versions of the Refapp is hosted at different public servers, you might be wondering, how OpenMRS releases the next version of the Reference Application, or how we release the next OpenMRS Platform. Read on to find out the exact steps following a release process.

#### [Releases](https://wiki.openmrs.org/x/Xw0z)

![Release diagram](/img/about-openmrs/release_diagram.png)

For every new release of the OpenMRS Platform or the Reference Application, there will be a [*Release Manager*](https://wiki.openmrs.org/display/docs/Being+an+OpenMRS+Release+Manager): an experienced member that will guide developers through the process of releasing a new version. He/she will curate and sort [JIRA tickets](https://issues.openmrs.org/) according to improvements for the next release, making sure the next version fixes major bugs in the current version, inform the community on [Talk](https://talk.openmrs.org/), and many other things. What's more, the role of a Release Manager is assigned months before the actual release process!

In this way, OpenMRS always makes sure that a release is competent for the release date and that there is an *agreement* on which tickets are set for the release and which will not be finished before the release deadline. Being able to finalize decisions is key part for the advance of a successful and ever growing community such as OpenMRS.

#### Modules

![OpenHMIS Inventory Module](/img/about-openmrs/list_of_modules.png)

The main way of extending the [*core*](https://github.com/openmrs/) functionalities of the Platform is by adding modules. After all, the [Reference Application](https://wiki.openmrs.org/display/docs/Reference+Application+2.7.0) is built by a collection of modules which depends on each other to function properly. For example, the Refapp's UI alone is mainly created from the [UI Framework](https://addons.openmrs.org/#/show/org.openmrs.module.uiframework) module, [UI Commons](https://addons.openmrs.org/#/show/org.openmrs.module.uicommons) module and the [App UI](https://addons.openmrs.org/#/show/org.openmrs.module.appui) module.

>All of these amazing modules can be accessed and downloaded via the new [Add-ons index](http://addons.openmrs.org/).

Now, I have said that OpenMRS is supported by a large, friendly community. It means that whenever you choose to join OpenMRS, there will always be someone (or people) to introduce you to the OpenMRS environment. All you need to do is [sign up for an OpenMRS ID](http://id.openmrs.org/) and introduce yourself in [this OpenMRS Talk thread](https://talk.openmrs.org/t/welcome-please-introduce-yourself)! Be sure to ask any of your queries and doubts prior to joining OpenMRS in your reply.

## Wait, [OpenMRS Talk](https://talk.openmrs.org)?

![OpenMRS Talk](/img/about-openmrs/talk_1.png)

Yes! [OpenMRS Talk](https://talk.openmrs.org) is our forums site. There, you are able to ask any questions related to OpenMRS: ranging from errors you faced when building with the [OpenMRS SDK](https://wiki.openmrs.org/x/JQMqBQ) to community discussions such as suggestions to improve the UI/UX of the web app.

When you want to learn more about the development side of an OpenMRS system, e.g. the technical details of a community-developed module, documentation regarding an Open Web App (OWA), etc. the Wiki is a great place to start looking for answers.

## [OpenMRS Wiki](https://wiki.openmrs.org/) - Read and Learn

OpenMRS has a community-maintained Wiki, having hundreds of pages with the latest information on every aspect of an OpenMRS environment, our software and our community.

What's more, end users like you and I can edit the Wiki space with ease, if necessary. All you need to do is login with your *OpenMRS ID*, then going to a Wiki page we'd like to edit, click the `Edit` button at the top of the page. Then, make your edits and click `Update`. And with the blink of an eye, the Wiki page is updated, notifying the Wiki page creator of your edits. Of course, your edits *can be reverted* at any time if you wish.

>If you have successfully created an OpenMRS ID, however you cannot log in to the Wiki page nor the JIRA issues page, you will need to create a new **helpdesk** case requesting access to those services. This is a normal procedure for a new developer to avoid spam and unsecure accounts.

## Helpdesk? Desks to Help People?

No. The OpenMRS [Helpdesk](http://help.openmrs.org/) is a community IT help desk providing support to OpenMRS implementers and developers at [openmrs.org](http://openmrs.org/). However, note that [Helpdesk](http://help.openmrs.org/) does not provide support with OpenMRS itself.

To give you an idea of the difference between a Helpdesk support and help for OpenMRS itself, the community Helpdesk provides support for broken OpenMRS IDs, issues with not being able to log in to JIRA or the Wiki, and requesting access to a specific service - such as requesting a custom test server. However, development related questions and questions to the general OpenMRS community are asked at OpenMRS [Talk](http://talk.openmrs.org/), as it is our main Q & A forums page.

## Active projects

![Active projects development](/img/about-openmrs/active_projects.png)

I really encourage you to check out active OpenMRS projects and [Development Sprints](https://wiki.openmrs.org/x/agLn). Joining a project is an excellent way of getting to know our community whilst getting right down to contributing code.

See **all** active OpenMRS projects in the **child pages** of [this Wiki page](https://wiki.openmrs.org/x/dINs). In addition, check out all projects development types on our [issue and project tracking site](https://issues.openmrs.org/secure/BrowseProjects.jspa?selectedCategory=all&selectedProjectType=all).

### I'd like to contribute to OpenMRS right now!

Then get up to speed to become a developer for OpenMRS by following the [*Getting Started as a Developer*](https://wiki.openmrs.org/x/MQAJ) guide.

Take a look at these additional links also:

- **OpenMRS Developer book** - http://om.rs/devmanual
- **Full Developer Guide** - https://wiki.openmrs.org/x/FgAJ
- **Technical overview of technologies used** - https://wiki.openmrs.org/x/-g4z
- **Frequently Asked Questions page** - https://wiki.openmrs.org/x/_BAz

The OpenMRS workflow is essentially 'Claim, Work, Submit, Review, Repeat' process. To file bugs and suggest new improvements, as well as all updating OpenMRS projects and sprints, we have a solid JIRA issue tracking system at [issues.openmrs.org](http://issues.openmrs.org/).

If you are an aspiring Java or React developer, I recommend joining OpenMRS today, contributing code to save lives. Here at OpenMRS, you are able to expand your programming skills as well as helping a real worldwide issue - developing an [EMR](https://en.wikipedia.org/wiki/Electronic_health_record) to replace paper-based record keeping and data storage systems in hospitals, especially in the developing world. Check out [our goal](https://issues.openmrs.org/projects/TRUNK/issues/TRUNK-1?filter=allopenissues) (the first **core** issue) to save trees and other materials used to meet the paper-based demands of hospitals!

If you would like to improve or start a new project for OpenMRS, check out the annual [Google Summer of Code](https://summerofcode.withgoogle.com/) event and apply to work with our organization.

### Google Summer of Code (GSOC)

![GSOC with OpenMRS](https://wiki.openmrs.org/download/attachments/94636778/gsoc-omrs.png?version=1&modificationDate=1454932801000&api=v2)

OpenMRS has been a part of GSOC from the year of 2007. Since then, GSOC students have developed amazing projects and have greatly benefited people who are on the front lines of the battle against HIV/AIDS and other public health challenges. Many GSOC students then become permanent members of the OpenRMS community, and has been contributing more to OpenMRS since.

>Check out the past [OpenMRS GSOC (2017)](https://wiki.openmrs.org/x/GwCaBg) and the official [GSOC website](https://summerofcode.withgoogle.com/) for more info.

### It doesn't have to be code

With that said, if you wish to contribute to OpenMRS but has little or no knowledge of programming, you can still contribute to OpenMRS by other means. Create beautiful stickers and posters to attract more people to OpenMRS, improve our documentation (either at our [Wiki](http://wiki.openmrs.org/) or [GitBook guides](https://www.gitbook.com/@openmrs)), and run thorough testing for our [demo web app](http://qa-refapp.openmrs.org/) (Quality Assurance) and suggest improvements on [our issues site](http://issues.openmrs.org/) and [Talk](http://talk.openmrs.org/).

If you are below 18 and would like to contribute to OpenMRS, the annual [**Google Code-in**](http://codein.withgoogle.com/) competition is a great way to apply your skills to our organization. [GCI](http://codein.withgoogle.com/) tasks range from designing posters, user interfaces to providing quality assurance to the web app. It's also a great way to interact with new students / developers and familiarizing yourself with the community.

Watch this awesome video for an introduction of **Google Code-in** with OpenMRS:
<iframe width="1px" height="1px"></iframe>

{{< youtube id="HPxx1_svu_A" >}}

<br>
So, what are you waiting for? Join the world's largest **open source medical record system** today, and be ready to improve living conditions around the world.

Have questions? Send them to [our forums page](http://talk.openmrs.org/).

#### Additional Links

- **Website** - http://openmrs.org/
- **OpenMRS codebase** - https://github.com/openmrs/
- **OpenMRS Wiki** - http://wiki.openmrs.org/
- **Create an OpenMRS ID** - http://id.openmrs.org/
- **OpenMRS Talk** - http://talk.openmrs.org/
- **Issue and project tracking** - http://issues.openmrs.org/
- **Helpdesk** - http://help.openmrs.org/
- **IRC** - [**#openmrs**](https://wiki.openmrs.org/display/IRC/Home) on Freenode
- **Telegram** - https://t.me/OpenMRS
