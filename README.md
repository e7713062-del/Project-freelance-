<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تاج - TAJ | المنتجات الغذائية الفاخرة</title>
    <!-- Google Fonts & Font Awesome Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- الأساسيات والألوان --- */
        :root {
            --primary-color: #d4af37; /* ذهبي تاج */
            --primary-dark: #b38f2a;
            --bg-light: #ffffff;
            --bg-secondary: #f9f9fb;
            --text-dark: #222222;
            --text-muted: #666666;
            --developer-green: #2ecc71; /* لون اسم مصطفى تامر */
            --shadow-light: 0 10px 30px rgba(0, 0, 0, 0.05);
            --shadow-hover: 0 15px 35px rgba(0, 0, 0, 0.12);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }

        body {
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* --- الهيدر وشريط التنقل --- */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.04);
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 26px;
            font-weight: 800;
            color: var(--text-dark);
            text-decoration: none;
        }

        .logo span {
            color: var(--primary-color);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 600;
            transition: var(--transition);
        }

        nav a:hover {
            color: var(--primary-color);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .cart-icon-btn {
            position: relative;
            background: var(--bg-secondary);
            border: none;
            padding: 10px 15px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 18px;
            color: var(--text-dark);
            transition: var(--transition);
        }

        .cart-icon-btn:hover {
            background: var(--primary-color);
            color: #fff;
        }

        .cart-count {
            position: absolute;
            top: -5px;
            right: -5px;
            background: #e74c3c;
            color: #fff;
            font-size: 12px;
            font-weight: bold;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* --- القسم الرئيسي (Hero) --- */
        .hero {
            padding: 60px 5%;
            background: linear-gradient(135deg, #ffffff 0%, #f7f7f7 100%);
            display: flex;
            align-items: center;
            justify-content: space-between;
            min-height: 70vh;
        }

        .hero-text {
            max-width: 550px;
        }

        .hero-text h1 {
            font-size: 48px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-text h1 span {
            color: var(--primary-color);
        }

        .hero-text p {
            color: var(--text-muted);
            font-size: 18px;
            margin-bottom: 30px;
        }

        .btn-primary {
            display: inline-block;
            background: var(--primary-color);
            color: #fff;
            padding: 12px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 700;
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.3);
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.4);
        }

        /* --- قسم المنتجات --- */
        .products-section {
            padding: 80px 5%;
            background: var(--bg-light);
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 36px;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: var(--primary-color);
            border-radius: 2px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        /* كارت المنتج مع تأثيرات CSS */
        .product-card {
            background: #fff;
            border-radius: 20px;
            padding: 20px;
            border: 1px solid #eee;
            box-shadow: var(--shadow-light);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            overflow: hidden;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
            border-color: var(--primary-color);
        }

        .product-img-holder {
            width: 100%;
            height: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #fcfcfc;
            border-radius: 15px;
            margin-bottom: 20px;
            overflow: hidden;
        }

        .product-img-holder img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
            transition: var(--transition);
        }

        .product-card:hover .product-img-holder img {
            transform: scale(1.08);
        }

        .product-info h3 {
            font-size: 20px;
            margin-bottom: 10px;
        }

        .product-info p {
            color: var(--text-muted);
            font-size: 14px;
            margin-bottom: 15px;
        }

        .price-section {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }

        .product-price {
            font-size: 22px;
            font-weight: 800;
            color: var(--text-dark);
        }

        .product-price span {
            font-size: 14px;
            color: var(--text-muted);
        }

        /* تخصيص اختيار السكر */
        .sugar-options {
            margin-bottom: 15px;
        }

        .sugar-options label {
            font-size: 13px;
            color: var(--text-muted);
            display: block;
            margin-bottom: 5px;
        }

        .sugar-select {
            width: 100%;
            padding: 8px 12px;
            border-radius: 8px;
            border: 1px solid #ddd;
            font-family: inherit;
            outline: none;
            cursor: pointer;
        }

        .add-to-cart-btn {
            width: 100%;
            margin-top: 15px;
            background: #222;
            color: #fff;
            border: none;
            padding: 12px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }

        .add-to-cart-btn:hover {
            background: var(--primary-color);
            color: #fff;
        }

        /* --- سلة التسوق التفاعلية (Drawer) --- */
        .cart-drawer {
            position: fixed;
            top: 0;
            left: -400px;
            width: 350px;
            height: 100vh;
            background: #fff;
            box-shadow: 5px 0 25px rgba(0,0,0,0.1);
            z-index: 1001;
            transition: var(--transition);
            padding: 25px;
            display: flex;
            flex-direction: column;
        }

        .cart-drawer.open {
            left: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #eee;
            padding-bottom: 15px;
            margin-bottom: 20px;
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 20px;
            cursor: pointer;
            color: var(--text-muted);
        }

        .cart-items {
            flex: 1;
            overflow-y: auto;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid #f5f5f5;
        }

        .cart-item-details h4 {
            font-size: 15px;
        }

        .cart-item-details p {
            font-size: 13px;
            color: var(--text-muted);
        }

        .cart-footer {
            border-top: 1px solid #eee;
            padding-top: 20px;
        }

        .total-price {
            display: flex;
            justify-content: space-between;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 15px;
        }

        /* --- الفوتر والحقوق --- */
        footer {
            background: #111;
            color: #fff;
            text-align: center;
            padding: 30px 20px;
            margin-top: 50px;
        }

        footer p {
            font-size: 16px;
            letter-spacing: 0.5px;
        }

        /* تخصيص لون اسم مصطفى تامر بالاخضر */
        .developer-name {
            color: var(--developer-green);
            font-weight: 800;
            text-decoration: none;
            display: inline-block;
            transition: var(--transition);
        }

        .developer-name:hover {
            transform: scale(1.05);
            text-shadow: 0 0 10px rgba(46, 204, 113, 0.4);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero {
                flex-direction: column;
                text-align: center;
            }
            .cart-drawer {
                width: 100%;
                left: -100%;
            }
        }
    </style>
</head>
<body>

    <!-- شريط التنقل -->
    <header>
        <a href="#" class="logo">
            <i class="fa-solid fa-crown" style="color: #d4af37;"></i>
            تاج <span>TAJ</span>
        </a>
        <nav>
            <ul>
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#products">المنتجات</a></li>
                <li><a href="#about">عن تاج</a></li>
            </ul>
        </nav>
        <div class="header-actions">
            <button class="cart-icon-btn" onclick="toggleCart()">
                <i class="fa-solid fa-cart-shopping"></i>
                <span class="cart-count" id="cartCount">0</span>
            </button>
        </div>
    </header>

    <!-- واجهة الترحيب الرئيسية -->
    <section class="hero" id="home">
        <div class="hero-text">
            <h1>أجود المنتجات الغذائية من <span>تاج</span> لتجهيز بيتك</h1>
            <p>أرز، مكرونة، سكر، وبهارات طازجة بأعلى معايير الجودة والتغليف الفاخر.</p>
            <a href="#products" class="btn-primary">تصفح المنتجات الآن</a>
        </div>
    </section>

    <!-- قسم عرض المنتجات -->
    <section class="products-section" id="products">
        <div class="section-title">
            <h2>تشكيلة منتجات تاج الفاخرة</h2>
        </div>

        <div class="products-grid">

            <!-- 1. الأرز -->
            <div class="product-card">
                <div>
                    <div class="product-img-holder">
                        <!-- استبدل الرابط بصورة الأرز الخاصة بك إذا أردت -->
                        <img src="1000437198.jpg" alt="أرز تاج الفاخر" onerror="this.src='https://via.placeholder.com/200?text=TAJ+Rice'">
                    </div>
                    <div class="product-info">
                        <h3>أرز تاج الفاخر (1 كجم)</h3>
                        <p>أرز حبة عريضة درجة أولى ناصع البياض وخالي من الشوائب.</p>
                    </div>
                </div>
                <div>
                    <div class="price-section">
                        <div class="product-price">35 <span>جنيه</span></div>
                    </div>
                    <button class="add-to-cart-btn" onclick="addToCart('أرز تاج الفاخر', 35)">
                        <i class="fa-solid fa-plus"></i> إضافة للسلة
                    </button>
                </div>
            </div>

            <!-- 2. المكرونة -->
            <div class="product-card">
                <div>
                    <div class="product-img-holder">
                        <img src="1000437192.jpg" alt="مكرونة تاج العضوية" onerror="this.src='https://via.placeholder.com/200?text=TAJ+Pasta'">
                    </div>
                    <div class="product-info">
                        <h3>مكرونة تاج العضوية (1 كجم)</h3>
                        <p>مصنوعة من أجود أنواع القمح الصلب، سهلة الطهي ولا تتلتصق.</p>
                    </div>
                </div>
                <div>
                    <div class="price-section">
                        <div class="product-price">28 <span>جنيه</span></div>
                    </div>
                    <button class="add-to-cart-btn" onclick="addToCart('مكرونة تاج العضوية', 28)">
                        <i class="fa-solid fa-plus"></i> إضافة للسلة
                    </button>
                </div>
            </div>

            <!-- 3. السكر (مع خيارات السعر والمتوسط والمرتفع) -->
            <div class="product-card">
                <div>
                    <div class="product-img-holder">
                        <img src="1000437189.jpg" alt="سكر تاج العضوي" onerror="this.src='https://via.placeholder.com/200?text=TAJ+Sugar'">
                    </div>
                    <div class="product-info">
                        <h3>سكر تاج (1 كجم)</h3>
                        <p>سكر نقي فاخر عالي الجودة للتحلية المثالية.</p>
                        
                        <!-- اختيارات الفئة للسكر -->
                        <div class="sugar-options">
                            <label for="sugarGrade">اختر الجودة / الدرجة:</label>
                            <select id="sugarGrade" class="sugar-select" onchange="updateSugarPrice()">
                                <option value="30" data-name="سكر تاج - درجة متوسطة">درجة متوسطة - 30 جنيه</option>
                                <option value="42" data-name="سكر تاج - درجة ممتازة مرتفعة">درجة ممتازة فاخرة - 42 جنيه</option>
                            </select>
                        </div>
                    </div>
                </div>
                <div>
                    <div class="price-section">
                        <div class="product-price" id="sugarPriceDisplay">30 <span>جنيه</span></div>
                    </div>
                    <button class="add-to-cart-btn" onclick="addSugarToCart()">
                        <i class="fa-solid fa-plus"></i> إضافة للسلة
                    </button>
                </div>
            </div>

            <!-- 4. بوكس البهارات -->
            <div class="product-card">
                <div>
                    <div class="product-img-holder">
                        <img src="1000437195.jpg" alt="مجموعة بهارات تاج" onerror="this.src='https://via.placeholder.com/200?text=TAJ+Spices'">
                    </div>
                    <div class="product-info">
                        <h3>مجموعة بهارات تاج الملكية</h3>
                        <p>تشمل 4 عبوات: فلفل أسود، ملح بحري، كمون بلدي، وشطة حارة.</p>
                    </div>
                </div>
                <div>
                    <div class="price-section">
                        <div class="product-price">95 <span>جنيه</span></div>
                    </div>
                    <button class="add-to-cart-btn" onclick="addToCart('مجموعة بهارات تاج الملكية', 95)">
                        <i class="fa-solid fa-plus"></i> إضافة للسلة
                    </button>
                </div>
            </div>

        </div>
    </section>

    <!-- سلة التسوق التفاعلية جانبيًا -->
    <div class="cart-drawer" id="cartDrawer">
        <div class="cart-header">
            <h3>سلة التسوق</h3>
            <button class="close-cart" onclick="toggleCart()"><i class="fa-solid fa-xmark"></i></button>
        </div>
        <div class="cart-items" id="cartItemsContainer">
            <p style="text-align: center; color: #888; margin-top: 20px;">السلة فارغة حالياً</p>
        </div>
        <div class="cart-footer">
            <div class="total-price">
                <span>الإجمالي:</span>
                <span id="cartTotal">0 جنيه</span>
            </div>
            <button class="btn-primary" style="width: 100%; text-align: center;" onclick="checkout()">إتمام الطلب</button>
        </div>
    </div>

    <!-- الفوتر وحقوق الملكية -->
    <footer>
        <p>جميع الحقوق محفوظة © 2026 - تم البرمجة بواسطة <span class="developer-name">مصطفى تامر</span></p>
    </footer>

    <!-- الجافاسكربت للتفاعل مع الواجهة -->
    <script>
        let cart = [];
        let total = 0;

        // فتح وإغلاق السلة
        function toggleCart() {
            document.getElementById('cartDrawer').classList.toggle('open');
        }

        // تحديث سعر السكر بناءً على اختيار الدرجة (متوسط / مرتفع)
        function updateSugarPrice() {
            const select = document.getElementById('sugarGrade');
            const price = select.value;
            document.getElementById('sugarPriceDisplay').innerHTML = `${price} <span>جنيه</span>`;
        }

        // إضافة السكر للسلة بناءً على خياره المحدد
        function addSugarToCart() {
            const select = document.getElementById('sugarGrade');
            const selectedOption = select.options[select.selectedIndex];
            const name = selectedOption.getAttribute('data-name');
            const price = parseFloat(select.value);
            
            addToCart(name, price);
        }

        // إضافة منتج للسلة
        function addToCart(title, price) {
            cart.push({ title, price });
            updateCartUI();
            
            // إشعار بسيط بالاضافة
            const btn = event.currentTarget;
            const originalText = btn.innerHTML;
            btn.innerHTML = `<i class="fa-solid fa-check"></i> تم التموين`;
            btn.style.background = "#2ecc71";
            setTimeout(() => {
                btn.innerHTML = originalText;
                btn.style.background = "";
            }, 1200);
        }

        // تحديث واجهة السلة
        function updateCartUI() {
            const cartCount = document.getElementById('cartCount');
          
