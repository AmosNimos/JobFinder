Steps to complete the project:

1. **Choose a Programming Language and Framework:** Select a programming language and a framework that supports web development and mapping functionality. For example, you can use JavaScript with the Leaflet or Google Maps API for mapping.

2. **Set Up a Web Server:** You'll need a web server to host your application. You can use a local development server for testing, such as Python's built-in HTTP server (`python -m http.server`), or deploy your application to a web hosting service.

3. **Get the User's Location:** Use the Geolocation API to get the user's current location. This will allow you to center the map on the user's location and find jobs nearby.

4. **Display a Map:** Use a mapping library like Leaflet or the Google Maps JavaScript API to display a map on your webpage.

5. **Fetch Job Data:** You'll need a source of job data. This could be a database, an API, or a static dataset. For simplicity, you can start with a static dataset.

6. **Display Jobs on the Map:** For each job in your dataset, add a marker to the map at the job's location. You can customize the marker to display the job's name and other details.

7. **Provide Job Details:** When a user clicks on a marker, display a popup or a sidebar with more details about the job, such as salary per hour and salary per year.

8. **Calculate Distance:** Optionally, you can calculate the distance between the user's location and each job location to display it on the map or in a list.

Here's a basic example using Leaflet and a static dataset of jobs:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Jobs Near Me</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <style>
        #map { height: 400px; }
    </style>
</head>
<body>
    <div id="map"></div>

    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <script>
        var map = L.map('map').setView([51.505, -0.09], 13);

        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);

        var jobs = [
            { name: "Job 1", salaryPerHour: 20, salaryPerYear: 40000, location: [51.5, -0.1] },
            { name: "Job 2", salaryPerHour: 25, salaryPerYear: 50000, location: [51.51, -0.12] }
        ];

        jobs.forEach(function(job) {
            var marker = L.marker(job.location).addTo(map);
            var popupContent = "<b>" + job.name + "</b><br>Salary per hour: $" + job.salaryPerHour + "<br>Salary per year: $" + job.salaryPerYear;
            marker.bindPopup(popupContent);
        });
    </script>
</body>
</html>
```

This example creates a map with two markers representing jobs. Clicking on a marker displays a popup with the job's details.

I suggest scraping job postings from a reliable site like "Emplois Québec," "Jobboom," "Indeed," or another similar site. 

The scraped data can then be used to populate the job listings on the application. 

For hosting the site, I recommend using the LAMP stack (Linux, Apache, MySQL, PHP). This stack is well-suited for web applications and can support both mobile and desktop browsers, ensuring compatibility across different devices.
