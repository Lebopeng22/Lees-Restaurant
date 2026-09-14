<script>
  import { fade } from 'svelte/transition'

  let activeCategory = 'starters'

  const menu = {
    starters: [
      { name: 'Italian Mini Meatballs', description: 'Tender homemade meatballs in marinara sauce', price: '$9.99' },
      { name: 'Fried Ravioli', description: 'Crispy fried ravioli with ricotta filling, served with marinara', price: '$8.99' },
      { name: 'Chicken Livers', description: 'Sautéed chicken livers with garlic and white wine', price: '$10.99' }
    ],
    salads: [
      { name: 'Greek Salad', description: 'Fresh tomatoes, cucumbers, olives, and feta cheese', price: '$11.99' },
      { name: 'Italian Salad', description: 'Mixed greens with Italian dressing and Parmesan', price: '$10.99' },
      { name: 'Chicken Salad with Mango', description: 'Grilled chicken, fresh mango, and mixed greens', price: '$13.99' }
    ],
    mains: [
      { name: 'Rump Steak', description: 'Tender rump steak served with crispy fries', price: '$21.99' },
      { name: 'T-Bone', description: 'Premium T-bone steak cooked to perfection with fries', price: '$28.99' },
      { name: 'Pork Ribs', description: 'Slow-cooked pork ribs with BBQ sauce and fries', price: '$19.99' },
      { name: 'Pork Chops', description: 'Grilled pork chops with herbs and fries', price: '$17.99' }
    ],
    pasta: [
      { name: 'Bolognese', description: 'Traditional spaghetti with rich meat sauce', price: '$14.99' },
      { name: 'Spaghetti Meatballs', description: 'Spaghetti topped with homemade meatballs and marinara', price: '$15.99' },
      { name: 'Lasagne', description: 'Layered pasta with meat sauce and melted cheese', price: '$16.99' }
    ]
  }

  const categories = [
    { key: 'starters', label: 'Starters' },
    { key: 'salads', label: 'Salads' },
    { key: 'mains', label: 'Meat Mains' },
    { key: 'pasta', label: 'Pasta' }
  ]

  function downloadPDF() {
    alert('Menu PDF download functionality would be implemented with a PDF library like jsPDF')
  }
</script>

<div class="menu-page">
  <div class="container">
    <h1>Our Menu</h1>
    <p class="menu-subtitle">Freshly prepared Italian cuisine, made to order</p>

    <div class="menu-controls">
      <div class="category-buttons">
        {#each categories as category}
          <button
            class="category-btn"
            class:active={activeCategory === category.key}
            on:click={() => activeCategory = category.key}
          >
            {category.label}
          </button>
        {/each}
      </div>
      <button class="download-btn" on:click={downloadPDF}>📥 Download Menu</button>
    </div>

    <div class="menu-items">
      {#each menu[activeCategory] as item (item.name)}
        <div class="menu-item" in:fade>
          <div class="item-header">
            <h3>{item.name}</h3>
            <span class="price">{item.price}</span>
          </div>
          <p class="description">{item.description}</p>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .menu-page {
    background: linear-gradient(135deg, #fff 0%, #f9f9f9 100%);
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

  .menu-subtitle {
    text-align: center;
    color: #666;
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }

  .menu-controls {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .category-buttons {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
  }

  .category-btn {
    padding: 0.75rem 1.5rem;
    border: 2px solid #8b0000;
    background: white;
    color: #8b0000;
    border-radius: 25px;
    cursor: pointer;
    font-weight: 600;
    transition: all 0.3s;
  }

  .category-btn:hover {
    background-color: rgba(139, 0, 0, 0.1);
  }

  .category-btn.active {
    background-color: #8b0000;
    color: white;
  }

  .download-btn {
    padding: 0.75rem 1.5rem;
    background: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%);
    color: #8b0000;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    font-weight: 600;
    transition: all 0.3s;
  }

  .download-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(255, 215, 0, 0.3);
  }

  .menu-items {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
  }

  .menu-item {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    border-left: 4px solid #8b0000;
    transition: all 0.3s;
  }

  .menu-item:hover {
    transform: translateY(-4px);
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.15);
  }

  .item-header {
    display: flex;
    justify-content: space-between;
    align-items: start;
    gap: 1rem;
    margin-bottom: 0.5rem;
  }

  .menu-item h3 {
    color: #8b0000;
    margin: 0;
    font-size: 1.2rem;
  }

  .price {
    color: #ffd700;
    font-weight: bold;
    font-size: 1.1rem;
    white-space: nowrap;
  }

  .description {
    color: #666;
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0;
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 2rem;
    }

    .menu-controls {
      flex-direction: column;
      align-items: stretch;
    }

    .category-buttons {
      width: 100%;
      justify-content: center;
    }

    .download-btn {
      width: 100%;
    }

    .menu-items {
      grid-template-columns: 1fr;
    }
  }
</style>
