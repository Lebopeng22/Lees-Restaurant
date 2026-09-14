<script>
  import { createEventDispatcher } from 'svelte'
  import MapComponent from '../components/MapComponent.svelte'
  const dispatch = createEventDispatcher()

  function handleBooking() {
    dispatch('navigate', 'booking')
  }
</script>

<div class="home-page">
  <!-- Hero Section -->
  <section class="hero">
    <div class="hero-content">
      <h1>Welcome to Lee's Restaurant</h1>
      <p>Experience Authentic Italian Cuisine Made Fresh to Order</p>
      <button class="cta-button" on:click={handleBooking}>Book a Table</button>
    </div>
  </section>

  <!-- About Section -->
  <section class="about">
    <div class="container">
      <h2>Our Story</h2>
      <p>At Lee's Restaurant, we believe in serving only the finest Italian cuisine prepared with the freshest ingredients. Every dish is made to order, ensuring quality and authenticity in every bite. Our commitment to excellence has made us a beloved destination for families and food enthusiasts alike.</p>
    </div>
  </section>

  <!-- Trading Hours -->
  <section class="trading-hours">
    <div class="container">
      <h2>Trading Hours</h2>
      <div class="hours-grid">
        <div class="hour-item">
          <h4>Monday - Thursday</h4>
          <p>11:00 AM - 10:00 PM</p>
        </div>
        <div class="hour-item">
          <h4>Friday - Saturday</h4>
          <p>11:00 AM - 11:00 PM</p>
        </div>
        <div class="hour-item">
          <h4>Sunday</h4>
          <p>12:00 PM - 9:00 PM</p>
        </div>
        <div class="hour-item">
          <h4>Holidays</h4>
          <p>Closed on Christmas & New Year</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section class="contact-section">
    <div class="container">
      <h2>Get In Touch</h2>
      <div class="contact-grid">
        <div class="contact-item">
          <h3>📍 Address</h3>
          <p>123 Italian Street<br>Flavor City, FC 12345</p>
        </div>
        <div class="contact-item">
          <h3>📞 Phone</h3>
          <p>(555) 123-4567</p>
        </div>
        <div class="contact-item">
          <h3>📧 Email</h3>
          <p>info@leesrestaurant.com</p>
        </div>
        <div class="contact-item">
          <h3>🌐 Web</h3>
          <p>www.leesrestaurant.com</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Map Section -->
  <section class="map-section">
    <div class="container">
      <h2>Find Us</h2>
      <MapComponent />
    </div>
  </section>
</div>

<style>
  .home-page {
    width: 100%;
  }

  .hero {
    background: linear-gradient(135deg, #8b0000 0%, #d90000 100%);
    color: white;
    padding: 8rem 1rem;
    text-align: center;
    position: relative;
  }

  .hero-content h1 {
    font-size: 3.5rem;
    margin: 0 0 1rem;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  }

  .hero-content p {
    font-size: 1.5rem;
    margin: 0 0 2rem;
    text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
  }

  .cta-button {
    background-color: #ffd700;
    color: #8b0000;
    border: none;
    padding: 1rem 2.5rem;
    font-size: 1.1rem;
    border-radius: 50px;
    cursor: pointer;
    font-weight: bold;
    transition: all 0.3s;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  }

  .cta-button:hover {
    background-color: #ffed4e;
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  section {
    padding: 3rem 0;
  }

  section h2 {
    text-align: center;
    font-size: 2.5rem;
    color: #8b0000;
    margin-bottom: 2rem;
  }

  .about {
    background-color: #fff;
  }

  .about p {
    font-size: 1.1rem;
    line-height: 1.8;
    text-align: center;
    color: #333;
    max-width: 800px;
    margin: 0 auto;
  }

  .trading-hours {
    background-color: #f9f9f9;
  }

  .hours-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
  }

  .hour-item {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    text-align: center;
  }

  .hour-item h4 {
    color: #8b0000;
    margin: 0 0 0.5rem;
  }

  .hour-item p {
    margin: 0;
    color: #666;
  }

  .contact-section {
    background-color: #fff;
  }

  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
  }

  .contact-item {
    background: linear-gradient(135deg, #f0f0f0 0%, #e8e8e8 100%);
    padding: 1.5rem;
    border-radius: 8px;
    border-left: 4px solid #8b0000;
  }

  .contact-item h3 {
    color: #8b0000;
    margin: 0 0 0.5rem;
  }

  .contact-item p {
    margin: 0;
    color: #333;
    line-height: 1.6;
  }

  .map-section {
    background-color: #f9f9f9;
  }

  @media (max-width: 768px) {
    .hero-content h1 {
      font-size: 2rem;
    }

    .hero-content p {
      font-size: 1.1rem;
    }

    .hero {
      padding: 4rem 1rem;
    }
  }
</style>
