<script>
  let currentIndex = 0

  const images = [
    {
      url: 'https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?w=600&h=400&fit=crop',
      title: 'Italian Pasta Bolognese',
      description: 'Authentic spaghetti with rich meat sauce'
    },
    {
      url: 'https://images.unsplash.com/photo-1645112411341-6c4ee32510d8?w=600&h=400&fit=crop',
      title: 'Fresh Meatballs',
      description: 'Homemade Italian meatballs with marinara'
    },
    {
      url: 'https://images.unsplash.com/photo-1599021429194-c12cf7da6e9f?w=600&h=400&fit=crop',
      title: 'Grilled Steak',
      description: 'Premium T-bone steak with fries'
    },
    {
      url: 'https://images.unsplash.com/photo-1597525871519-f31e6ffb3a9d?w=600&h=400&fit=crop',
      title: 'Fresh Salad',
      description: 'Crisp Greek salad with feta cheese'
    },
    {
      url: 'https://images.unsplash.com/photo-1598103442097-8b74394b95c6?w=600&h=400&fit=crop',
      title: 'Fried Ravioli',
      description: 'Golden crispy fried ravioli'
    },
    {
      url: 'https://images.unsplash.com/photo-1613383523369-16729bc77a19?w=600&h=400&fit=crop',
      title: 'Pork Ribs',
      description: 'Slow-cooked tender pork ribs'
    }
  ]

  function nextSlide() {
    currentIndex = (currentIndex + 1) % images.length
  }

  function prevSlide() {
    currentIndex = (currentIndex - 1 + images.length) % images.length
  }

  function goToSlide(index) {
    currentIndex = index
  }
</script>

<div class="gallery-container">
  <div class="main-image">
    <img src={images[currentIndex].url} alt={images[currentIndex].title} />
    <div class="image-info">
      <h3>{images[currentIndex].title}</h3>
      <p>{images[currentIndex].description}</p>
    </div>
  </div>

  <div class="gallery-controls">
    <button class="control-btn prev" on:click={prevSlide}>❮</button>
    <button class="control-btn next" on:click={nextSlide}>❯</button>
  </div>

  <div class="thumbnails">
    {#each images as image, index}
      <button
        class="thumbnail"
        class:active={currentIndex === index}
        on:click={() => goToSlide(index)}
        title={image.title}
      >
        <img src={image.url} alt={image.title} />
      </button>
    {/each}
  </div>

  <div class="slide-counter">
    {currentIndex + 1} / {images.length}
  </div>
</div>

<style>
  .gallery-container {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .main-image {
    position: relative;
    width: 100%;
    overflow: hidden;
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
  }

  .main-image img {
    width: 100%;
    height: 500px;
    object-fit: cover;
    display: block;
    transition: transform 0.3s ease;
  }

  .main-image:hover img {
    transform: scale(1.02);
  }

  .image-info {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
    color: white;
    padding: 2rem 1.5rem 1rem;
  }

  .image-info h3 {
    margin: 0 0 0.5rem 0;
    font-size: 1.5rem;
  }

  .image-info p {
    margin: 0;
    font-size: 0.95rem;
  }

  .gallery-controls {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 1rem;
  }

  .control-btn {
    background: linear-gradient(135deg, #8b0000 0%, #d90000 100%);
    color: white;
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    font-size: 1.5rem;
    cursor: pointer;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .control-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 4px 12px rgba(139, 0, 0, 0.4);
  }

  .control-btn:active {
    transform: scale(0.95);
  }

  .thumbnails {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
  }

  .thumbnail {
    background: none;
    border: 3px solid transparent;
    border-radius: 8px;
    overflow: hidden;
    cursor: pointer;
    transition: all 0.3s;
    height: 100px;
  }

  .thumbnail img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .thumbnail:hover {
    transform: scale(1.05);
  }

  .thumbnail.active {
    border-color: #8b0000;
    box-shadow: 0 0 0 2px white, 0 0 0 4px #8b0000;
  }

  .slide-counter {
    text-align: center;
    color: #666;
    font-weight: bold;
    font-size: 1rem;
  }

  @media (max-width: 768px) {
    .main-image img {
      height: 300px;
    }

    .image-info {
      padding: 1rem;
    }

    .image-info h3 {
      font-size: 1.2rem;
    }

    .control-btn {
      width: 40px;
      height: 40px;
      font-size: 1.2rem;
    }

    .thumbnails {
      grid-template-columns: repeat(3, 1fr);
      gap: 0.5rem;
      padding: 0 0.5rem;
    }

    .thumbnail {
      height: 80px;
    }
  }
</style>
