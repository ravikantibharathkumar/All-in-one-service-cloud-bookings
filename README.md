<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>All-in-One Service Booking</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f5f7fa;
      color: #333;
    }
    header {
      background: #007bff;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      display: flex;
      justify-content: center;
      background: #0056b3;
      padding: 10px;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover {
      text-decoration: underline;
    }
    .container {
      padding: 20px;
      max-width: 1000px;
      margin: auto;
    }
    .services {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .service-card {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
      transition: transform 0.3s;
    }
    .service-card:hover {
      transform: translateY(-5px);
    }
    .service-card h3 {
      margin-top: 0;
      color: #007bff;
    }
    .service-card button {
      background: #007bff;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    .service-card button:hover {
      background: #0056b3;
    }
    form {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    }
    form input, form select {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    form button {
      background: #28a745;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    form button:hover {
      background: #218838;
    }
    .booking-summary {
      background: #e9f7ef;
      padding: 15px;
      margin-top: 15px;
      border-radius: 5px;
    }
  </style>
</head>
<body>

<header>
  <h1>All-in-One Service Booking</h1>
  <p>Book any service online — Cloud, Electricity, Restaurant, Home, and more!</p>
</header>

<div class="container" id="homePage">
  <h2>Available Services</h2>
  <div class="services">
    <!-- Cloud Services -->
    <div class="service-card"><h3>Cloud Storage</h3><p>Secure storage for your files.</p><button onclick="goToBooking('Cloud Storage')">Book Now</button></div>
    <div class="service-card"><h3>Web Hosting</h3><p>Reliable hosting for websites and apps.</p><button onclick="goToBooking('Web Hosting')">Book Now</button></div>
    <div class="service-card"><h3>Virtual Servers</h3><p>High-performance virtual servers.</p><button onclick="goToBooking('Virtual Servers')">Book Now</button></div>
    <div class="service-card"><h3>Database Management</h3><p>Managed databases for apps.</p><button onclick="goToBooking('Database Management')">Book Now</button></div>
    <div class="service-card"><h3>AI Services</h3><p>AI model hosting and APIs.</p><button onclick="goToBooking('AI Services')">Book Now</button></div>
    <div class="service-card"><h3>Content Delivery</h3><p>Fast content delivery network (CDN).</p><button onclick="goToBooking('Content Delivery')">Book Now</button></div>

    <!-- Electricity & Utilities -->
    <div class="service-card"><h3>Electricity Connection</h3><p>Request new electricity connection or support.</p><button onclick="goToBooking('Electricity Connection')">Book Now</button></div>
    <div class="service-card"><h3>Plumbing Services</h3><p>Fix leaks, install water systems.</p><button onclick="goToBooking('Plumbing Services')">Book Now</button></div>
    <div class="service-card"><h3>Cleaning Services</h3><p>Home or office cleaning services.</p><button onclick="goToBooking('Cleaning Services')">Book Now</button></div>
    <div class="service-card"><h3>Internet Setup</h3><p>Get your internet connection installed.</p><button onclick="goToBooking('Internet Setup')">Book Now</button></div>

    <!-- Food & Restaurant -->
    <div class="service-card"><h3>Restaurant Booking</h3><p>Reserve a table at top restaurants.</p><button onclick="goToBooking('Restaurant Booking')">Book Now</button></div>
    <div class="service-card"><h3>Home Catering</h3><p>Get catering services for events.</p><button onclick="goToBooking('Home Catering')">Book Now</button></div>
    <div class="service-card"><h3>Food Delivery</h3><p>Order food from local restaurants.</p><button onclick="goToBooking('Food Delivery')">Book Now</button></div>

    <!-- IT & Security -->
    <div class="service-card"><h3>Cybersecurity</h3><p>Protect your systems from threats.</p><button onclick="goToBooking('Cybersecurity')">Book Now</button></div>
    <div class="service-card"><h3>Server Monitoring</h3><p>24/7 monitoring of servers and apps.</p><button onclick="goToBooking('Server Monitoring')">Book Now</button></div>

    <!-- Miscellaneous Services -->
    <div class="service-card"><h3>Domain Registration</h3><p>Register and manage your domains.</p><button onclick="goToBooking('Domain Registration')">Book Now</button></div>
    <div class="service-card"><h3>Email Hosting</h3><p>Professional email hosting services.</p><button onclick="goToBooking('Email Hosting')">Book Now</button></div>
    <div class="service-card"><h3>Backup & Recovery</h3><p>Secure backup and recovery solutions.</p><button onclick="goToBooking('Backup & Recovery')">Book Now</button></div>
    <div class="service-card"><h3>Event Management</h3><p>Plan your events with professionals.</p><button onclick="goToBooking('Event Management')">Book Now</button></div>
  </div>
</div>

<div class="container" id="bookingPage" style="display:none;">
  <h2>Book Your Service: <span id="selectedService"></span></h2>
  <form id="bookingForm" onsubmit="submitBooking(event)">
    <label for="name">Full Name</label>
    <input type="text" id="name" name="name" placeholder="Enter your full name" required>

    <label for="email">Email</label>
    <input type="email" id="email" name="email" placeholder="Enter your email" required>

    <label for="phone">Phone Number</label>
    <input type="text" id="phone" name="phone" placeholder="Enter your phone number" required>

    <label for="date">Preferred Date</label>
    <input type="date" id="date" name="date" required>

    <button type="submit">Confirm Booking</button>
  </form>

  <div class="booking-summary" id="summary" style="display:none;">
    <h3>Booking Summary</h3>
    <p id="summaryText"></p>
    <button onclick="goHome()">Back to Services</button>
  </div>
</div>

<script>
  let selectedService = "";

  function goToBooking(serviceName) {
    selectedService = serviceName;
    document.getElementById('homePage').style.display = 'none';
    document.getElementById('bookingPage').style.display = 'block';
    document.getElementById('selectedService').innerText = serviceName;
    document.getElementById('summary').style.display = 'none';
    document.getElementById('bookingForm').style.display = 'block';
  }

  function submitBooking(event) {
    event.preventDefault();
    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const phone = document.getElementById('phone').value;
    const date = document.getElementById('date').value;

    const summaryText = `
      <strong>Service:</strong> ${selectedService} <br>
      <strong>Name:</strong> ${name} <br>
      <strong>Email:</strong> ${email} <br>
      <strong>Phone:</strong> ${phone} <br>
      <strong>Date:</strong> ${date} <br>
      <strong>Status:</strong> Booking Confirmed!
    `;
    document.getElementById('summaryText').innerHTML = summaryText;
    document.getElementById('summary').style.display = 'block';
    document.getElementById('bookingForm').style.display = 'none';
  }

  function goHome() {
    document.getElementById('homePage').style.display = 'block';
    document.getElementById('bookingPage').style.display = 'none';
  }
</script>

</body>
</html># All-in-one-service-cloud-bookings
