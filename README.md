<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SK Foods | ঘি ও আচার</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; background: #fffaf5; }
    header { background: #8b4513; color: white; padding: 15px; text-align: center; }
    section { padding: 20px; }
    .products { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .card { background: white; border-radius: 10px; padding: 15px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
    .card img { width: 100%; border-radius: 10px; }
    .card h3 { margin: 10px 0 5px; }
    .card p { font-size: 14px; }
    .order-btn { background: #25D366; color: white; padding: 10px; border: none; width: 100%; border-radius: 5px; font-size: 16px; cursor: pointer; }
    footer { background: #333; color: white; text-align: center; padding: 10px; }
    form input { width: 100%; padding: 8px; margin: 6px 0; }
  </style>
</head>
<body>

<header>
  <h1>SK Foods</h1>
  <p>খাঁটি ঘি ও ঘরোয়া আচার | Pure Ghee & Homemade Pickles</p>
</header>

<section>
  <h2>Our Products / আমাদের পণ্য</h2>
  <div class="products">

    <div class="card">
      <img src="https://images.unsplash.com/photo-1627485937980-221c88ac04c1" alt="Ghee">
      <h3>Pure Ghee | খাঁটি ঘি</h3>
      <p>100% খাঁটি দেশি ঘি। স্বাস্থ্যসম্মত ও ঘরোয়া।</p>
      <p><strong>দাম:</strong> 1200 টাকা / কেজি</p>
      <button class="order-btn" onclick="order('খাঁটি ঘি','1200 টাকা / কেজি')">Order on WhatsApp</button>
    </div>

    <div class="card">
      <img src="https://images.unsplash.com/photo-1604909053191-8c01c3b45c2a" alt="Pickle">
      <h3>Homemade Pickle | ঘরোয়া আচার</h3>
      <p>ঘরোয়া রেসিপিতে তৈরি মজাদার আচার।</p>
      <p><strong>দাম:</strong> 400 টাকা / 500 গ্রাম</p>
      <button class="order-btn" onclick="order('ঘরোয়া আচার','400 টাকা / 500 গ্রাম')">Order on WhatsApp</button>
    </div>

  </div>
</section>

<section>
  <h2>Order Form</h2>
  <form onsubmit="sendOrder(event)">
    <input id="name" placeholder="আপনার নাম / Your Name" required />
    <input id="mobile" placeholder="মোবাইল নাম্বার" required />
    <input id="product" placeholder="প্রোডাক্টের নাম" required />
    <input id="price" placeholder="দাম" required />
    <button class="order-btn" type="submit">Send Order</button>
  </form>
</section>

<footer>
  <p>© 2026 SK Foods</p>
</footer>

<script>
  let whatsappNumber = '8801757488142'; // এখান থেকে ভবিষ্যতে নম্বর পরিবর্তন করা যাবে

  function order(product, price) {
    document.getElementById('product').value = product;
    document.getElementById('price').value = price;
    window.scrollTo(0, document.body.scrollHeight);
  }

  function sendOrder(e) {
    e.preventDefault();
    const name = document.getElementById('name').value;
    const mobile = document.getElementById('mobile').value;
    const product = document.getElementById('product').value;
    const price = document.getElementById('price').value;
    const delivery = 'ঢাকার ভিতরে: ৬০ টাকা, ঢাকার বাইরে: ১২০ টাকা';

    const text = `নাম: ${name}\nমোবাইল: ${mobile}\nপ্রোডাক্ট: ${product}
দাম: ${price}
ডেলিভারি: ${delivery}`;
    const url = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(text)}`;
    window.open(url, '_blank');
  }
</script>

</body>
</html>
