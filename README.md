# online shooping app
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shopping Application</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f8f9fa;
        }

        header {
            background-color: #343a40;
            color: #fff;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            animation: slideDown 1s ease-in-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        header h1 {
            margin: 0;
        }

        main {
            padding: 2rem;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
        }

        .product-list {
            display: flex;
            gap: 2rem;
            flex-wrap: wrap;
            justify-content: center;
            width: 100%;
            max-width: 1200px;
        }

        .product {
            background-color: #fff;
            border: 1px solid #dee2e6;
            border-radius: 0.5rem;
            padding: 1rem;
            width: calc(33.333% - 2rem);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.2s, box-shadow 0.2s;
            text-align: center;
            animation: fadeIn 1s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .product:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .product img {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-bottom: 1px solid #dee2e6;
            margin-bottom: 1rem;
        }

        .product h2 {
            margin: 0.5rem 0;
        }

        .product p {
            margin: 0.5rem 0;
            color: #6c757d;
        }

        .product button {
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 0.25rem;
            padding: 0.5rem 1rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .product button:hover {
            background-color: #0056b3;
        }

        .product button:active {
            transform: scale(0.95);
        }

        footer {
            background-color: #343a40;
            color: #fff;
            text-align: center;
            padding: 1rem;
            position: fixed;
            width: 100%;
            bottom: 0;
            box-shadow: 0 -4px 6px rgba(0, 0, 0, 0.1);
        }

        .cart {
            position: fixed;
            top: 1rem;
            right: 1rem;
            background-color: #fff;
            border: 1px solid #dee2e6;
            border-radius: 0.5rem;
            padding: 1rem;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 350px;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            max-height: 80vh;
            overflow-y: auto;
        }

        .cart h2 {
            margin-top: 0;
            margin-bottom: 1rem;
        }

        .cart ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
            flex-grow: 1;
        }

        .cart ul li {
            border-bottom: 1px solid #dee2e6;
            padding: 0.5rem 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .cart ul li button {
            background-color: #dc3545;
            color: #fff;
            border: none;
            border-radius: 0.25rem;
            cursor: pointer;
            padding: 0.2rem 0.5rem;
            transition: background-color 0.2s;
        }

        .cart ul li button:hover {
            background-color: #c82333;
        }

        .cart ul li button:active {
            transform: scale(0.95);
        }

        .total {
            font-weight: bold;
            text-align: right;
            padding: 0.5rem 0;
            margin-top: 1rem;
        }

        .buy-button {
            display: block;
            width: 100%;
            text-align: center;
            background-color: #28a745;
            color: #fff;
            border: none;
            border-radius: 0.25rem;
            padding: 1rem;
            cursor: pointer;
            text-decoration: none;
            font-size: 1.2rem;
            margin-top: 1rem;
            transition: background-color 0.2s;
        }

        .buy-button:hover {
            background-color: #218838;
        }

        .buy-button:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Our Shopping App</h1>
    </header>
    <main>
        <section class="product-list">
            <article class="product">
                <img src="https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_600,h_600/global/054277/01/bv/fnd/IND/fmt/png/PUMA-Sportstyle-Training-Water-Bottle&nbsp;600ml" alt="Bottle Image">
                <h2>Bottle</h2>
                <p>A reusable water bottle.</p>
                <p>Price: $10.00</p>
                <button onclick="addToCart('Bottle', 10.00)">Add to Cart</button>
            </article>
            <article class="product">
                <img src="https://cdn.shopify.com/s/files/1/1676/0567/products/gray_1_2000x.jpg?v=1577712301" alt="Umbrella Image">
                <h2>Umbrella</h2>
                <p>A sturdy umbrella for rainy days.</p>
                <p>Price: $15.00</p>
                <button onclick="addToCart('Umbrella', 15.00)">Add to Cart</button>
            </article>
            <article class="product">
                <img src="https://lp2.hm.com/hmgoepprod?set=format%5Bwebp%5D%2Cquality%5B79%5D%2Csource%5B%2F04%2Fd5%2F04d5ad5eb274dbec9fa51623324b540ef70d9528.jpg%5D%2Corigin%5Bdam%5D%2Ccategory%5B%5D%2Ctype%5BLOOKBOOK%5D%2Cres%5Bm%5D%2Chmver%5B1%5D&call=url%5Bfile%3A%2Fproduct%2Fmain%5D" alt="Clothes Image">
                <h2>Clothes</h2>
                <p>Comfortable clothing for all seasons.</p>
                <p>Price: $25.00</p>
                <button onclick="addToCart('Clothes', 25.00)">Add to Cart</button>
            </article>
            <article class="product">
                <img src="https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_600,h_600/global/107744/03/sv01/fnd/AUS/fmt/png/ULTRA-ULTIMATE-FG/AG-Unisex-Football-Boots" alt="Shoes Image">
                <h2>Shoes</h2>
                <p>Stylish and comfortable shoes.</p>
                <p>Price: $40.00</p>
                <button onclick="addToCart('Shoes', 40.00)">Add to Cart</button>
            </article>
            <article class="product">
                <img src="https://images-na.ssl-images-amazon.com/images/I/6156n3Ool1L._AC_UX679_.jpg" alt="Watch Image">
                <h2>Watch</h2>
                <p>A stylish watch for any occasion.</p>
                <p>Price: $50.00</p>
                <button onclick="addToCart('Watch', 50.00)">Add to Cart</button>
            </article>
            <article class="product">
                <img src="https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_600,h_600/global/079392/03/fnd/IND/fmt/png/PUMA-School-Unisex-Backpack" alt="Bag Image">
                <h2>Bag</h2>
                <p>A spacious and durable bag.</p>
                <p>Price: $30.00</p>
                <button onclick="addToCart('Bag', 30.00)">Add to Cart</button>
            </article>
        </section>
    </main>

    <div class="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items">
            <!-- Cart items will be added here dynamically -->
        </ul>
        <div class="total" id="total-price">Total: $0.00</div>
        <a class="buy-button" href="checkout.html">Buy</a>
    </div>

    <script>
        let cart = [];

        function addToCart(product, price) {
            const index = cart.findIndex(item => item.product === product);
            if (index !== -1) {
                cart[index].quantity += 1;
            } else {
                cart.push({ product, price, quantity: 1 });
            }
            renderCart();
        }

        function removeFromCart(index) {
            if (cart[index].quantity > 1) {
                cart[index].quantity -= 1;
            } else {
                cart.splice(index, 1);
            }
            renderCart();
        }

        function renderCart() {
            const cartItems = document.getElementById('cart-items');
            const totalPrice = document.getElementById('total-price');
            cartItems.innerHTML = '';
            let total = 0;

            cart.forEach((item, index) => {
                total += item.price * item.quantity;
                const li = document.createElement('li');
                li.innerHTML = `${item.product} - $${item.price.toFixed(2)} x ${item.quantity} <button onclick="removeFromCart(${index})">Remove</button>`;
                cartItems.appendChild(li);
            });

            totalPrice.innerHTML = `Total: $${total.toFixed(2)}`;
        }
    </script>
</body>
</html>
