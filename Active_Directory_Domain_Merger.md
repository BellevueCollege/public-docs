# Active Directory Domain Merger<span id="active-directory-domain-merger"></span>
---

##### Contents<span id="contents"></span> 

<!-- TOC -->

- [Active Directory Domain Merger>](#active-directory-domain-merger)
- [Tasks](#tasks)
  - [Pre-Merge<span id="pre-merge"></span>](#pre-mergespan-idpre-mergespan)
  - [During 8/24-8/26 Merge](#during-824-826-merge)
  - [Post-Merge ASAP](#post-merge-asap)
  - [Post-Merge](#post-merge)
- [Questions](#questions)
- [System Documentation](#system-documentation)
  - [Seattle & Star](#seattle--star)
  - [Application Pools](#application-pools)
  - [Anonymous Access](#anonymous-access)
- [MyBC (SharePoint 2007)](#mybc-sharepoint-2007)
  - [Audiences](#audiences)
    - [Admin Exempt Staff](#admin-exempt-staff)
    - [All Employees](#all-employees)
    - [All faculty](#all-faculty)
    - [All Students](#all-students)
    - [Classified Staff](#classified-staff)
    - [Deans](#deans)
    - [Degree Audit Advisors](#degree-audit-advisors)
    - [Ed Services Cabinet](#ed-services-cabinet)
    - [Hourly Employees](#hourly-employees)
    - [President's Staff](#presidents-staff)
    - [President's Staff Assistants](#presidents-staff-assistants)
    - [Property Team](#property-team)
    - [Staff with faculty view](#staff-with-faculty-view)
    - [Staff with student view](#staff-with-student-view)
    - [Student Employees](#student-employees)
    - [Student Test Accounts](#student-test-accounts)
    - [Supervisors](#supervisors)

<!-- /TOC -->
<span id="tasks"></span>

## Tasks
#### Pre-Merge<span id="pre-merge"></span>
* <strike>Decide on OU structure changes to ‘campus’ domain (NSS - done)</strike>
* <strike>Create separate policy for lab computers to have a different rootuser10 password than admin computers (Rodger - done)</strike>
* <strike>Notify current student and employee users of forthcoming changes via email(Lori)</strike>
* <strike>Assign existing EmployeeID value to UserID field on remaining ‘student’ domain user accounts (Tim)</strike>
* <strike>Populate ‘campus’ domain employee user accounts with student SIDs in UserID field (Tim)</strike>
* <strike>Create new GPO for ‘campus’ domain student used computers to write ‘student’ locally to the ‘Computer Description’ field (will be used for WOL and other purposes) (Rick/Rodger)</strike>
* <strike>Move/recreate existing GPOs and groups originally on 'student' domain (Rodger/Tim)</strike>
* <strike>Recreate Outlook instructor student accounts on ‘campus’ domain (Wayne/Tim)</strike>
* <strike>Restrict VPN access to specific groups so students don't use VPN (Tim)</strike>
* <strike>Coordinate with Melissa S. on iModules email addresses (Rodger)</strike>
* Notify users who will have their username/account changed (Lori)
* Coordinate with Melissa S. on physical mailings (ex: 'welcome new student - go to SAM') (Lori)
* Migrate ‘student’ domain computers to ‘campus’ domain (including servers, if applicable) (NSS/CS)
* Prepare documentation on updating mobile devices with stored student domain info (CS)
* Update media carts and mobile classrooms and other student laptops (CS/Tim)

<span id="during-824-826-merge"></span>
#### During 8/24-8/26 Merge

* <strike>For employees who are also students, make their ‘student’ domain e-mail address a secondary SMTP address for their ‘employee’ account (Wayne/Tim)</strike>
* <strike>Move/Copy remaining student accounts to ‘campus’ domain (except where student is also an employee) (Tim)</strike>
* <strike>Delete ‘student’ domain user accounts that have duplicates on the ‘campus’ domain (NSS)</strike>
* Delete ‘student’ domain user accounts last used more than 5 quarters ago (approx. 50,000+) (Tim) - Pending

<span id="post-merge-asap"></span>
#### Post-Merge ASAP

* <strike>Update Canvas student import scripts - student email address (Lori/Eden)</strike>
* <strike>Update MyBC student audience groups to use ‘campus’ domain groups (Windle/Lori)</strike>
* <strike>Remove custom OWA message regarding how to log on (Wayne/Lori)</strike>
* <strike>Delete old portal groups from student and then create new portal groups on campus (Tim scheduled for morning of 8/27)</strike>
* <strike>Update Rave alerts import (Tim)</strike>
* <strike>Remove policy that adds numbers to the ends of email addresses (ex: new student marcella.taylor) (Tim/Rick)</strike>
* Migrate web apps still depending on ‘student’ domain resources (Windle, Eden) - Dev work mostly done. Needs testing and deployment to production to be complete. [Jonathan Windle]()
* Release production CAS [Does not query Student Domain] (Windle/DevCom) - Dev environment created for [Erik Steen]() to complete theme. CAS will then need testing before being released to production. [Jonathan Windle]() 
* Update user logon information where domain specific directions are posted (DevCom)

<span id="post-merge"></span>
#### Post-Merge

* Migrate web apps still depending on 'bcc_srv1' domain resources (Windle, Eden)
* Assist employees who use their ‘student’ domain accounts on employee computers in transferring their data to their employee profiles (primarily C200 users) (Jason)
* Configure fa.bellevuecollege.edu to use new production CAS service (DevCom)
* Remove ‘student’ domain user account information from MyBC (this will delete personal sites) (Windle)
* Update student Display Names be to first and last names and not be the username (Tim/Rick)
* Change all employee account ‘Full Name’ fields to be username and not display name (to prevent name collisions) (Tim/Rick)
* Move all pre-existing employees out of old OU structure (Gary/Rick)
* Delete ‘student’ domain user mailboxes (Wayne)
* Delete ‘BCC_SRV1’ domain after all is well (report exec, Seattle/Star, etc.) (NSS)
* Delete ‘student’ domain after all is well (NSS)
* Delete 'academic' domain (Tim)

<span id="questions"></span>
## Questions

* Should all students (alumni or never atteneded included) be issued an email account? (currently only 'active' students get email)
* Should triple star students be enforced to create their accounts as their name? (are there current ones?)
* What is the status of the application that will constantly update the AD mirroring HP information? Note: without this updating, separated employees who are also students will continue to be able to use their one account with all permissions previously held as an employee unless manual intervention is taken. (Russ/HR, DevCom)
* Who is responsible for reviewing new accounts in the 'NeedingReview' OU?

* <strike>Should student passwords be set to expire (historically they do not expire)? (new ones set to expire, not copied) + force pwd resetting users to have expiring passwords (Rick/Tim)</strike> - Yes and completed
* <strike>Should students be configured for Lync? (Rodger/Rick)</strike> - Yes, but not OCS
* <strike>What will the address of the new SAM/PAM/NetID be? (Rick/Windle/Lori)</strike> - https://bellevuecollege.edu/netid
* <strike>Should any ‘student’ domain groups and/or GPOs be moved to or recreated in the ‘campus’ domain? (Rodger/Tim)</strike> - Yes (now a task)
* <strike>Are there late ending classes (past the end of Summer Quarter) that use ‘student’ domain accounts (Nursing, North Campus)?</strike> - Yes, there are - ouch (Lori will communicate - Gary has list)
* <strike>Should all existing student account Display Names be updated to first and last names and not be the username any longer?</strike> - Yes, RB

<span id="system-documentation"></span>
## System Documentation
<span id="seattle--star"></span>
#### Seattle & Star
<span id="application-pools"></span>
#### Application Pools

The following are web applications that run under identities that still reside on the bcc.ctc.edu Active Directory domain. "Migrated" status should either be changed to "Yes" or "Deleted" when an application is no longer dependent on the bcc.ctc.edu domain. "Will it Break?" status may be changed to "Yes", "No", "Delete", or "Maybe" as applications are investigated.

|  **Application Pool** | **Identity** | **Description** | **Path** | **Will it break?** | **Migrated** |
| --------------------- | -------------------- | -------------------- | ---------------------------------------- | ------ | ------ |
| DefaultAppPool | BCC_SRV1\ASPNET | AC Administration Application | 	`<Application Center 2000 Administrative Site>` | Maybe | No |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<ASBCC Elections>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | bcceval | `<bcceval>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | bookstore | `<bookstore>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | DELETE - BugTracker | `<BugTracker>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ROOT | `<CallToParents>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<CertCreate>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | collegechannel | `<collegechannel>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Continuing Education>` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | CESiteUpdates | `<Continuing Education>/CESiteUpdates` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | CEUpdates | `<Continuing Education>/CEUpdates` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | test-j | `<Continuing Education>/test-j` | Deleted | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | CEUpdates | `<continuingeducation.bellevuecollege.edu>/CEUpdates` | Maybe | No |
| DefaultAppPool | BCC_SRV1\ASPNET | cps | `<cps>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | iquiz | `<cybercareers>/iquiz` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | BudgetAuthorityold | `<Default Web Site>/BudgetAuthorityold` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | careercenter | `<Default Web Site>/careercenter` | Maybe | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | careercenterqa | `<Default Web Site>/careercenterqa` | Maybe | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | cite | `<Default Web Site>/cite` | Maybe | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | clozetool | `<Default Web Site>/clozetool` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | httpsredirectdefaultapppool | `<Default Web Site>/clozetool` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | idev | `<Default Web Site>/idev` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | MagicPacketl | `<Default Web Site>/MagicPacket` | Delete |Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | mobile | `<Default Web Site>/httpsredirectdefaultapppool` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | clozetool | `<Default Web Site>/mobile` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Peptest | `<Default Web Site>/Peptest` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ps | `<Default Web Site>/ps` | Maybe | No |
| DefaultAppPool | BCC_SRV1\ASPNET | SAGEWS | `<Default Web Site>/sage/SAGEWS` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | sam_old | `<Default Web Site>/sam_old` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | SAMTool AuthLog | `<Default Web Site>/sam/AuthLog` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | sam2 | `<Default Web Site>/sam2` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | sam3 | `<Default Web Site>/sam3_old` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | schedule | `<Default Web Site>/scheduled` | Delete | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | search2003e | `<Default Web Site>/search2003` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ContEd | `<Default Web Site>/search2003/ContEd` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | StuPro | `<Default Web Site>/search2003/StuPro` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | thejibsheet | `<Default Web Site>/thejibsheet` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | atc1 | `<Default Web Site>/Tutoring/atc1t` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Virtual EMS | `<Default Web Site>/VirtualEMSt` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | MarketAnalysisTemp | `<Default Web Site>/wcit/Toolkit/MarketAnalysis` | Maybe | No |
| DefaultAppPool | BCC_SRV1\ASPNET | MarketAnalysis | `<Default Web Site>/wcit/Toolkit/MarketAnalysisolds` | Delete | Deleted  |
| DefaultAppPool | BCC_SRV1\ASPNET | ModuleWizard | `<Default Web Site>/wcit/Toolkit/ModuleWizard` | Maybe | No  |
| DefaultAppPool | BCC_SRV1\ASPNET | WCITModuleWizard | `<Default Web Site>/WCITModuleWizard` | Maybe | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | writinglab | `<Default Web Site>/writinglab` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Developer Support | `<Developer Support>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | directory | `<directory>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | distance-ed | `<distance-ed>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | cs110webcam | `<distance-ed>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | edlearn.org | `<distance-ed>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<ETT>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | facweb | `<facweb>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | DELETE - Potluckb | `<facweb>/jreynold/Potluck` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<gotobcc>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Intranet | `<Intranet>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<gotobcc>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | pr | `<Intranet>/curriculum/pr` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | frcsurvey | `<Intranet>/frc/frcsurvey` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ir | `<ir>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | MissingSIDRept | `<ir>/MissingSIDRept` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | PwdChangeRept | `<ir>/PwdChangeRept` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | isp | `<isp>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Lab Tracker | `<Lab Tracker>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | MainSite Test | `<MainSite Test>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | mediafest | `<mediafest>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<my.bellevuecollege.edu>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | VirtualEms | `<my.bellevuecollege.edu>/VirtualEms` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<mybcc>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<netechprep.org>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | nwcet | `<nwcet>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | NWCET-IQuiz | `<nwcet>/iquiz` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | test | `<nwcet>/programs/cyberCareers/students/test` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | iquiz | `<nwcet>/programs/cyberCareers/students/test/iquiz` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | PIT | `<Personnel Information Tool>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<sage>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | School Status | `<School Status>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | aspnet_client | `<School Status>/aspnet_client` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<techprepcc.org>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Work Redirect>` | Delete | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<www.techprepcc.org>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Admissions imodules redirect >` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<collegecreditcareersnetwork.* (Redirect)>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<continuingeducation.bellevuecollege.edu>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Default Web Site (Redirect)>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Web Site | `<Default Web Site>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Distance-ed bcclearn.com redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Distance-ed onlinebcc.com redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<ems.bellevuecollege.edu (Redirect)>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<erequester.bellevuecollege.edu>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ROOT | `<gaming.bcc.edu redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<in.bellevuecollege.edu>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | ROOT | `<KBCS-fm.org redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | ROOT | `<KBCS.fm www redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | KBCS.fm | `<KBCS.fm>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | underwriterlist | `<KBCS.fm>/underwriterlist` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<Lyrislist Join Redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<mybcc redirect>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<nwnews redirect>` | No | Deleted |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<pants.bellevuecollege.edu>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<roboto.bellevuecollege.edu>` | No | Yes |
| DefaultAppPool | BCC_SRV1\ASPNET | Default Application | `<VISTA REDIRECT>` | No | Deleted |
| EMSAppPool | BCC_SRV1\ASPNET | Default Application | `<ems.bellevuecollege.edu>` | No | Yes |
| NET1.1 | BCC_SRV1\ASPNET | ett | `<Default Web Site>/ett` | Maybe | Deleted |
| NET1.1 | BCC_SRV1\ASPNET | pep | `<Default Web Site>/pep` | Deleted | Deleted |
| NET2.0 | BCC_SRV1\ASPNET | A1Transcript | `<Default Web Site>/A1Transcript` | Maybe | Deleted |
| NET2.0 | BCC_SRV1\ASPNET | Alerts | `<Default Web Site>/Alerts` | No | Yes |
| NET2.0 | BCC_SRV1\ASPNET | ASGElections | `<Default Web Site>/ASGElections` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | BudgetAuthority | `<Default Web Site>/BudgetAuthority` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | ClubProposals | `<Default Web Site>/ClubProposals` | Maybe | Deleted |
| NET2.0 | BCC_SRV1\ASPNET | coursehistory | `<Default Web Site>/coursehistory` | Maybe | Yes |
| NET2.0 | BCC_SRV1\ASPNET | coursehistoryqa | `<Default Web Site>/coursehistoryqa` | Maybe | Yes |
| NET2.0 | BCC_SRV1\ASPNET | eli | `<Default Web Site>/eli` | Maybe | Yes |
| NET2.0 | BCC_SRV1\ASPNET | frc | `<Default Web Site>/frc` | No | Yes |
| NET2.0 | BCC_SRV1\ASPNET | HTTPSredirect | `<Default Web Site>/HTTPSredirect` | No | No |
| NET2.0 | BCC_SRV1\ASPNET | Catalog | `<Default Web Site>/kbcs/Catalog` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | CatalogSearch | `<Default Web Site>/kbcs/CatalogSearch` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | ReportTesting | `<Default Web Site>/ReportTesting` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | requestcenter | `<Default Web Site>/requestcenter` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | search | `<Default Web Site>/search` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | stsc | `<Default Web Site>/stsc` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | surveys | `<Default Web Site>/surveys` | No | Yes |
| NET2.0 | BCC_SRV1\ASPNET | transcriptlookup | `<Default Web Site>/transcriptlookup` | Maybe | No |
| NET2.0 | BCC_SRV1\ASPNET | atc | `<Default Web Site>/Tutoring/atc` | No | Yes |
| School Status Admin | BCC_SRV1\SchoolStatus | School Status Admin | `<School Status>/Admin` | Delete | Deleted |

<span id="anonymous-access"></span>
#### Anonymous Access
Content that does not require authentication is considered to be anonymously accessed by IIS. Currently IIS is configured to identify anonymous users as '''BCC_SRV1\IUSR_Generic'''. This account relies on the depreciated bcc.ctc.edu Active Directory domain, and needs to be updated to a new account that is attached to the bellevuecollege.edu domain.

<span id="mybc-sharepoint-2007"></span>
### MyBC (SharePoint 2007)

<span id="audiences"></span>
#### Audiences

<span id="admin-exempt-staff"></span>
#### Admin Exempt Staff

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| :------------------- | :----------------: | :------------------------------: | :----------: |
| User | Member Of | Exempt Employees | No |
| Account name | = | campus\t-staff3 | Maybe |
| Account name | = | campus\rachel.solemsaas | Maybe |
| Account name | = | campus\gbennett | Maybe |
| Account name | = | campus\gjackson | Maybe |

<span id="all-employees"></span> 
#### All Employees
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | All Employees | No |
| Account name | = | campus\t-staff3 | Maybe |
| Account name | = | campus\t-ltiede | Maybe |
| User | Member Of | Non-existent Membership group (CN=All Employees,OU=Automated Groups,OU=All Groups,DC=bellevuecollege,DC=edu)  | Maybe |
| Account name | = | campus\rachel.solemsaas | Maybe |
| User | Member Of | MyBCC Portal Admins | Maybe |
| User | Member Of | Classified | Maybe |
| User | Member Of | All Faculty | Maybe |
| Account name | = | campus\terry.hatcher | Maybe |
| Account name | = | campus\TiJones | Maybe |

<span id="all-faculty"></span>
#### All faculty

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Faculty-Full Time | Maybe |
| User | Member Of | Faculty-Full Time | Maybe |
| User | Member Of | All Faculty | No |
| User | Member Of | campus\hjackson  | Maybe |
| Account name | = | campus\mari.brunson | Maybe |
| Account name | = | campus\ann.taylor | Maybe |
| Account name | = | campus\bradetta.vines | Maybe |
| Account name | = | campus\tatiana.mihaylova | Maybe |
| Account name | = | campus\lynne.walker | Maybe |
| Account name | = | campus\bhealy | Maybe |
| Account name | = |campus\sumita.dhingra | Maybe |
| Account name | = | campus\juan.rodriguez | Maybe |
| Account name | = | campus\dawn.kinder | Maybe |
| Account name | = | campus\badams | Maybe |

<span id="all-students"></span>
#### All Students
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | MOSS Test Accounts | Maybe |
| User | Member Of | CollegeStudents | No |
| Account name | = | campus\d-ltiede | Maybe |
| Account name | = | student\pjconcannon | Maybe |

<span id="classified-staff"></span>
#### Classified Staff
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Non-existent Membership group (cn=classified employees,ou=automatedgroups,ou=allgroups,dc=bellevuecollege,dc=edu)
 | Maybe |
| User | Member Of | Classified | No |
| Account name | = | campus\rachelle.federighi | Maybe |

<span id="deans"></span>
#### Deans
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Instructional Deans | No |
| Account name | = | campus\d-ltiede | Maybe |
| Account name | = | campus\t-staff2 | Maybe |
| Account name | = | campus\eerickso | Maybe |
| Account name | = | campus\kevin.mccarthy | Maybe |
| Account name | = | campus\lsage | Maybe |
| Account name | = | campus\mslowins | Maybe |
| Account name | = | campus\pboyum | Maybe |
| Account name | = | campus\vbridwel | Maybe |
| Account name | = | campus\jorja.gunderson | Maybe |
| Account name | = | campus\leslie.newquist | Maybe |
| Account name | = | campus\gschmidt | Maybe |

<span id="degree-audit-advisors"></span>
#### Degree Audit Advisors

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | DegreeAuditAdvisor | No |

<span id="ed-services-cabinet"></span>
#### Ed Services Cabinet
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Educational Services Cabinet | No |

<span id="hourly-employees"></span> 
#### Hourly Employees
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Hourly Employees | No |

===== Online Students =====
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | OnlineStudents | No |

<span id="presidents-staff"></span>
#### President's Staff

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Non-existent Membership group (cn=president's staff,ou=general distribution - security groups,ou=allgroups,dc=bellevuecollege,dc=edu) | No |

<span id="presidents-staff-assistants"></span>
#### President's Staff Assistants 
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Non-existent Membership group (cn=president's staff assistants,ou=general distribution - security groups,ou=allgroups,dc=bellevuecollege,dc=edu) | Maybe |

<span id="property-team"></span>
#### Property Team

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| Account name | = | campus\khutchin | Maybe |
| Account name | = | campus\bfloten | Maybe |
| Account name | = | campus\ltaylor | Maybe |
| Account name | = | campus\kpaustai | Maybe |
| Account name | = | campus\rachel.solemsaas | Maybe |
| Account name | = | campus\larry.price | Maybe |
| Account name | = | campus\jennifer.strother | Maybe |
| Account name | = | campus\rhay | Maybe |
| Account name | = | campus\d.johnson | Maybe |
| Account name | = | campus\maribeth.thomas | Maybe |

<span id="staff-with-faculty-view"></span>
#### Staff with faculty view
Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Non-existent Membership group (cn=employees w/facultyaudience access,ou=portal audience groups,ou=automated groups,ou=all groups,dc=bellevuecollege,dc=edu) | Maybe |

<span id="staff-with-student-view"></span>
#### Staff with student view

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Non-existent Membership group (cn=employees w/studentaudience access,ou=portal audience groups,ou=automated groups,ou=all groups,dc=bellevuecollege,dc=edu) | Maybe |

<span id="student-employees"></span>
#### Student Employees

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| User | Member Of | Student Employees | No |

<span id="student-test-accounts"></span>
#### Student Test Accounts

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |
| Account name | = | student\t-stu1 | Maybe |
| Account name | = | student\t-stu2 | Maybe |
| Account name | = | student\t-stu3 | Maybe |

<span id="supervisors"></span>
#### Supervisors

Are we using this audience?

Do we need to keep this audience?

Can we delete this audience?

| **Operand** | **Operator** | **Value** | **Delete it?** |
| ------------------ | :------------------: | :--------------------------------: | :------------------: |