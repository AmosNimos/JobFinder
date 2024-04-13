# The mission:
This open project aims to provide a non-monetized service to help job seekers find decent jobs at decent salaries. The focus is on simplicity and user-friendliness, with no intention of commercial gain. The goal is to address a need in the community and offer a solution that is accessible to all.

# Steps to complete the project:

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

For the application process, users should not apply through the site. Instead, the site should provide an email address or phone number for users to contact the employer directly. This approach avoids the need for subscriptions to apply for jobs. Additionally, any job postings that cannot provide a fixed salary should not be shown on the site.

1. **Simplified Job Categories:** Provide broad categories for job types such as physical work, desk jobs, social work, etc., to make it quick and easy for users to find relevant job listings.

2. **One-Click Job Search:** Allow users to find job listings with just a click, eliminating the need for complex search criteria or filters.

3. **No Unnecessary Requirements:** Remove requirements like study level or specific qualifications to make the application more accessible to job seekers looking for decent jobs at decent salaries.

4. **Quick Application Process:** Enable users to contact employers directly via email or phone, eliminating the need for subscriptions or lengthy application processes.

5. **Mobile-Friendly Design:** Ensure the website is optimized for mobile devices, allowing users to access job listings and apply for jobs on the go.

6. **Save and Share Jobs:** Allow users to save job listings they're interested in and share them easily with others, enhancing the usability of the application.

7. **User Feedback:** Provide a way for users to provide feedback on job listings or employers, helping improve the overall user experience.

8. **Local Job Market Insights:** Offer insights into the local job market trends, helping users make informed decisions about their job search.

By focusing on simplicity and user-friendliness, the job finder map application can make job finding quick and easy for users looking for decent jobs at decent salaries.


