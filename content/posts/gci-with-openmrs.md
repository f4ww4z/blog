---
title: "Google Code-in Experience with OpenMRS"
date: 2018-01-24T11:05:08+07:00
categories: ["OpenMRS"]
tags: ["openmrs", "outreach", "documentation"]
cover:
  image: /img/gci-with-openmrs/gci_at_openmrs_cover.png
  caption: Google Code-in 2017 at OpenMRS
  style: full
---

Checking out the [Google Open Source Blog](https://opensource.googleblog.com) on October 2017, I saw a [post](https://opensource.googleblog.com/2017/10/welcoming-25-mentor-organizations-for.html) listing out numerous organizations that are taking part in the annual [Google Code-in](https://codein.withgoogle.com/) competition. The Google team had chosen a diverse range of organizations: from game development and computer graphics software to worldwide medical record systems and Operating Systems.

Because all of these open source organizations are amazing, choosing one *org* to work with during the seven week period of Google Code-in is personally very challenging to me. Nevertheless, I remembered one organization from GCI last year that values a friendly, positive community while working to improve living conditions around the world - **OpenMRS**.

So by the time Google Code-in starts (29th November in my region), I quickly got myself involved in the [OpenMRS chat](https://wiki.openmrs.org/x/EQAP) and started *writing code to save lives*.

## OpenMRS for the World

![OpenMRS around the world](/img/gci-with-openmrs/openmrs_banner.png)

OpenMRS is short for the Open Medical Record System, providing hospitals and clinics an Electronic Record system (EMR) to replace the inefficient but widely-used paper based record systems, especially in the developing world. Since 2004, OpenMRS has evolved from a small clinic in Kenya to providing health care delivery in almost every continent around the globe. Now OpenMRS is a global organization with thousands of active community members contributing to the open source system codebase.

>Read more about the OpenMRS community [here](/post/about-openmrs).

And since 2014, OpenMRS participated in the Google Code-in program with pre-university students. For Google Code-in 2017 (29th November 2017 - 17th January 2018), OpenMRS elected experienced members of the community to become GCI mentors. This means that our GCI tasks are judged fairly and that a standard was set between mentors for each GCI task completed by a student. Nevertheless, GCI mentors and admins are very friendly in the chat and will certainly help shortly when a student is having issues regarding OpenMRS or Google Code-in.

#### First Task

The very first task I completed for OpenMRS was actually the process of getting involved in the community. That is: creating an OpenMRS Talk, Wiki and OpenMRS JIRA account (which are integrated with an [OpenMRS ID](http://id.openmrs.org/)) and introducing myself to the GCI 2017 [*"Student and Mentor meet and greet"*](https://talk.openmrs.org/t/google-code-in-2017-student-and-mentor-meet-and-greet) thread on OpenMRS Talk. Once complete, I wrote short comments on the benefits of having an OpenMRS Talk account when we start to integrate ourselves with the community. [*See my comments for this task*](https://issues.openmrs.org/browse/GCI-134?focusedCommentId=242770&page=com.atlassian.jira.plugin.system.issuetabpanels%3Acomment-tabpanel#comment-242770).

## From Zero to Hero

Having completed the introductory task, I started work on a bunch of exciting tasks for OpenMRS, and around half of them were submitting Pull Requests to the [OpenRMS codebase](https://github.com/openmrs/) on GitHub. I will divide the description of tasks I have completed during the GCI period into smaller categories.

### Quality Assurance / Reporting Bugs

![Quality assurance at a glance](/img/gci-with-openmrs/quality_assurance_pic_1.jpg)

These tasks basically focus on experimenting with the accustomed application (e.g. a web app, a mobile app) and finding errors or bugs relating to the app.

My first Quality Assurance task was trying out the [OpenMRS SysAdmin OWA](https://addons.openmrs.org/#/show/org.openmrs.owa.sysadmin) (short for [Open Web App](https://wiki.openmrs.org/x/C4KIBQ)) and then evaluating the app. This includes finding out workflow issues, UX and UI bugs and also suggestions on providing a better SysAdmin OWA for the end user.

>See the full [Google Doc I had written](https://docs.google.com/document/d/1YQ3FSbw5Vsl4V37bBm-jBM6xPhYcLIVJL6BDFSTxSos/edit?usp=sharing) regarding the evaluation process of the SysAdmin OWA.

The second QA (Quality Assurance) I worked on was evaluating the OpenMRS Reference Application itself. In this task, I found two fresh bugs from the latest *Reference application* version, which until now can be reproduced at http://qa-refapp.openmrs.org/. Here's hoping that an experienced member can fix those bugs soon!

>See examples of bugs I found in this task: [**RA-1442**](https://issues.openmrs.org/browse/RA-1442) and [**RA-1443**](https://issues.openmrs.org/browse/RA-1443).

Another QA task I completed was choosing specifically one [*bundled module*](https://wiki.openmrs.org/x/WQ8z) from the OpenMRS Reference Application and testing that module out. I chose to assess the **Admin UI** module as I guess that module is incorporated closely with the **Appointment Scheduling** module, thus more prone to integration bugs.

Here are the three bugs I found relating to the Admin UI module:

- https://issues.openmrs.org/browse/RA-1449
- https://issues.openmrs.org/browse/RA-1448
- https://issues.openmrs.org/browse/RA-1447

I also complied OpenMRS's main website at http://openmrs.org/ with WCAG's guidelines, and have created a document [here](https://docs.google.com/document/d/14lzESgbCkhAh9W1gmzxrJWbcNFtftfYJ4qMtashw05c/edit?usp=sharing).

Last, my final QA task was completing QA testing for new features developed for **Refapp** v**2.7.0**, and the relevant Google Document is [here](https://docs.google.com/document/d/1jDRuUKDG5rmkAXyLLuGV_4mfl8hio0poLscGZnE-IEQ/edit?usp=sharing).

>P.S. All Quality Assurance (QA) evaluations are done on the demo server http://qa-refapp.openmrs.org/, which includes the **latest** changes from the codebase on GitHub.


### Documentation

Having done a bunch of QA tasks, I moved on to documentation tasks. As OpenMRS is moving the way they publicize and distribute modules, from the old [modules.openmrs.org](http://modules.openmrs.org/) to the new [Add-ons index](http://addons.openmrs.org/), here I mostly update the OpenMRS Wiki from providing old instructions to upload to *modules.openmrs.org* and point to [the new way](https://wiki.openmrs.org/x/zIMmAQ) of publishing modules. See my rampage of edits to the Wiki page on [**this GitHub gist**](https://gist.github.com/f4ww4z/186cd956403d18bbe2a359a7e76ab35f).

(P.S. I was going to include the gist in this post as a shortcode, although I think it will too long to be readable.)

### //TODO: Code

Now, it is time for the main part of the competition - it isn't called Google '**Code**'-in for nothing ;)

The first coding task for me is to fix one type of bad code practice in the main `openmrs-core` repository on GitHub. Check out my Pull Request (PR) at https://github.com/openmrs/openmrs-core/pull/2367 .

My second coding task is to group modules with similar characteristics at the new Add-ons index. In this task I improved my JSON skills as well as getting to know more about common modules used in the OpenMRS Refapp. See my Pull Request (PR) at https://github.com/openmrs/openmrs-contrib-addonindex/pull/30 .

Next, as I was more comfortable with writing code for the OpenMRS Android client, I chose an Android client (AC) task that requires me to change the implementation of date entering on the registration screen. It took 5 days of reviews and feedback, but I felt glad when my code was merged. See my complete PR at [**AC-428**](https://github.com/openmrs/openmrs-contrib-android-client/pull/399).

After completing the Android client task above, a mentor (also the leader of the Android client project) advised me to write unit tests for the new implementation, so I did exactly that. See my [unit tests PR here](https://github.com/openmrs/openmrs-contrib-android-client/pull/403/).

### Outreach and Design tasks

I have also produced videos to explain the various features of the OpenMRS structure. In this case, I made a tutorial video on the usage of [OpenMRS Talk](http://talk.openmrs.org/) (our forums page) and another instructional video on the [release process](https://wiki.openmrs.org/display/docs/Release+Process) of OpenMRS applications.

My video on the usage of OpenMRS Talk:
<iframe width="1" height="1" src="https://www.youtube.com/embed/eVpd4qLyTlA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

{{< youtube eVpd4qLyTlA >}}

and the release process tutorial is live at https://youtu.be/krf-MpfPVWE

Next, I constructed an HTML Email template to thank Google Code-in and Google Summer of Code students for all their hard work at OpenMRS. My GCI Email template is live at ***https://f4ww4z.github.io/openmrs-template-gci/*** whilst my GSOC Email template is at ***https://f4ww4z.github.io/openmrs-template-gsoc/*** .

After those tasks are complete, I designed a custom 404 page for the OpenMRS website. I managed to integrate the [404 page source code](https://github.com/f4ww4z/gci-89) and deploying it to OpenShift as a WAR package.

>See my 404 page at http://gci-89-gci-89.a3c1.starter-us-west-1.openshiftapps.com/GCI-89/

Lastly, I have published a [*blog article*](/post/about-openmrs/) to get more people to join the OpenMRS community as the Google Code-in period was coming to an end. Hopefully more people are eager to join OpenMRS and at the same time writing code to save lives. See it live [here](/post/about-openmrs/).

---

Personally, I loved working on documentation and Quality Assurance tasks and I will continue to do so in the near future.


## What I Learned from Google Code-in

#### Requested Code Changes are Okay

I realized when a reviewer requested changes and wrote comments suggestively for my PR, it does not mean the code is bad - rather they care enough about me that they like to see me improving the PR.

#### Being Active in the Community

Being active is a key part of one's commitment in an open source project. Whether it would be responding to questions on a Talk thread, PR reviews, etc. it is a great way for the community to know about yourself and vice versa. Being active also means that one can work with a mentor or another developer effectively, with the exception of Time Zone differences.

#### Feel Free to Ask

Everyone has the right to ask any query they are facing regarding OpenMRS (or an open source project in general), whether that would be development, software, community queries and etc. This is especially true in an open source organization such as OpenMRS as the goal is to create a friendly environment where everyone feels they can ask anything willingly to the community.

## From Google Code-in until Now

Truly, Google Code-in has been an exceptional program for us students to be introduced to the world of open source. I personally have learned a lot through GCI alone, and so I guess there is no going back. Well, after the last day of task submission, I kept and will continue contributing to the OpenMRS community, especially with the [OpenMRS Android client](https://github.com/openmrs/openmrs-contrib-android-client) as well as the [Android app's user guide](https://github.com/openmrs/openmrs-android-client-user-guide/).

<!-- Although there might not be payment on offer, our very code will be used by thousands of clinics around the world, improving patients' living conditions in the developing world. And I guess saving lives are more valuable than what money can buy. -->
