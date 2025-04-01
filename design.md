# Design
Jai-Paul Sooriya (Student)
Anas Abdulkadir (Student)

HOME PAGE:

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourChoiceAccom - Home</title>
<style>
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
    }
    /* Header */
    .header {
        background-color: #0077b6;
        color: white;
        text-align: center;
        padding: 20px;
        font-size: 2em;
        font-weight: bold;
    }
    /* Navigation */
    .nav-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #005f87;
        padding: 15px 20px;
    }
    .nav-btn {
        color: white;
        text-decoration: none;
        padding: 10px 15px;
        border-radius: 5px;
        font-size: 1.2em;
    }
    .nav-btn:hover {
        background-color: #004466;
    }
    /* Banner */
    .banner {
        text-align: center;
        padding: 50px;
        background-color: #0077b6;
        color: white;
        font-size: 1.5em;
    }
    .banner img {
        max-width: 100%;
        height: auto;
        border-radius: 10px;
    }
    /* Content */
    .container {
        max-width: 800px;
        margin: 20px auto;
        background: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        text-align: center;
    }
    .features {
        display: flex;
        justify-content: space-around;
        margin-top: 20px;
    }
    .feature {
        background: #0077b6;
        color: white;
        padding: 20px;
        border-radius: 10px;
        flex: 1;
        margin: 10px;
    }
</style>
</head>
<body>

<div class="header">YourChoiceAccom - Student Housing</div>

<!-- Navigation Bar -->
<nav class="nav-container">
    <a href="home page.html" class="nav-btn">Home</a>
    <a href="profile page.html" class="nav-btn">Profile</a>
    <a href="login.html" class="nav-btn">Log In</a>
</nav>

<!-- Banner Section -->
<div class="banner">
    <h1>Find Your Perfect Student Home</h1>
</div>

<!-- Main Content -->
<div class="container">
    <h2>Why Choose Us?</h2>
    <p>We offer a variety of student accommodations tailored to your needs. Whether you prefer a shared house, a studio apartment, or a quiet place to study, we have options for you!</p>
    <div class="features">
        <div class="feature">Affordable Pricing</div>
        <div class="feature">Prime Locations</div>
        <div class="feature">Student-Friendly Environment</div>
    </div>
</div>

</body>
</html>

LOGIN PAGE:

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourChoiceAccom - Login / Sign Up</title>
<style>
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 100vh;
    }
    .header {
        background-color: #0077b6;
        color: white;
        text-align: center;
        padding: 20px;
        font-size: 2em;
        font-weight: bold;
        width: 100%;
    }
    .container {
        background: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        width: 300px;
        text-align: center;
    }
    .tabs {
        display: flex;
        justify-content: space-between;
        margin-bottom: 10px;
    }
    .tab {
        flex: 1;
        padding: 10px;
        cursor: pointer;
        background: #0077b6;
        color: white;
        border-radius: 5px;
    }
    .tab.active {
        background: #005f87;
    }
    input {
        width: 100%;
        margin: 10px 0;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    button {
        width: 100%;
        padding: 10px;
        background-color: #0077b6;
        color: white;
        border: none;
        border-radius: 5px;
    }
    button:hover {
        background-color: #005f87;
    }
</style>
</head>
<body>

<div class="header">YourChoiceAccom - Student Housing</div>

<div class="container">
    <div class="tabs">
        <div class="tab active" onclick="showForm('login')">Log In</div>
        <div class="tab" onclick="showForm('signup')">Sign Up</div>
    </div>

    <form id="login-form">
        <input type="email" placeholder="Email" required>
        <input type="password" placeholder="Password" required>
        <button type="submit">Log In</button>
    </form>

    <form id="signup-form" style="display: none;">
        <input type="text" placeholder="Full Name" required>
        <input type="email" placeholder="Email" required>
        <input type="password" placeholder="Password" required>
        <input type="password" placeholder="Confirm Password" required>
        <button type="submit">Sign Up</button>
    </form>
</div>

<script>
    function showForm(formType) {
        document.getElementById('login-form').style.display = formType === 'login' ? 'block' : 'none';
        document.getElementById('signup-form').style.display = formType === 'signup' ? 'block' : 'none';
        
        document.querySelectorAll('.tab').forEach(tab => tab.classList.remove('active'));
        document.querySelector(`[onclick="showForm('${formType}')"]`).classList.add('active');
    }
</script>

</body>
</html>

PROFILE PAGE:

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourChoiceAccom - Student Housing</title>
<style>
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
    }
    /* Header */
    .header {
        background-color: #0077b6;
        color: white;
        text-align: center;
        padding: 20px;
        font-size: 2em;
        font-weight: bold;
    }
    /* Navigation */
    .nav-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #005f87;
        padding: 15px 20px;
    }
    .nav-btn {
        color: white;
        text-decoration: none;
        padding: 10px 15px;
        border-radius: 5px;
        font-size: 1.2em;
    }
    .nav-btn:hover {
        background-color: #004466;
    }
    /* Main Content */
    .container {
        max-width: 800px;
        margin: 20px auto;
        background: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    label, select, input, textarea {
        display: block;
        width: 100%;
        margin: 10px 0;
        padding: 10px;
        border-radius: 5px;
        border: 1px solid #ccc;
    }
    button {
        width: 100%;
        padding: 10px;
        background-color: #0077b6;
        color: white;
        border: none;
        border-radius: 5px;
        font-size: 1.2em;
    }
    button:hover {
        background-color: #005f87;
    }
</style>
</head>
<body>

<div class="header">YourChoiceAccom - Find Your Perfect Student Home</div>

<!-- Navigation Bar -->
<nav class="nav-container">
    <a href="home page.html" class="nav-btn">Home</a>
    <a href="profile page.html" class="nav-btn">Profile</a>
    <a href="login.html" class="nav-btn">Log In</a>
</nav>

<!-- Profile Section -->
<div class="container">
    <h2>Profile Page</h2>
    <label for="profilePic">Upload Profile Picture:</label>
    <input type="file" id="profilePic" name="profilePic" accept="image/*">

    <textarea rows="3" name="bio" placeholder="Write a short bio about yourself..."></textarea>
    
    <label for="housingType">Select Housing Type:</label>
    <select id="housingType">
        <option disabled selected>Please select housing type</option>
        <option value="shared_apartment">Shared Apartment</option>
        <option value="shared_house">Shared House</option>
    </select>

    <label for="roomType">Room Type:</label>
    <select id="roomType">
        <option value="single">Single Room</option>
        <option value="shared">Shared Room</option>
        <option value="studio">Studio Apartment</option>
    </select>

    <label for="budget">Budget (per month):</label>
    <input type="number" id="budget" name="budget" min="0" placeholder="Enter max budget">
    
    <label>Preferred Gender:</label>
    <select name="gender">
        <option value="any">Any</option>
        <option value="male">Male</option>
        <option value="female">Female</option>
        <option value="non-binary">Non-binary</option>
    </select>
    
    <label for="studyField">Field of Study:</label>
    <input type="text" id="studyField" name="studyField" placeholder="Enter study field">
    
    <label>Are you okay with pets?</label>
    <input type="radio" name="pets" value="yes"> Yes
    <input type="radio" name="pets" value="no"> No
    
    <label>Preferred Noise Level:</label>
    <select name="noiseLevel">
        <option value="quiet">Quiet</option>
        <option value="moderate">Moderate</option>
        <option value="lively">Lively</option>
    </select>
    
    <label>Preferred Amenities:</label>
    <label><input type="checkbox" name="amenities" value="wifi"> Wi-Fi</label>
    <label><input type="checkbox" name="amenities" value="laundry"> Laundry Facilities</label>
    <label><input type="checkbox" name="amenities" value="parking"> Parking</label>
    
    <button>Find Accommodation</button>
</div>

</body>
</html>

## User Interface design
TODO: Specify and develop a user interface mockup using a wireframe.

![![Wireframe](image.png)]
