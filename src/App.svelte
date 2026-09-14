<script>
  import Navbar from './components/Navbar.svelte'
  import HomePage from './pages/HomePage.svelte'
  import BookingPage from './pages/BookingPage.svelte'
  import MenuPage from './pages/MenuPage.svelte'
  import GalleryPage from './pages/GalleryPage.svelte'
  import Footer from './components/Footer.svelte'

  let currentPage = 'home'

  function navigateTo(page) {
    currentPage = page
    window.scrollTo(0, 0)
  }
</script>

<Navbar on:navigate={(e) => navigateTo(e.detail)} />

<main>
  {#if currentPage === 'home'}
    <HomePage on:navigate={(e) => navigateTo(e.detail)} />
  {:else if currentPage === 'booking'}
    <BookingPage />
  {:else if currentPage === 'menu'}
    <MenuPage />
  {:else if currentPage === 'gallery'}
    <GalleryPage />
  {/if}
</main>

<Footer />

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f5f5f5;
  }

  :global(html) {
    scroll-behavior: smooth;
  }

  main {
    min-height: calc(100vh - 120px);
  }
</style>
