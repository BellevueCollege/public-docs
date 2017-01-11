<span id="blue-card"></span>
# Blue Card
---

<span id=""></span>
##### Contents

- [Blue Card](#blue-card)
  - [Contents](#contents)
- [Statement of need](#statement-of-need)
  - [Problem](#problem)
  - [Goal](#goal)
  - [Statement of intent](#statement-of-intent)
  - [Title](#title)
  - [Stakeholders](#stakeholders)
  - [Project Stakeholders](#project-stakeholders)
  - [Size](#size)
  - [Scope](#scope)
- [Current status](#current-status)
- [Requirements](#requirements)
  - [Audience](#audience)
  - [Current Functions](#current-functions)
  - [New Functions](#new-functions)
  - [Function Details](#function-details)
    - [a) Turn ON/OFF open enrollment](#a-turn-onoff-open-enrollment)
    - [b) Distribute Blue Card entry codes (OPEN ENROLLMENT CLOSED)](#b-distribute-blue-card-entry-codes-open-enrollment-closed)
    - [c) Blue Card entry code rational](#c-blue-card-entry-code-rational)
    - [d) Email Notification](#d-email-notification)
    - [e) SSRS Reporting](#e-ssrs-reporting)
    - [f) Search Feature](#f-search-feature)
    - [g) Permissions Improvements](#g-permissions-improvements)
    - [h) Revisit logic for selecting active quarter](#h-revisit-logic-for-selecting-active-quarter)
- [Roadmap](#roadmap)
- [Open Questions](#open-questions)
- [References](#references)
- [Sprint Retro](#sprint-retro)
  - [What went wrong?](#what-went-wrong)

<span id="statement-of-need"></span>
## Statement of need

<span id="problem"></span>
#### Problem

Enrollment Services processes more than 1,800 blue cards for late registration each quarter. Currently we have two different processes in place for online classes and campus classes. In May 2012, the Blue Card Taskforce was formed to look for possible solutions to streamline the process. The Taskforce has delegated its members to look into three areas for possible improvement: Best/Current practices, Policy/Practices, and Technology Support. Based on the study and discussion from the past months, the Taskforce has made some recommendations.

Issues with the current process:

* Online blue cards may take days to process due to back and forth communications between ENR, the instructor, and the student.
* Paper blue cards are not properly filled out by instructor, potentially giving the student a free pass into any class if it is not caught by ENR
* Can not confirm signature on the paper blue card.
* Students in evening classes have to come to campus during the day to process their blue card.
* If a student gets a blue card on Friday they have to wait until Monday to register in person at ENR.

<span id="goal"></span>
#### Goal
The Taskforce members have gathered ideas from their areas to construct a dream world for blue card late registration. Our hope is to streamline the process so students can be enrolled into classes smoothly. Their suggestions can be consolidated into the following aspirations:

* Adopt one consistent process for all online and campus classes so students will have the same experience no matter what type of classes they are enrolled.
* Enable students to register themselves online anytime after they have received instructor permission so they do not need to wait for office hours and stand in line. This will enable students to start accessing class site and materials sooner.
* Replace paper form by electronic permission which can be tracked and managed through a centralized website. This also saves paper and printing cost as well as streamlines the process for instructors.

<span id="statement-of-intent"></span>
## Statement of intent

<span id="title"></span>
#### Title
Electronic Blue Card

<span id="stakeholders"></span>
#### Stakeholders

* Students
* Faculty
* Enrollment and Registration Services
* Divisions

<span id="project-stakeholders"></span>
#### Project Stakeholders

* Catherine Kwong
* Matt Groshong
* Virginia Bridwell
* Melissa Sitzenstock
* Steve Downing
* Expected scope/scale/size[edit]

<span id="scope"></span>
#### Size

Medium

<span id="scope"></span>
#### Scope

The Blue Card project will incorporate the Blue Card process into the existing entry code application. Entry codes will replace blue cards after open enrollment has closed.

<span id="current-status"></span>
## Current status
Currently, we have two different processes for online classes and campus classes.

For online classes, students fill out a web form to submit a request to instructor. A copy of the request is also sent to the Enrollment and Registrar Services (ERS). Instructor will email their decision and instruction to ERS to enroll the student manually. However, this process may take a few days before the student is finally enrolled into the class due to communications gap.

For campus classes, students contact the instructor in person to obtain a paper blue card, and then bring the card to the ERS front desk during office hours to register. Paper blue card have a security flaw as some instructors only sign their name on the card without filling out the student name and class information. It is also difficult to determine who signed the blue card from the signature. Because students come to the ERS desk, this results in long lines for registration. If the class only meets for one or two days, they may wait for another week to register in person at the ERS desk. If students got a blue card on Friday, they need to wait until Monday to go in person to register.

<span style="color: green">Some departments do (may?) not allow instructors to make the final decision on Blue Cards. In the past, I have had to get approval from my dept. chair.<span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)

<span id="requirements"></span>
## Requirements

<span id="audience"></span>
#### Audience

* Instructors
* Program Chair
* Program Manager

<span id="current-functions"></span>
#### Current Functions

1. Distribute entry codes during (open enrollment)
2. Email entry code to student directly during open enrollment
3. View issued entry codes
4. Search issued entry codes
5. Assign another entry code while on the ‘Issuing page”
6. Entry code SSRS report
7. CC: instructor on entry code email
8. Add additional text to entry code email

<span id="new-functions"></span>
#### New Functions

1. Distribute Blue Card entry codes (only when open enrollment is closed)
2. Email entry code to ENR and send communication to student (only when open enrollment is closed)
3. Manually setting to turn off/on open enrollment period (Admin)
4. Modify SSRS report to include blue card process info
5. Search feature may need to be enhanced
6. Permissions may need to be revisited

<span id="function-details"></span>
### Function Details

<span id="a-turn-onoff-open-enrollment"></span>
##### a) Turn ON/OFF open enrollment

1. Blue card entry codes are distributed after Open Enrollment has closed, because there is no good way to programmatically determine this time period as it can change from quarter to quarter a setting will need to be created in the tool so that an admin user can manually toggle the application once open enrollment has closed. During open enrollment the application will show the standard (current) entry code rational, once open enrollment has CLOSED the application will show the Blue Card entry code rational when instructors are distributing codes to students.

<span id="b-distribute-blue-card-entry-codes-open-enrollment-closed"></span>
##### b) Distribute Blue Card entry codes (OPEN ENROLLMENT CLOSED)

1. ENR will convert all classes to “permission only” in the HP (manual process)
2. ENR will generate entry codes for all courses in the HP (manual process)
3. ENR will change setting in the Entry Code application to indicate Open Enrollment is closed. (New Feature) <span style="color: red">Do we know who will need this level of access? What happens if they forget - are we going to get frantic support calls?</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)
<span style="color: blue">
This will likely be a few different employees in the ENR office. Could we design this feature in a way that it may reduce support. For example would it be better to have them set a date range for each quarter?</span> - <span style="color: red">Elasater</span> 08:59, 2 April 2013 (PDT)
1. Entry code application will pull down codes for all classes (may do this automatically with no change to code)
2. Instructor issues entry code when open enrollment closed:
   1. Instructor select course from list
   2. Instructor enters in the student’s SID or name
   3. Student information is pulled up
   4. Instructor verified information and issues code
   5. Instructor selects blue card rational (New Feature)
   6. Entry code notification is distributed according to workflow (New Notification Feature)

<span id="c-blue-card-entry-code-rational"></span>
#### c) Blue Card entry code rational

Once open enrollment is closed the workflow for entry codes changes and the office of ENR will need to manually register the student. Unless the student is only seeking permission to register late. - <span style="color : red">Do we need, or are we expected, to programmatically determine any of these situations?</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)

<span style="color: blue">Yes, you make a good point below with your example of a full class. If the class is full and open enrollment is closed they will need to also select to waive the class cap. Ideally we would catch this scenario and inform the issuer with a error message.</span> - <span style="color : red">Elasater</span> 09:04, 2 April 2013 (PDT)

1. Rational 1: Permission for late registration
   1. Notification & Entry code sent directly to student, the student can register themselves. - <span style="color : red">e.g. Do we need to confirm that the class isn't full?</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)
2. Rational 2: Waiving prerequisite requirement (late registration is assumed)
   1. Notification & entry code sent to ENR, ENR will manually register the student and send them notification
   2. Notification sent to student informing them that ENR will be responsible for registering the student and sending them confirmation the task has been complete by ENR staff.
3. Rational 3: Waiving Class Cap (late registration is assumed - <span style="color : green">I don't think so. An entry code is needed to register for a full class even before enrollment closes.</span> <span style="color : red">Note also: There is another cap beyond which the Division head's approval is required.</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth))

<span style="color : blue">I believe the difference is that once open enrollment is closed the student can no longer register themselves, like they can when enrollment is open. We will need to get further clarification on this question</span> - <span style="color : red">Elasater</span> 09:07, 2 April 2013 (PDT)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. Notification & entry code sent to ENR, ENR will manually register the student and send them notification
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Notification sent to student informing them that ENR will be responsible for registering the student and sending them confirmation the task has been complete by ENR staff.
4. Rational 4: Waiving Pre-req requirement & Class Cap
   1. Notification & entry code sent to ENR, ENR will manually register the student and send them notification
   2. Notification sent to student informing them that ENR will be responsible for registering the student and sending them confirmation the task has been complete by ENR staff.
5. Rational 5: Allow for time conflict
   1. Notification & entry code sent to ENR, ENR will manually register the student and send them notification
   2. Notification sent to student informing them that ENR will be responsible for registering the student and sending them confirmation the task has been complete by ENR staff.
<span style="color : blue">NOTE: The UI for issuing blue cards will need to be designed and the design should be reviewed and approved by ENR</span>

<span id="d-email-notification"></span>
##### d) Email Notification

1. Open Enrollment Closed (New Feature)
   1. When open enrollment is closed the only time the entry code is sent directly to the student is if they only need permission for late registration. If any other rational (blue card) is selected ENR will be required to register the student. In this case the entry code application will send ENR an email (included in the email are the entry code, student ID, and class/section) notifying them that they need to make a change to the student record, ENR will make change in HP and send follow up email to the student.
   2. A notification will be sent to the student explaining the process and what they can expect .
2. Open Enrollment
   1. During open enrollment the entry code is sent to the student directly and the student can register themselves. (No change to the existing behavior.

<span id="e-ssrs-reporting"></span>
##### e) SSRS Reporting

1. We may need to modify our existing report to indicate if the entry code was distributed during open enrollment or after.
2. New report for ENR – Report that ENR can run on a as needed basis once open enrollment is closed. This report will show a list of students who have been issued entry codes when open enrollment is closed, once the student is registered they will drop off the list as no more action is needed from ENR.

<span id="f-search-feature"></span>
##### f) Search Feature

1. Search feature should be improved if we have time. Some of the current issues are:
   1. Must type an exact word match (i.e. eng101, eng 101, eng 101)
   2. Currently users can only search by Student SID, Class, and issuer. - <span style="color : red">What would they like to be able to search by?</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)
<span style="color : blue">Just mentioning this as a check list item so we make sure to account for search as we make changes in case it needs to be modified to work with the new blue card feature. As of right now there has not been a request to modify/extend the search feature</span> - <span style="color : red">Elasater</span> 09:12, 2 April 2013 (PDT)
Do not indicate enrollment period in search results - I'm not sure what is meant by this. - Shawn
<span style="color : blue">Add a column to indicate if the entry code was issued as a entry code(Enrollment Open) or as a Blue Card (Enrollment Closed)</span> - <span style="red">Elasater</span> 09:12, 2 April 2013 (PDT)

<span id="g-permissions-improvements"></span>
##### g) Permissions Improvements

1. Our initial design of the entry code application made some assumptions about who would be issuing entry codes. Since the release we have found that our logic does not work for every division in every instance. We often have to give access individually, via a manual process that involves manually mapping a division/program to an individual. We may want to revisit permissions and make improvements to the existing logic. - <span style="color : red">Depending on how flexible this needs to be, this could potentially be the largest part of this project.</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)
<span style="red">I agree that this would be a huge undertaking, as of right now we do not have plans to do this. I wanted to make sure we at least documented the current issues</span> - <span style="color : red">Elasater</span> 09:12, 2 April 2013 (PDT)

<span id="h-revisit-logic-for-selecting-active-quarter"></span>
##### h) Revisit logic for selecting active quarter
The quarter is turned over automatically, we may need to revisit this logic to make sure it works with the new setting for Open/Closed enrollment.

<span id="roadmap"></span>
## Roadmap

<span id="open-questions"></span>
## Open Questions
* When open enrollment is closed is only the instructor allowed to distribute the code? Or will this be done my Admin managers and Program Chairs?
* Are there different departments workflows for issueing blue cards? Do insturctors always have permission or do they need to get aproval?
  * <span style="color : red">Will this always be one or the other (for all depts)? Or do we need to support the ability for each dept to specify?</span> - [Shawn](https://wikiwiki.bellevuecollege.edu/wiki/User:Ssouth)
* Is it better to send ENR a notification directly when action is needed on their part or would it be better to build a report that they can run and then take action?

<span id="references"></span>
## References

* Old documents (are these still relevant?)
  * [entry code flow1.pdf](https://wikiwiki.bellevuecollege.edu/wiki/File:Online_entry_code_flow1.pdf)
  * [registration flow1.pdf](https://wikiwiki.bellevuecollege.edu/wiki/File:Late_registration_flow1.pdf)

<span id="sprint-retro"></span>
## Sprint Retro

<span id="what-went-wrong"></span>
##### What went wrong?

* Team not involved in the design process
  * What is the best way to engage the designer in the process and what is their role
* Review the existing frameworks before making design changes
* Designers authority over the UI not clear
  * Role definitions unclear
* What do we mean by Design
  * HTML code
  * Mock ups
  * Front-End Implementation
* Scrum master needs to clearly communicate process changes to the team
* Ran into a few communication breakdowns
* Assumptions made by team
* Remember to add estimates
* Define sprint goals more clearly
* Improve fogbugz filters for sharing information
* If tasks are complete work on documentation
* Feature
* Project documentation
* What went right?[edit]
* Sprint went well - stayed on time
* PO interaction went well
* Good project to learn ASP.net
* "Grab Me" worked well
* Code Review was great.
* Process changes[edit]
* Scrum Master should send a reminder out ot add times to work items
* Cross training on development process
* Specifically around releasing applications to test or production
* More Code reviews
* Add documentation tasks to sprints
* Add sprint retro notes directly to project and scrum rules pages.
