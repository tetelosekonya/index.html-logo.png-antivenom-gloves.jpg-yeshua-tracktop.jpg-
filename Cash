<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cash Garments | Official Store</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Helvetica Neue', Arial, sans-serif;
    }

    :root {
      --black: #000000;
      --white: #FFFFFF;
      --grey: #1a1a1a;
      --accent: #E5E5E5;
    }

    body {
      background: var(--black);
      color: var(--white);
      line-height: 1.6;
    }

    header {
      background: var(--black);
      padding: 1rem 5%;
      border-bottom: 1px solid var(--grey);
      position: sticky;
      top: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .logo img {
      width: 40px;
      height: 40px;
      object-fit: contain;
    }

    .logo h1 {
      font-size: 1.5rem;
      font-weight: 800;
      letter-spacing: 1px;
    }

    .cart-btn {
      background: var(--white);
      color: var(--black);
      border: none;
      padding: 10px 20px;
      font-weight: 700;
      cursor: pointer;
      border-radius: 4px;
      position: relative;
    }

    .cart-count {
      position: absolute;
      top: -8px;
      right: -8px;
      background: #ff3b30;
      color: white;
      border-radius: 50%;
      width: 20px;
      height: 20px;
      font-size: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .hero {
      text-align: center;
      padding: 4rem 5% 2rem;
    }

    .hero img {
      width: 120px;
      margin-bottom: 1.5rem;
    }

    .hero h2 {
      font-size: 2.5rem;
      margin-bottom: 0.5rem;
      font-weight: 900;
    }

    .hero p {
      color: var(--accent);
      font-size: 1.1rem;
    }

    .products {
      padding: 2rem 5% 4rem;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }

    .product-card {
      background: var(--grey);
      border-radius: 8px;
      overflow: hidden;
      transition: transform 0.2s;
    }

    .product-card:hover {
      transform: translateY(-5px);
    }

    .product-img {
      width: 100%;
      height: 400px;
      object-fit: cover;
      background: #111;
    }

    .product-info {
      padding: 1.5rem;
    }

    .product-info h3 {
      font-size: 1.3rem;
      margin-bottom: 0.5rem;
    }

    .price {
      font-size: 1.5rem;
      font-weight: 700;
      margin: 1rem 0;
    }

    .add-cart {
      width: 100%;
      background: var(--white);
      color: var(--black);
      border: none;
      padding: 12px;
      font-weight: 700;
      cursor: pointer;
      border-radius: 4px;
      font-size: 1rem;
    }

    .add-cart:hover {
      background: var(--accent);
    }

    /* Cart Sidebar */
    .cart-sidebar {
      position: fixed;
      right: -400px;
      top: 0;
      width: 100%;
      max-width: 400px;
      height: 100vh;
      background: var(--grey);
      transition: right 0.3s ease;
      z-index: 200;
      display: flex;
      flex-direction: column;
      border-left: 1px solid #333;
    }

    .cart-sidebar.active {
      right: 0;
    }

    .cart-header {
      padding: 1.5rem;
      border-bottom: 1px solid #333;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .close-cart {
      background: none;
      border: none;
      color: var(--white);
      font-size: 1.5rem;
      cursor: pointer;
    }

    .cart-items {
      flex: 1;
      overflow-y: auto;
      padding: 1rem;
    }

    .cart-item {
      display: flex;
      gap: 1rem;
      margin-bottom: 1rem;
      padding-bottom: 1rem;
      border-bottom: 1px solid #333;
    }

    .cart-item img {
      width: 80px;
      height: 80px;
      object-fit: cover;
      border-radius: 4px;
    }

    .cart-footer {
      padding: 1.5rem;
      border-top: 1px solid #333;
    }

    .total {
      display: flex;
      justify-content: space-between;
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 1rem;
    }

    .checkout {
      width: 100%;
      background: var(--white);
      color: var(--black);
      border: none;
      padding: 15px;
      font-weight: 700;
      cursor: pointer;
      border-radius: 4px;
      font-size: 1rem;
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.7);
      z-index: 150;
      display: none;
    }

    .overlay.active {
      display: block;
    }

    footer {
      text-align: center;
      padding: 2rem 5%;
      border-top: 1px solid var(--grey);
      color: var(--accent);
    }

    @media (max-width: 768px) {
      .hero h2 { font-size: 2rem; }
      .products { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="overlay" id="overlay"></div>

  <header>
    <div class="logo">
      <img src="logo.png" alt="Cash Garments Logo">
      <h1>CASH GARMENTS</h1>
    </div>
    <button class="cart-btn" id="cartBtn">
      Cart <span class="cart-count" id="cartCount">0</span>
    </button>
  </header>

  <section class="hero">
    <img src="logo.png" alt="Cash Garments">
    <h2>Mainly made for individuals with motion</h2>
    <p>The home of streetwear & sportswear.</p>
  </section>

  <section class="products" id="products">
    <!-- Products loaded by JS -->
  </section>

  <div class="cart-sidebar" id="cartSidebar">
    <div class="cart-header">
      <h3>Your Cart</h3>
      <button class="close-cart" id="closeCart">&times;</button>
    </div>
    <div class="cart-items" id="cartItems">
      <p style="text-align: center; color: #888;">Your cart is empty</p>
    </div>
    <div class="cart-footer">
      <div class="total">
        <span>Total:</span>
        <span id="cartTotal">R0.00</span>
      </div>
      <button class="checkout" id="checkoutBtn">Checkout via WhatsApp
      <https://wa.me/27676619171>
    </div>
  </div>

  <footer>
    <p>&copy; 2026 Cash Garments. All rights reserved.</p>
  <script>
    // PRODUCT DATA
    const products = [
      {
        id: 1,
        name: "Antivenom Gloves",
        price: 249.99,
        image: "antivenom-gloves.jpg",
        desc: "Signature CG gloves with the Yeshua Cash Garments logo"
      },
      {
        id: 2,
        name: "Yeshua Sportswear Tracktop",
        price: 399.99,
        image: "yeshua-tracktop.jpg",
        desc: "Premium black tracktop with CG icon"
      }
    ];

    let cart = [];

    // DOM Elements
    const productsEl = document.getElementById('products');
    const cartBtn = document.getElementById('cartBtn');
    const cartSidebar = document.getElementById('cartSidebar');
    const closeCart = document.getElementById('closeCart');
    const overlay = document.getElementById('overlay');
    const cartItemsEl = document.getElementById('cartItems');
    const cartCount = document.getElementById('cartCount');
    const cartTotal = document.getElementById('cartTotal');
    const checkoutBtn = document.getElementById('checkoutBtn');

    // Render Products
    function renderProducts() {
      productsEl.innerHTML = products.map(product => `
        <div class="product-card">
          <img src="${product.image}" alt="${product.name}" class="product-img">
          <div class="product-info">
            <h3>${product.name}</h3>
            <p style="color: #aaa; font-size: 0.9rem;">${product.desc}</p>
            <div class="price">R${product.price.toFixed(2)}</div>
            <button class="add-cart" onclick="addToCart(${product.id})">Add to Cart</button>
          </div>
        </div>
      `).join('');
    }

    // Cart Functions
    function addToCart(id) {
      const product = products.find(p => p.id === id);
      const existing = cart.find(item => item.id === id);
      
      if (existing) {
        existing.qty++;
      } else {
        cart.push({...product, qty: 1});
      }
      updateCart();
      openCart();
    }

    function updateCart() {
      // Update count
      const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
      cartCount.textContent = totalQty;

      // Update items
      if (cart.length === 0) {
        cartItemsEl.innerHTML = '<p style="text-align: center; color: #888;">Your cart is empty</p>';
      } else {
        cartItemsEl.innerHTML = cart.map(item => `
          <div class="cart-item">
            <img src="${item.image}" alt="${item.name}">
            <div>
              <h4>${item.name}</h4>
              <p>R${item.price.toFixed(2)} x ${item.qty}</p>
              <button onclick="removeFromCart(${item.id})" style="background:none;border:none;color:#ff3b30;cursor:pointer;">Remove</button>
            </div>
          </div>
        `).join('');
      }

      // Update total
      const total = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
      cartTotal.textContent = `R${total.toFixed(2)}`;
    }

    function removeFromCart(id) {
      cart = cart.filter(item => item.id !== id);
      updateCart();
    }

    function openCart() {
      cartSidebar.classList.add('active');
      overlay.classList.add('active');
    }

    function closeCartFn() {
      cartSidebar.classList.remove('active');
      overlay.classList.remove('active');
    }

    // Checkout via WhatsApp
    function checkout() {
      if (cart.length === 0) return alert('Cart is empty');
      
      let message = `Hi Cash Garments! I want to order:%0A`;
      cart.forEach(item => {
        message += `• ${item.name} x${item.qty} - R${(item.price * item.qty).toFixed(2)}%0A`;
      });
      const total = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
      message += `%0ATotal: R${total.toFixed(2)}`;
      
      // Replace with your WhatsApp number
      const phone = "27676619171"; 
      window.open(`https://wa.me/${phone}?text=${message}`, '_blank');
    }

    // Event Listeners
    cartBtn.addEventListener('click', openCart);
    closeCart.addEventListener('click', closeCartFn);
    overlay.addEventListener('click', closeCartFn);
    checkoutBtn.addEventListener('click', checkout);

    // Init
    renderProducts();
  </script>
</body>
</html></html>