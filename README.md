<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus - Cyberpunk Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --neon-cyan: #00f3ff;
            --neon-pink: #ff00ff;
            --neon-green: #00ff9c;
            --dark-bg: #0a0a16;
            --dark-purple: #1a1a2e;
            --text-color: #e6e6e6;
        }
        
        body {
            background-color: var(--dark-bg);
            color: var(--text-color);
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(0, 243, 255, 0.05) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(255, 0, 255, 0.05) 0%, transparent 20%);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: rgba(26, 26, 46, 0.8);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            border-bottom: 1px solid var(--neon-cyan);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 2.5rem;
            font-weight: 800;
            text-transform: uppercase;
            background: linear-gradient(45deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 10px rgba(0, 243, 255, 0.5);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .nav-links a:hover {
            color: var(--neon-cyan);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--neon-cyan);
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            text-align: center;
            padding: 80px 0 50px;
            position: relative;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 3px;
            background: linear-gradient(45deg, var(--neon-cyan), var(--neon-pink), var(--neon-green));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 15px rgba(0, 243, 255, 0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 40px;
            line-height: 1.6;
        }
        
        /* Products Section */
        .products {
            padding: 60px 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--neon-green);
            text-shadow: 0 0 10px rgba(0, 255, 156, 0.5);
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: linear-gradient(145deg, rgba(26, 26, 46, 0.8), rgba(10, 10, 22, 0.8));
            border: 1px solid rgba(0, 243, 255, 0.3);
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4), 0 0 15px rgba(0, 243, 255, 0.5);
            border-color: var(--neon-cyan);
        }
        
        .product-image {
            height: 250px;
            position: relative;
            overflow: hidden;
        }
        
        .carousel {
            display: flex;
            transition: transform 0.5s ease;
            height: 100%;
        }
        
        .carousel img {
            min-width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .carousel-nav {
            position: absolute;
            bottom: 15px;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        
        .carousel-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .carousel-dot.active {
            background: var(--neon-cyan);
            box-shadow: 0 0 10px var(--neon-cyan);
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-info h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--neon-green);
        }
        
        .product-info p {
            color: #ccc;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .product-price {
            font-size: 1.5rem;
            color: var(--neon-pink);
            margin-bottom: 20px;
            font-weight: 700;
            text-shadow: 0 0 5px rgba(255, 0, 255, 0.5);
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(45deg, var(--neon-cyan), var(--neon-pink));
            color: white;
            padding: 12px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4), 0 0 15px rgba(0, 243, 255, 0.5);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-purple);
            padding: 50px 0 20px;
            border-top: 1px solid var(--neon-pink);
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-column h3 {
            font-size: 1.4rem;
            margin-bottom: 20px;
            color: var(--neon-cyan);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .footer-column p {
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--neon-cyan), var(--neon-pink));
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 243, 255, 0.5);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 20px;
            }
            
            .nav-links {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">Nexus</div>
            <nav class="nav-links">
                <a href="#">Início</a>
                <a href="#products">Produtos</a>
                <a href="#">Sobre</a>
                <a href="#">Contato</a>
            </nav>
        </div>
    </header>
    
    <section class="hero">
        <div class="container">
            <h1>Bem-vindo ao Futuro</h1>
            <p>Descubra os produtos mais inovadores e tecnológicos que preparamos para você. Qualidade e estilo em um só lugar.</p>
            <a href="#products" class="btn">Explorar Produtos</a>
        </div>
    </section>
    
    <section id="products" class="products">
        <div class="container">
            <h2 class="section-title">Nossos Produtos</h2>
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-image">
                        <div class="carousel">
                            <img src="https://via.placeholder.com/300x250/0a0a16/00f3ff?text=Teclado+Mecânico" alt="Teclado Mecânico">
                            <img src="https://via.placeholder.com/300x250/1a1a2e/ff00ff?text=Teclado+RGB" alt="Teclado RGB">
                            <img src="https://via.placeholder.com/300x250/0a0a16/00ff9c?text=Teclado+Iluminado" alt="Teclado Iluminado">
                        </div>
                        <div class="carousel-nav">
                            <div class="carousel-dot active"></div>
                            <div class="carousel-dot"></div>
                            <div class="carousel-dot"></div>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3>Brinquedo Para Aliviar O Estresse Teclado Mecânico</h3>
                        <p>Teclado mecânico de brinquedo para aliviar o estresse. Perfeito para escritório e uso doméstico.</p>
                        <div class="product-price">R$ 18,02</div>
                        <a href="https://mercadolivre.com/sec/2czF3Vu" class="btn">Confira Agora</a>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-image">
                        <div class="carousel">
                            <img src="https://via.placeholder.com/300x250/1a1a2e/00f3ff?text=Pedal+Plataforma" alt="Pedal Plataforma">
                            <img src="https://via.placeholder.com/300x250/0a0a16/ff00ff?text=Pedal+Absolute" alt="Pedal Absolute">
                            <img src="https://via.placeholder.com/300x250/1a1a2e/00ff9c?text=Pedal+MTB" alt="Pedal MTB">
                        </div>
                        <div class="carousel-nav">
                            <div class="carousel-dot active"></div>
                            <div class="carousel-dot"></div>
                            <div class="carousel-dot"></div>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3>Pedal Plataforma Absolute Prime Flat Bike Mtb Urbana 9/16</h3>
                        <p>A marca Absolute é amplamente reconhecida por sua qualidade superior e inovação constante. Produtos testados e aprovados por ciclistas profissionais.</p>
                        <div class="product-price">R$ 207,99</div>
                        <a href="https://mercadolivre.com/sec/2HGCCXr" class="btn">Confira Agora</a>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-image">
                        <div class="carousel">
                            <img src="https://via.placeholder.com/300x250/0a0a16/00f3ff?text=Manopla+Downhill" alt="Manopla Downhill">
                            <img src="https://via.placeholder.com/300x250/1a1a2e/ff00ff?text=Manopla+Gios" alt="Manopla Gios">
                            <img src="https://via.placeholder.com/300x250/0a0a16/00ff9c?text=Manopla+BMX" alt="Manopla BMX">
                        </div>
                        <div class="carousel-nav">
                            <div class="carousel-dot active"></div>
                            <div class="carousel-dot"></div>
                            <div class="carousel-dot"></div>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3>Manopla Gios Freeride Bmx Downhill Manobra Grau Longa 165mm</h3>
                        <p>A Manopla Gios GI-058H é ideal para ciclistas que querem dar um visual diferenciado na bike, sem abrir mão da firmeza e conforto nas manobras.</p>
                        <div class="product-price">R$ 34,90</div>
                        <a href="https://mercadolivre.com/sec/2xkCb5a" class="btn">Confira Agora</a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Sobre a Nexus</h3>
                    <p>Somos uma loja especializada em produtos tecnológicos com design futurista e inovador. Trazendo o amanhã para o hoje.</p>
                </div>
                <div class="footer-column">
                    <h3>Links Rápidos</h3>
                    <a href="#">Política de Privacidade</a><br>
                    <a href="#">Termos de Uso</a><br>
                    <a href="#">Trocas e Devoluções</a>
                </div>
                <div class="footer-column">
                    <h3>Conecte-se</h3>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-tiktok"></i></a>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Nexus Store. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>
    
    <script>
        // Script para o carrossel de imagens
        document.addEventListener('DOMContentLoaded', function() {
            const products = document.querySelectorAll('.product-card');
            
            products.forEach(product => {
                const carousel = product.querySelector('.carousel');
                const dots = product.querySelectorAll('.carousel-dot');
                const images = product.querySelectorAll('.carousel img');
                let currentIndex = 0;
                
                // Inicializa o carrossel
                function showSlide(index) {
                    carousel.style.transform = `translateX(-${index * 100}%)`;
                    
                    // Atualiza os dots
                    dots.forEach((dot, i) => {
                        dot.classList.toggle('active', i === index);
                    });
                    
                    currentIndex = index;
                }
                
                // Adiciona eventos de clique aos dots
                dots.forEach((dot, index) => {
                    dot.addEventListener('click', () => {
                        showSlide(index);
                    });
                });
                
                // Rotação automática do carrossel
                setInterval(() => {
                    let nextIndex = (currentIndex + 1) % images.length;
                    showSlide(nextIndex);
                }, 4000);
            });
        });
    </script>
</body>
</html>
