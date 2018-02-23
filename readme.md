# OAS Partners Service

**Owner** : Oas Platform Squad

**Getting Started**
1. Clone the repository using your method of choice and the HTTPS link:
    https://hgtfs15.healthgrades.com/tfs/HealthGrades%20Portfolio/Source-Services/_git/oas-partners-service.     
2. Checkout the 'develop' branch. 
3. Open the solution file using Visual Studio 2015 or 2017.
4. Build the solution and then use this library as a Nuget packages into the Healthgrades.Oas.Services.Oas project.
5. Tests are run using MS-Test. After a successful build of the project you should be able to run all the unit tests using the test explorer in Visual Studio. 
6. [Here](http://wiki.healthgrades.com/devstandards/OAS/200%20Framework) is the complete information and steps to build the Nuget package then publish to local then how to use in another solution for ex: Healthgrades.Oas.WebApis.Oas.
	
 **Packages are Used in**:
 - All partner service packages are used in these solution
	 - Healthgrades.Oas.WebApis.Oas.sln
	 - Healthgrades.Oas.AppointmentManagement.Processing.sln

**Technical Details**:
C# Class Libraries : Target Framework 4.6.1

### Open and Build Solution
Open OnlineAppointments.sln file using Visual Studio 2015
Build the Solution
Oas.Api.External is the startup project and the web project in the solution

```
Solution 'OnlineAppointments' (33 projects)
+-- Tests
+-- Oas
+-- Oas.Api.External
+-- Oas.Epic
+-- Oas.Common
+-- Oas.DAL.Interfaces
+-- Oas.DAL.SQL
+-- Oas.Entity
+-- Oas.Service
+-- Oas.Service.Interfaces
```
----------

### Useful information to run locally

- To run locally use this Global CID : **8A81A973-5F0B-4E99-B7AA-6AE6FD582972**
	
----------

### Main Endpoints in Oas.Api.External

- ProvidersController.cs :
	 - /providers 
		 - Get all available provider from our system mapped based on the CID.
	- /providers/{providerid} : 
		- Returns Provider Details for the given providerId.
	 - /providers/{providerid}/reasons :
		 - Returns Appointment Reasons for the given providerid 
		 - Example: providers/{providerId}/reasons?officeCode={officeCode}
- TimeslotController.cs :  
	- /providers/{providerid}/timeslots :
		-  Returns Appointment Timeslots for the given Providerid 
		-	Example: providers/{providerId}/timeslots?officecode={officeCode}&startdate={startDate}&numberofdays={numberOfDays}&reasonid={reasonId}

- AppointmentsController.cs:
	- Get :- /providers/{providerid}/appointments/{appointmentid}
		-  Returns appointment details for the existing appointmentid provided.
	- Post :-  /providers/{providerid}/appointments
		-  Books a new appointment based on Appointment details and Patient details provided.
	- Put :- /providers/{providerid}/appointments/{appointmentid}
		- Reschedules an existing appointment to a new time based on appointment timeslot provided.
	- Delete :- /providers/{providerid}/appointments/{appointmentid}  
		- Cancels an existing appointment for the existing appointmentid provided.   
 
----------

### Unit Tests
OnlineAppointmentsuses
- MSTest framework for Unit Tests, and 
- MOQ framework for mocking data.
 
Main tests for controllers and services reside in
- Oas.Api.External.Tests project and
-  Oas.Epic.Testproject

To run tests:
Open "Test Explorer" window from Test->Windows->Test Explorer
Click on "Run All" or you can run a specific test listed under each Category of tests.

----------

### Partners and Example Pwids in Test
```
Partners and Example Pwids in Test
+-- MISSBPOAS
¦   +-- GHGWN   
+-- ATH
¦   +-- xmq8p
¦   +-- q3snq
¦   +-- whcbd
+-- OCH
¦   +-- 2cjgy
+-- LehighOAS
¦   +-- ymjt5
```

----------

### Questions : 
**Email** : squad_oasisoasplatform@healthgrades.com
**Slack**: oasis-oas-platform 

----------