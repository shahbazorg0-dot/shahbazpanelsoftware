<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Mobile Panel Shop — Buy & Sell</title>
  <style>
    :root{
      --bg:#f6fbfb; --card:#ffffff; --muted:#6b7280; --accent:#0ea5a4; --accent-dark:#0b8b86;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:Inter,system-ui,Arial,Helvetica,sans-serif;background:var(--bg);color:#111}
    .wrap{max-width:1100px;margin:24px auto;padding:18px}
    header{display:flex;flex-wrap:wrap;justify-content:space-between;align-items:center;gap:12px;background:linear-gradient(90deg,var(--accent),var(--accent-dark));padding:18px;border-radius:10px;color:#fff}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:10px;background:#fff;color:var(--accent-dark);display:flex;align-items:center;justify-content:center;font-weight:800}
    header h1{margin:0;font-size:1.1rem}
    nav a{color:#fff;text-decoration:none;margin-left:12px;font-weight:600}
    main{display:grid;grid-template-columns:1fr;gap:18px;margin-top:18px}
    @media(min-width:980px){main{grid-template-columns:340px 1fr}}
    .card{background:var(--card);padding:14px;border-radius:10px;box-shadow:0 8px 22px rgba(8,10,15,0.06)}
    h2{margin:0 0 8px 0;color:var(--accent)}
    label{display:block;font-size:13px;color:var(--muted);margin-bottom:6px}
    input[type=text],input[type=number],input[type=file],select,textarea{width:100%;padding:8px;border:1px solid #e6eef0;border-radius:8px;font-size:14px}
    button.btn{background:var(--accent);color:#fff;border:0;padding:9px 12px;border-radius:8px;cursor:pointer;font-weight:700}
    .ghost{background:transparent;border:1px solid #e6eef0;color:var(--muted);padding:8px 10px;border-radius:8px}
    .left-col{display:flex;flex-direction:column;gap:12px}
    .services .svc{display:flex;justify-content:space-between;align-items:center;padding:10px;border-radius:8px;border:1px solid #eef6f5;background:#f0fdf9}
    .products{display:grid;grid-template-columns:1fr;gap:12px}
    @media(min-width:680px){.products{grid-template-columns:repeat(2,1fr)}}
    .product{display:flex;gap:12px;border-radius:10px;overflow:hidden;border:1px solid #eef6f6;background:#fff}
    .product img{width:160px;height:120px;object-fit:cover}
    .meta{padding:10px;flex:1}
    .meta h3{margin:0;font-size:16px}
    .meta p{margin:6px 0;color:var(--muted);font-size:13px}
    .price{font-weight:800;color:var(--accent)}
    .actions{display:flex;gap:8px;align-items:center;margin-top:8px}
    .cart{margin-top:12px}
    .cart-item{display:flex;justify-content:space-between;padding:8px;border-radius:8px;border:1px solid #f1f5f9;margin-bottom:8px;background:#fff}
    .cart-summary{display:flex;justify-content:space-between;align-items:center;margin-top:8px}
    .small{font-size:13px;color:var(--muted)}
    .link{color:var(--accent);text-decoration:none}
    footer{margin-top:18px;text-align:center;color:var(--muted);font-size:13px}
    .controls{display:flex;gap:8px;flex-wrap:wrap}
    .copyBtn{background:#111827;color:#fff;padding:8px;border-radius:8px;border:0;cursor:pointer}
    .orderLinkBox{word-break:break-all;background:#f8fafc;padding:8px;border-radius:8px;border:1px dashed #cbd5e1}
    .top-actions{display:flex;gap:8px;align-items:center}
    .muted-note{font-size:12px;color:var(--muted);margin-top:6px}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo">MS</div>
        <div>
          <h1>Mobile Panel Shop</h1>
          <p class="small">Buy & Sell panels · Unlock services · Shareable orders</p>
        </div>
      </div>

      <nav>
        <a href="#products">Products</a>
        <a href="#add">Add Product</a>
        <a href="#unlock">Unlock</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <!-- LEFT: Add product, services, social -->
      <aside class="card left-col">
        <div>
          <h2 id="add">➕ Add / Edit Product</h2>
          <p class="small">Upload product image. For editing: click Edit on a product (it will populate the form).</p>

          <form id="addForm">
            <label>Product Title</label>
            <input id="title" type="text" placeholder="e.g. iPhone 11 Panel" required>

            <label>Category</label>
            <select id="category"><option>Panel</option><option>Software</option><option>Accessory</option></select>

            <label>Price (PKR)</label>
            <input id="price" type="number" placeholder="e.g. 12000" required>

            <label>Quantity</label>
            <input id="qty" type="number" value="1" min="1">

            <label>Product Image (upload / change)</label>
            <input id="imageFile" type="file" accept="image/*">

            <div style="display:flex;gap:8px;margin-top:8px">
              <button class="btn" type="submit">Save Product</button>
              <button id="resetDemo" type="button" class="ghost">Reset Demo</button>
            </div>
            <div class="muted-note">Products saved locally in your browser (localStorage). To publish publicly, host this file on Netlify / GitHub Pages / Vercel.</div>
          </form>
        </div>

        <div>
          <h2 id="unlock">🔓 Mobile Software Unlock</h2>
          <p class="small">Click Order to send a WhatsApp message to the selected number.</p>
          <div class="services">
            <div class="svc"><div><strong>Network Unlock</strong><div class="small">Permanent unlock</div></div><div><strong>PKR 2000</strong><div><a class="link svc-order" data-name="Network Unlock" data-price="2000">Order</a></div></div></div>
            <div class="svc"><div><strong>FRP Removal</strong><div class="small">Google account unlock</div></div><div><strong>PKR 1500</strong><div><a class="link svc-order" data-name="FRP Removal" data-price="1500">Order</a></div></div></div>
            <div class="svc"><div><strong>IMEI Repair</strong><div class="small">Software IMEI</div></div><div><strong>PKR 3500</strong><div><a class="link svc-order" data-name="IMEI Repair" data-price="3500">Order</a></div></div></div>
          </div>
        </div>

        <div>
          <h2 id="contact">📞 Social & Contact</h2>
          <p class="small">Customers can message you directly via WhatsApp. Choose default number below for outgoing messages.</p>
          <div class="small"><strong>+923462071265</strong><br><strong>+923312199771</strong></div>

          <label style="margin-top:8px">Default WhatsApp number (for orders)</label>
          <select id="waNumber" style="margin-bottom:8px"><option value="923462071265">+923462071265</option><option value="923312199771">+923312199771</option></select>

          <label>Your public website link (optional)</label>
          <input id="publicUrl" type="text" placeholder="https://your-site.example.com (optional)" />

          <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:8px">
            <a id="fbLink" class="ghost link" href="#" target="_blank">Facebook</a>
            <a id="waLink" class="ghost link" href="#" target="_blank">WhatsApp</a>
            <a id="ytLink" class="ghost link" href="#" target="_blank">YouTube</a>
          </div>
          <div class="muted-note">If you host this file publicly, paste its URL above so Share buttons use that link.</div>
        </div>
      </aside>

      <!-- RIGHT: Products & cart -->
      <section>
        <div class="card">
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div>
              <h2 id="products">🛒 Products</h2>
              <div class="small" id="itemsCount">0 items</div>
            </div>
            <div class="top-actions">
              <button id="shareShop" class="ghost">Share Shop</button>
              <button id="openCart" class="ghost">Open Cart</button>
            </div>
          </div>

          <div id="productGrid" class="products" style="margin-top:12px"></div>
        </div>

        <div class="card cart" style="margin-top:12px">
          <h2>🧾 Cart & Checkout</h2>
          <div id="cartList" class="small">Cart is empty.</div>
          <div class="cart-summary">
            <div class="small">Total:</div>
            <div style="font-weight:800">PKR <span id="cartTotal">0</span></div>
          </div>

          <div style="display:flex;gap:8px;margin-top:12px;flex-wrap:wrap">
            <button id="checkoutWhatsApp" class="btn">Order via WhatsApp</button>
            <button id="checkoutSite" class="btn">Order on Website (Get Link)</button>
            <button id="clearCart" class="ghost">Clear Cart</button>
          </div>

          <div id="orderResult" style="margin-top:12px;display:none">
            <p class="small">Shareable order link:</p>
            <div class="orderLinkBox" id="orderLink"></div>
            <div style="margin-top:8px">
              <button id="copyLink" class="copyBtn">Copy Link</button>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div class="small">Replace Facebook/YouTube links above if you have your pages. Payments not integrated — orders via WhatsApp or shared link.</div>
      <div style="margin-top:6px;font-size:12px">© 2025 Mobile Panel Shop</div>
    </footer>
  </div>

  <script>
    // ====== CONFIG: change these defaults if you want ======
    const CONFIG = {
      facebookPage: 'https://www.facebook.com/',
      youtubeChannel: 'https://www.youtube.com/',
      fallbackWa: '923462071265'
    };

    // ====== localStorage keys ======
    const KEY_PRODUCTS = 'mp_products_v1';
    const KEY_CART = 'mp_cart_v1';

    // ====== default demo products ======
    const defaultProducts = [
      { id: 1, title: 'iPhone 11 Panel', category: 'Panel', price: 12000, qty: 5, img: 'https://via.placeholder.com/400x300?text=iPhone+11+Panel' },
      { id: 2, title: 'Samsung S9 Panel', category: 'Panel', price: 8000, qty: 3, img: 'https://via.placeholder.com/400x300?text=Samsung+S9+Panel' }
    ];

    // ====== helpers ======
    const $ = id => document.getElementById(id);
    function save(key,val){ localStorage.setItem(key, JSON.stringify(val)); }
    function load(key,fallback){ const v = localStorage.getItem(key); return v ? JSON.parse(v) : fallback; }
    function base64Encode(str){ return btoa(unescape(encodeURIComponent(str))); }
    function base64Decode(b64){ return decodeURIComponent(escape(atob(b64))); }
    function escapeHtml(s){ return String(s||'').replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;'); }

    // ====== state ======
    let products = load(KEY_PRODUCTS, defaultProducts.slice());
    let cart = load(KEY_CART, []);

    // ====== elements ======
    const productGrid = $('productGrid'), itemsCount = $('itemsCount');
    const cartList = $('cartList'), cartTotal = $('cartTotal');
    const waNumberSelect = $('waNumber'), publicUrlInput = $('publicUrl');

    // set social links initial
    $('fbLink').href = CONFIG.facebookPage;
    $('ytLink').href = CONFIG.youtubeChannel;
    $('waLink').href = `https://wa.me/${CONFIG.fallbackWa}`;

    // ====== render products ======
    function renderProducts(){
      productGrid.innerHTML = '';
      products.forEach(p => {
        const div = document.createElement('div'); div.className = 'product';
        div.innerHTML = `
          <img src="${p.img || 'https://via.placeholder.com/400x300?text=No+Image'}" alt="${escapeHtml(p.title)}">
          <div class="meta">
            <h3>${escapeHtml(p.title)}</h3>
            <p class="small">${escapeHtml(p.category)} · ${escapeHtml(p.qty || 1)} pcs</p>
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div><div class="price">PKR ${Number(p.price)}</div></div>
              <div class="actions">
                <button class="btn" onclick="addToCart(${p.id})">Add to Cart</button>
                <button class="ghost" onclick="editProduct(${p.id})">Edit</button>
                <button class="ghost" onclick="deleteProduct(${p.id})">Delete</button>
                <a class="link" href="https://wa.me/${waNumberSelect.value || CONFIG.fallbackWa}?text=${encodeURIComponent('Hi, is '+p.title+' available? ID:'+p.id)}" target="_blank">Contact</a>
              </div>
            </div>
          </div>
        `;
        productGrid.appendChild(div);
      });
      itemsCount.textContent = products.length + ' items';
    }

    // ====== cart functions ======
    function renderCart(){
      if(cart.length === 0){
        cartList.innerHTML = 'Cart is empty.';
        cartTotal.textContent = '0';
        return;
      }
      cartList.innerHTML = '';
      let total = 0;
      cart.forEach((c, idx) => {
        total += Number(c.price);
        const node = document.createElement('div'); node.className = 'cart-item';
        node.innerHTML = `<div><strong>${escapeHtml(c.title)}</strong><div class="small">PKR ${c.price} · ${c.qty||1} pc</div></div><div><button class="ghost" onclick="removeFromCart(${idx})">Remove</button></div>`;
        cartList.appendChild(node);
      });
      cartTotal.textContent = total;
    }

    window.addToCart = function(productId){
      const p = products.find(x => x.id === productId);
      if(!p){ alert('Product not found'); return; }
      cart.push({...p});
      save(KEY_CART, cart);
      renderCart();
      alert('Added to cart');
    };

    window.removeFromCart = function(idx){
      cart.splice(idx,1); save(KEY_CART,cart); renderCart();
    };

    $('clearCart').addEventListener('click', ()=>{ if(!confirm('Clear cart?')) return; cart=[]; save(KEY_CART,cart); renderCart(); });

    // ====== checkout whatsapp ======
    $('checkoutWhatsApp').addEventListener('click', ()=>{
      if(cart.length === 0){ alert('Cart empty'); return; }
      const number = waNumberSelect.value || CONFIG.fallbackWa;
      const items = cart.map(i => `${i.title} (PKR ${i.price})`).join(', ');
      const msg = `Hello, I want to order: ${items}.`;
      window.open(`https://wa.me/${number}?text=${encodeURIComponent(msg)}`, '_blank');
    });

    // ====== checkout on-site -> shareable order link ======
    $('checkoutSite').addEventListener('click', ()=>{
      if(cart.length === 0){ alert('Cart empty'); return; }
      const name = prompt('Enter your name for the order:') || 'Customer';
      const phone = prompt('Enter contact number (e.g. 03XXXXXXXXX):') || '';
      const address = prompt('Enter address (optional):') || '';
      const order = {
        id: Date.now(),
        name, phone, address,
        items: cart.map(i => ({ title: i.title, price: i.price, qty: i.qty || 1 })),
        total: cart.reduce((s, it) => s + Number(it.price), 0),
        time: new Date().toISOString()
      };
      const json = JSON.stringify(order);
      const encoded = base64Encode(json);
      const base = publicUrlInput.value.trim() || location.origin + location.pathname;
      const orderUrl = (base.endsWith('/') ? base.slice(0,-1) : base) + '?order=' + encodeURIComponent(encoded);
      $('orderResult').style.display = 'block';
      $('orderLink').textContent = orderUrl;
      $('copyLink').onclick = ()=>{ navigator.clipboard.writeText(orderUrl).then(()=>alert('Link copied')); };
      // clear cart after creating order link
      cart = []; save(KEY_CART, cart); renderCart();
      alert('Order link created — copy & share it with seller or customer.');
    });

    // ====== copy & share shop ======
    $('shareShop').addEventListener('click', ()=>{
      const base = publicUrlInput.value.trim() || location.href;
      if(navigator.share){
        navigator.share({ title: 'Mobile Panel Shop', text: 'Check my shop', url: base }).catch(()=>{ /* ignore */ });
      } else {
        prompt('Copy this link to share', base);
      }
    });

    // ====== product add/edit/delete ======
    let editingId = null;
    $('addForm').addEventListener('submit', (e)=>{
      e.preventDefault();
      const t = $('title').value.trim();
      const c = $('category').value;
      const p = Number($('price').value) || 0;
      const q = Number($('qty').value) || 1;
      const file = $('imageFile').files[0];

      if(!t || !p){ alert('Title and price required'); return; }

      function finalize(imgData){
        if(editingId){
          // replace editing product
          const idx = products.findIndex(x => x.id === editingId);
          if(idx !== -1){
            products[idx] = { id: editingId, title: t, category: c, price: p, qty: q, img: imgData };
          } else {
            products.unshift({ id: Date.now(), title: t, category: c, price: p, qty: q, img: imgData });
          }
          editingId = null;
        } else {
          products.unshift({ id: Date.now(), title: t, category: c, price: p, qty: q, img: imgData });
        }
        save(KEY_PRODUCTS, products);
        renderProducts();
        $('addForm').reset();
      }

      if(file){
        const reader = new FileReader();
        reader.onload = (ev) => finalize(ev.target.result);
        reader.readAsDataURL(file);
      } else {
        // if editing and no new file chosen, keep previous image if exists
        if(editingId){
          const existing = products.find(x=>x.id===editingId);
          const img = existing ? existing.img : '';
          finalize(img);
        } else {
          finalize('');
        }
      }
    });

    window.editProduct = function(id){
      const p = products.find(x=>x.id===id);
      if(!p) return;
      $('title').value = p.title; $('category').value = p.category; $('price').value = p.price; $('qty').value = p.qty;
      editingId = id;
      window.scrollTo({top:0,behavior:'smooth'});
      alert('Edit the values and click Save Product. To change image, choose a new image file.');
    };

    window.deleteProduct = function(id){
      if(!confirm('Delete this product?')) return;
      products = products.filter(x=>x.id !== id);
      save(KEY_PRODUCTS, products); renderProducts();
    };

    $('resetDemo').addEventListener('click', ()=>{
      if(!confirm('Reset demo products?')) return;
      products = defaultProducts.slice(); save(KEY_PRODUCTS, products); renderProducts();
    });

    // ====== service order links (unlock) ======
    document.querySelectorAll('.svc-order').forEach(el=>{
      el.addEventListener('click', ev=>{
        const name = ev.currentTarget.dataset.name;
        const price = ev.currentTarget.dataset.price;
        const number = waNumberSelect.value || CONFIG.fallbackWa;
        const msg = `Hello, I want to order service: ${name} (PKR ${price}).`;
        window.open(`https://wa.me/${number}?text=${encodeURIComponent(msg)}`, '_blank');
      });
    });

    // ====== shareable order link viewer: when URL has ?order=... decode and show ======
    function loadOrderFromUrl(){
      const params = new URLSearchParams(location.search);
      if(params.has('order')){
        try{
          const encoded = params.get('order');
          const decodedJson = base64Decode(decodeURIComponent(encoded));
          const order = JSON.parse(decodedJson);
          showOrderWindow(order);
        } catch(err){
          console.error('Invalid order param', err);
        }
      }
    }

    function showOrderWindow(order){
      const win = window.open('', '_blank');
      const itemsHtml = order.items.map(it => `<li>${escapeHtml(it.title)} — PKR ${it.price} (qty ${it.qty})</li>`).join('');
      const html = `
        <html><head><meta charset="utf-8"/><title>Order #${order.id}</title></head><body style="font-family:Arial;padding:18px">
        <h2>Order #${order.id}</h2>
        <p><strong>Name:</strong> ${escapeHtml(order.name)}<br/>
        <strong>Phone:</strong> ${escapeHtml(order.phone)}<br/>
        <strong>Address:</strong> ${escapeHtml(order.address)}</p>
        <h3>Items</h3><ul>${itemsHtml}</ul>
        <p><strong>Total:</strong> PKR ${order.total}</p>
        <p><em>Time: ${order.time}</em></p>
        <p><a href="https://wa.me/${waNumberSelect.value || CONFIG.fallbackWa}?text=${encodeURIComponent('New order received. Order ID: '+order.id)}" target="_blank">Message seller on WhatsApp</a></p>
        </body></html>
      `;
      win.document.write(html); win.document.close();
    }

    // ====== startup ======
    function renderAll(){ renderProducts(); renderCart(); }
    renderAll();
    loadOrderFromUrl();

    // ====== ensure products saved under KEY_PRODUCTS ======
    save(KEY_PRODUCTS, products);
    save(KEY_CART, cart);
  </script>
</body>
</html>
