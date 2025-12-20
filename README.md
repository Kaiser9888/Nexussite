<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #d62828;
            --secondary-color: #003049;
            --accent-color: #f77f00;
            --light-color: #fcbf49;
            --dark-color: #2a2d34;
            --background-color: #eae2b7;
            --text-color: #333;
            --card-bg: #f8f9fa;
            --border-color: #ddd;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23d62828' fill-opacity='0.03' fill-rule='evenodd'/%3E%3C/svg%3E");
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background-color: var(--secondary-color);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo i {
            font-size: 2.5rem;
            color: var(--primary-color);
        }
        
        .logo h1 {
            color: white;
            font-size: 1.8rem;
            letter-spacing: 1px;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s;
            padding: 5px 10px;
            border-radius: 3px;
        }
        
        nav a:hover {
            color: var(--light-color);
            background-color: rgba(255, 255, 255, 0.1);
        }
        
        /* Carrossel */
        .carousel-container {
            position: relative;
            height: 500px;
            overflow: hidden;
            margin-bottom: 40px;
            border-radius: 0 0 10px 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .carousel-slide {
            display: flex;
            width: 400%;
            height: 100%;
            transition: transform 0.8s ease-in-out;
        }
        
        /* IMAGENS DO CARROSSEL - TAMANHO CORRIGIDO */
        .carousel-slide img {
            width: 25%;
            height: 100%;
            object-fit: cover;
            filter: sepia(0.3) contrast(1.1);
        }
        
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            font-size: 2rem;
            padding: 10px 15px;
            cursor: pointer;
            transition: all 0.3s;
            z-index: 10;
        }
        
        .carousel-btn:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }
        
        .prev-btn {
            left: 20px;
        }
        
        .next-btn {
            right: 20px;
        }
        
        .carousel-indicators {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }
        
        .indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .indicator.active {
            background-color: var(--primary-color);
            transform: scale(1.2);
        }
        
        /* Seções */
        section {
            margin-bottom: 60px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
            padding-bottom: 15px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--secondary-color);
            display: inline-block;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            width: 100px;
            height: 4px;
            background-color: var(--primary-color);
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* História */
        .history-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }
        
        .history-text p {
            margin-bottom: 20px;
            font-size: 1.1rem;
            text-align: justify;
        }
        
        .history-images {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
        
        .history-img {
            height: 200px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            cursor: pointer;
        }
        
        .history-img:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        /* IMAGENS DA SEÇÃO HISTÓRIA - TAMANHO CORRIGIDO */
        .history-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: sepia(0.4);
        }
        
        .history-img.large {
            grid-column: span 2;
            height: 250px;
        }
        
        /* Produtos */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: all 0.3s;
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .product-img {
            height: 200px;
            overflow: hidden;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #f0f0f0;
        }
        
        /* IMAGENS DOS PRODUTOS - TAMANHO CORRIGIDO */
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: contain;
            transition: all 0.5s;
            background-color: white;
        }
        
        .product-card:hover .product-img img {
            transform: scale(1.05);
        }
        
        .product-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: all 0.3s;
        }
        
        .product-card:hover .product-overlay {
            opacity: 1;
        }
        
        .zoom-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
        }
        
        .zoom-btn:hover {
            background-color: var(--accent-color);
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-info h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
            font-size: 1.3rem;
        }
        
        .product-info p {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.95rem;
        }
        
        .product-price {
            font-size: 1.4rem;
            font-weight: bold;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        
        .affiliate-btn {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: var(--secondary-color);
            color: white;
            text-align: center;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .affiliate-btn:hover {
            background-color: var(--accent-color);
        }
        
        /* Modal de imagem */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 2000;
        }
        
        .modal-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* IMAGEM DO MODAL - TAMANHO CORRIGIDO */
        .modal-content img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            border-radius: 5px;
            background-color: white;
        }
        
        .close-modal {
            position: absolute;
            top: -40px;
            right: 0;
            color: white;
            font-size: 2rem;
            cursor: pointer;
            background: none;
            border: none;
        }
        
        .modal-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            color: white;
            font-size: 2rem;
            background: none;
            border: none;
            cursor: pointer;
            padding: 10px;
        }
        
        .prev-modal {
            left: -60px;
        }
        
        .next-modal {
            right: -60px;
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary-color);
            color: white;
            padding: 40px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
            margin-bottom: 30px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            color: var(--accent-color);
            font-size: 1.3rem;
        }
        
        .footer-column p, .footer-column a {
            color: #ccc;
            margin-bottom: 10px;
            display: block;
            text-decoration: none;
        }
        
        .footer-column a:hover {
            color: var(--light-color);
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: all 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--primary-color);
            transform: translateY(-5px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #aaa;
            font-size: 0.9rem;
        }
        
        /* Responsividade */
        @media (max-width: 992px) {
            .history-container {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 15px;
            }
            
            .carousel-container {
                height: 350px;
            }
            
            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
            
            .modal-nav {
                position: static;
                transform: none;
                margin: 0 10px;
            }
            
            .modal-content {
                display: flex;
                flex-direction: column;
                align-items: center;
            }
            
            .prev-modal, .next-modal {
                position: static;
                margin: 10px;
            }
        }
        
        @media (max-width: 576px) {
            .footer-content {
                grid-template-columns: 1fr;
            }
            
            .history-images {
                grid-template-columns: 1fr;
            }
            
            .history-img.large {
                grid-column: span 1;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-bicycle"></i>
                <h1>NEXUS <span>STORE</span></h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#history">História</a></li>
                    <li><a href="#products">Produtos</a></li>
                    <li><a href="#contact">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Carrossel -->
    <section id="home" class="carousel-container">
        <div class="carousel-slide">
            <img src="https://media.gettyimages.com/id/492717102/pt/foto/virgin-ut-an-athlete-rides-along-the-ridge-line-during-a-practice-session-for-the-red-bull.jpg?s=612x612&w=0&k=20&c=Abh-B9NSvsVZp4ScC1XiTsjI1_pGxIb7TG6S-uvpZ_w=" alt="Downhill vintage bike">
            <img src="https://media.gettyimages.com/id/492863770/pt/foto/virgin-ut-mitch-chubey-of-canada-goes-over-a-jump-during-a-practice-session-for-the-red-bull.jpg?s=612x612&w=0&k=20&c=_dxkOQCYfCxfGHnbTz3_WLFSzhvYi6D8wqfhYwcEPng=" alt="Mountain bike retro">
            <img src="https://media.gettyimages.com/id/2153693565/pt/foto/bielsko-biala-poland-marine-cabirou-of-france-competes-in-the-uci-mountain-bike-world-cup.jpg?s=612x612&w=0&k=20&c=sappU6C4se1yt6_5yrjb_v1zOFqRnI30824D_Ds3k8k=" alt="Old school downhill racing">
            <img src="https://media.gettyimages.com/id/170165827/pt/foto/fort-william-scotland-yuki-kushima-of-japan-competes-in-the-mens-downhill-qualifying-round-at.jpg?s=612x612&w=0&k=20&c=dWAXmTbZfOMYhfZBqDD-1QSWr8vNdye7k821G8oym1M=" alt="Classic bike parts">
        </div>
        <button class="carousel-btn prev-btn"><i class="fas fa-chevron-left"></i></button>
        <button class="carousel-btn next-btn"><i class="fas fa-chevron-right"></i></button>
        <div class="carousel-indicators">
            <div class="indicator active" data-index="0"></div>
            <div class="indicator" data-index="1"></div>
            <div class="indicator" data-index="2"></div>
            <div class="indicator" data-index="3"></div>
        </div>
    </section>

    <!-- História do Downhill -->
    <section id="history" class="container">
        <div class="section-title">
            <h2>A HISTÓRIA DO DOWNHILL</h2>
        </div>
        <div class="history-container">
            <div class="history-text">
                <p>O downhill, uma das modalidades mais radicais do ciclismo, surgiu na década de 1970 na Califórnia, quando ciclistas começaram a descer montanhas em bicicletas modificadas, buscando adrenalina e velocidade.</p>
                <p>As primeiras bicicletas de downhill eram pesadas e rústicas, adaptadas de bikes de passeio ou cruisers. Os pioneiros da modalidade, como os membros do "Repack Downhill" em Marin County, usavam freios a tambor e quadros reforçados para suportar as descidas íngremes.</p>
                <p>Nos anos 80, a modalidade ganhou popularidade com o surgimento das primeiras competições organizadas. As bikes começaram a evoluir com suspensão dianteira, pneus mais largos e materiais mais leves como o alumínio.</p>
                <p>A década de 90 foi a era de ouro do downhill, com campeonatos mundiais estabelecidos e avanços tecnológicos significativos. As bicicletas ganharam suspensão traseira, geometria específica para descida e componentes especializados.</p>
                <p>Hoje, o downhill old school é cultuado por entusiastas que buscam reviver a essência da modalidade, com bikes vintage, equipamentos clássicos e a estética retro que marcou época.</p>
            </div>
            <div class="history-images">
                <div class="history-img">
                    <img src="https://media.gettyimages.com/id/104588962/pt/foto/virgin-ut-an-event-participant-practices-during-the-red-bull-rampage-biking-competition-on.jpg?s=612x612&w=0&k=20&c=LvZ9Z69yzg-YMDCzfgoiDVeB8Qm5hV1MbWSsxxegcuw=" alt="Primeiras bikes de downhill">
                </div>
                <div class="history-img">
                    <img src="https://media.gettyimages.com/id/845157562/pt/foto/cairns-australia-loic-bruni-of-france-practices-in-the-elite-mens-downhill-championship-during.jpg?s=612x612&w=0&k=20&c=bXOLd1n_-xkgDqsBy4oFdIBkGDgf-1V2kCZOcWfI8lY=" alt="Downhill nos anos 90">
                </div>
                <div class="history-img large">
                    <img src="https://media.gettyimages.com/id/1497464773/pt/foto/lenzerheide-switzerland-benoit-coulanges-of-france-competes-in-the-uci-mountain-bike-world-cup.jpg?s=612x612&w=0&k=20&c=M05E9ULESSo96xall7iflnoyG6MJ-K8RzasbbZYPHLY=" alt="Competição de downhill vintage">
                </div>
            </div>
        </div>
    </section>

    <!-- Produtos -->
    <section id="products" class="container">
        <div class="section-title">
            <h2>Quadros e Peças</h2>
        </div>
        <div class="products-grid">
            <!-- Produtos serão inseridos via JavaScript -->
        </div>
    </section>

    <!-- Modal para zoom de imagens -->
    <div class="modal-overlay" id="imageModal">
        <button class="close-modal"><i class="fas fa-times"></i></button>
        <button class="modal-nav prev-modal"><i class="fas fa-chevron-left"></i></button>
        <div class="modal-content">
            <img id="modalImage" src="" alt="">
        </div>
        <button class="modal-nav next-modal"><i class="fas fa-chevron-right"></i></button>
    </div>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Nexus Store</h3>
                    <p>Especializados em peças e quadros de downhill. Trazemos o melhor do downhill para os entusiastas do ciclismo radical.</p>
                    <div class="social-icons">
                        <a href="https://www.instagram.com/nexus09877?igsh=aGh4YzZvcTV0NjZu" target="_blank"><i class="fab fa-instagram"></i></a>
                        <a href="https://www.tiktok.com/@nexus.store48?_r=1&_t=ZS-92NqaJt40bl" target="_blank"><i class="fab fa-tiktok"></i></a>
                        <a href="mailto:nexusstore00@gmail.com"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Links Rápidos</h3>
                    <a href="#home">Home</a>
                    <a href="#history">História do Downhill</a>
                    <a href="#products">Produtos</a>
                    <a href="#contact">Contato</a>
                </div>
                <div class="footer-column">
                    <h3>Contato</h3>
                    <p><i class="fas fa-envelope"></i> nexusstore00@gmail.com</p>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2026 Nexus Store. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Carrossel
        const carouselSlide = document.querySelector('.carousel-slide');
        const carouselImages = document.querySelectorAll('.carousel-slide img');
        const prevBtn = document.querySelector('.prev-btn');
        const nextBtn = document.querySelector('.next-btn');
        const indicators = document.querySelectorAll('.indicator');
        
        let counter = 0;
        const size = carouselImages[0].clientWidth;
        
        // Configuração inicial do carrossel
        carouselSlide.style.transform = 'translateX(' + (-size * counter) + 'px)';
        
        // Botões do carrossel
        nextBtn.addEventListener('click', () => {
            if (counter >= carouselImages.length - 1) return;
            carouselSlide.style.transition = "transform 0.8s ease-in-out";
            counter++;
            carouselSlide.style.transform = 'translateX(' + (-size * counter) + 'px)';
            updateIndicators();
        });
        
        prevBtn.addEventListener('click', () => {
            if (counter <= 0) return;
            carouselSlide.style.transition = "transform 0.8s ease-in-out";
            counter--;
            carouselSlide.style.transform = 'translateX(' + (-size * counter) + 'px)';
            updateIndicators();
        });
        
        // Indicadores
        indicators.forEach(indicator => {
            indicator.addEventListener('click', () => {
                counter = parseInt(indicator.getAttribute('data-index'));
                carouselSlide.style.transition = "transform 0.8s ease-in-out";
                carouselSlide.style.transform = 'translateX(' + (-size * counter) + 'px)';
                updateIndicators();
            });
        });
        
        // Atualizar indicadores ativos
        function updateIndicators() {
            indicators.forEach(indicator => {
                indicator.classList.remove('active');
            });
            indicators[counter].classList.add('active');
        }
        
        // Carrossel automático
        setInterval(() => {
            if (counter >= carouselImages.length - 1) {
                counter = -1;
            }
            carouselSlide.style.transition = "transform 0.8s ease-in-out";
            counter++;
            carouselSlide.style.transform = 'translateX(' + (-size * counter) + 'px)';
            updateIndicators();
        }, 5000);
        
        // Produtos - AGORA COM LINKS REAIS DO MERCADO LIVRE
        const productsGrid = document.querySelector('.products-grid');
        const products = [
            { 
                id: 1, 
                name: "Quadro gios 4freaks", 
                desc: "Quadro indicado para downhill, material de alta resistência", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_669856-MLB89374727079_082025-F-quadro-gios-26-4-freaks-wheeling-free-ride-dj-grau-manobra.webp",
                link: "https://mercadolivre.com/sec/22qEJV4"
            },
            { 
                id: 2, 
                name: "Quadro Gios 26 frx ", 
                desc: "Gios frx um ecelente quadro", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_775732-MLB89208044956_082025-F-quadro-26-gios-frx-evo-wheeling-downhill-dirt-file-bike.webp",
                link: "https://mercadolivre.com/sec/1715fbf"
            },
            { 
                id: 3, 
                name: "Quadro De Bike Aro 26 Marca Gtk Pulse Rz Para Downhill Azul-aço Ml", 
                desc: "Quadro extremamente confiavel Gtk para Downhill", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_852705-MLB90368149713_082025-F.webp",
                link: "https://mercadolivre.com/sec/2SSH3xk"
            },
            { 
                id: 4, 
                name: "Quadro Bike Gtk Dh Spanked Azul/preto M", 
                desc: "Quadro de alta performance para downhill", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_915617-MLB93486475637_092025-F.webp",
                link: "https://mercadolivre.com/sec/1f4nkTA"
            },
            { 
                id: 5, 
                name: "Freio Hidráulico Shimano Mt200", 
                desc: "Freio Hidráulico Otimo custo Beneficio", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_971327-MLA100008941325_122025-F.webp",
                link: "https://mercadolivre.com/sec/1n2dieX"
            },
            { 
                id: 6, 
                name: "Guidão Bike Pro Knz 780mm 720mm Preto Enduro Downhill Voador", 
                desc: "Guidão Otimo para Downhill", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_748653-MLB96534153311_102025-F-guido-bike-pro-knz-780mm-720mm-preto-enduro-downhill-voador.webp",
                link: "https://mercadolivre.com/sec/1Jqkr6V"
            },
            { 
                id: 7, 
                name: "Guia Corrente Bike Relação Ciclismo Mtb Iscg 03 / 05 / Bb Preto", 
                desc: "Guia de Corrente Ecencial para uma melhor performance", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_948528-MLB98238234567_112025-F.webp",
                link: "https://mercadolivre.com/sec/1c4GBpJ"
            },
            { 
                id: 8, 
                name: "Capacete Fox Bike Mtb Fullface Cores Proframe Protecao Mips", 
                desc: "Capacete Fox ande com segurança e estilo", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_671753-MLB97531761310_112025-F-capacete-fox-bike-mtb-fullface-cores-proframe-protecao-mips.webp",
                link: "https://mercadolivre.com/sec/2esqPtR"
            },
            { 
                id: 9, 
                name: "Suporte Guidão Mesa Gios Boxer Integrada Downhill Vermelho Vermelho", 
                desc: "Mesa Gios Downhill tenha uma melhor performance", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_615181-MLB87718515416_072025-F.webp",
                link: "https://mercadolivre.com/sec/2AbrJKy"
            },
            { 
                id: 10, 
                name: "Kit 2 Aros Rodas 26 36f Vmaxx Downhill Freio A Disco Vzan Cor Preto", 
                desc: "Aros Vmaxx ótimo para Downhill", 
                price: "Consulte o valor", 
                img: "https://http2.mlstatic.com/D_NQ_NP_2X_930806-MLA99504794024_112025-F.webp",
                link: "https://mercadolivre.com/sec/1cDU2oZ"
            }
        ];
        
        // Renderizar produtos
        function renderProducts() {
            productsGrid.innerHTML = '';
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <div class="product-img">
                        <img src="${product.img}" alt="${product.name}">
                        <div class="product-overlay">
                            <button class="zoom-btn" data-id="${product.id}">
                                <i class="fas fa-search-plus"></i> Ampliar
                            </button>
                        </div>
                    </div>
                    <div class="product-info">
                        <h3>${product.name}</h3>
                        <p>${product.desc}</p>
                        <div class="product-price">${product.price}</div>
                        <!-- LINK CORRIGIDO: agora aponta para o Mercado Livre -->
                        <a href="${product.link}" target="_blank" class="affiliate-btn">VER OFERTA</a>
                    </div>
                `;
                productsGrid.appendChild(productCard);
            });
            
            // Adicionar eventos aos botões de zoom
            document.querySelectorAll('.zoom-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const productId = parseInt(e.target.closest('.zoom-btn').getAttribute('data-id'));
                    openModal(productId);
                });
            });
        }
        
        // Modal de zoom
        const modal = document.getElementById('imageModal');
        const modalImage = document.getElementById('modalImage');
        const closeModal = document.querySelector('.close-modal');
        const prevModal = document.querySelector('.prev-modal');
        const nextModal = document.querySelector('.next-modal');
        
        let currentProductId = 1;
        
        function openModal(productId) {
            currentProductId = productId;
            const product = products.find(p => p.id === productId);
            modalImage.src = product.img;
            modalImage.alt = product.name;
            modal.style.display = 'flex';
        }
        
        function closeImageModal() {
            modal.style.display = 'none';
        }
        
        function navigateModal(direction) {
            let newId = currentProductId + direction;
            
            if (newId < 1) {
                newId = products.length;
            } else if (newId > products.length) {
                newId = 1;
            }
            
            openModal(newId);
        }
        
        closeModal.addEventListener('click', closeImageModal);
        prevModal.addEventListener('click', () => navigateModal(-1));
        nextModal.addEventListener('click', () => navigateModal(1));
        
        // Fechar modal clicando fora da imagem
        modal.addEventListener('click', (e) => {
            if (e.target === modal) {
                closeImageModal();
            }
        });
        
        // Navegação por teclado
        document.addEventListener('keydown', (e) => {
            if (modal.style.display === 'flex') {
                if (e.key === 'Escape') closeImageModal();
                if (e.key === 'ArrowLeft') navigateModal(-1);
                if (e.key === 'ArrowRight') navigateModal(1);
            }
        });
        
        // Inicializar
        renderProducts();
        
        // Suavizar rolagem para âncoras
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>