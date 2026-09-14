<script>
  import { onMount } from 'svelte'

  let mapContainer
  let map

  const restaurantLocation = {
    lat: 40.7128,
    lng: -74.0060
  }

  onMount(async () => {
    // Load Google Maps API
    if (!window.google) {
      const script = document.createElement('script')
      script.src = `https://maps.googleapis.com/maps/api/js?key=${import.meta.env.VITE_GOOGLE_MAPS_API_KEY || 'AIzaSyDDfEH4l-tPQpnuXfhR-NpYrV4Z-7L5XEE'}`
      script.async = true
      script.defer = true
      script.onload = () => initMap()
      document.head.appendChild(script)
    } else {
      initMap()
    }
  })

  function initMap() {
    if (!mapContainer) return

    map = new window.google.maps.Map(mapContainer, {
      zoom: 15,
      center: restaurantLocation,
      styles: [
        {
          featureType: 'all',
          elementType: 'labels.text.fill',
          stylers: [{ color: '#8b0000' }]
        }
      ]
    })

    const marker = new window.google.maps.Marker({
      position: restaurantLocation,
      map: map,
      title: "Lee's Restaurant",
      animation: window.google.maps.Animation.DROP
    })

    const infoWindow = new window.google.maps.InfoWindow({
      content: `
        <div style="color: #333; font-family: Arial, sans-serif;">
          <h3 style="margin: 0; color: #8b0000;">Lee's Restaurant</h3>
          <p style="margin: 5px 0;">📍 123 Italian Street, Flavor City</p>
          <p style="margin: 5px 0;">📞 (555) 123-4567</p>
          <p style="margin: 5px 0;">📧 info@leesrestaurant.com</p>
        </div>
      `
    })

    marker.addListener('click', () => {
      infoWindow.open(map, marker)
    })
  }
</script>

<div class="map-wrapper">
  <div class="map-container" bind:this={mapContainer}></div>
  <div class="map-info">
    <p><strong>📍 Address:</strong> 123 Italian Street, Flavor City, FC 12345</p>
    <p><strong>📞 Phone:</strong> (555) 123-4567</p>
    <p><strong>📧 Email:</strong> info@leesrestaurant.com</p>
    <p><strong>🕐 Hours:</strong> Mon-Thu 11AM-10PM | Fri-Sat 11AM-11PM | Sun 12PM-9PM</p>
  </div>
</div>

<style>
  .map-wrapper {
    width: 100%;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  }

  .map-container {
    width: 100%;
    height: 400px;
    background-color: #e5e3df;
  }

  .map-info {
    background: linear-gradient(135deg, #f9f9f9 0%, #fff 100%);
    padding: 1.5rem;
    border-top: 2px solid #8b0000;
  }

  .map-info p {
    margin: 0.5rem 0;
    color: #333;
    line-height: 1.6;
  }

  @media (max-width: 768px) {
    .map-container {
      height: 300px;
    }
  }
</style>
