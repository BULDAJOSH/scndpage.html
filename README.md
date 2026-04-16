<html>
<head>
    <title>Beyond The Limit Store</title>

    <style>
        body {
            margin: 0;
            font-family: Arial;
            background: linear-gradient(to right, #f5f5f5, #e6ccff);
        }

        /* NAVBAR */
        .navbar {
            background-color: black;
            color: white;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            margin: 0 10px;
        }

        .nav-links a:hover {
            color: violet;
        }

        /* SECTIONS */
        .section {
            display: none;
            padding: 30px;
        }

        .active {
            display: block;
        }

        /* HERO */
        .hero {
            background: linear-gradient(to right, black, purple);
            color: white;
            padding: 60px;
            text-align: center;
            border-radius: 10px;
        }

        /* PRODUCTS */
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .card {
            background: white;
            padding: 15px;
            text-align: center;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: 0.3s;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .card img {
            width: 100%;
            border-radius: 10px;
        }

        button {
            padding: 8px 12px;
            border: none;
            background: black;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background: purple;
        }

        select {
            padding: 5px;
        }

        .box {
            background: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 400px;
            margin: auto;
            text-align: center;
        }

        footer {
            background: black;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }
    </style>

    <script>
        let cart = [];

        function showSection(id) {
            let sections = document.querySelectorAll(".section");
            sections.forEach(sec => sec.classList.remove("active"));
            document.getElementById(id).classList.add("active");
        }

        function addToCart(product) {
            cart.push(product);
            updateCart();
        }

        function updateCart() {
            let cartBox = document.querySelector("#cart .box");

            if (cart.length === 0) {
                cartBox.innerHTML = "<h2>Your Cart</h2><p>No items yet</p>";
            } else {
                let items = cart.map(item => `<p>${item}</p>`).join("");
                cartBox.innerHTML = "<h2>Your Cart</h2>" + items;
            }
        }
    </script>
</head>

<body>

<!-- NAVBAR -->
<div class="navbar">
    <h1>BEYOND THE LIMIT</h1>
    <div class="nav-links">
        <a href="#" onclick="showSection('home')">Home</a>
        <a href="#" onclick="showSection('shirts')">Shirts</a>
        <a href="#" onclick="showSection('shorts')">Shorts</a>
        <a href="#" onclick="showSection('cart')">Cart</a>
        <a href="#" onclick="showSection('profile')">Profile</a>
    </div>
</div>

<!-- HOME -->
<div id="home" class="section active">

    <div class="hero">
        <h1>BEYOND THE LIMIT</h1>
        <p>Push your style beyond boundaries</p>
        <button onclick="showSection('shirts')">Shop Now</button>
    </div>

    <h2 style="text-align:center; margin-top:30px;">Featured Items</h2>

    <div class="products">
        <div class="card">
            <img src="https://highabovesociety.com/cdn/shop/files/image.jpg?v=1684951865">
            <h3>Best Seller Tee</h3>
            <p style="color: green;">₱450</p>
        </div>

        <div class="card">
            <img src="https://neweracap.ph/cdn/shop/files/14148834_01064834_grab_5.jpg?v=1716628262&width=2000">
            <h3>Top Shorts</h3>
            <p style="color: green;">₱350</p>
        </div>
    </div>

</div>

<!-- SHIRTS -->
<div id="shirts" class="section">
    <h2>Shirt Collection</h2>

    <div class="products">

        <div class="card">
            <img src="https://highabovesociety.com/cdn/shop/files/image.jpg?v=1684951865">
            <h3>Classic Logo Shirt</h3>
            <p style="color: green;">₱450</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Classic Logo Shirt')">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://thecrescendobrand.com/cdn/shop/files/RISEBEYONDLIMITSGLOBETEEBACKBLACKCPPR.png?v=1712864958">
            <h3>Streetwear Tee</h3>
            <p style="color: green;">₱500</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Streetwear Tee')">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://img.gem.app/1809161916/1t/1758866266/tailored-originals-beyond-the-limit-t-shirt.jpg">
            <h3>Minimal Tee</h3>
            <p style="color: green;">₱480</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Minimal Tee')">Add to Cart</button>
        </div>

    </div>
</div>

<!-- SHORTS -->
<div id="shorts" class="section">
    <h2>Shorts Collection</h2>

    <div class="products">

        <div class="card">
            <img src="https://neweracap.ph/cdn/shop/files/14148834_01064834_grab_5.jpg?v=1716628262&width=2000">
            <h3>Sport Shorts</h3>
            <p style="color: green;">₱350</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Sport Shorts')">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://encrypted-tbn1.gstatic.com/shopping?q=tbn:ANd9GcR3TT2mUoedZOGHgJrrfeHxLgDjpDurG_XHRVWjHESVfXzK43BlSQkio-0zSOUPOMVgOaYc2rx-ZE46q7pZ5eBxc2MDOfJIx__nKXKkGIxu97RFQZhWwIt2VdM">
            <h3>Casual Shorts</h3>
            <p style="color: green;">₱380</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Casual Shorts')">Add to Cart</button>
        </div>

        <div class="card">
            <img src="https://encrypted-tbn3.gstatic.com/shopping?q=tbn:ANd9GcRO1E_Mk3_jDxvoQ9pcmmq1ZfiO-1uuzGJKC1DTVcVmYQObE0e87yU-gwTSB3RuMjSs5fJYK_stfWxJZJwn4IeivD523df1jLNkXYY1e5oloSvnoYY_gqQIBQ">
            <h3>Training Shorts</h3>
            <p style="color: green;">₱400</p>
            <select>
                <option>SIZE</option><option>S</option><option>M</option><option>L</option><option>XL</option>
            </select><br><br>
            <button onclick="addToCart('Training Shorts')">Add to Cart</button>
        </div>

    </div>
</div>

<!-- CART -->
<div id="cart" class="section">
    <div class="box">
        <h2>Your Cart</h2>
        <p>No items yet</p>
    </div>
</div>

<!-- PROFILE -->
<div id="profile" class="section">
    <div class="box">
        <h2>User Profile</h2>
        <p>Name: Josh Bulda</p>
        <p>Email: beyondthelimit@gmail.com</p>
        <button>Edit Profile</button>
    </div>
</div>

<!-- FOOTER -->
<footer>
    <hr width="50%">
    <p>© 2026 BEYOND THE LIMIT</p>
    <p>Follow us: Instagram | Facebook | TikTok</p>
    <p>Made in the Philippines</p>
</footer>

</body>
</html>
