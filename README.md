<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mundo Delivery News - As últimas notícias sobre delivery</title>
    <style>
        /* Reset e estilos gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', Arial, sans-serif;
        }
        
        :root {
            --primary-color: #ff6b00;
            --secondary-color: #333;
            --light-color: #f9f9f9;
            --dark-color: #222;
            --text-color: #333;
            --text-light: #777;
            --border-color: #e0e0e0;
            --success-color: #28a745;
        }
        
        body {
            background-color: #f5f5f5;
            color: var(--text-color);
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        ul {
            list-style: none;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid var(--border-color);
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-color);
        }
        
        .logo span {
            color: var(--secondary-color);
        }
        
        .search-bar {
            flex: 0 1 400px;
            position: relative;
        }
        
        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid var(--border-color);
            border-radius: 30px;
            font-size: 14px;
        }
        
        .search-bar button {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--text-light);
            cursor: pointer;
        }
        
        .user-actions a {
            margin-left: 15px;
            color: var(--text-color);
            font-size: 14px;
        }
        
        .user-actions a:hover {
            color: var(--primary-color);
        }
        
        nav {
            padding: 15px 0;
        }
        
        nav ul {
            display: flex;
            justify-content: center;
        }
        
        nav li {
            margin: 0 15px;
        }
        
        nav a {
            font-weight: 500;
            font-size: 16px;
            padding: 5px 0;
            position: relative;
        }
        
        nav a:hover {
            color: var(--primary-color);
        }
        
        nav a.active {
            color: var(--primary-color);
        }
        
        nav a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: var(--primary-color);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1565299624946-b28f40a0ca4b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            margin-bottom: 40px;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 42px;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 18px;
            margin-bottom: 30px;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 25px;
            background-color: var(--primary-color);
            color: white;
            border-radius: 30px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .btn:hover {
            background-color: #e05e00;
            transform: translateY(-2px);
        }
        
        /* Main Content */
        .main-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        /* Featured News */
        .featured-news {
            margin-bottom: 40px;
        }
        
        .section-title {
            font-size: 24px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-color);
            display: inline-block;
        }
        
        .featured-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
        
        .news-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        
        .news-card:hover {
            transform: translateY(-5px);
        }
        
        .news-card.large {
            grid-column: 1 / -1;
            display: flex;
        }
        
        .news-card.large .news-image {
            flex: 0 0 50%;
        }
        
        .news-card.large .news-content {
            flex: 1;
            padding: 20px;
        }
        
        .news-image {
            height: 200px;
            overflow: hidden;
        }
        
        .news-card.large .news-image {
            height: auto;
        }
        
        .news-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .news-card:hover .news-image img {
            transform: scale(1.05);
        }
        
        .news-content {
            padding: 15px;
        }
        
        .news-category {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            font-size: 12px;
            padding: 3px 8px;
            border-radius: 3px;
            margin-bottom: 10px;
        }
        
        .news-title {
            font-size: 18px;
            margin-bottom: 10px;
            line-height: 1.4;
        }
        
        .news-card.large .news-title {
            font-size: 24px;
        }
        
        .news-excerpt {
            color: var(--text-light);
            font-size: 14px;
            margin-bottom: 15px;
        }
        
        .news-meta {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--text-light);
        }
        
        /* Latest News */
        .latest-news {
            margin-bottom: 40px;
        }
        
        .news-list .news-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .news-list .news-item:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .news-list .news-image {
            flex: 0 0 100px;
            height: 80px;
            margin-right: 15px;
        }
        
        .news-list .news-content {
            flex: 1;
            padding: 0;
        }
        
        .news-list .news-title {
            font-size: 16px;
            margin-bottom: 5px;
        }
        
        /* Sidebar */
        .sidebar-widget {
            background-color: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 30px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .widget-title {
            font-size: 18px;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .trending-list li {
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .trending-list li:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .trending-list .number {
            display: inline-block;
            width: 24px;
            height: 24px;
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            line-height: 24px;
            border-radius: 50%;
            margin-right: 10px;
            font-size: 12px;
        }
        
        .app-promo {
            background: linear-gradient(135deg, var(--primary-color), #ff8c42);
            color: white;
            text-align: center;
            padding: 30px 20px;
            border-radius: 8px;
        }
        
        .app-promo h3 {
            margin-bottom: 15px;
        }
        
        .app-promo p {
            margin-bottom: 20px;
            font-size: 14px;
        }
        
        .app-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        
        .app-btn {
            display: inline-block;
            padding: 8px 15px;
            background-color: white;
            color: var(--primary-color);
            border-radius: 5px;
            font-size: 12px;
            font-weight: 600;
        }
        
        /* Newsletter */
        .newsletter {
            background-color: var(--dark-color);
            color: white;
            padding: 50px 0;
            text-align: center;
        }
        
        .newsletter h2 {
            margin-bottom: 15px;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 25px;
            color: #ccc;
        }
        
        .newsletter-form {
            max-width: 500px;
            margin: 0 auto;
            display: flex;
        }
        
        .newsletter-form input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 30px 0 0 30px;
        }
        
        .newsletter-form button {
            padding: 0 25px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 0 30px 30px 0;
            cursor: pointer;
            font-weight: 600;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary-color);
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #ccc;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #999;
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-bar {
                flex: 1;
                width: 100%;
            }
            
            nav ul {
                flex-wrap: wrap;
            }
            
            nav li {
                margin: 5px 10px;
            }
            
            .featured-grid {
                grid-template-columns: 1fr;
            }
            
            .news-card.large {
                flex-direction: column;
            }
            
            .news-card.large .news-image {
                flex: 0 0 auto;
            }
            
            .hero h1 {
                font-size: 32px;
            }
        }
        
        @media (max-width: 576px) {
            .footer-content {
                grid-template-columns: 1fr;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 30px;
                margin-bottom: 10px;
            }
            
            .newsletter-form button {
                border-radius: 30px;
                padding: 12px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <div class="logo">Mundo<span>Delivery</span>News</div>
                <div class="search-bar">
                    <input type="text" placeholder="Buscar notícias...">
                    <button>🔍</button>
                </div>
                <div class="user-actions">
                    <a href="https://s.shopee.com.br/804ZIJtlMr">Entrar</a>
                    <a href="https://s.shopee.com.br/804ZIJtlMr">Cadastrar</a>
                </div>
            </div>
            <nav>
                <ul>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr" class="active">Início</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Apps</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Restaurantes</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Tecnologia</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Mercado</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Entregadores</a></li>
                    <li><a href="https://s.shopee.com.br/804ZIJtlMr">Promoções</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Keeta inicia operação no Brasil com entregas em Santos e São Vicente</h1>
                <p>O aplicativo de delivery Keeta, braço internacional da chinesa Meituan, inicia as operações no litoral paulista com mil restaurantes cadastrados.</p>
                <a href="https://s.shopee.com.br/804ZIJtlMr" class="btn">Ler Mais</a>
            </div>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <div class="main-content">
            <!-- Left Column -->
            <div class="left-column">
                <!-- Featured News -->
                <section class="featured-news">
                    <h2 class="section-title">Destaques</h2>
                    <div class="featured-grid">
                        <article class="news-card large">
                            <div class="news-image">
                                <img src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="iFood anuncia nova funcionalidade">
                            </div>
                            <div class="news-content">
                                <span class="news-category">Tecnologia</span>
                                <h3 class="news-title">iFood anuncia nova funcionalidade de entrega em tempo real</h3>
                                <p class="news-excerpt">Plataforma brasileira lança sistema que permite acompanhar o preparo do pedido em tempo real nos restaurantes parceiros.</p>
                                <div class="news-meta">
                                    <span>Por Redação</span>
                                    <span>2 horas atrás</span>
                                </div>
                                <a href="https://s.shopee.com.br/804ZIJtlMr" class="btn" style="margin-top: 10px; display: inline-block;">Ler Mais</a>
                            </div>
                        </article>
                        
                        <article class="news-card">
                            <a href="https://s.shopee.com.br/804ZIJtlMr">
                                <div class="news-image">
                                    <img src="https://images.unsplash.com/photo-1571091718767-18b5b1457add?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Rappi investe R$ 1,4 bi">
                                </div>
                                <div class="news-content">
                                    <span class="news-category">Mercado</span>
                                    <h3 class="news-title">Rappi anuncia investimento de R$ 1,4 bilhão para expansão no Brasil</h3>
                                    <div class="news-meta">
                                        <span>Por João Silva</span>
                                        <span>5 horas atrás</span>
                                    </div>
                                </div>
                            </a>
                        </article>
                        
                        <article class="news-card">
                            <a href="https://s.shopee.com.br/804ZIJtlMr">
                                <div class="news-image">
                                    <img src="https://images.unsplash.com/photo-1542838132-92c53300491e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="99Food retorna ao mercado">
                                </div>
                                <div class="news-content">
                                    <span class="news-category">Apps</span>
                                    <h3 class="news-title">99Food retorna ao mercado brasileiro com investimento de R$ 2 bilhões</h3>
                                    <div class="news-meta">
                                        <span>Por Maria Santos</span>
                                        <span>1 dia atrás</span>
                                    </div>
                                </div>
                            </a>
                        </article>
                    </div>
                </section>
                
                <!-- Latest News -->
                <section class="latest-news">
                    <h2 class="section-title">Últimas Notícias</h2>
                    <div class="news-list">
                        <article class="news-item">
                            <a href="https://s.shopee.com.br/804ZIJtlMr" style="display: flex; width: 100%;">
                                <div class="news-image">
                                    <img src="https://images.unsplash.com/photo-1559339352-11d035aa65de?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Delivery sustentável">
                                </div>
                                <div class="news-content">
                                    <span class="news-category">Sustentabilidade</span>
                                    <h3 class="news-title">Apps de delivery adotam embalagens sustentáveis em parceria com ONGs</h3>
                                    <div class="news-meta">
                                        <span>Por Carlos Lima</span>
                                        <span>3 horas atrás</span>
                                    </div>
                                </div>
                            </a>
                        </article>
                        
                        <article class="news-item">
                            <a href="https://s.shopee.com.br/804ZIJtlMr" style="display: flex; width: 100%;">
                                <div class="news-image">
                                    <img src="https://images.unsplash.com/photo-1587339278756-d81457bb1d1c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Entregadores">
                                </div>
                                <div class="news-content">
                                    <span class="news-category">Entregadores</span>
                                    <h3 class="news-title">Entregadores aprovam nova política de remuneração do iFood</h3>
                                    <div class="news-meta">
                                        <span>Por Ana Costa</span>
                                        <span>6 horas atrás</span>
                                    </div>
                                </div>
                            </a>
                        </article>
                        
                        <article class="news-item">
                            <a href="https://s.shopee.com.br/804ZIJtlMr" style="display: flex; width: 100%;">
                                <div class="news-image">
                                    <img src="https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Restaurantes">
                                </div>
                                <div class="news-content">
                                    <span class="news-category">Restaurantes</span>
                                    <h3 class="news-title">Restaurantes veem aumento de 30% nas vendas com sistema de delivery integrado</h3>
                                    <div class="news-meta">
                                        <span>Por Pedro Almeida</span>
                                        <span>1 dia atrás</span>
                                    </div>
                                </div>
                            </a>
                        </article>
                    </div>
                </section>
            </div>
            
            <!-- Right Column (Sidebar) -->
            <div class="right-column">
                <!-- Trending News -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Em Alta</h3>
                    <ul class="trending-list">
                        <li>
                            <span class="number">1</span>
                            <a href="https://s.shopee.com.br/804ZIJtlMr">Keeta chega ao Brasil com promessa de descontos de até R$ 100</a>
                        </li>
                        <li>
                            <span class="number">2</span>
                            <a href="https://s.shopee.com.br/804ZIJtlMr">Guerra do delivery se intensifica com entrada de novos players</a>
                        </li>
                        <li>
                            <span class="number">3</span>
                            <a href="https://s.shopee.com.br/804ZIJtlMr">iFood planeja investir R$ 17 bilhões até 2026</a>
                        </li>
                        <li>
                            <span class="number">4</span>
                            <a href="https://s.shopee.com.br/804ZIJtlMr">Apps testam drones para entrega em grandes centros</a>
                        </li>
                        <li>
                            <span class="number">5</span>
                            <a href="https://s.shopee.com.br/804ZIJtlMr">Como escolher o melhor app de delivery para seu restaurante</a>
                        </li>
                    </ul>
                </div>
                
                <!-- App Promotion -->
                <div class="sidebar-widget app-promo">
                    <h3>Baixe nosso app</h3>
                    <p>Receba as notícias mais quentes do mundo delivery direto no seu celular</p>
                    <div class="app-buttons">
                        <a href="https://s.shopee.com.br/804ZIJtlMr" class="app-btn">Google Play</a>
                        <a href="https://s.shopee.com.br/804ZIJtlMr" class="app-btn">App Store</a>
                    </div>
                </div>
                
                <!-- Categories -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Categorias</h3>
                    <ul class="footer-links">
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Apps de Delivery</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Restaurantes</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Tecnologia</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Mercado & Finanças</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Entregadores</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Promoções & Cupons</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="container">
            <h2>Fique por dentro das novidades</h2>
            <p>Assine nossa newsletter e receba as principais notícias do mundo do delivery diretamente no seu e-mail.</p>
            <form class="newsletter-form">
                <input type="email" placeholder="Seu melhor e-mail" required>
                <button type="submit">Assinar</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>MundoDeliveryNews</h3>
                    <p>O portal de notícias mais completo sobre o universo do delivery. Trazemos as últimas novidades sobre apps, restaurantes, tecnologia e muito mais.</p>
                    <div class="social-links">
                        <a href="https://s.shopee.com.br/804ZIJtlMr"><span>f</span></a>
                        <a href="https://s.shopee.com.br/804ZIJtlMr"><span>t</span></a>
                        <a href="https://s.shopee.com.br/804ZIJtlMr"><span>in</span></a>
                        <a href="https://s.shopee.com.br/804ZIJtlMr"><span>ig</span></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Links Rápidos</h3>
                    <ul class="footer-links">
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Início</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Sobre Nós</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Contato</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Política de Privacidade</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Termos de Uso</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Categorias</h3>
                    <ul class="footer-links">
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Apps</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Restaurantes</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Tecnologia</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Mercado</a></li>
                        <li><a href="https://s.shopee.com.br/804ZIJtlMr">Entregadores</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contato</h3>
                    <ul class="footer-links">
                        <li>contato@mundodeliverynews.com.br</li>
                        <li>(11) 9999-9999</li>
                        <li>Av. Paulista, 1000<br>São Paulo - SP</li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2023 MundoDeliveryNews. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>
</body>
</html>
