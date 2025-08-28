<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>DonorDrop - Blood Donation & Arrangements</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #d32f2f;
      --primary-dark: #b71c1c;
      --primary-light: #ff6659;
      --secondary: #f8f5f5;
      --accent: #ffcccb;
      --text: #333;
      --text-light: #777;
      --white: #ffffff;
      --shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    /* Enable smooth scrolling for the entire page */
    html {
      scroll-behavior: smooth;
    }
    
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: var(--secondary);
      color: var(--text);
      line-height: 1.6;
    }
    
    /* Header Styles */
    .main-header {
      background: var(--primary);
      color: var(--white);
      padding: 1rem 2rem;
      box-shadow: var(--shadow);
      position: sticky;
      top: 0;
      z-index: 100;
    }
    
    .header-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .logo {
      font-size: 2.2rem;
      font-weight: bold;
      display: flex;
      align-items: center;
    }
    
    .logo-icon {
      width: 50px;
      height: 50px;
      margin-right: 12px;
      background: var(--accent);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--primary);
      font-weight: bold;
      font-size: 1.8rem;
      box-shadow: 0 0 0 3px var(--white);
    }
    
    .slogan {
      font-style: italic;
      font-size: 1.1rem;
      opacity: 0.9;
      margin: 0.5rem 0;
      text-align: center;
      color: var(--accent);
    }
    
    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--white);
    }
    
    nav {
      margin-top: 1rem;
    }
    nav ul {
      display: flex;
      justify-content: center;
      list-style: none;
      flex-wrap: wrap;
    }
    nav li {
      margin: 0 0.5rem;
    }

    nav a {
      color: var(--white);
      text-decoration: none;
      padding: 0.5rem 1rem;
      border-radius: 4px;
      transition: all 0.3s;
      font-weight: 500;
      position: relative;
    }

    nav a:hover {
      background: rgba(255, 255, 255, 0.2);
    }
    nav a::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 0;
      height: 2px;
      background: var(--accent);
      transition: all 0.3s;
      transform: translateX(-50%);
    }

    nav a:hover::after {
      width: 70%;
    }
    
    /* Hero Section with changing background */
    .hero {
      background: url('https://images.unsplash.com/photo-1576866209830-3314d3b43a2a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
      background-size: cover;
      background-position: center;
      color: var(--white);
      text-align: center;
      padding: 5rem 1rem;
      margin-bottom: 2rem;
      position: relative;
      animation: changeBackground 15s infinite;
    }
    
    @keyframes changeBackground {
      0% {
        background-image: url('https://images.unsplash.com/photo-1576866209830-3314d3b43a2a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
      }
      33% {
        background-image: url('https://images.unsplash.com/photo-1584697964358-3e14e514c563?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
      }
      66% {
        background-image: url('https://images.unsplash.com/photo-1615461066841-6116e61058f4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
      }
      100% {
        background-image: url('https://images.unsplash.com/photo-1576866209830-3314d3b43a2a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwa90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
      }
    }
    
    .hero-content {
      position: relative;
      z-index: 1;
      max-width: 800px;
      margin: 0 auto;
      background: rgba(199, 33, 33, 0.85);
      padding: 2rem;
      border-radius: 10px;
      box-shadow: var(--shadow);
    }
    
    .hero h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    }
    
    .hero p {
      font-size: 1.3rem;
      margin: 0 auto 2rem;
      max-width: 600px;
    }
    
    .slogan-banner {
      background: var(--primary-dark);
      color: var(--white);
      padding: 1rem;
      text-align: center;
      font-style: italic;
      margin: 1rem 0;
      border-left: 4px solid var(--accent);
    }
    
    .cta-button {
      display: inline-block;
      background: var(--primary);
      color: var(--white);
      padding: 1rem 2.5rem;
      border-radius: 50px;
      text-decoration: none;
      font-weight: bold;
      transition: all 0.3s;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      border: 2px solid var(--accent);
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-top: 1rem;
    }
    
    .cta-button:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 15px rgba(0,0,0,0.3);
      background: var(--primary-dark);
    }
    
    /* Features Section */
    .features {
      padding: 4rem 1rem;
      background: var(--white);
      text-align: center;
    }
    
    .features h2 {
      color: var(--primary);
      margin-bottom: 2rem;
      position: relative;
      display: inline-block;
    }
    
    .features h2::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 3px;
      background: var(--primary);
    }
    
    .features-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .feature-card {
      flex: 1 1 300px;
      background: var(--secondary);
      padding: 2rem;
      border-radius: 10px;
      box-shadow: var(--shadow);
      transition: transform 0.3s;
    }
    
    .feature-card:hover {
      transform: translateY(-10px);
    }
    
    .feature-card i {
      font-size: 3rem;
      color: var(--primary);
      margin-bottom: 1rem;
    }
    
    /* Form Tabs */
    .form-tabs {
      display: flex;
      margin-bottom: 1.5rem;
      border-bottom: 2px solid var(--primary-light);
    }
    
    .form-tab {
      padding: 0.8rem 1.5rem;
      background: var(--primary-light);
      color: var(--white);
      cursor: pointer;
      transition: all 0.3s;
      font-weight: bold;
      flex: 1;
      text-align: center;
    }
    
    .form-tab:first-child {
      border-radius: 5px 0 0 0;
    }
    
    .form-tab:last-child {
      border-radius: 0 5px 0 0;
    }
    
    /* Hide radio inputs */
    .tab-input {
      display: none;
    }
    
    #donor-tab:checked ~ .form-tabs .donor-tab-label,
    #request-tab:checked ~ .form-tabs .request-tab-label {
      background: var(--primary);
    }
    
    #donor-tab:checked ~ .form-contents .donor-form-content,
    #request-tab:checked ~ .form-contents .request-form-content {
      display: block;
    }
    
    .form-content {
      display: none;
    }
    
    /* Main Content */
    main {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      padding: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .form-container, .inventory-container {
      background: var(--white);
      border-radius: 10px;
      box-shadow: var(--shadow);
      padding: 2rem;
      margin: 1rem;
      flex: 1 1 400px;
      max-width: 500px;
      position: relative;
      overflow: hidden;
    }
    
    .form-container::before, .inventory-container::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 5px;
      background: var(--primary);
    }
    
    h2 {
      margin-top: 0;
      color: var(--primary);
      padding-bottom: 0.5rem;
      border-bottom: 2px solid var(--primary-light);
      display: flex;
      align-items: center;
    }
    
    h2 i {
      margin-right: 10px;
    }
    
    label {
      display: block;
      margin: 1rem 0 0.5rem;
      font-weight: 500;
      color: var(--primary-dark);
    }
    
    input, select, textarea {
      width: 100%;
      padding: 0.8rem;
      border: 1px solid #ddd;
      border-radius: 5px;
      font-family: inherit;
      transition: border 0.3s;
    }
    
    input:focus, select:focus, textarea:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 2px var(--accent);
    }
    
    button {
      margin-top: 1.5rem;
      background: var(--primary);
      color: var(--white);
      border: none;
      padding: 1rem 2rem;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1rem;
      font-weight: bold;
      transition: all 0.3s;
      width: 100%;
      position: relative;
      overflow: hidden;
    }
    
    button:hover {
      background: var(--primary-dark);
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
    
    .blood-group {
      display: flex;
      justify-content: space-between;
      padding: 0.8rem;
      border-bottom: 1px solid #eee;
      transition: background 0.2s;
      align-items: center;
    }
    
    .blood-group:hover {
      background: #fff5f5;
    }
    
    .blood-group:last-child {
      border-bottom: none;
    }
    
    .blood-type {
      display: flex;
      align-items: center;
    }
    
    .blood-type::before {
      content: '';
      display: inline-block;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: var(--primary);
      margin-right: 10px;
    }
    
    .blood-cell-container {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 2rem;
    }
    
    .blood-cell {
      width: 50px;
      height: 50px;
      background: radial-gradient(circle, var(--primary-light) 20%, var(--primary-dark) 100%);
      border-radius: 50%;
      margin: 10px;
      box-shadow: inset -2px -2px 4px rgba(255,255,255,0.2);
      animation: pulse 2s infinite;
      position: relative;
    }
    
    .blood-cell::after {
      content: '';
      position: absolute;
      top: 15px;
      left: 15px;
      width: 10px;
      height: 10px;
      background: rgba(255, 255, 255, 0.5);
      border-radius: 50%;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }
    
    /* Success Message */
    .success-message {
      display: none;
      background: #4CAF50;
      color: white;
      padding: 1rem;
      border-radius: 5px;
      margin-top: 1rem;
      text-align: center;
    }
    
    /* Stats Section */
    .stats {
      background: var(--primary);
      color: var(--white);
      padding: 4rem 1rem;
      text-align: center;
      margin: 3rem 0;
    }
    
    .stats-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .stat-item {
      flex: 1 1 200px;
      padding: 1.5rem;
    }
    
    .stat-number {
      font-size: 2.5rem;
      font-weight: bold;
      margin-bottom: 0.5rem;
      color: var(--accent);
    }
    
    /* Blood Compatibility Section */
    .blood-compatibility {
      padding: 4rem 1rem;
      background: var(--secondary);
      text-align: center;
    }
    
    .blood-compatibility h2 {
      color: var(--primary);
      margin-bottom: 2rem;
    }
    
    .compatibility-info {
      text-align: center;
      max-width: 800px;
      margin: 0 auto 3rem;
      color: var(--text-light);
    }
    
    .compatibility-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .compatibility-card {
      background: var(--white);
      border-radius: 10px;
      padding: 1.5rem;
      box-shadow: var(--shadow);
      transition: transform 0.3s;
    }
    
    .compatibility-card:hover {
      transform: translateY(-5px);
    }
    
    .blood-type-header {
      display: flex;
      align-items: center;
      margin-bottom: 1.5rem;
      padding-bottom: 1rem;
      border-bottom: 1px solid #eee;
    }
    
    .blood-type {
      font-size: 2rem;
      font-weight: bold;
      color: var(--primary);
      margin-right: 1rem;
      width: 60px;
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      background: var(--accent);
    }
    
    .blood-type-title {
      font-size: 1.2rem;
      font-weight: 600;
      text-align: left;
    }
    
    .compatibility-details h3 {
      margin-bottom: 1rem;
      color: var(--primary-dark);
      text-align: left;
    }
    
    .compatibility-list {
      list-style-type: none;
      text-align: left;
    }
    
    .compatibility-list li {
      padding: 0.5rem 0;
      border-bottom: 1px dashed #eee;
      display: flex;
      align-items: center;
    }
    
    .compatibility-list li:last-child {
      border-bottom: none;
    }
    
    .compatibility-list li::before {
      content: '•';
      color: var(--primary);
      font-weight: bold;
      display: inline-block;
      width: 1em;
      margin-right: 0.5em;
    }
    
    .compatibility-table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 2rem;
      box-shadow: var(--shadow);
      background: var(--white);
      border-radius: 8px;
      overflow: hidden;
    }
    
    .compatibility-table th, 
    .compatibility-table td {
      padding: 1rem;
      text-align: left;
      border: 1px solid #ddd;
    }
    
    .compatibility-table th {
      background-color: var(--primary);
      color: var(--white);
    }
    
    .compatibility-table tr:nth-child(even) {
      background-color: #f9f9f9;
    }
    
    /* Slogans Section */
    .slogans {
      padding: 4rem 1rem;
      text-align: center;
      background: var(--white);
    }
    
    .slogan-slider {
      max-width: 800px;
      margin: 0 auto;
      padding: 2rem;
      background: var(--secondary);
      border-radius: 10px;
      box-shadow: var(--shadow);
    }
    
    .slogan {
      font-size: 1.5rem;
      font-style: italic;
      color: var(--primary);
      margin: 1rem 0;
      padding: 1rem;
      border-left: 4px solid var(--primary);
      background: var(--white);
      border-radius: 0 5px 5px 0;
    }
    
    /* Footer */
    footer {
      background: var(--primary-dark);
      color: var(--white);
      padding: 3rem 1rem;
      margin-top: 3rem;
    }
    
    .footer-content {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .footer-section {
      flex: 1 1 300px;
      margin: 1rem;
    }
    
    .footer-section h3 {
      font-size: 1.3rem;
      margin-bottom: 1.2rem;
      position: relative;
      padding-bottom: 0.5rem;
      color: var(--accent);
    }
    
    .footer-section h3::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 50px;
      height: 2px;
      background: var(--accent);
    }
    
    .footer-links {
      list-style: none;
    }
    
    .footer-links li {
      margin-bottom: 0.8rem;
    }
    
    .footer-links a {
      color: var(--white);
      text-decoration: none;
      transition: all 0.3s;
      display: inline-block;
    }
    
    .footer-links a:hover {
      color: var(--accent);
      padding-left: 5px;
    }
    
    .contact-info {
      list-style: none;
    }
    
    .contact-info li {
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
    }
    
    .contact-info i {
      margin-right: 10px;
      width: 20px;
      color: var(--accent);
    }
    
    .social-links {
      display: flex;
      margin-top: 1.5rem;
    }
    
    .social-links a {
      display: inline-block;
      height: 40px;
      width: 40px;
      background: rgba(255, 255, 255, 0.1);
      margin-right: 10px;
      border-radius: 50%;
      text-align: center;
      line-height: 40px;
      color: var(--white);
      transition: all 0.3s;
    }
    
    .social-links a:hover {
      background: var(--primary-light);
      transform: translateY(-5px);
    }
    
    .footer-bottom {
      text-align: center;
      padding-top: 2rem;
      margin-top: 2rem;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      max-width: 1200px;
      margin-left: auto;
      margin-right: auto;
      color: var(--accent);
    }
    
    /* Responsive Design */
    @media (max-width: 768px) {
      .menu-toggle {
        display: block;
      }
      
      nav ul {
        flex-direction: column;
        text-align: center;
        display: none;
      }
      
      nav ul.show {
        display: flex;
      }
      
      nav li {
        margin: 0.5rem 0;
      }
      
      .header-top {
        flex-wrap: wrap;
      }
      
      .logo {
        font-size: 1.8rem;
      }
      
      .hero h1 {
        font-size: 2.2rem;
      }
      
      .hero p {
        font-size: 1.1rem;
      }
      
      .form-tabs {
        flex-direction: column;
      }
      
      .form-tab {
        border-radius: 0;
      }
      
      .form-tab:first-child {
        border-radius: 5px 5px 0 0;
      }
      
      .form-tab:last-child {
        border-radius: 0 0 5px 5px;
      }
      
      .compatibility-grid {
        grid-template-columns: 1fr;
      }
    }
    
    @media (max-width: 480px) {
      .hero h1 {
        font-size: 1.8rem;
      }
      
      .hero p {
        font-size: 1rem;
      }
      
      .form-container, .inventory-container {
        padding: 1.5rem;
      }
      
      .feature-card {
        flex: 1 1 100%;
      }
    }
  </style>
</head>
<body>
  <header class="main-header">
    <div class="header-top">
      <div class="logo">
        <div class="logo-icon">DD</div>
        <span>DonorDrop</span>
      </div>
      <span class="menu-toggle" id="menuToggle">&#9776;</span>
    </div>
    
    <p class="slogan">Save a life, donate blood</p>
    
    <nav>
      <ul id="navMenu">
        <li><a href="#home"><i class="fas fa-home"></i> Home</a></li>
        <li><a href="#form-section"><i class="fas fa-heart"></i> Donate</a></li>
        <li><a href="#form-section"><i class="fas fa-tint"></i> Request</a></li>
        <li><a href="#about"><i class="fas fa-info-circle"></i> About</a></li>
        <li><a href="#footer"><i class="fas fa-phone"></i> Contact</a></li>
      </ul>
    </nav>
  </header>
  
  <section class="hero" id="home">
    <div class="hero-content">
      <h1>DonorDrop Blood Center</h1>
      <p>Join us in our mission to save lives by donating blood. Your single donation can save up to three lives. Register today and become a lifesaver!</p>
      
      <div class="slogan-banner">
        "Be a hero, donate blood - the gift of life"
      </div>
      
      <a href="#form-section" class="cta-button">Donate Now <i class="fas fa-arrow-right"></i></a>
    </div>
  </section>
  
  <section class="features" id="about">
    <h2>Why Donate Blood?</h2>
    <div class="features-grid">
      <div class="feature-card">
        <i class="fas fa-heartbeat"></i>
        <h3>Save Lives</h3>
        <p>Your donation can save up to three lives. There's no greater gift than giving someone another chance at life.</p>
      </div>
      
      <div class="feature-card">
        <i class="fas fa-users"></i>
        <h3>Community Support</h3>
        <p>Join a community of dedicated donors who make a difference in their local communities every day.</p>
      </div>
      
      <div class="feature-card">
        <i class="fas fa-shield-alt"></i>
        <h3>Safe Process</h3>
        <p>Donating blood is safe, sterile, and performed under the supervision of medical professionals.</p>
      </div>
    </div>
  </section>
  
  <section class="slogan-banner">
    "Blood donation will cost you nothing but it will save a life!"
  </section>
  
  <!-- Blood Compatibility Section -->
  <section class="blood-compatibility">
    <div class="container">
      <h2>Blood Type Compatibility</h2>
      <div class="compatibility-info">
        <p>Not all blood types are compatible. Knowing who can receive your blood and whose blood you can receive is crucial for safe transfusions.</p>
      </div>
      
      <div class="compatibility-grid">
        <div class="compatibility-card">
          <div class="blood-type-header">
            <div class="blood-type">A+</div>
            <div class="blood-type-title">Blood Type A Positive</div>
          </div>
          <div class="compatibility-details">
            <h3>Can donate to:</h3>
            <ul class="compatibility-list">
              <li>A+</li>
              <li>AB+</li>
            </ul>
            <h3>Can receive from:</h3>
            <ul class="compatibility-list">
              <li>A+</li>
              <li>A-</li>
              <li>O+</li>
              <li>O-</li>
            </ul>
          </div>
        </div>
        
        <div class="compatibility-card">
          <div class="blood-type-header">
            <div class="blood-type">O+</div>
            <div class="blood-type-title">Blood Type O Positive</div>
          </div>
          <div class="compatibility-details">
            <h3>Can donate to:</h3>
            <ul class="compatibility-list">
              <li>O+</li>
              <li>A+</li>
              <li>B+</li>
              <li>AB+</li>
            </ul>
            <h3>Can receive from:</h3>
            <ul class="compatibility-list">
              <li>O+</li>
              <li>O-</li>
            </ul>
          </div>
        </div>
        
        <div class="compatibility-card">
          <div class="blood-type-header">
            <div class="blood-type">B+</div>
            <div class="blood-type-title">Blood Type B Positive</div>
          </div>
          <div class="compatibility-details">
            <h3>Can donate to:</h3>
            <ul class="compatibility-list">
              <li>B+</li>
              <li>AB+</li>
            </ul>
            <h3>Can receive from:</h3>
            <ul class="compatibility-list">
              <li>B+</li>
              <li>B-</li>
              <li>O+</li>
              <li>O-</li>
            </ul>
          </div>
        </div>
        
        <div class="compatibility-card">
          <div class="blood-type-header">
            <div class="blood-type">AB+</div>
            <div class="blood-type-title">Blood Type AB Positive</div>
          </div>
          <div class="compatibility-details">
            <h3>Can donate to:</h3>
            <ul class="compatibility-list">
              <li>AB+</li>
            </ul>
            <h3>Can receive from:</h3>
            <ul class="compatibility-list">
              <li>All blood types</li>
            </ul>
          </div>
        </div>
      </div>
      
      <table class="compatibility-table">
        <thead>
          <tr>
            <th>Blood Type</th>
            <th>Can Donate To</th>
            <th>Can Receive From</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>A+</td>
            <td>A+, AB+</td>
            <td>A+, A-, O+, O-</td>
          </tr>
          <tr>
            <td>O+</td>
            <td>O+, A+, B+, AB+</td>
            <td>O+, O-</td>
          </tr>
          <tr>
            <td>B+</td>
            <td>B+, AB+</td>
            <td>B+, B-, O+, O-</td>
          </tr>
          <tr>
            <td>AB+</td>
            <td>AB+</td>
            <td>Everyone</td>
          </tr>
          <tr>
            <td>A-</td>
            <td>A+, A-, AB+, AB-</td>
            <td>A-, O-</td>
          </tr>
          <tr>
            <td>O-</td>
            <td>Everyone</td>
            <td>O-</td>
          </tr>
          <tr>
            <td>B-</td>
            <td>B+, B-, AB+, AB-</td>
            <td>B-, O-</td>
          </tr>
          <tr>
            <td>AB-</td>
            <td>AB+, AB-</td>
            <td>AB-, A-, B-, O-</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
  
  <main id="form-section">
    <!-- Form Container with Tabs -->
    <div class="form-container">
      <input type="radio" name="tabs" id="donor-tab" class="tab-input" checked>
      <input type="radio" name="tabs" id="request-tab" class="tab-input">
      
      <div class="form-tabs">
        <label for="donor-tab" class="form-tab donor-tab-label">Be a Donor</label>
        <label for="request-tab" class="form-tab request-tab-label">Need Blood</label>
      </div>
      
      <div class="form-contents">
        <!-- Donor Form -->
        <div class="form-content donor-form-content">
          <h2><i class="fas fa-user-plus"></i> Donor Registration</h2>
          <form id="donorForm">
            <label for="name">Full Name</label>
            <input type="text" id="name" placeholder="John Doe" required />

            <label for="email">Email Address</label>
            <input type="email" id="email" placeholder="john.doe@example.com" required />
            
            <label for="blood-group">Blood Group</label>
            <select id="blood-group" required>
              <option value="">Select Blood Type</option>
              <option>A+</option>
              <option>A-</option>
              <option>B+</option>
              <option>B-</option>
              <option>AB+</option>
              <option>AB-</option>
              <option>O+</option>
              <option>O-</option>
            </select>

            <label for="contact">Contact Number</label>
            <input type="tel" id="contact" placeholder="123-456-7890" required />
            
            <label for="location">Location</label>
            <input type="text" id="location" placeholder="City, State" required />

            <label for="availability">Availability</label>
            <select id="availability" required>
              <option value="">Select Availability</option>
              <option>Immediately</option>
              <option>Within a week</option>
              <option>Next month</option>
              <option>On call</option>
            </select>

            <button type="submit">Register as Donor <i class="fas fa-heart"></i></button>
          </form>
        </div>
        
        <!-- Request Form -->
        <div class="form-content request-form-content">
          <h2><i class="fas fa-tint"></i> Blood Request</h2>
          <form id="requestForm">
            <label for="patient-name">Patient Name</label>
            <input type="text" id="patient-name" placeholder="Patient Name" required />

            <label for="blood-group-needed">Blood Group Needed</label>
            <select id="blood-group-needed" required>
              <option value="">Select Blood Type</option>
              <option>A+</option>
              <option>A-</option>
              <option>B+</option>
              <option>B-</option>
              <option>AB+</option>
              <option>AB-</option>
              <option>O+</option>
              <option>O-</option>
            </select>

            <label for="units-needed">Units Needed</label>
            <input type="number" id="units-needed" min="1" placeholder="e.g. 2" required />

            <label for="hospital">Hospital Name</label>
            <input type="text" id="hospital" placeholder="Hospital Name" required />

            <label for="contact-request">Contact Number</label>
            <input type="tel" id="contact-request" placeholder="123-456-7890" required />
            
            <label for="location-request">Location</label>
            <input type="text" id="location-request" placeholder="City, State" required />

            <label for="urgency">Urgency</label>
            <select id="urgency" required>
              <option value="">Select Urgency</option>
              <option>Emergency (Within 1 hour)</option>
              <option>Urgent (Today)</option>
              <option>Within 2 days</option>
              <option>Within a week</option>
            </select>

            <label for="message">Additional Message</label>
            <textarea id="message" placeholder="Any additional information..." rows="3"></textarea>

            <button type="submit">Submit Request <i class="fas fa-hand-holding-heart"></i></button>
          </form>
        </div>
      </div>
    </div>

    <!-- Blood Inventory -->
    <div class="inventory-container">
      <h2><i class="fas fa-warehouse"></i> Available Blood Inventory</h2>
      <div class="blood-group"><div class="blood-type">A+</div><span>12 units</span></div>
      <div class="blood-group"><div class="blood-type">A-</div><span>5 units</span></div>
      <div class="blood-group"><div class="blood-type">B+</div><span>9 units</span></div>
      <div class="blood-group"><div class="blood-type">B-</div><span>4 units</span></div>
      <div class="blood-group"><div class="blood-type">AB+</div><span>7 units</span></div>
      <div class="blood-group"><div class="blood-type">AB-</div><span>2 units</span></div>
      <div class="blood-group"><div class="blood-type">O+</div><span>15 units</span></div>
      <div class="blood-group"><div class="blood-type">O-</div><span>3 units</span></div>

      <div class="blood-cell-container">
        <div class="blood-cell"></div>
        <div class="blood-cell"></div>
        <div class="blood-cell"></div>
        <div class="blood-cell"></div>
        <div class="blood-cell"></div>
        <div class="blood-cell"></div>
      </div>
    </div>
  </main>
  
  <section class="stats">
    <div class="stats-grid">
      <div class="stat-item">
        <div class="stat-number">1M+</div>
        <div class="stat-desc">Lives Saved</div>
      </div>
      <div class="stat-item">
        <div class="stat-number">500K+</div>
        <div class="stat-desc">Active Donors</div>
      </div>
      <div class="stat-item">
        <div class="stat-number">250+</div>
        <div class="stat-desc">Centers Nationwide</div>
      </div>
      <div class="stat-item">
        <div class="stat-number">24/7</div>
        <div class="stat-desc">Emergency Services</div>
      </div>
    </div>
  </section>
  
  <section class="slogans">
    <div class="slogan-slider">
      <div class="slogan">"The blood you donate gives someone another chance at life. One day that someone may be a close relative, a friend, a loved one—or even you."</div>
      <div class="slogan">"Blood is meant to circulate. Pass it around."</div>
      <div class="slogan">"Don't think of it as losing a pint of blood. Think of it as gaining three lives."</div>
    </div>
  </section>
  
  <footer id="footer">
    <div class="footer-content">
      <div class="footer-section">
        <h3>About DonorDrop</h3>
        <p>DonorDrop is a non-profit organization dedicated to connecting blood donors with those in need. Our mission is to ensure that safe blood is available to every patient whenever and wherever needed.</p>
        <div class="social-links">
          <a href="#"><i class="fab fa-facebook-f"></i></a>
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
        </div>
      </div>
      
      <div class="footer-section">
        <h3>Quick Links</h3>
        <ul class="footer-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#form-section">Donate Blood</a></li>
          <li><a href="#form-section">Request Blood</a></li>
          <li><a href="#about">Eligibility Criteria</a></li>
          <li><a href="#about">Blood Donation Process</a></li>
          <li><a href="#about">Upcoming Blood Drives</a></li>
        </ul>
      </div>
      
      <div class="footer-section">
        <h3>Contact Information</h3>
        <ul class="contact-info">
          <li><i class="fas fa-map-marker-alt"></i> 123 Life Saver Street, Health City</li>
          <li><i class="fas fa-phone"></i> +1 (800) 123-4567</li>
          <li><i class="fas fa-envelope"></i> info@donordrop.org</li>
          <li><i class="fas fa-clock"></i> Monday-Friday: 8AM-6PM</li>
          <li><i class="fas fa-clock"></i> Saturday: 9AM-4PM</li>
        </ul>
      </div>
    </div>
    
    <div class="footer-bottom">
      <p>&copy; 2023 DonorDrop. All rights reserved. | Designed with <i class="fas fa-heart" style="color: #ffcccb;"></i> for humanity</p>
    </div>
  </footer>

  <script>
    // Simple script for mobile menu toggle
    document.getElementById('menuToggle').addEventListener('click', function() {
      const navMenu = document.getElementById('navMenu');
      navMenu.classList.toggle('show');
    });

    // Form submission handling
    document.getElementById('donorForm').addEventListener('submit', function(e) {
      e.preventDefault();
      alert('Thank you for registering as a donor! We will contact you soon.');
      this.reset();
    });

    document.getElementById('requestForm').addEventListener('submit', function(e) {
      e.preventDefault();
      alert('Your blood request has been submitted. We will contact you shortly.');
      this.reset();
    });

    // Tab switching functionality
    const tabInputs = document.querySelectorAll('.tab-input');
    const tabContents = document.querySelectorAll('.form-content');
    
    // Show donor form by default
    document.querySelector('.donor-form-content').style.display = 'block';
    
    tabInputs.forEach(input => {
      input.addEventListener('change', () => {
        tabContents.forEach(content => content.style.display = 'none');
        if (input.id === 'donor-tab') {
          document.querySelector('.donor-form-content').style.display = 'block';
        } else {
          document.querySelector('.request-form-content').style.display = 'block';
        }
      });
    });
  </script>
</body>
</html>
