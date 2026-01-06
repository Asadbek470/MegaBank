# MegaBank
.
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MegabankUz - Надежный банк Узбекистана</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        :root {
            --primary: #2D5BFF;
            --primary-dark: #1A4AFF;
            --primary-light: rgba(45, 91, 255, 0.1);
            --secondary: #00C896;
            --dark: #121212;
            --dark-light: #1E1E1E;
            --darker: #0A0A0A;
            --light: #F8F9FA;
            --gray: #8A8A8A;
            --gray-dark: #555;
            --gray-light: rgba(255, 255, 255, 0.08);
            --border-radius: 16px;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
        }

        body {
            background-color: var(--darker);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Декоративные элементы */
        .bg-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(circle at 20% 80%, rgba(45, 91, 255, 0.03) 0%, transparent 40%),
                              radial-gradient(circle at 80% 20%, rgba(0, 200, 150, 0.03) 0%, transparent 40%);
            pointer-events: none;
            z-index: -1;
        }

        /* Header */
        .header {
            background: linear-gradient(180deg, rgba(18, 18, 18, 0.95) 0%, rgba(18, 18, 18, 0.8) 100%);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .logo {
            display: flex;
            align-items: center;
            font-weight: 700;
            font-size: 28px;
            color: white;
            text-decoration: none;
        }

        .logo i {
            margin-right: 12px;
            font-size: 32px;
            color: var(--primary);
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav {
            display: flex;
            gap: 40px;
        }

        .nav a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            font-size: 16px;
            transition: var(--transition);
            position: relative;
        }

        .nav a:hover {
            color: var(--primary);
        }

        .nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            transition: var(--transition);
        }

        .nav a:hover::after {
            width: 100%;
        }

        .header-btns {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 12px 28px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .btn-outline {
            background: transparent;
            color: var(--light);
            border: 2px solid var(--gray-light);
        }

        .btn-outline:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: translateY(-3px);
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary), var(--primary-dark));
            color: white;
            border: none;
            box-shadow: 0 5px 15px rgba(45, 91, 255, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(45, 91, 255, 0.4);
            background: linear-gradient(45deg, var(--primary-dark), var(--primary));
        }

        /* Hero Section */
        .hero {
            padding: 180px 5% 100px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .hero-content h1 {
            font-size: 56px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 24px;
            background: linear-gradient(45deg, #fff, var(--primary-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-content p {
            font-size: 20px;
            color: var(--gray);
            margin-bottom: 40px;
            max-width: 600px;
        }

        .hero-stats {
            display: flex;
            gap: 40px;
            margin-top: 60px;
        }

        .stat-item h3 {
            font-size: 42px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .stat-item p {
            font-size: 16px;
            color: var(--gray);
            margin: 0;
        }

        .hero-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.9), rgba(18, 18, 18, 0.9));
            border-radius: 24px;
            padding: 30px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }

        .hero-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .card-bank {
            font-weight: 700;
            font-size: 24px;
            color: white;
        }

        .card-badge {
            background: var(--primary-light);
            color: var(--primary);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 600;
        }

        .card-number {
            font-family: monospace;
            font-size: 22px;
            letter-spacing: 2px;
            margin-bottom: 20px;
            color: white;
            background: rgba(0, 0, 0, 0.2);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }

        .card-holder {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        .card-info {
            color: var(--gray);
            font-size: 14px;
            margin-bottom: 5px;
        }

        .card-name {
            font-size: 18px;
            font-weight: 600;
            color: white;
        }

        .card-type {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card-type-icon {
            font-size: 32px;
            color: #1A1A2E;
        }

        .app-showcase {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-top: 30px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .app-showcase img {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            object-fit: cover;
            border: 2px solid var(--primary);
        }

        .app-showcase-content h4 {
            font-size: 18px;
            margin-bottom: 5px;
        }

        .app-showcase-content p {
            font-size: 14px;
            color: var(--gray);
            margin: 0;
        }

        /* Features Section */
        .section {
            padding: 100px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 70px;
        }

        .section-title {
            font-size: 42px;
            font-weight: 800;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-subtitle {
            font-size: 18px;
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--dark-light);
            border-radius: var(--border-radius);
            padding: 40px 30px;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            font-size: 32px;
            color: white;
        }

        .feature-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 15px;
            color: white;
        }

        .feature-desc {
            color: var(--gray);
            font-size: 16px;
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: var(--dark-light);
            border-radius: var(--border-radius);
            padding: 30px;
            display: flex;
            align-items: flex-start;
            gap: 20px;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .service-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
            background: linear-gradient(135deg, rgba(45, 91, 255, 0.1), rgba(30, 30, 30, 0.9));
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: var(--primary-light);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: var(--primary);
            flex-shrink: 0;
        }

        .service-content h3 {
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 10px;
            color: white;
        }

        .service-content p {
            color: var(--gray);
            font-size: 16px;
        }

        /* CEO Section */
        .ceo-section {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.9), rgba(10, 10, 10, 0.9));
            border-radius: var(--border-radius);
            padding: 60px;
            margin: 100px 5%;
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 50px;
            align-items: center;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .ceo-photo {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
            border: 3px solid var(--primary);
        }

        .ceo-content h2 {
            font-size: 36px;
            font-weight: 800;
            margin-bottom: 20px;
            color: white;
        }

        .ceo-title {
            color: var(--primary);
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 20px;
            display: block;
        }

        .ceo-quote {
            font-size: 20px;
            font-style: italic;
            color: var(--light);
            margin-bottom: 30px;
            line-height: 1.8;
            border-left: 4px solid var(--primary);
            padding-left: 20px;
        }

        .ceo-name {
            font-size: 24px;
            font-weight: 700;
            color: white;
        }

        /* CTA Section */
        .cta-section {
            text-align: center;
            padding: 100px 5%;
            background: linear-gradient(135deg, rgba(45, 91, 255, 0.1), rgba(10, 10, 10, 0.9));
            border-radius: var(--border-radius);
            margin: 0 5% 100px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .cta-title {
            font-size: 42px;
            font-weight: 800;
            margin-bottom: 20px;
            color: white;
        }

        .cta-subtitle {
            font-size: 18px;
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto 40px;
        }

        /* Footer */
        .footer {
            background: var(--darker);
            padding: 80px 5% 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 50px;
            margin-bottom: 50px;
        }

        .footer-logo {
            font-size: 28px;
            font-weight: 700;
            color: white;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        .footer-logo i {
            margin-right: 10px;
            color: var(--primary);
        }

        .footer-about {
            color: var(--gray);
            font-size: 16px;
            margin-bottom: 30px;
        }

        .footer-title {
            font-size: 20px;
            font-weight: 700;
            color: white;
            margin-bottom: 25px;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 15px;
        }

        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-links a:hover {
            color: var(--primary);
            transform: translateX(5px);
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            color: var(--gray);
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background: var(--primary-light);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--gray);
            font-size: 14px;
        }

        .certificates {
            display: flex;
            gap: 20px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .cert-badge {
            background: var(--dark-light);
            padding: 10px 20px;
            border-radius: 50px;
            font-size: 12px;
            color: var(--gray);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .hero {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-stats {
                justify-content: center;
            }

            .ceo-section {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .nav {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .header-btns {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 42px;
            }

            .section-title {
                font-size: 36px;
            }

            .ceo-section {
                padding: 40px 20px;
            }

            .features-grid,
            .services-grid {
                grid-template-columns: 1fr;
            }

            .hero-stats {
                flex-direction: column;
                gap: 30px;
            }
        }

        /* Animation */
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

        .animate {
            animation: fadeInUp 0.8s ease forwards;
        }

        .delay-1 {
            animation-delay: 0.2s;
        }

        .delay-2 {
            animation-delay: 0.4s;
        }

        .delay-3 {
            animation-delay: 0.6s;
        }
    </style>
</head>
<body>
    <!-- Декоративный фон -->
    <div class="bg-pattern"></div>

    <!-- Header -->
    <header class="header">
        <a href="#" class="logo">
            <i class="fas fa-university"></i>
            MegabankUz
        </a>

        <nav class="nav">
            <a href="#features">Возможности</a>
            <a href="#services">Услуги</a>
            <a href="#ceo">Руководство</a>
            <a href="#contact">Контакты</a>
        </nav>

        <div class="header-btns">
            <button class="btn btn-outline">Войти</button>
            <button class="btn btn-primary">Открыть счёт</button>
        </div>

        <button class="mobile-menu-btn" id="mobileMenuBtn">
            <i class="fas fa-bars"></i>
        </button>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content animate">
            <h1>Банк будущего уже здесь</h1>
            <p>MegabankUz — это современный банк с более чем 15-летним опытом работы на рынке Узбекистана. Безопасность, надежность и инновации в каждом сервисе.</p>
            
            <div class="hero-btns">
                <button class="btn btn-primary" style="margin-right: 15px;">
                    <i class="fas fa-mobile-alt"></i> Скачать приложение
                </button>
                <button class="btn btn-outline">
                    <i class="fas fa-credit-card"></i> Оформить карту
                </button>
            </div>

            <div class="hero-stats">
                <div class="stat-item">
                    <h3>15+</h3>
                    <p>Лет на рынке</p>
                </div>
                <div class="stat-item">
                    <h3>500K+</h3>
                    <p>Довольных клиентов</p>
                </div>
                <div class="stat-item">
                    <h3>24/7</h3>
                    <p>Поддержка клиентов</p>
                </div>
            </div>
        </div>

        <div class="hero-card animate delay-1">
            <div class="card-header">
                <div class="card-bank">megabankUz</div>
                <div class="card-badge">PREMIUM</div>
            </div>
            
            <div class="card-number">8600 1230 9364 8619</div>
            
            <div class="card-holder">
                <div>
                    <div class="card-info">CARD HOLDER</div>
                    <div class="card-name">ASADBEK ABDUMALIKOV</div>
                </div>
                <div>
                    <div class="card-info">EXPIRES</div>
                    <div class="card-name">12/28</div>
                </div>
            </div>
            
            <div class="card-type">
                <div class="card-type-icon">
                    <i class="fab fa-cc-visa" style="color: #1A1A2E; font-size: 40px;"></i>
                </div>
                <div style="flex-grow: 1;"></div>
                <div class="card-type-icon">
                    <i class="fas fa-wifi" style="color: #2D5BFF; font-size: 30px;"></i>
                </div>
            </div>

            <div class="app-showcase">
                <img src="https://images.unsplash.com/photo-1611605698335-8b1569810432?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80" alt="Bank App">
                <div class="app-showcase-content">
                    <h4>MegabankUz App</h4>
                    <p>Управляйте финансами в одном приложении</p>
                </div>
                <div style="flex-grow: 1;"></div>
                <i class="fas fa-arrow-right" style="color: var(--primary);"></i>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section" id="features">
        <div class="section-header animate">
            <h2 class="section-title">Почему выбирают MegabankUz?</h2>
            <p class="section-subtitle">Современные технологии и надежность в каждом аспекте банковского обслуживания</p>
        </div>

        <div class="features-grid">
            <div class="feature-card animate delay-1">
                <div class="feature-icon">
                    <i class="fas fa-shield-alt"></i>
                </div>
                <h3 class="feature-title">Максимальная безопасность</h3>
                <p class="feature-desc">ISO 27001 сертификация, многофакторная аутентификация и шифрование данных военного уровня</p>
            </div>

            <div class="feature-card animate delay-2">
                <div class="feature-icon">
                    <i class="fas fa-bolt"></i>
                </div>
                <h3 class="feature-title">Мгновенные переводы</h3>
                <p class="feature-desc">Переводы между картами за секунды, 24/7 без выходных и праздников</p>
            </div>

            <div class="feature-card animate delay-3">
                <div class="feature-icon">
                    <i class="fas fa-mobile-alt"></i>
                </div>
                <h3 class="feature-title">Удобное приложение</h3>
                <p class="feature-desc">Все банковские операции в вашем смартфоне с интуитивным интерфейсом</p>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="section" id="services">
        <div class="section-header animate">
            <h2 class="section-title">Наши услуги</h2>
            <p class="section-subtitle">Полный спектр финансовых услуг для частных и корпоративных клиентов</p>
        </div>

        <div class="services-grid">
            <div class="service-card animate delay-1">
                <div class="service-icon">
                    <i class="fas fa-credit-card"></i>
                </div>
                <div class="service-content">
                    <h3>Банковские карты</h3>
                    <p>VISA, UZCARD, Mastercard с индивидуальным дизайном и премиальными условиями обслуживания</p>
                </div>
            </div>

            <div class="service-card animate delay-2">
                <div class="service-icon">
                    <i class="fas fa-home"></i>
                </div>
                <div class="service-content">
                    <h3>Ипотечное кредитование</h3>
                    <p>Выгодные ставки от 12% годовых на покупку жилья с минимальным пакетом документов</p>
                </div>
            </div>

            <div class="service-card animate delay-3">
                <div class="service-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <div class="service-content">
                    <h3>Инвестиции</h3>
                    <p>Доверительное управление, фондовый рынок и структурные продукты с доходностью до 25% годовых</p>
                </div>
            </div>
        </div>

        <div class="services-grid" style="margin-top: 30px;">
            <div class="service-card animate delay-1">
                <div class="service-icon">
                    <i class="fas fa-exchange-alt"></i>
                </div>
                <div class="service-content">
                    <h3>Международные переводы</h3>
                    <p>Быстрые и безопасные переводы в 150+ стран мира с минимальной комиссией</p>
                </div>
            </div>

            <div class="service-card animate delay-2">
                <div class="service-icon">
                    <i class="fas fa-university"></i>
                </div>
                <div class="service-content">
                    <h3>Корпоративное обслуживание</h3>
                    <p>Полный комплекс банковских услуг для бизнеса любого масштаба</p>
                </div>
            </div>

            <div class="service-card animate delay-3">
                <div class="service-icon">
                    <i class="fas fa-file-invoice-dollar"></i>
                </div>
                <div class="service-content">
                    <h3>Государственные услуги</h3>
                    <p>Оплата налогов, пошлин и других государственных платежей в один клик</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CEO Section -->
    <section class="ceo-section" id="ceo">
        <div class="animate">
            <!-- Фото из предоставленных картинок -->
            <div style="width: 300px; height: 400px; background: linear-gradient(135deg, var(--primary), var(--secondary)); border-radius: 20px; display: flex; align-items: center; justify-content: center; color: white; font-size: 48px; margin: 0 auto;">
                <i class="fas fa-user-tie"></i>
            </div>
        </div>
        
        <div class="ceo-content animate delay-1">
            <span class="ceo-title">ГЕНЕРАЛЬНЫЙ ДИРЕКТОР</span>
            <h2>Асадбек Абдумаликов</h2>
            <p class="ceo-quote">"В MegabankUz мы верим, что банковские услуги должны быть не только надежными, но и удобными, доступными и безопасными для каждого клиента. Наша миссия — создавать финансовые решения, которые делают жизнь людей лучше."</p>
            <div class="ceo-name">Асадбек Абдумаликов</div>
            <p style="color: var(--gray); margin-top: 10px;">Генеральный директор MegabankUz с 2015 года</p>
            
            <div style="margin-top: 30px; display: flex; gap: 20px;">
                <div>
                    <h3 style="color: var(--primary); font-size: 32px;">15+</h3>
                    <p style="color: var(--gray);">лет в банковской сфере</p>
                </div>
                <div>
                    <h3 style="color: var(--primary); font-size: 32px;">MBA</h3>
                    <p style="color: var(--gray);">Гарвардская бизнес-школа</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section animate">
        <h2 class="cta-title">Готовы стать клиентом?</h2>
        <p class="cta-subtitle">Присоединяйтесь к более чем 500 000 клиентов, которые уже выбрали MegabankUz для управления своими финансами</p>
        
        <div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap;">
            <button class="btn btn-primary" style="padding: 18px 40px; font-size: 18px;">
                <i class="fas fa-user-plus"></i> Открыть счёт онлайн
            </button>
            <button class="btn btn-outline" style="padding: 18px 40px; font-size: 18px;">
                <i class="fas fa-phone-alt"></i> Позвонить нам
            </button>
        </div>
        
        <div class="certificates" style="margin-top: 40px; justify-content: center;">
            <div class="cert-badge">Лицензия ЦБ РУз №7721</div>
            <div class="cert-badge">AML/KYC Compliant</div>
            <div class="cert-badge">ISO 27001 Certified</div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer" id="contact">
        <div class="footer-content">
            <div>
                <div class="footer-logo">
                    <i class="fas fa-university"></i>
                    MegabankUz
                </div>
                <p class="footer-about">Лицензированная финансовая организация, осуществляющая деятельность в соответствии с законодательством Республики Узбекистан.</p>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <div style="color: white; font-weight: 600;">Телефон</div>
                            <div>+998 99 910 00 97</div>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-globe"></i>
                        </div>
                        <div>
                            <div style="color: white; font-weight: 600;">Сайт</div>
                            <div>https://megabank.uz</div>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <div style="color: white; font-weight: 600;">Email</div>
                            <div>info@megabank.uz</div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div>
                <h3 class="footer-title">Услуги</h3>
                <ul class="footer-links">
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Банковские карты</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Кредиты</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Вклады</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Переводы</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Инвестиции</a></li>
                </ul>
            </div>
            
            <div>
                <h3 class="footer-title">О банке</h3>
                <ul class="footer-links">
                    <li><a href="#"><i class="fas fa-chevron-right"></i> О нас</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Новости</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Вакансии</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Контакты</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Документы</a></li>
                </ul>
            </div>
            
            <div>
                <h3 class="footer-title">Поддержка</h3>
                <ul class="footer-links">
                    <li><a href="#"><i class="fas fa-chevron-right"></i> FAQ</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Отделения и банкоматы</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Курсы валют</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Тарифы</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Безопасность</a></li>
                </ul>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>© 2026 MegabankUz. Все права защищены.</p>
            <p>Лицензия ЦБ РУз №7721 | AML/KYC Compliant | ISO 27001 Certified</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Mobile menu toggle
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const nav = document.querySelector('.nav');
            const headerBtns = document.querySelector('.header-btns');
            
            mobileMenuBtn.addEventListener('click', function() {
                nav.style.display = nav.style.display === 'flex' ? 'none' : 'flex';
                headerBtns.style.display = headerBtns.style.display === 'flex' ? 'none' : 'flex';
                
                if (nav.style.display === 'flex') {
                    nav.style.flexDirection = 'column';
                    nav.style.position = 'absolute';
                    nav.style.top = '100%';
                    nav.style.left = '0';
                    nav.style.right = '0';
                    nav.style.background = 'var(--darker)';
                    nav.style.padding = '20px';
                    nav.style.gap = '20px';
                    nav.style.borderTop = '1px solid rgba(255, 255, 255, 0.05)';
                    
                    headerBtns.style.position = 'absolute';
                    headerBtns.style.top = 'calc(100% + 180px)';
                    headerBtns.style.left = '0';
                    headerBtns.style.right = '0';
                    headerBtns.style.padding = '20px';
                    headerBtns.style.background = 'var(--darker)';
                    headerBtns.style.flexDirection = 'column';
                    headerBtns.style.gap = '15px';
                }
            });

            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        // Close mobile menu if open
                        if (window.innerWidth <= 1024) {
                            nav.style.display = 'none';
                            headerBtns.style.display = 'none';
                        }
                        
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });

            // Animate elements on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate');
                    }
                });
            }, observerOptions);

            // Observe all sections
            document.querySelectorAll('.section-header, .feature-card, .service-card, .ceo-section, .cta-section').forEach(el => {
                observer.observe(el);
            });

            // Header scroll effect
            let lastScroll = 0;
            window.addEventListener('scroll', function() {
                const header = document.querySelector('.header');
                const currentScroll = window.pageYOffset;
                
                if (currentScroll <= 0) {
                    header.style.background = 'linear-gradient(180deg, rgba(18, 18, 18, 0.95) 0%, rgba(18, 18, 18, 0.8) 100%)';
                    header.style.boxShadow = 'none';
                } else if (currentScroll > lastScroll) {
                    // Scrolling down
                    header.style.background = 'rgba(18, 18, 18, 0.95)';
                    header.style.boxShadow = '0 10px 30px rgba(0, 0, 0, 0.3)';
                } else {
                    // Scrolling up
                    header.style.background = 'rgba(18, 18, 18, 0.98)';
                    header.style.boxShadow = '0 10px 30px rgba(0, 0, 0, 0.3)';
                }
                
                lastScroll = currentScroll;
            });

            // Button click handlers
            document.querySelectorAll('.btn-primary').forEach(btn => {
                if (!btn.id) {
                    btn.addEventListener('click', function() {
                        alert('Благодарим за интерес к MegabankUz! Наш менеджер свяжется с вами в ближайшее время.');
                    });
                }
            });
        });
    </script>
</body>
</html>
