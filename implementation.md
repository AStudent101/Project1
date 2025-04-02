# Implementation

## Introduction
TODO: Describe the system implemented (Describe the dataset. Are there any known issues? Describe any configuration data).

For our coursework, we built a student accommodation web app that helps students find not just a place to live, but also compatible roommates. Most accommodation websites only focus on location and room types, but they don’t consider personal preferences like lifestyle, habits, or study schedules. Our app solves this by letting students set their preferences and match with others who have similar needs.

We used the Bristol Open Data student accommodation dataset, which gives us basic info about housing options (like location, room types, and prices). However, this dataset doesn’t include anything about roommate matching, so we had to add our own system for that.

One of problems maybe that the dataset doesn’t update in real-time, so we can’t track live availability.
another problem is that our matching system relies on users honestly filling out their profiles, which might not always happen.
Since we where on a time crunch, we kept the design simple—no advanced features like live chat yet.

## Project Structure
TODO: Provide an outline of the project folder structure and the role of each file within it.
provide a table listing the number of jslint warnings/reports for each module.

yourchoiceaccom/  
│── **public/**             (Main web pages)  
│   ├── Main.html           (Homepage)  
│   ├── login.html          (Login/Signup)  
│   ├── profile.html        (User profile setup)  
│   ├── css/                (Styling files)  
│   └── images/             (Logos, icons, etc.)  
│  
│── **src/**                (JavaScript logic)  
│   ├── auth.js             (Handles logins & signups)  
│   ├── matching.js         (Roommate matching algorithm)  
│   ├── data.js             (Fetches Bristol Open Data)  
│   └── ui.js               (Makes the site interactive)  
│  
│── **tests/**              (Basic checks for functions)  

JSLint Warnings:
Since our code is structured, we didn’t have many errors, but JSLint flagged a few things like missing semicolons and unused variables.

File	Warnings	Errors

auth.js 	2	      0
matching.js	1	      0
data.js	    3	      0
ui.js	    0         0

## Software Architecture
TODO: Describe the major components of your architecture. Are any particular architectural styles being used?

Our app follows a client-server structure (even though we don’t have a full backend yet). Here’s how it works:
Frontend (What users see)
HTML/CSS for the layout
JavaScript for buttons, forms, and displaying data

Backend (Our simple logic)
auth.js → Checks login details (using localStorage for now)
matching.js → Compares user preferences to suggest roommates
data.js → Fetches accommodation data from Bristol Open Data

Data Layer
Bristol Open Data API (for accommodation listings)
User profiles stored in localStorage

Architecture Style
Layered (Frontend → Logic → Data)
Event-Driven (Buttons trigger functions, like searching for roommates)

![Insert your component Diagram here](images/component.png)

## Bristol Open Data API
TODO: Document each query to Bristol Open Data

We used two main API calls Get all Accommodations and Filter by Location/Room type
Get All Accommodation
async function getAccommodations() {
  const response = await fetch(
    "https://opendata.bristol.gov.uk/api/v2/catalog/datasets/student-accommodation/records"
  );
  const data = await response.json();
  return data.records; // Returns list of places to stay
}
Filter by location/room type
async function searchAccommodations(area, roomType) {
  const query = `area="${area}" AND type="${roomType}"`;
  const response = await fetch(
    `https://opendata.bristol.gov.uk/api/v2/catalog/datasets/student-accommodation/records?where=${query}`
  );
  return await response.json();
}

![UML Class diagrams representing JSON query results](images/class1.png)
TODO: Repeat as necessary

We didn’t use a proper UML tool, but our JSON response looks like:

Accommodation
Properties: name, address, type, price

Methods: getDistanceToUni(), checkAvailability()

# User guide
TODO: Explain how each use-case works by providing step-by-step screenshots for each use-case. This should be based on a tested scenario.

(We tested this ourselves—here’s how a student would use it.)

Sign Up / Log In

Go to /login.html
Click "Sign Up" if new
Enter email, name, password
Log in to access profile

Set Preferences

Go to /profile.html
Fill in:
Budget
Preferred gender of roommates
Noise tolerance (Quiet/Moderate/Lively)
Pet allergies?
Study habits (Night owl/Early bird)
Click Save

Find Roommates

The app compares your preferences with others
Shows a list of matches with % compatibility
Click a profile to see more details

Admin Features

(Not fully built yet, but planned:)
View all users
Delete fake accounts
Update accommodation listings