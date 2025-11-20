<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sarvatta Cafe - Taste the Difference</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: 700;
            color: #d35400;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #d35400;
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            gap: 4px;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: #333;
            transition: all 0.3s ease;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
                        url('https://images.unsplash.com/photo-1554118811-1e0d58224f24?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: #d35400;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease 0.6s both;
        }

        .cta-button:hover {
            background: #e67e22;
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Menu Section */
        .menu-section {
            padding: 5rem 2rem;
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #2c3e50;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: #d35400;
            margin: 1rem auto;
        }

        .menu-categories {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .category-btn {
            padding: 0.8rem 2rem;
            background: white;
            border: 2px solid #d35400;
            color: #d35400;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .category-btn.active,
        .category-btn:hover {
            background: #d35400;
            color: white;
        }

        .menu-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
        }

        .menu-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .menu-item-content {
            padding: 1.5rem;
        }

        .menu-item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 0.5rem;
        }

        .menu-item h3 {
            font-size: 1.3rem;
            color: #2c3e50;
        }

        .price {
            font-size: 1.2rem;
            color: #d35400;
            font-weight: 600;
        }

        .menu-item p {
            color: #7f8c8d;
            font-size: 0.9rem;
        }

        /* Reviews Section */
        .reviews-section {
            padding: 5rem 2rem;
            background: white;
        }

        .reviews-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .review-card {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .review-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .reviewer-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            background: #d35400;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
        }

        .stars {
            color: #f1c40f;
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .review-text {
            font-style: italic;
            color: #555;
            margin-bottom: 1rem;
        }

        .reviewer-name {
            font-weight: 600;
            color: #2c3e50;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 3rem 2rem 1rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #d35400;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 1rem;
        }

        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: #d35400;
            color: white;
            text-align: center;
            line-height: 40px;
            border-radius: 50%;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: #e67e22;
            transform: translateY(-3px);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .menu-categories {
                gap: 0.5rem;
            }

            .category-btn {
                padding: 0.6rem 1.5rem;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <a href="#home" class="logo">Sarvatta</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#reviews">Reviews</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Welcome to Sarvatta Cafe</h1>
            <p>Where Every Bite Tells a Story</p>
            <a href="#menu" class="cta-button">Explore Our Menu</a>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="menu-section">
        <h2 class="section-title">Our Menu</h2>
        
        <div class="menu-categories">
            <button class="category-btn active" onclick="filterMenu('all')">All</button>
            <button class="category-btn" onclick="filterMenu('pizza')">Pizza</button>
            <button class="category-btn" onclick="filterMenu('dosa')">Dosa</button>
            <button class="category-btn" onclick="filterMenu('drinks')">Drinks</button>
            <button class="category-btn" onclick="filterMenu('combo')">Combos</button>
        </div>

        <div class="menu-grid" id="menuGrid">
            <!-- Pizza Items -->
            <div class="menu-item" data-category="pizza">
                <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Margherita Pizza">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Margherita Pizza</h3>
                        <span class="price">₹90</span>
                    </div>
                    <p>Fresh mozzarella, basil, and our signature tomato sauce</p>
                </div>
            </div>

            <div class="menu-item" data-category="pizza">
                <img src="https://images.unsplash.com/photo-1604382355076-af4b0eb60143?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Veggie Supreme">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Veggie Supreme</h3>
                        <span class="price">₹140</span>
                    </div>
                    <p>Loaded with fresh vegetables and extra cheese</p>
                </div>
            </div>

            <div class="menu-item" data-category="pizza">
                <img src="https://images.unsplash.com/photo-1628840042765-356cda07504e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Paneer Tikka">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Paneer Tikka Pizza</h3>
                        <span class="price">₹150</span>
                    </div>
                    <p>Tandoori paneer with capsicum and onions</p>
                </div>
            </div>

            <!-- Dosa Items -->
            <div class="menu-item" data-category="dosa">
                <img src="https://images.unsplash.com/photo-1585937421612-70a008356fbe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Masala Dosa">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Masala Dosa</h3>
                        <span class="price">₹80</span>
                    </div>
                    <p>Crispy dosa with spiced potato filling</p>
                </div>
            </div>

            <div class="menu-item" data-category="dosa">
                <img src="https://images.unsplash.com/photo-1618040996337-56904b7850b7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Paneer Dosa">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Paneer Dosa</h3>
                        <span class="price">₹120</span>
                    </div>
                    <p>Crispy dosa stuffed with spiced paneer</p>
                </div>
            </div>

            <!-- Drinks -->
            <div class="menu-item" data-category="drinks">
                <img src="https://images.unsplash.com/photo-1556679343-c7306c1976bc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Cold Coffee">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Cold Coffee</h3>
                        <span class="price">₹80</span>
                    </div>
                    <p>Refreshing cold coffee with ice cream</p>
                </div>
            </div>

            <div class="menu-item" data-category="drinks">
                <img src="https://images.unsplash.com/photo-1553909489-cd47e0907980?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Mango Shake">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Mango Shake</h3>
                        <span class="price">₹100</span>
                    </div>
                    <p>Fresh mango milkshake with ice cream</p>
                </div>
            </div>

            <div class="menu-item" data-category="drinks">
                <img src="https://images.unsplash.com/photo-1517705008128-361805f42e86?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Oreo Shake">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Oreo Shake</h3>
                        <span class="price">₹110</span>
                    </div>
                    <p>Delicious oreo cookie milkshake</p>
                </div>
            </div>

            <!-- Combos -->
            <div class="menu-item" data-category="combo">
                <img src="https://images.unsplash.com/photo-1569718212165-3a8278d5f624?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Combo 1">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Chilli Paneer Combo</h3>
                        <span class="price">₹200</span>
                    </div>
                    <p>Chilli Paneer + Rice + Cold Drink</p>
                </div>
            </div>

            <div class="menu-item" data-category="combo">
                <img src="https://images.unsplash.com/photo-1559314809-0d155014e29e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Combo 2">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Manchurian Combo</h3>
                        <span class="price">₹250</span>
                    </div>
                    <p>Manchurian + Noodles + Veg Roll</p>
                </div>
            </div>

            <div class="menu-item" data-category="combo">
                <img src="https://images.unsplash.com/photo-1609501676725-7186f017a4b7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Thali">
                <div class="menu-item-content">
                    <div class="menu-item-header">
                        <h3>Veg Deluxe Thali</h3>
                        <span class="price">₹180</span>
                    </div>
                    <p>Complete meal with dal, rice, roti, and sweets</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Reviews Section -->
    <section id="reviews" class="reviews-section">
        <h2 class="section-title">Customer Reviews</h2>
        
        <div class="reviews-container">
            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="review-text">"Amazing food and excellent service! The paneer tikka pizza is to die for. Will definitely come back!"</p>
                <p class="reviewer-name">- Priya Sharma</p>
            </div>

            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star-half-alt"></i>
                </div>
                <p class="review-text">"Great ambiance and delicious food. The dosa here is as authentic as it gets. Highly recommended!"</p>
                <p class="reviewer-name">- Rahul Patel</p>
            </div>

            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="review-text">"Best cafe in town! The combos are value for money and the shakes are absolutely delicious."</p>
                <p class="reviewer-name">- Anjali Singh</p>
            </div>

            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star-half-alt"></i>
                </div>
                <p class="review-text">"Love the variety in the menu. Something for everyone. The staff is very courteous too."</p>
                <p class="reviewer-name">- Vikas Kumar</p>
            </div>

            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="review-text">"Perfect place for family dinners. The thali is wholesome and tasty. Must visit!"</p>
                <p class="reviewer-name">- Sunita Verma</p>
            </div>

            <div class="review-card">
                <div class="reviewer-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="review-text">"The oreo shake here is the best I've ever had! Quick service and hygienic preparation."</p>
                <p class="reviewer-name">- Arjun Mehta</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-section">
                <h3>Visit Us</h3>
                <p>123, Main Street<br>
                Prayagraj, Uttar Pradesh<br>
                Pin: 211003</p>
            </div>
            
            <div class="footer-section">
                <h3>Contact</h3>
                <p>Phone: +91 98765 43210<br>
                Email: info@sarvattacafe.com<br>
                Timings: 9 AM - 11 PM</p>
            </div>
            
            <div class="footer-section">
                <h3>Follow Us</h3>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
        </div>
        
        <p>&copy; 2024 Sarvatta Cafe. All rights reserved. | Made with <i class="fas fa-heart" style="color: #e74c3c;"></i> for food lovers</p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Navbar background on scroll
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.98)';
            } else {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
            }
        });

        // Menu filtering
        function filterMenu(category) {
            const items = document.querySelectorAll('.menu-item');
            const buttons = document.querySelectorAll('.category-btn');
            
            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            
            items.forEach(item => {
                if (category === 'all' || item.dataset.category === category) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        }

        // Mobile menu toggle
        function toggleMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        }

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease forwards';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.menu-item, .review-card').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
