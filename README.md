# yogeshdesiegg18
farm

import zipfile
import os

# Create folder for project
project_folder = '/mnt/data/Yogesh_Desi_Egg_Website'
os.makedirs(project_folder, exist_ok=True)

# HTML content (full website code)
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Yogesh Desi Egg - Fresh Organic Eggs</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Yogesh Desi Egg</h1>
    <nav>
      <a href="#products">Products</a>
      <a href="#about">About</a>
      <a href="#benefits">Benefits</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="hero">
    <h2>Fresh Organic Desi Eggs</h2>
    <p>Healthy, Nutritious, and Farm Fresh – Straight from our farm to your plate.</p>
    <button onclick="window.location.href='#contact'">Order Now</button>
  </section>

  <section id="products">
    <h2 class="section-title">Our Products</h2>
    <div class="products">
      <div class="card hidden">
        <img src="https://images.unsplash.com/photo-1589923188900-7b4d3c07f8aa" alt="Desi Egg Pack">
        <h3>Desi Egg Pack (12 pcs)</h3>
        <p>₹120 only</p>
      </div>
      <div class="card hidden">
        <img src="https://images.unsplash.com/photo-1603048306845-2f0d35e1d4b8" alt="Farm Fresh Eggs">
        <h3>Farm Fresh Eggs (30 pcs)</h3>
        <p>₹280 only</p>
      </div>
      <div class="card hidden">
        <img src="https://images.unsplash.com/photo-1610440043114-4aa5db74e8a3" alt="Organic Eggs">
        <h3>Organic Eggs (6 pcs)</h3>
        <p>₹70 only</p>
      </div>
    </div>
  </section>

  <section id="about">
    <h2 class="section-title">About Us</h2>
    <p class="hidden">Yogesh Desi Egg is owned by <strong>Yogesh Pandey</strong>. We provide 100% organic Desi Eggs raised in natural conditions with love and care. Our farm is located at <strong>Haldwani, Lamachour, Puranpur Kumatiya, near Amaltas Villa</strong>. Our mission is to deliver health and nutrition to every home.</p>
  </section>

  <section id="benefits">
    <h2 class="section-title">Why Choose Yogesh Desi Egg?</h2>
    <div class="benefits">
      <div class="benefit hidden">High in Protein</div>
      <div class="benefit hidden">Boosts Immunity</div>
      <div class="benefit hidden">Farm Fresh Guarantee</div>
      <div class="benefit hidden">Chemical Free</div>
    </div>
  </section>

  <section class="testimonials">
    <h2 class="section-title">What Our Customers Say</h2>
    <p class="testimonial hidden">“The eggs are so fresh and tasty. I can feel the quality. Highly recommended!” – Ramesh</p>
    <p class="testimonial hidden">“Best Desi Eggs I’ve ever had. Healthy and natural.” – Priya</p>
  </section>

  <section id="contact">
    <h2 class="section-title">Contact & Order</h2>
    <!-- Formspree Email Form -->
    <form action="https://formspree.io/f/meorobdn" method="POST">
      <label>Your Name:
        <input type="text" name="name" required>
      </label>
      <label>Your Email:
        <input type="email" name="email" required>
      </label>
      <label>Your Phone:
        <input type="text" name="phone" required>
      </label>
      <label>Your Order:
        <textarea name="order" required></textarea>
      </label>
      <button type="submit">Send Order</button>
    </form>
    <p style="margin-top:10px;">Or <a href="https://wa.me/91PHONE_NUMBER?text=Hello%20Yogesh%20Desi%20Egg,%20I%20want%20to%20place%20an%20order" target="_blank" style="color:#ff9900;">Order on WhatsApp</a></p>
  </section>

  <footer>
    <p>&copy; 2025 Yogesh Desi Egg | Owned by Yogesh Pandey | Farm Location: Haldwani, Lamachour, Puranpur Kumatiya, near Amaltas Villa</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
"""

# CSS content
css_content = """
* {margin:0; padding:0; box-sizing:border-box; font-family: Arial,sans-serif;}
body {background:#fffdf7; color:#333; overflow-x:hidden;}
header {background: linear-gradient(90deg,#ff9900,#ffcc00); padding:20px; text-align:center; position:sticky; top:0; z-index:100;}
header h1 {color:white; font-size:2rem; animation:bounce 2s infinite;}
nav {margin-top:10px;}
nav a {color:white; margin:0 15px; text-decoration:none; font-weight:bold; transition:0.3s;}
nav a:hover {color:#333;}
.hero {display:flex; flex-direction:column; justify-content:center; align-items:center; height:100vh; background:url('https://images.unsplash.com/photo-1611078489935-79a3f1c5f0bb') center/cover no-repeat; color:white; text-align:center;}
.hero h2 {font-size:3rem; text-shadow:2px 2px 6px rgba(0,0,0,0.7); animation:fadeInUp 2s;}
.hero p {font-size:1.2rem; margin:20px 0; animation:fadeInUp 3s;}
.hero button {background:#ffcc00; color:#333; border:none; padding:15px 30px; font-size:1rem; border-radius:30px; cursor:pointer; transition:0.3s;}
.hero button:hover {background:#ff9900; color:white; transform:scale(1.1);}
section {padding:60px 20px; text-align:center;}
h2.section-title {font-size:2rem; margin-bottom:30px; color:#ff9900;}
.products {display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px;}
.card {background:white; padding:20px; border-radius:15px; box-shadow:0 4px 15px rgba(0,0,0,0.1); transition:0.3s;}
.card:hover {transform:translateY(-10px) scale(1.05);}
.card img {width:100%; border-radius:15px;}
.card h3 {margin:15px 0; color:#333;}
.benefits {display:flex; flex-wrap:wrap; justify-content:center; gap:20px;}
.benefit {flex:1 1 200px; background:#fff3cd; padding:20px; border-radius:15px;}
.testimonials {background:#f9f9f9;}
.testimonial {margin:20px auto; max-width:600px; font-style:italic;}
form {max-width:500px; margin:auto; text-align:left;}
form label {display:block; margin-bottom:10px;}
form input, form textarea {width:100%; padding:10px; margin:5px 0 15px 0; border:1px solid #ccc; border-radius:10px;}
form button {background:#ff9900; border:none; padding:12px 20px; color:white; border-radius:10px; cursor:pointer;}
form button:hover {background:#e68a00;}
footer {background:#333; color:white; padding:20px; text-align:center;}
@keyframes fadeInUp {from{opacity:0; transform:translateY(50px);}to{opacity:1; transform:translateY(0);}}
@keyframes bounce {0%,20%,50%,80%,100%{transform:translateY(0);}40%{transform:translateY(-15px);}60%{transform:translateY(-7px);}}
.hidden{opacity:0; transform:translateY(40px); transition:all 1s;}
.show{opacity:1; transform:translateY(0);}
"""

# JS content
js_content = """
const hiddenEls = document.querySelectorAll('.hidden');
const observer = new IntersectionObserver((entries)=>{
  entries.forEach(entry=>{
    if(entry.isIntersecting){ entry.target.classList.add('show'); }
  });
}, {threshold:0.2});
hiddenEls.forEach(el=>observer.observe(el));
"""

# Write files
with open(os.path.join(project_folder, 'index.html'), 'w') as f:
    f.write(html_content)

with open(os.path.join(project_folder, 'style.css'), 'w') as f:
    f.write(css_content)

with open(os.path.join(project_folder, 'script.js'), 'w') as f:
    f.write(js_content)

# Create zip file
zip_path = '/mnt/data/Yogesh_Desi_Egg_Website.zip'
with zipfile.ZipFile(zip_path, 'w') as zipf:
    zipf.write(os.path.join(project_folder, 'index.html'), arcname='index.html')
    zipf.write(os.path.join(project_folder, 'style.css'), arcname='style.css')
    zipf.write(os.path.join(project_folder, 'script.js'), arcname='script.js')

zip_path
