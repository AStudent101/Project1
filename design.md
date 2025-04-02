# Design
Jai-Paul Sooriya (Student)
Anas Abdulkadir (Student)

home page:


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
    <a href="Find your roommate.html" class="nav-btn">Find Your Roommate</a>
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

</body>
</html>
<title>Student Accommodation</title>

<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v3.1.2/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v3.1.2/mapbox-gl.js"></script>
<style>
  #map { position: absolute; top: 1; height: 60%; width: 60%; }
</style>

<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"/>
<link rel="preconnect" href="https://fonts.gstatic.com"> 
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@600&family=Roboto:wght@500&display=swap">
<script src="script.js"> // mapping functions </script>
<script>
  const MY_TOKEN = "pk.eyJ1Ijoic3RldmViYXR0bGUiLCJhIjoiY2xzcWQxZzBiMHExZTJxbmpnN2hqbHMwZyJ9.hIauJCmUD0AzB4Uwru49QQ";

  // see: https://docs.mapbox.com/mapbox-gl-js/example/geojson-polygon/

  function addGeoJSON(json) {
    let features = json.features;
    for (i=0; i<features.length; i++) {
      let p = features[i].properties;

      // Add GeoJSON data source.
      map.addSource("data-"+p.OBJECTID, { 
        type: 'geojson', 
        data: features[i]
      });

      // Add polygon fill
      map.addLayer({
        'id': "fill-"+p.OBJECTID,
        'type': 'fill',
        'source': "data-"+p.OBJECTID, // reference the data source
        'layout': {},
        // blue fill, 50% opacity
        'paint': { 'fill-color': '#0080ff', 'fill-opacity': 0.5 }
      });

      // Add polygon outline
      map.addLayer({
        'id': "line-"+p.OBJECTID,
        'type': 'line',
        'source': "data-"+p.OBJECTID,
        'layout': {},
        'paint': { 'line-color': '#000', 'line-width': 1 }
      });
    }
  }

  function query() {
    let url="https://maps2.bristol.gov.uk/server2/rest/services/ext/datagov/FeatureServer/195/query?outFields=*&where=1%3D1&f=geojson";
    fetch(url, { method: 'GET', headers: { 'Accept': 'application/json' }})
    .then (response => response.json())
    .then(addGeoJSON);
  }
</script>
</head>  
<body>
<div class="grid-container">
  <header>
    <span class="heading"><a href="https://opendata.bristol.gov.uk/datasets/bf5887008d63414f9532f750927945f7_0/explore?showTable=true">Student Accommodation</a></span>
  </header>
  <nav class="w3-container w3-margin">
    <button onclick="getLocation('ward.html')" class="w3-button w3-block w3-blue w3-margin-top">Find on Map</button>
  </nav>
  <main>
    <div id="map"></div>
  </main>
</div>
<script>
  // get query string parameters lat, lon
  // var urlParams = new URLSearchParams(location.search);
  // var lat = urlParams.get('lat');
  // var lon = urlParams.get('lon');
  var lat = 51.454514;
  var lon = -2.587910

  mapboxgl.accessToken = MY_TOKEN;
  var map = new mapboxgl.Map({
      container: 'map', // container ID
      center: [lon, lat], // longitude, latitude
      zoom: 10 // zoom level
  });

  map.on('load', () => { query(map); });
</script>
</body>
</html>



find your roommate:

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Roommate Matching</title>
<style>
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
        text-align: center;
    }
    .container {
        max-width: 800px;
        margin: 20px auto;
        background: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    .profiles-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        padding: 10px;
    }
    .profile {
        background: #0077b6;
        color: white;
        padding: 10px;
        border-radius: 5px;
        margin: 10px;
        min-width: 250px;
    }
    .filter {
        margin-bottom: 20px;
    }
</style>
</head>
<body>

<nav>
    <h2>Roommate Matching</h2>
</nav>

<div class="container">
    <h2>Find a Roommate</h2>
    <div class="filter">
        <label for="gender">Gender:</label>
        <select id="gender">
            <option value="all">All</option>
            <option value="male">Male</option>
            <option value="female">Female</option>
            <option value="non-binary">Non-binary</option>
        </select>
        
        <label for="pets">Pets:</label>
        <select id="pets">
            <option value="all">All</option>
            <option value="yes">Yes</option>
            <option value="no">No</option>
        </select>
        
        <label for="noise">Noise Level:</label>
        <select id="noise">
            <option value="all">All</option>
            <option value="quiet">Quiet</option>
            <option value="moderate">Moderate</option>
            <option value="lively">Lively</option>
        </select>
        
        <button onclick="filterProfiles()">Apply Filter</button>
    </div>
</div>

<div id="profiles-container" class="profiles-container">
</div>

<script>
const profiles = [
    { name: "Alice", budget: 500, gender: "female", studyField: "Engineering", pets: "yes", noiseLevel: "quiet" },
    { name: "Bob", budget: 600, gender: "male", studyField: "Business", pets: "no", noiseLevel: "moderate" },
    { name: "Charlie", budget: 450, gender: "non-binary", studyField: "Art", pets: "yes", noiseLevel: "lively" },
    { name: "David", budget: 550, gender: "male", studyField: "Medicine", pets: "no", noiseLevel: "quiet" },
    { name: "Emma", budget: 700, gender: "female", studyField: "Law", pets: "yes", noiseLevel: "moderate" },
    { name: "Frank", budget: 500, gender: "male", studyField: "Computer Science", pets: "no", noiseLevel: "lively" },
    { name: "Grace", budget: 400, gender: "female", studyField: "Psychology", pets: "yes", noiseLevel: "quiet" },
    { name: "Henry", budget: 650, gender: "male", studyField: "Engineering", pets: "no", noiseLevel: "moderate" },
    { name: "Isla", budget: 600, gender: "female", studyField: "Marketing", pets: "yes", noiseLevel: "lively" },
    { name: "Jack", budget: 550, gender: "male", studyField: "Finance", pets: "no", noiseLevel: "quiet" }
];

function displayProfiles(filteredProfiles = profiles) {
    const container = document.getElementById('profiles-container');
    container.innerHTML = '';
    
    filteredProfiles.forEach(profile => {
        const profileDiv = document.createElement('div');
        profileDiv.className = 'profile';
        profileDiv.innerHTML = `
            <p><strong>Name:</strong> ${profile.name}</p>
            <p><strong>Budget:</strong> $${profile.budget}</p>
            <p><strong>Gender:</strong> ${profile.gender}</p>
            <p><strong>Study Field:</strong> ${profile.studyField}</p>
            <p><strong>Pets:</strong> ${profile.pets}</p>
            <p><strong>Noise Level:</strong> ${profile.noiseLevel}</p>
        `;
        container.appendChild(profileDiv);
    });
}

displayProfiles();

function filterProfiles() {
    const gender = document.getElementById('gender').value;
    const pets = document.getElementById('pets').value;
    const noise = document.getElementById('noise').value;
    
    const filtered = profiles.filter(profile => 
        (gender === "all" || profile.gender === gender) &&
        (pets === "all" || profile.pets === pets) &&
        (noise === "all" || profile.noiseLevel === noise)
    );
    
    displayProfiles(filtered);
}
</script>
</body>
</html>




log in page :







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


profile page 






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
    <a href="Find your roommate.html" class="nav-btn">Find Your Roommate</a>
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

    <!-- Navigation Bar -->
<nav class="nav-container">
<a href="Find your roommate.html" class="nav-btn">Find Your Roommate</a>   
 <nav
</div>

</body>
</html>




## User Interface design
TODO: Specify and develop a user interface mockup using a wireframe.

![![Wireframe](image.png)]
