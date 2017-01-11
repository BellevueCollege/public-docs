# ODS Known Issues
---

## Paycheck information ETL fails

Dima's explanation:

HR puts in a new employee record (EMP_M) which then gets into ODS. Then for some reason they put in another employee record with the same SSN but which generates a new SID number. And then they delete the first one they created. In ODS I never delete any employee records for archiving purposes, but rather just set those that are invalid for some reason to “S” (Separated) employee status. As a result of what I described I end up with two “A” (Active) employees in ODS with the same SSN but different SIDs. And because the procedure copying paycheck information into ODS goes off of SSN and “Active” employee status it gets confused. I basically have to go into the ODS and for one of those duplicate employee records set employee status to “S”(Separated).

This happens pretty consistently (once every couple of months or so) and so far I haven’t thought of a way to automatically take care of this. My suspicion is though that this will need to be addressed at the HR level somehow. Maybe tweak how they put in employees into the HP.