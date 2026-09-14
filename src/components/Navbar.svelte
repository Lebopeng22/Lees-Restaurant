<script>
  import { createEventDispatcher } from 'svelte'
  const dispatch = createEventDispatcher()

  let mobileMenuOpen = false

  function navigate(page) {
    dispatch('navigate', page)
    mobileMenuOpen = false
  }
</script>

<nav class="navbar">
  <div class="nav-container">
    <div class="logo">🍝 Lee's Restaurant</div>
    <button class="menu-toggle" on:click={() => mobileMenuOpen = !mobileMenuOpen}>
      ☰
    </button>
    <ul class="nav-menu" class:active={mobileMenuOpen}>
      <li><button on:click={() => navigate('home')} class="nav-btn">Home</button></li>
      <li><button on:click={() => navigate('menu')} class="nav-btn">Menu</button></li>
      <li><button on:click={() => navigate('gallery')} class="nav-btn">Gallery</button></li>
      <li><button on:click={() => navigate('booking')} class="nav-btn highlight">Book Table</button></li>
    </ul>
  </div>
</nav>

<style>
  .navbar {
    background-color: #8b0000;
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }

  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    font-size: 1.8rem;
    font-weight: bold;
    color: #fff;
    cursor: pointer;
  }

  .nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
    margin: 0;
    padding: 0;
  }

  .nav-btn {
    background: none;
    border: none;
    color: #fff;
    font-size: 1rem;
    cursor: pointer;
    transition: color 0.3s;
    padding: 0.5rem 1rem;
    border-radius: 4px;
  }

  .nav-btn:hover {
    color: #ffd700;
    background-color: rgba(255,255,255,0.1);
  }

  .nav-btn.highlight {
    background-color: #ffd700;
    color: #8b0000;
    font-weight: bold;
  }

  .nav-btn.highlight:hover {
    background-color: #ffed4e;
    color: #8b0000;
  }

  .menu-toggle {
    display: none;
    background: none;
    border: none;
    color: #fff;
    font-size: 1.5rem;
    cursor: pointer;
  }

  @media (max-width: 768px) {
    .menu-toggle {
      display: block;
    }

    .nav-menu {
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background-color: #8b0000;
      flex-direction: column;
      gap: 0;
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s;
    }

    .nav-menu.active {
      max-height: 300px;
    }

    .nav-menu li {
      border-bottom: 1px solid rgba(255,255,255,0.1);
    }

    .nav-btn {
      width: 100%;
      text-align: left;
      border-radius: 0;
    }
  }
</style>
