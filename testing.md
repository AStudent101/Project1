# Testing

## Test Plan
TODO: Describe any manual and automated (unit) tests. Uniquely identify each test case. Include prerequisites and test data.

Test ID	Test Type	Description	Scenario	Expected Result
TF1	UAT	User Registration	User signs up with email & password	Account is created, stored in localStorage
TF2	UAT	Login Functionality	User logs in with correct details	Access granted to profile page
TF3	UAT	Profile Setup	User fills in preferences (noise, pets, budget)	Data saves correctly
TF4	UAT	Roommate Search	User clicks "Find Roommates"	List of matches appears
TF5	UAT	Send Request	User clicks "Connect" on a profile	Request is logged in system
TF6	UAT	Admin Access (Basic)	Admin views user list	All accounts are displayed

Test Runs
TODO: For each test described above, indicate the current status. 
Create a requirements traceability matrix to validate the completeness of the product.

use case ID            requirement ID       test case                   status 

UC1(register)           FR1                   TF1                         PASS

UC2(login)              FR8                   TF2                         PASS

UC3(set prefences)      FR2                   TF3                         PASS

UC4(serach roommates)   FR3,FR6               TF4                           PARTIAL

UC5(send request)       FR5                   TF5                          FAIL
   
UC6(admin)              FR9                   TF6                          FAIL

                        NFR1(usability)       ALL UI TESTS                  PASS

                        NFR2(perforance)      TU4 (DATA LOAD SPEED)         SLOW

                        NFR3 (SECURITY)       TF1, TF2                      PASS (BASIC)

                        NFR6(MAINTAINABILITY)  CODE DTRUCTURE REVIEW        PASS


TODO: Add rows for each test, current status is eg. pass/fail

What Works:
User registration & login
Saving profile preferences
Basic roommate matching
Fetches Bristol Open Data

What Needs Improvement:
Roommate requests don’t notify users yet
Admin panel isn’t fully functional
Matching algorithm is too simple (just compares arrays)
Data loading is slow (API response time)

What Failed:
Real-time notifications (not implemented)
Admin features (only basic layout exists)