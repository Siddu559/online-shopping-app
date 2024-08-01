# online-shopping-app
its an basic shopping app where u can add or remove the given products 
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
            background-color: #fff5f5; /* Light pink background color */
        }

        header {
            background-color: #d32f2f; /* Red background color */
            color: #fff;
            padding: 1rem;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        main {
            padding: 2rem;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
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
            background-color: #ffffff; /* White background for product cards */
            border: 1px solid #f5c6c6; /* Light red border color */
            padding: 1rem;
            width: calc(33.333% - 2rem);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s, box-shadow 0.2s;
            text-align: center;
        }

        .product:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
        }

        .product img {
            max-width: 100%;
            height: auto;
            border-bottom: 1px solid #f5c6c6;
            margin-bottom: 1rem;
        }

        .product h2 {
            margin-top: 0;
        }

        .product p {
            margin: 1rem 0;
        }

        .product button {
            background-color: #c62828; /* Dark red button color */
            color: #fff;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .product button:hover {
            background-color: #b71c1c; /* Even darker red button color */
        }

        footer {
            background-color: #d32f2f; /* Same red as header */
            color: #fff;
            text-align: center;
            padding: 1rem;
            position: fixed;
            width: 100%;
            bottom: 0;
        }

        .cart {
            position: fixed;
            top: 1rem;
            right: 1rem;
            background-color: #ffffff; /* White background for cart */
            border: 1px solid #f5c6c6; /* Light red border color */
            padding: 1rem;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            width: 300px;
        }

        .cart h2 {
            margin-top: 0;
        }

        .cart ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        .cart ul li {
            border-bottom: 1px solid #f5c6c6;
            padding: 0.5rem 0;
            display: flex;
            justify-content: space-between;
        }

        .cart ul li button {
            background-color: #c62828; /* Red button color */
            color: #fff;
            border: none;
            cursor: pointer;
            padding: 0.2rem 0.5rem;
        }

        .cart ul li button:hover {
            background-color: #b71c1c; /* Darker red button color */
        }

        .total {
            font-weight: bold;
            text-align: right;
            padding: 0.5rem 0;
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
            <!-- Cart items will be added here -->
        </ul>
        <div class="total" id="cart-total">Total: $0.00</div>
    </div>

    <script>
        let cart = [];

        function addToCart(productName, productPrice) {
            cart.push({ name: productName, price: productPrice });
            renderCart();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            renderCart();
        }

        function renderCart() {
            const cartItems = document.getElementById('cart-items');
            cartItems.innerHTML = '';

            let total = 0;

            cart.forEach((item, index) => {
                const newItem = document.createElement('li');
                newItem.innerHTML = `
                    ${item.name} - $${item.price.toFixed(2)}
                    <button onclick="removeFromCart(${index})">Remove</button>
                `;
                cartItems.appendChild(newItem);
                total += item.price;
            });

            document.getElementById('cart-total').textContent = `Total: $${total.toFixed(2)}`;
        }
    </script>
</body>
</html>
