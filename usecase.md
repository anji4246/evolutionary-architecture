## Example Use Case

| Topic | Description |
| - | - |
| Title | Register for courses |
| Description | Student accesses the system and views the courses currently available for him to register. Then he selects the courses and registers for them. |
| Primary Actor | Student |
| Preconditions | - Student is logged into system <br/> - Student has not previously enrolled or registered <br/> - Student cannot register within 5 days of course start date |
| Postconditions | Student is registered for courses | 
| Main Success Scenario | 1. Student selects "Register New Courses" from the menu. <br/> 2. System display list of courses available for registering. <br/> 3. Student selects one or more courses he wants to register for. <br/> 4. Student clicks "Submit" button. <br/> 5. System registers student for the selected courses and displays a confirmation message. | 
| Extensions | - (2a) No courses are available for this student <br/> 1. System displays error message saying no courses are available, and provides the reason and how to rectify if possible. <br/> 2. Student either backs out of this use case, or tries again after rectifying the cause. <br/> - (5a) Some courses could not be registered. <br/> 1. System displays message showing which courses were registered, and which courses were not registered along with a reason for each failure. <br/> - (5b) None of the courses could be registered. <br/> 1. System displays message saying none of the courses could be registered, along with a reason for each failure. |


## Template
```
Title: <perform action>
Description: <actor> accesses the system and wants to <perform action>
Primary Actor: <actor>
Secondary Actor: system
Preconditions:
- <actor> is logged into system
Postconditions:
- <actor> successfully completed <action>
Main success scenario:
- 1. The use case begins when <actor> <perform action>
- 2. <actor> <perform another action>
- 3. <system> respond with <response>
Extensions
- (1a) when <null condition>. 
    - <system> should respond with <message>.
    - <actor> backs out of this use case.
```

## Example Passwordless Login
```
Title: Passwordless login
Description: User ask system for a passwordless login token
Primary actor: User
Preconditions:
- User have a valid e-mail address
- User is not logged in
Postconditions:
- User is logged in the system
Main success scenario:
- 1. The use case begins when User is at the login page
- 2. The User enters the email address
     Business Rule: email must be valid
- 3. The User click submits
- 4. The system validate the email
- 5. The system sends an email containing a token that is valid for 5 minutes
- 6. The User clicks the link on the email
- 7. The system checks if the token is valid
     Business Rule: token has not expired
- 8. The system logs the user in
Extensions:
- 4a) The email is not valid
    - The system display an error message and ask the User to submit a new email
    - The User can opt to back out of this use case
- 5a) The User did not receive the email
    - The User back out of the use case and start from beginning
- 7b) The User clicks the link after token is expired.
    - The system display an error message saying that the token is expired
    - The User back out of this use case and start from the beginning
```   
# References

Use Cases:
- https://fullstackmark.com/post/11/better-software-design-with-clean-architecture
- http://www.eg.bucknell.edu/~cs475/F04-S05/useCases.pdf
- https://en.m.wikipedia.org/wiki/Use_case
- https://creately.com/blog/diagrams/use-case-diagram-guidelines/
- http://tynerblain.com/blog/2007/01/22/how-to-write-good-use-case-names/
- http://tynerblain.com/blog/2007/04/09/sample-use-case-example/
- http://www.agilemodeling.com/artifacts/systemUseCase.htm#Figure1
- ftp://ftp.software.ibm.com/software/rational/web/whitepapers/RAW14023-USEN-00.pdf
- https://www.ibm.com/developerworks/rational/library/content/legacy/parttwo/1000/0669/0669_Rosenberg_Ch03.pdf
- https://www.ibm.com/developerworks/rational/library/content/RationalEdge/may02/m_chapter4_jr.pdf
- https://www.ibm.com/developerworks/rational/library/content/legacy/parttwo/1000/0670/0670_Schneider_Ch07.pdf
- https://www.ibm.com/support/knowledgecenter/en/SSWSR9_11.0.0/com.ibm.pim.dev.doc/pim_ref_usecasetemp.html

UML 2.0
- http://agilemodeling.com/style/useCaseDiagram.htm