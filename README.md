<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Fiyinty Draping • Timeless Nigerian Elegance</title>
  <script src="https://js.paystack.co/v2/inline.js"></script>
  <style>
    :root {
      --gold: #d4af37;
      --dark: #0f0f0f;
      --card-bg: #1a1a1a;
      --text: #f0f0f0;
      --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * { margin:0; padding:0; box-sizing:border-box; }
    
    body {
      background: var(--dark);
      color: var(--text);
      font-family: 'Didot', 'Georgia', serif;
      line-height: 1.6;
      overflow-x: hidden;
    }

    .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }

    /* Header */
    header {
      height: 100vh;
      background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.9)), 
                  url('https://images.unsplash.com/photo-1583391733956-6c78276477e2?auto=format&fit=crop&q=80&w=1600') center/cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 0 20px;
    }

    .logo {
      font-size: clamp(3rem, 10vw, 5rem);
      font-weight: bold;
      letter-spacing: 8px;
      color: var(--gold);
      text-shadow: 0 0 30px rgba(212,175,55,0.4);
    }

    .tagline {
      font-size: clamp(1rem, 4vw, 1.4rem);
      color: #ccc;
      margin-bottom: 40px;
      text-transform: uppercase;
      letter-spacing: 2px;
    }

    /* Sticky Nav */
    nav {
      background: rgba(15,15,15,0.98);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 20px 0;
      border-bottom: 1px solid rgba(212,175,55,0.2);
      backdrop-filter: blur(10px);
    }

    nav .container {
      display: flex;
      justify-content: center;
      gap: 30px;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      transition: var(--transition);
    }

    nav a:hover { color: var(--gold); }

    /* Grid & Cards */
    section { padding: 100px 0; opacity: 0; transform: translateY(30px); transition: 1s ease; }
    section.visible { opacity: 1; transform: translateY(0); }

    h2 {
      text-align: center;
      font-size: clamp(2rem, 5vw, 2.8rem);
      margin-bottom: 50px;
      color: var(--gold);
      font-weight: 300;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
    }

    .product-card {
      background: var(--card-bg);
      border-radius: 4px;
      border: 1px solid #222;
      transition: var(--transition);
      display: flex;
      flex-direction: column;
    }

    .product-card:hover {
      border-color: var(--gold);
      transform: translateY(-10px);
    }

    .info { padding: 25px; text-align: center; flex-grow: 1; }
    .price { font-size: 1.4rem; color: var(--gold); margin: 15px 0; font-family: sans-serif; }

    /* Buttons */
    .btn {
      background: var(--gold);
      color: #000;
      padding: 12px 30px;
      border: none;
      border-radius: 2px;
      font-weight: bold;
      cursor: pointer;
      text-transform: uppercase;
      transition: var(--transition);
      width: 100%;
    }

    .btn:hover { background: #fff; letter-spacing: 1px; }

    /* Floating UI */
    .fab {
      position: fixed;
      right: 25px;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      z-index: 999;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }
    .chat-fab { bottom: 25px; background: #25D366; font-size: 24px; }
    .admin-fab { bottom: 100px; background: #333; font-size: 20px; color: var(--gold); }

    /* Chat Window */
    #chat-window {
      position: fixed;
      bottom: 95px;
      right: 25px;
      width: 320px;
      height: 400px;
      background: var(--card-bg);
      border: 1px solid var(--gold);
      border-radius: 12px;
      display: none;
      flex-direction: column;
      z-index: 1000;
      overflow: hidden;
    }
    .chat-header { background: var(--gold); color: black; padding: 15px; font-weight: bold; }
    .chat-body { flex: 1; padding: 15px; overflow-y: auto; font-size: 0.9rem; }
    .chat-input { padding: 10px; border-top: 1px solid #333; display: flex; }
    .chat-input input { flex: 1; padding: 8px; background: #222; border: none; color: white; border-radius: 4px; }

    /* Modal Styling */
    .modal {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.9);
      z-index: 2000;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .modal-content {
      background: var(--card-bg);
      padding: 30px;
      width: 100%;
      max-width: 500px;
      border: 1px solid var(--gold);
    }
    input, textarea {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      background: #222;
      border: 1px solid #444;
      color: white;
    }

    @media (max-width: 600px) {
      nav .container { gap: 15px; }
      nav a { font-size: 0.75rem; }
      section { padding: 60px 0; }
    }
  </style>
</head>
<body>

  <header>
    <div class="container">
      <div class="logo">FIYINTY</div>
      <div class="tagline">Draping Timeless Nigerian Elegance</div>
      <button class="btn" style="width:auto;" onclick="document.getElementById('shop').scrollIntoView({behavior:'smooth'})">
        Enter the Gallery
      </button>
    </div>
  </header>

  <nav id="navbar">
    <div class="container">
      <a href="#shop">Collection</a>
      <a href="#about">Our Story</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>

  <section id="shop">
    <div class="container">
      <h2>The Collection</h2>
      <div class="products" id="products-grid"></div>
    </div>
  </section>

  <section id="about">
    <div class="container" style="text-align:center;">
      <h2>Our Story</h2>
      <p style="max-width:800px; margin:0 auto; font-size:1.1rem; color: #aaa; font-style: italic;">
        "Fiyinty Draping was born from a desire to preserve the majesty of Nigerian textiles. 
        Each garment is more than fabric—it is a vessel for history, handwoven with pride for the modern monarch."
      </p>
    </div>
  </section>

  <div class="fab admin-fab" onclick="toggleModal('admin-modal', true)">⚙️</div>
  <div class="fab chat-fab" onclick="toggleChat()">💬</div>

  <div id="chat-window">
    <div class="chat-header">Fiyinty Assistant</div>
    <div class="chat-body" id="chat-msgs">
      <div style="background:#333; padding:10px; border-radius:8px; margin-bottom:10px;">
        Welcome to Fiyinty Draping. How may we assist your elegance today?
      </div>
    </div>
    <div class="chat-input">
      <input type="text" id="user-msg" placeholder="Ask a question..." onkeypress="handleChat(event)">
    </div>
  </div>

  <div id="admin-modal" class="modal">
    <div class="modal-content">
      <h2 id="admin-title">Admin Access</h2>
      <div id="login-gate">
        <input type="password" id="admin-pass" placeholder="Enter Security Code">
        <button class="btn" onclick="login()">Access Dashboard</button>
      </div>
      <div id="dashboard" style="display:none;">
        <h3>Inventory Management</h3>
        <input id="new-name" placeholder="Item Name">
        <input id="new-price" type="number" placeholder="Price (₦)">
        <textarea id="new-desc" placeholder="Description"></textarea>
        <button class="btn" onclick="addItem()">Add to Gallery</button>
        <button class="btn" onclick="clearData()" style="background:#555; margin-top:10px;">Reset Inventory</button>
      </div>
      <button onclick="toggleModal('admin-modal', false)" style="background:none; border:none; color:#aaa; margin-top:15px; cursor:pointer; width:100%;">Close</button>
    </div>
  </div>

  <script>
    // --- APP STATE ---
    const ADMIN_KEY = "fiyinty2026";
    let products = JSON.parse(localStorage.getItem("fiyinty_db")) || [
      { name: "Luxury Aso-Oke Agbada", price: 125000, desc: "Handwoven premium metallic thread aso-oke." },
      { name: "Elegant Lace Iro & Buba", price: 85000, desc: "Intricate laser-cut Swiss lace with silk underlay." },
      { name: "Suede Embellished Kaftan", price: 65000, desc: "Minimalist luxury for the modern man." }
    ];

    // --- INITIALIZE ---
    window.onload = () => {
      render();
      checkScroll();
    };

    // --- CORE FUNCTIONS ---
    function render() {
      const grid = document.getElementById("products-grid");
      grid.innerHTML = products.map((p, i) => `
        <div class="product-card">
          <div style="height:350px; background:#111; display:flex; align-items:center; justify-content:center; color:#333; font-size:0.8rem; letter-spacing:2px;">[REPRESENTATIVE IMAGE]</div>
          <div class="info">
            <h3 style="color:var(--gold); font-weight:400;">${p.name}</h3>
            <p style="font-size:0.9rem; color:#888; margin-top:5px;">${p.desc}</p>
            <div class="price">₦${p.price.toLocaleString()}</div>
            <button class="btn" onclick="initiatePayment(${i})">Acquire Piece</button>
          </div>
        </div>
      `).join('');
    }

    function initiatePayment(index) {
      const item = products[index];
      const handler = PaystackPop.setup({
        key: "pk_test_YOUR_ACTUAL_KEY", // Get this from paystack.com
        email: "client@fiyinty.com",
        amount: item.price * 100, // Amount in kobo
        currency: "NGN",
        callback: (res) => alert("Order Confirmed! Ref: " + res.reference),
        onClose: () => console.log("Window closed")
      });
      handler.openIframe();
    }

    // --- ADMIN LOGIC ---
    function toggleModal(id, show) {
      document.getElementById(id).style.display = show ? 'flex' : 'none';
    }

    function login() {
      const pass = document.getElementById("admin-pass").value;
      if (pass === ADMIN_KEY) {
        document.getElementById("login-gate").style.display = "none";
        document.getElementById("dashboard").style.display = "block";
        document.getElementById("admin-title").innerText = "Fiyinty Dashboard";
      } else {
        alert("Access Denied.");
      }
    }

    function addItem() {
      const name = document.getElementById("new-name").value;
      const price = parseInt(document.getElementById("new-price").value);
      const desc = document.getElementById("new-desc").value;

      if (name && price) {
        products.push({ name, price, desc });
        localStorage.setItem("fiyinty_db", JSON.stringify(products));
        render();
        alert("Gallery Updated.");
      }
    }

    function clearData() {
      if(confirm("Wipe all products?")) {
        localStorage.removeItem("fiyinty_db");
        location.reload();
      }
    }

    // --- CHAT LOGIC ---
    function toggleChat() {
      const win = document.getElementById("chat-window");
      win.style.display = (win.style.display === 'flex') ? 'none' : 'flex';
    }

    function handleChat(e) {
      if (e.key === 'Enter') {
        const input = document.getElementById("user-msg");
        const chatBody = document.getElementById("chat-msgs");
        if (!input.value) return;

        chatBody.innerHTML += `<div style="text-align:right; margin:10px 0; color:var(--gold);">${input.value}</div>`;
        
        setTimeout(() => {
          chatBody.innerHTML += `<div style="background:#333; padding:10px; border-radius:8px; margin-bottom:10px;">I am connecting you with our head stylist on WhatsApp for personalized measurement...</div>`;
          chatBody.scrollTop = chatBody.scrollHeight;
          
          setTimeout(() => {
            window.open(`https://wa.me/234YOURNUMBER?text=Hello, I need help with: ${input.value}`, "_blank");
          }, 1500);
        }, 800);
        
        input.value = "";
      }
    }

    // --- ANIMATIONS ---
    function checkScroll() {
      document.querySelectorAll('section').forEach(sec => {
        const top = sec.getBoundingClientRect().top;
        if (top < window.innerHeight * 0.85) sec.classList.add('visible');
      });
    }
    window.addEventListener('scroll', checkScroll);
  </script>
</body>
</html>
