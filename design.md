# Design
Jai-Paul Sooriya (Student)
Anas Abdulkadir (Student)

<!DOCTYPE html>
<html lang="en">
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourChoiceAccom Logo</title>
<style>
/* Logo Container */
.logo-container {
display: flex;
align-items: center;
justify-content: center;
background-color: #0077b6; /* Blue background */
color: white;
font-family: 'Poppins', sans-serif; /* Modern font */
font-size: 2.5em;
font-weight: bold;
padding: 20px;
border-radius: 10px;
width: fit-content;
margin: 50px auto;
box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2);
}

/* Icon Style */
.logo-icon {
width: 50px;
height: 50px;
margin-right: 15px;
}
</style>
</head>
<body>

<!-- Logo Section -->
<div class="logo-container">
<!-- Simple Home Icon -->
<svg class="logo-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white">
<path d="M12 3l10 9h-3v9h-6v-6h-2v6h-6v-9h-3l10-9z"/>
</svg>
YourChoiceAccom
</div>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Navigation</title>
<style>
/* Main Navigation Container */
.nav-container {
display: flex;
justify-content: space-between;
align-items: center;
background-color: #0077b6; /* Blue background */
padding: 15px 20px;
border-radius: 10px;
box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2);
}

/* Navigation Buttons */
.nav-btn {
font-family: 'Poppins', sans-serif;
font-size: 1.2em;
font-weight: 600;
color: white;
text-decoration: none;
padding: 8px 15px;
border-radius: 5px;
background-color: #005f87; /* Slightly darker blue */
}

/* Top Left - Home Button */
.home-btn {
font-size: 1em;
background-color: #004466; /* Darker shade */
}

/* Top Right - Log In/Sign Up */
.auth-buttons {
display: flex;
gap: 10px;
}

.auth-btn {
font-size: 0.9em;
padding: 5px 12px;
background-color: #00334d; /* Even darker shade */
}

/* Bottom Right - Home Button */
.bottom-home {
position: fixed;
bottom: 20px;
right: 20px;
}
</style>
</head>
<body>

<!-- Top Navigation -->
<nav class="nav-container">
<!-- Top Left: Home Button -->
<a href="#" class="nav-btn home-btn">Go Back to Home</a>

<!-- middle: Map -->
<a href="#" class="nav-btn auth-btn">Map</a>
<!-- Top Right: Log In / Sign Up -->
<div class="auth-buttons">
<a href="#" class="nav-btn auth-btn">Log In</a>
<a href="#" class="nav-btn auth-btn">Sign Up</a>
</div>
</nav>

<!-- Bottom Right: Home Button -->
<a href="#" class="nav-btn home-btn bottom-home">Go Back to Home</a>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Profile Page</title>
<style>
/* Subheading Styling */
.subheading {
text-align: center;
font-family: 'Poppins', sans-serif; /* Modern font */
font-size: 2em;
font-weight: 600;
color: #0077b6; /* Blue color */
margin-top: 20px;
padding: 10px;
border-bottom: 3px solid #0077b6; /* Underline effect */
display: inline-block;
}

/* Centering the subheading */
.subheading-container {
text-align: center;
margin-top: 30px;
}
</style>
</head>
<body>

<!-- Subheading Section -->
<div class="subheading-container">
<h2 class="subheading">Profile Page</h2>
</div>

</body>
</html>


<p></p>
<body>
<label for="profilePic">Upload Profile Picture:</label>
<input type="file" id="profilePic" name="profilePic" accept="image/*">
<p></p>
<textarea rows="3" cols="50" name="bio" placeholder="Write a short bio about yourself..."></textarea>
<p></p>
<select>
<option value="" disabled="disabled" selected="selected" >Please select housing type</option>
<option value="1-3 people">Shared appartments</option>
<option value="1-3 people">Shared housing</option>
</select>
<p></p>
<select multiple>
<option value="1-3 people">Shared appartments</option>
<option value="1-3 people">Shared housing</option>
</select>
<button>Use my location</button>
<input type="text" name="search" placeholder="Search box">
<p></p>
<textarea rows="6" cols="50" placeholder="Enter your feedback"></textarea>
</textarea>
<input type="search" name="search" placeholder="Search by keywords (e.g., 'near university')">
<p></p>
<input type="date" name="startDate">
<input type="time" name="reminder">
<p></p>
<label for="gender">Preferred Gender:</label>
<select id="gender" name="gender">
<option value="any">Any</option>
<option value="male">Male</option>
<option value="female">Female</option>
<option value="non-binary">Non-binary</option>
</select>
<p></p>
<label for="studyField">Field of Study:</label>
<input type="text" id="studyField" name="studyField" placeholder="Enter study field">
<p></p>
<label for="budget">Budget (per month):</label>
<input type="number" id="budget" name="budget" min="0" placeholder="Enter max budget">
<p></p>
<label for="roomType">Room Type:</label>
<select id="roomType" name="roomType">
<option value="single">Single Room</option>
<option value="shared">Shared Room</option>
<option value="studio">Studio Apartment</option>
</select>
<p></p>
<label><input type="checkbox" name="amenities" value="wifi"> Wi-Fi</label>
<label><input type="checkbox" name="amenities" value="laundry"> Laundry Facilities</label>
<label><input type="checkbox" name="amenities" value="parking"> Parking</label>
<p></p>
<label>Are you okay with pets?</label>
<input type="radio" name="pets" value="yes">Yes
<input type="radio" name="pets" value="no">No
<p></p>
<label>Preferred Noise Level:</label>
<select name="noiseLevel">
<option value="quiet">Quiet</option>
<option value="moderate">Moderate</option>
<option value="lively">Lively</option>
</select>
<p></p>
<label for="accommodationPics">Upload Photos of Accommodation:</label>
<input type="file" id="accommodationPics" name="accommodationPics" accept="image/*" multiple>
<input type="search" name="search" placeholder="Search by keywords (e.g., 'near university')">

<button>Connect via WhatsApp</button>
<button>Send a Message</button>
<p></p>
<input type="checkbox" name="check1" value="show">Show Map<br>
<input type="radio" name="location" value="location" checked>Use my location<br>
<input type="radio" name="location" value="default">Use central Bristol<br>

</body>
</html>

## User Interface design
TODO: Specify and develop a user interface mockup using a wireframe.

![![Wireframe](image.png)]
