<!DOCTYPE html>
<html lang="pt-br" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>L'Essence Lingerie - Elegância e Sensualidade</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.3.2/dist/tailwind.min.css" rel="stylesheet" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat&display=swap" rel="stylesheet" />
  <script src="https://unpkg.com/feather-icons"></script>
  <style>
    body {
      font-family: 'Montserrat', sans-serif;
      color: #1f1f1f;
      background-color: #fff;
    }
    h1, h2, h3, h4 {
      font-family: 'Playfair Display', serif;
    }
    header {
      backdrop-filter: saturate(180%) blur(20px);
      background-color: rgba(255 255 255 / 0.85);
      border-bottom: 1px solid #eee;
      z-index: 100;
    }
    nav ul li:hover > ul {
      display: block;
    }
    nav ul ul {
      display: none;
      position: absolute;
      background: white;
      border: 1px solid #ddd;
      margin-top: 0.5rem;
      padding: 0.5rem 0;
      border-radius: 0.25rem;
      min-width: 10rem;
      box-shadow: 0 2px 8px rgb(0 0 0 / 0.1);
      z-index: 200;
    }
    nav ul ul li {
      padding: 0.5rem 1rem;
      white-space: nowrap;
    }
    nav ul ul li:hover {
      background-color: #f9e4ea;
      cursor: pointer;
    }
    .btn-primary {
      background-color: #d6336c;
      color: white;
      transition: background-color 0.3s ease;
    }
    .btn-primary:hover {
      background-color: #a92754;
    }
  </style>
</head>
<body>

<!-- HEADER -->
<header class="fixed w-full top-0 left-0 shadow-sm">
  <div class="container mx-auto flex items-center justify-between px-8 py-4">
    <a href="#" class="text-3xl font-playfair text-pink-700 font-bold tracking-wide">L'Essence</a>
    <nav>
      <ul class="flex space-x-8 text-gray-700 font-semibold text-sm relative">
        <li><a href="#hero" class="hover:text-pink-700 transition">Início</a></li>
        <li class="relative group">
          <a href="#categorias" class="hover:text-pink-700 transition">Categorias</a>
          <ul class="absolute left-0 top-full mt-2 hidden group-hover:block">
            <li><a href="#seducao" class="block hover:text-pink-700">Sedução Clássica</a></li>
            <li><a href="#conforto" class="block hover:text-pink-700">Conforto Sexy</a></li>
            <li><a href="#renda" class="block hover:text-pink-700">Renda de Luxo</a></li>
            <li><a href="#noite" class="block hover:text-pink-700">Noite Misteriosa</a></li>
          </ul>
        </li>
        <li><a href="#produtos" class="hover:text-pink-700 transition">Produtos</a></li>
        <li><a href="#contato" class="hover:text-pink-700 transition">Contato</a></li>
      </ul>
    </nav>
    <button id="btn-cart" class="relative focus:outline-none" aria-label="Abrir carrinho">
      <i data-feather="shopping-cart" class="w-6 h-6 text-pink-700"></i>
      <span id="cart-count" class="absolute -top-2 -right-2 bg-pink-700 text-white rounded-full text-xs font-semibold px-2">0</span>
    </button>
  </div>
</header>

<!-- HERO -->
<section id="hero" class="h-screen flex items-center justify-center text-center px-8" style="background: url('https://images.unsplash.com/photo-1514996937319-344454492b37?auto=format&fit=crop&w=1470&q=80') center/cover no-repeat;">
  <div class="bg-white bg-opacity-60 p-12 max-w-2xl rounded-lg shadow-lg">
    <h1 class="text-5xl font-playfair font-bold mb-6 text-pink-700">L'Essence Lingerie</h1>
    <p class="mb-8 text-gray-800 text-lg leading-relaxed font-medium">Elegância, conforto e sensualidade em cada peça.</p>
    <a href="#produtos" class="btn-primary px-10 py-4 text-xl rounded-lg inline-block font-semibold shadow-lg hover:shadow-xl">Ver Coleção</a>
  </div>
</section>

<!-- PRODUTOS (exemplo simplificado com 1 produto) -->
<section id="produtos" class="py-24 px-8 bg-pink-50">
  <div class="container mx-auto max-w-6xl">
    <h2 class="text-4xl font-playfair font-bold mb-16 text-center text-pink-700">Coleção Destaque</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-12">
      <article class="bg-white rounded-lg shadow-lg hover:shadow-2xl transition overflow-hidden flex flex-col">
        <img src="https://images.unsplash.com/photo-1618354691057-5c2d379dd607?auto=format&fit=crop&w=600&q=80" alt="Conjunto Elegance" class="h-96 object-cover w-full" />
        <div class="p-6 flex flex-col flex-grow">
          <h3 class="text-2xl font-playfair mb-3 text-gray-900">Conjunto Elegance</h3>
          <p class="text-pink-700 text-xl font-semibold mb-6">R$ 119,90</p>
          <button class="btn-primary mt-auto px-6 py-3 rounded-lg font-semibold" data-name="Conjunto Elegance" data-price="119.90" onclick="addToCart(event)">Adicionar ao Carrinho</button>
        </div>
      </article>
    </div>
  </div>
</section>

<!-- CARRINHO -->
<div id="cart-sidebar" class="fixed top-0 right-0 w-96 h-full bg-white shadow-xl transform translate-x-full transition-transform z-50 flex flex-col" aria-label="Carrinho de compras">
  <header class="flex justify-between items-center p-6 border-b border-gray-200">
    <h3 class="text-xl font-playfair font-bold text-pink-700">Seu Carrinho</h3>
    <button id="close-cart" class="text-gray-600 hover:text-pink-700 focus:outline-none"><i data-feather="x" class="w-6 h-6"></i></button>
  </header>
  <div id="cart-items" class="flex-grow overflow-y-auto p-6 space-y-4">
    <p class="text-gray-500">Seu carrinho está vazio.</p>
  </div>
  <footer class="p-6 border-t border-gray-200">
    <button onclick="finalizarCompra()" class="btn-primary w-full py-3 rounded-lg font-semibold">Finalizar Compra</button>
  </footer>
</div>

<!-- SCRIPTS -->
<script>
  feather.replace();

  const btnCart = document.getElementById('btn-cart');
  const cartSidebar = document.getElementById('cart-sidebar');
  const closeCart = document.getElementById('close-cart');
  const cartItems = document.getElementById('cart-items');
  const cartCount = document.getElementById('cart-count');

  let cart = JSON.parse(localStorage.getItem('cart')) || [];

  function saveCart() {
    localStorage.setItem('cart', JSON.stringify(cart));
    updateCartUI();
  }

  function updateCartUI() {
    cartCount.textContent = cart.length;
    cartItems.innerHTML = '';
    if (cart.length === 0) {
      cartItems.innerHTML = '<p class="text-gray-500">Seu carrinho está vazio.</p>';
      return;
    }

    cart.forEach((item, index) => {
      const div = document.createElement('div');
      div.classList = 'flex justify-between items-center border-b pb-4';
      div.innerHTML = `
        <div>
          <h4 class="text-md font-semibold text-pink-700">${item.name}</h4>
          <p class="text-sm text-gray-600">R$ ${item.price.toFixed(2)}</p>
        </div>
        <button onclick="removeFromCart(${index})" class="text-red-500 hover:text-red-700">Remover</button>
      `;
      cartItems.appendChild(div);
    });
  }

  function addToCart(e) {
    const btn = e.currentTarget;
    const name = btn.dataset.name;
    const price = parseFloat(btn.dataset.price);
    cart.push({ name, price });
    saveCart();
    btn.textContent = 'Adicionado!';
    setTimeout(() => { btn.textContent = 'Adicionar ao Carrinho'; }, 1500);
  }

  function removeFromCart(index) {
    cart.splice(index, 1);
    saveCart();
  }

  function finalizarCompra() {
    alert('Compra finalizada com sucesso!');
    cart = [];
    saveCart();
  }

  btnCart.addEventListener('click', () => cartSidebar.classList.remove('translate-x-full'));
  closeCart.addEventListener('click', () => cartSidebar.classList.add('translate-x-full'));

  updateCartUI();
</script>

</body>
</html>
