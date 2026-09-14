<script>
  import GallerySlider from '../components/GallerySlider.svelte'
</script>

<div class="gallery-page">
  <div class="container">
    <h1>Photo Gallery</h1>
    <p class="gallery-subtitle">Explore our delicious Italian dishes</p>
    <GallerySlider />
  </div>
</div>

<style>
  .gallery-page {
    background: linear-gradient(135deg, #f5f5f5 0%, #fff 100%);
    padding: 3rem 1rem;
    min-height: 80vh;
  }

  .container {
    max-width: 1000px;
    margin: 0 auto;
  }

  h1 {
    color: #8b0000;
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
  }

  .gallery-subtitle {
    text-align: center;
    color: #666;
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }
</style>
