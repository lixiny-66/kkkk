
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>手机商城</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
        }

        .header {
            background-color: #ff4444;
            color: white;
            padding: 15px;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            padding: 80px 10px 60px;
        }

        .product-item {
            background: white;
            border-radius: 10px;
            padding: 10px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .product-img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 5px;
        }

        .price {
            color: #ff4444;
            font-weight: bold;
            margin: 10px 0;
        }

        .buy-btn {
            background-color: #ff4444;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
        }

        .cart {
            position: fixed;
            bottom: 0;
            width: 100%;
            background: white;
            padding: 10px;
            box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
        }

        @media (min-width: 768px) {
            .products {
                grid-template-columns: repeat(3, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>手机商城</h1>
    </div>

    <div class="products">
        <!-- 商品1 -->
        <div class="product-item">
            < img src="product1.jpg" alt="商品1" class="product-img">
            <h3>智能手机</h3>
            <p class="price">¥1999</p >
            <button class="buy-btn" onclick="addToCart('智能手机')">加入购物车</button>
        </div>

        <!-- 商品2 -->
        <div class="product-item">
            < img src="product2.jpg" alt="商品2" class="product-img">
            <h3>无线耳机</h3>
            <p class="price">¥399</p >
            <button class="buy-btn" onclick="addToCart('无线耳机')">加入购物车</button>
        </div>

        <!-- 更多商品... -->
    </div>

    <div class="cart">
        <h3>购物车</h3>
        <div id="cart-items"></div>
        <button onclick="checkout()">立即结算</button>
    </div>

    <script>
        let cart = [];

        function addToCart(product) {
            cart.push(product);
            updateCartDisplay();
        }

        function updateCartDisplay() {
            const cartDiv = document.getElementById('cart-items');
            cartDiv.innerHTML = cart.join('<br>');
        }

        function checkout() {
            if (cart.length === 0) {
                alert('请先添加商品到购物车！');
                return;
            }
            alert('即将跳转支付页面，共' + cart.length + '件商品');
            // 这里可以添加实际支付逻辑
        }
    </script>
</body>
</html>
