<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="CanarIAgentic - Agencia líder en soluciones de inteligencia artificial para empresas. Formación, consultoría y desarrollo de agentes IA.">
    <meta name="keywords" content="inteligencia artificial, IA, consultoría IA, formación IA, agentes IA, transformación digital">
    <meta name="author" content="CanarIAgentic">
    <title>CanarIAgentic - Agencia de Inteligencia Artificial</title>
    
    <!-- Preload critical resources -->
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" as="style">
    <link rel="preload" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" as="style">
    
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Supabase JS -->
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2.39.7"></script>
    
    <style>
        :root {
            --primary-color: #0a2463;
            --secondary-color: #3e92cc;
            --accent-color: #00b4d8;
            --light-color: #f8f9fa;
            --dark-color: #212529;
            --success-color: #2a9d8f;
            --gradient: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            color: var(--dark-color);
            background-color: #f5f7fa;
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header Styles */
        header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--accent-color);
            font-size: 2rem;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark-color);
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--accent-color);
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover {
            color: var(--accent-color);
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--primary-color);
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: var(--gradient);
            color: white;
            padding: 150px 0 100px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50px;
            right: -50px;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            z-index: 1;
        }
        
        .hero::after {
            content: '';
            position: absolute;
            bottom: -100px;
            left: -100px;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            z-index: 1;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            font-weight: 700;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s forwards;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s 0.2s forwards;
        }
        
        .hero-buttons {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s 0.4s forwards;
        }
        
        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            margin: 10px;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transform: translateX(-100%);
            transition: transform 0.3s ease;
            z-index: -1;
        }
        
        .btn:hover::before {
            transform: translateX(0);
        }
        
        .btn:hover {
            background-color: #0096c7;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 180, 216, 0.2);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid white;
        }
        
        .btn-outline:hover {
            background-color: white;
            color: var(--primary-color);
        }
        
        /* Pillars Section */
        .pillars {
            padding: 100px 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }
        
        .section-title.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            width: 60px;
            height: 4px;
            background-color: var(--accent-color);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .section-title p {
            font-size: 1.1rem;
            color: #6c757d;
            max-width: 700px;
            margin: 20px auto 0;
        }
        
        .pillars-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }
        
        .pillar-card {
            flex: 1;
            min-width: 300px;
            background-color: #fff;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            border-top: 4px solid var(--accent-color);
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }
        
        .pillar-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .pillar-card:nth-child(1) {
            transition-delay: 0.1s;
        }
        
        .pillar-card:nth-child(2) {
            transition-delay: 0.2s;
        }
        
        .pillar-card:nth-child(3) {
            transition-delay: 0.3s;
        }
        
        .pillar-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .pillar-icon {
            font-size: 3rem;
            color: var(--accent-color);
            margin-bottom: 20px;
        }
        
        .pillar-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }
        
        .pillar-card p {
            color: #6c757d;
            margin-bottom: 20px;
        }
        
        /* Services Section */
        .services {
            padding: 100px 0;
            background-color: #f8f9fa;
        }
        
        .services-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }
        
        .service-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .service-card:nth-child(1) {
            transition-delay: 0.1s;
        }
        
        .service-card:nth-child(2) {
            transition-delay: 0.2s;
        }
        
        .service-card:nth-child(3) {
            transition-delay: 0.3s;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .service-img {
            height: 200px;
            background: var(--gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .service-content {
            padding: 25px;
        }
        
        .service-content h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }
        
        .service-content p {
            color: #6c757d;
            margin-bottom: 20px;
        }
        
        .service-features {
            list-style: none;
            margin-bottom: 20px;
        }
        
        .service-features li {
            margin-bottom: 8px;
            display: flex;
            align-items: flex-start;
        }
        
        .service-features li i {
            color: var(--accent-color);
            margin-right: 10px;
            font-size: 0.9rem;
            margin-top: 5px;
        }
        
        /* Testimonials Section */
        .testimonials {
            padding: 100px 0;
            background-color: white;
        }
        
        .testimonials-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }
        
        .testimonial-card {
            flex: 1;
            min-width: 300px;
            max-width: 500px;
            background-color: #f8f9fa;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            position: relative;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }
        
        .testimonial-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .testimonial-card:nth-child(1) {
            transition-delay: 0.1s;
        }
        
        .testimonial-card:nth-child(2) {
            transition-delay: 0.2s;
        }
        
        .testimonial-card:nth-child(3) {
            transition-delay: 0.3s;
        }
        
        .testimonial-card::before {
            content: '\f10d';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 2rem;
            color: rgba(10, 36, 99, 0.1);
        }
        
        .testimonial-content {
            margin-bottom: 20px;
            font-style: italic;
            color: #495057;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--accent-color);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
            margin-right: 15px;
        }
        
        .author-info h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
            color: var(--primary-color);
        }
        
        .author-info p {
            font-size: 0.9rem;
            color: #6c757d;
        }
        
        .rating {
            color: #ffc107;
            margin-bottom: 15px;
        }
        
        /* Contact Section */
        .contact {
            padding: 100px 0;
            background: var(--gradient);
            color: white;
        }
        
        .contact-container {
            display: flex;
            flex-wrap: wrap;
            gap: 50px;
        }
        
        .contact-info, .contact-form {
            flex: 1;
            min-width: 300px;
        }
        
        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
        }
        
        .contact-info p {
            margin-bottom: 30px;
            opacity: 0.9;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }
        
        .contact-item i {
            font-size: 1.5rem;
            margin-right: 15px;
            color: var(--accent-color);
            margin-top: 5px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: none;
            border-radius: 5px;
            font-family: 'Montserrat', sans-serif;
            font-size: 1rem;
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .footer-col {
            flex: 1;
            min-width: 200px;
        }
        
        .footer-col h4 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-col h4::after {
            content: '';
            position: absolute;
            width: 40px;
            height: 2px;
            background-color: var(--accent-color);
            bottom: 0;
            left: 0;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--accent-color);
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
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            max-width: 800px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #6c757d;
            transition: color 0.3s ease;
        }
        
        .close-modal:hover {
            color: var(--dark-color);
        }
        
        .modal h3 {
            margin-bottom: 20px;
            color: var(--primary-color);
            font-size: 1.8rem;
        }
        
        .modal h4 {
            margin: 20px 0 10px;
            color: var(--secondary-color);
        }
        
        .modal ul {
            margin-left: 20px;
            margin-bottom: 20px;
        }
        
        .modal p {
            margin-bottom: 15px;
            color: #495057;
        }
        
        .process-step {
            background-color: #f8f9fa;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 4px solid var(--accent-color);
        }
        
        .process-step h4 {
            margin-top: 0;
            margin-bottom: 10px;
            color: var(--primary-color);
        }
        
        .modal-footer {
            margin-top: 30px;
            text-align: center;
        }
        
        /* Formspree Styles */
        .form-message {
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 5px;
            display: none;
        }
        
        .form-message.success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .form-message.error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        /* Loading Spinner */
        .spinner {
            border: 4px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top: 4px solid white;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
            display: inline-block;
            margin-left: 10px;
            vertical-align: middle;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .section-title h2 {
                font-size: 2.2rem;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background-color: white;
                flex-direction: column;
                align-items: center;
                padding: 20px 0;
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
                transform: translateY(-150%);
                transition: transform 0.3s ease;
                z-index: 999;
            }
            
            .nav-links.active {
                transform: translateY(0);
            }
            
            .nav-links li {
                margin: 10px 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .contact-container {
                flex-direction: column;
            }
        }
        
        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .pillar-card, .service-card, .testimonial-card {
                min-width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">
                    <i class="fas fa-robot"></i>
                    <span>CanarIAgentic</span>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Inicio</a></li>
                    <li><a href="#pillars">Pilares</a></li>
                    <li><a href="#services">Servicios</a></li>
                    <li><a href="#testimonials">Testimonios</a></li>
                    <li><a href="#contact">Contacto</a></li>
                </ul>
                <button class="mobile-menu-btn" id="mobileMenuBtn">
                    <i class="fas fa-bars"></i>
                </button>
            </nav>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Transformando Empresas con Inteligencia Artificial</h1>
                <p>CanarIAgentic es la agencia líder en soluciones de IA que impulsa la innovación y eficiencia empresarial a través de tecnología vanguardista.</p>
                <div class="hero-buttons">
                    <a href="#contact" class="btn">Contactar Ahora</a>
                    <a href="#pillars" class="btn btn-outline">Conocer Más</a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Pillars Section -->
    <section class="pillars" id="pillars">
        <div class="container">
            <div class="section-title">
                <h2>Nuestros Pilares Fundamentales</h2>
                <p>En CanarIAgentic basamos nuestra estrategia en tres pilares que garantizan el éxito en la transformación digital de las empresas.</p>
            </div>
            <div class="pillars-container">
                <div class="pillar-card">
                    <div class="pillar-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h3>Formación Personalizada de IA</h3>
                    <p>Desarrollamos programas de capacitación a medida para que tu equipo domine las herramientas y conceptos de inteligencia artificial.</p>
                    <button class="btn" onclick="openPillarModal('formacion')">Ver Detalles</button>
                </div>
                <div class="pillar-card">
                    <div class="pillar-icon">
                        <i class="fas fa-lightbulb"></i>
                    </div>
                    <h3>Consultoría Vanguardista</h3>
                    <p>Ayudamos a las empresas a identificar oportunidades de mejora e innovación mediante el análisis estratégico con IA.</p>
                    <button class="btn" onclick="openPillarModal('consultoria')">Ver Detalles</button>
                </div>
                <div class="pillar-card">
                    <div class="pillar-icon">
                        <i class="fas fa-cogs"></i>
                    </div>
                    <h3>Creación de Agentes IA</h3>
                    <p>Diseñamos e implementamos agentes inteligentes que automatizan y optimizan los procesos empresariales.</p>
                    <button class="btn" onclick="openPillarModal('agentes')">Ver Detalles</button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-title">
                <h2>Nuestros Servicios</h2>
                <p>Ofrecemos soluciones integrales de inteligencia artificial adaptadas a las necesidades específicas de cada cliente.</p>
            </div>
            <div class="services-container">
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                    <div class="service-content">
                        <h3>Formación en IA</h3>
                        <p>Programas de capacitación personalizados para que tu equipo domine las herramientas y conceptos de inteligencia artificial.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> Diagnóstico inicial de competencias digitales</li>
                            <li><i class="fas fa-check"></i> Programas formativos a medida</li>
                            <li><i class="fas fa-check"></i> Talleres prácticos con casos de uso reales</li>
                            <li><i class="fas fa-check"></i> Acompañamiento en la implementación</li>
                        </ul>
                        <a href="#contact" class="btn">Más Información</a>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="service-content">
                        <h3>Consultoría de IA</h3>
                        <p>Análisis estratégico para identificar oportunidades de mejora e innovación mediante la implementación de inteligencia artificial.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> Análisis de madurez digital y de IA</li>
                            <li><i class="fas fa-check"></i> Identificación de casos de uso prioritarios</li>
                            <li><i class="fas fa-check"></i> Diseño de estrategias de implementación</li>
                            <li><i class="fas fa-check"></i> Evaluación de tecnologías y proveedores</li>
                        </ul>
                        <a href="#contact" class="btn">Más Información</a>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="service-content">
                        <h3>Desarrollo de Agentes IA</h3>
                        <p>Creación e implementación de agentes inteligentes que automatizan y optimizan los procesos empresariales.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> Análisis y modelado de procesos</li>
                            <li><i class="fas fa-check"></i> Diseño de arquitecturas de agentes</li>
                            <li><i class="fas fa-check"></i> Desarrollo e implementación de soluciones</li>
                            <li><i class="fas fa-check"></i> Integración con sistemas existentes</li>
                        </ul>
                        <a href="https://studio.pickaxe.co/STUDIOD9VCTFILPI7W0YP" target="_blank" class="btn">Ver Demostración</a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Testimonios de Clientes</h2>
                <p>Descubre lo que dicen las empresas que han confiado en nuestros servicios de inteligencia artificial.</p>
            </div>
            <div class="testimonials-container">
                <div class="testimonial-card">
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="testimonial-content">
                        <p>"La formación en IA que recibimos de CanarIAgentic transformó completamente nuestra operación. Nuestro equipo ahora domina las herramientas de inteligencia artificial, lo que nos ha permitido aumentar nuestra productividad en un 40%."</p>
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">LG</div>
                        <div class="author-info">
                            <h4>Laura García</h4>
                            <p>CTO, Innovatech Systems</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="testimonial-content">
                        <p>"Gracias a la consultoría de CanarIAgentic, identificamos oportunidades de mejora que ni imaginábamos. Su análisis vanguardista nos posicionó como líderes en nuestro sector, con un crecimiento del 35% en el último año."</p>
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">AR</div>
                        <div class="author-info">
                            <h4>Ana Rodríguez</h4>
                            <p>CEO, Global Retail Group</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="testimonial-content">
                        <p>"CanarIAgentic transformó por completo nuestra operación logística. Sus agentes IA redujeron nuestros tiempos de procesamiento en un 70% y los errores en un 95%. ¡Invertir con ellos fue la mejor decisión que hemos tomado!"</p>
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">CM</div>
                        <div class="author-info">
                            <h4>Carlos Méndez</h4>
                            <p>Director de Operaciones, LogiFast Solutions</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title" style="color: white;">
                <h2>Contacto</h2>
                <p>¿Listo para transformar tu empresa con inteligencia artificial? Contáctanos hoy mismo.</p>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Información de Contacto</h3>
                    <p>Nuestro equipo de expertos está listo para ayudarte a encontrar las mejores soluciones de IA para tu empresa.</p>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>
                            <h4>Dirección</h4>
                            <p>calle La Palma 52 Valle de Guerra 38270 Santa Cruz de Tenerife</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone-alt"></i>
                        <div>
                            <h4>Teléfono</h4>
                            <p>+34 922 150 801</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>
                            <h4>Email</h4>
                            <p>franchut76business@gmail.com</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <div id="form-message" class="form-message"></div>
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Nombre</label>
                            <input type="text" id="name" name="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="company">Empresa</label>
                            <input type="text" id="company" name="company" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Mensaje</label>
                            <textarea id="message" name="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn" id="submitBtn">Enviar Mensaje</button>
                    </form>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-col">
                    <div class="logo" style="margin-bottom: 20px;">
                        <i class="fas fa-robot"></i>
                        <span>CanarIAgentic</span>
                    </div>
                    <p>Transformando empresas con inteligencia artificial de vanguardia.</p>
                    <div class="social-links">
                        <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="footer-col">
                    <h4>Enlaces Rápidos</h4>
                    <ul class="footer-links">
                        <li><a href="#home">Inicio</a></li>
                        <li><a href="#pillars">Pilares</a></li>
                        <li><a href="#services">Servicios</a></li>
                        <li><a href="#testimonials">Testimonios</a></li>
                        <li><a href="#contact">Contacto</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h4>Servicios</h4>
                    <ul class="footer-links">
                        <li><a href="#">Formación en IA</a></li>
                        <li><a href="#">Consultoría de IA</a></li>
                        <li><a href="#">Desarrollo de Agentes IA</a></li>
                        <li><a href="#">Análisis Predictivo</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h4>Suscríbete</h4>
                    <p>Recibe las últimas noticias y actualizaciones sobre inteligencia artificial.</p>
                    <form id="subscribeForm" style="margin-top: 15px;">
                        <div class="form-group" style="margin-bottom: 15px;">
                            <input type="email" class="form-control" id="subscribeEmail" placeholder="Tu email" required>
                        </div>
                        <button type="submit" class="btn">Suscribirse</button>
                    </form>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 CanarIAgentic. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>
    
    <!-- Modal -->
    <div id="pillarModal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closePillarModal()" aria-label="Cerrar modal">&times;</span>
            <div id="pillarModalBody">
                <!-- Content will be dynamically inserted here -->
            </div>
        </div>
    </div>
    
    <!-- Notification -->
    <div id="notification" style="position: fixed; bottom: 20px; right: 20px; background-color: #2a9d8f; color: white; padding: 15px 25px; border-radius: 5px; box-shadow: 0 5px 15px rgba(0,0,0,0.2); transform: translateY(100px); transition: transform 0.3s ease; z-index: 3000;">
        <p id="notification-text"></p>
    </div>
    
    <script>
        // Initialize Supabase with your project credentials
        const supabaseUrl = 'https://mfargfnhebhgmkjochyg.supabase.co';
        const supabaseKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im1mYXJnZm5oZWJoZ21ram9jaHlnIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDI5NTU0ODIsImV4cCI6MjAxODUzMTQ4Mn0.S7z6KzZQ8x8w9qY9X8x8w9qY9X8x8w9qY9X8x8w9qY9X';
        const supabase = window.supabase.createClient(supabaseUrl, supabaseKey);
        
        // Mobile menu toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            
            // Change icon
            const icon = mobileMenuBtn.querySelector('i');
            if (icon.classList.contains('fa-bars')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            } else {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            }
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                const icon = mobileMenuBtn.querySelector('i');
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            });
        });
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Modal functionality for pillars
        function openPillarModal(pillar) {
            const modal = document.getElementById('pillarModal');
            const modalBody = document.getElementById('pillarModalBody');
            
            let content = '';
            
            switch(pillar) {
                case 'formacion':
                    content = `
                        <h3>Formación Personalizada de IA</h3>
                        <p>Nuestro proceso de formación en inteligencia artificial está diseñado para adaptarse a las necesidades específicas de cada empresa, garantizando que tu equipo adquiera las competencias necesarias para aprovechar al máximo la tecnología de IA.</p>
                        
                        <h4>Nuestro Proceso de Formación</h4>
                        
                        <div class="process-step">
                            <h4>1. Diagnóstico Inicial</h4>
                            <p>Realizamos una evaluación exhaustiva de las competencias digitales actuales de tu equipo y las necesidades específicas de tu empresa en materia de IA.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>2. Diseño del Programa Formativo</h4>
                            <p>Basándonos en el diagnóstico, diseñamos un programa de formación a medida que aborda las áreas de mejora identificadas y se alinea con los objetivos estratégicos de tu empresa.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>3. Implementación de la Formación</h4>
                            <p>Llevamos a cabo la formación a través de una combinación de sesiones teóricas, talleres prácticos y casos de uso reales, garantizando una experiencia de aprendizaje completa y aplicable.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>4. Acompañamiento y Seguimiento</h4>
                            <p>Proporcionamos acompañamiento continuo durante la implementación de los conocimientos adquiridos, asegurando que tu equipo pueda aplicar eficazmente lo aprendido en su día a día.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>5. Evaluación y Certificación</h4>
                            <p>Realizamos una evaluación final para medir el impacto de la formación y proporcionamos certificados que reconocen las nuevas competencias adquiridas por tu equipo.</p>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>
                        </div>
                    `;
                    break;
                case 'consultoria':
                    content = `
                        <h3>Consultoría Vanguardista con IA</h3>
                        <p>Nuestro servicio de consultoría en inteligencia artificial ayuda a las empresas a identificar oportunidades de mejora e innovación, diseñando estrategias que aprovechan todo el potencial de la IA para transformar sus operaciones y modelos de negocio.</p>
                        
                        <h4>Nuestro Proceso de Consultoría</h4>
                        
                        <div class="process-step">
                            <h4>1. Análisis de Madurez Digital</h4>
                            <p>Evaluamos el nivel actual de madurez digital y de adopción de IA en tu empresa, identificando fortalezas, debilidades y áreas de oportunidad.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>2. Identificación de Casos de Uso</h4>
                            <p>Trabajamos contigo para identificar y priorizar los casos de uso de IA con mayor potencial de impacto en tu negocio, considerando factores como viabilidad técnica, retorno de inversión y alineación estratégica.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>3. Diseño de la Estrategia de Implementación</h4>
                            <p>Desarrollamos una hoja de ruta detallada para la implementación de soluciones de IA, incluyendo objetivos, cronograma, recursos necesarios y métricas de éxito.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>4. Evaluación de Tecnologías y Proveedores</h4>
                            <p>Analizamos y recomendamos las tecnologías y proveedores más adecuados para tus necesidades específicas, asegurando que tomes decisiones informadas y estratégicas.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>5. Planificación de la Transformación Digital</h4>
                            <p>Elaboramos un plan integral de transformación digital que integra la IA en tu estrategia empresarial, preparando a tu organización para los desafíos y oportunidades del futuro.</p>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>
                        </div>
                    `;
                    break;
                case 'agentes':
                    content = `
                        <h3>Creación de Agentes IA</h3>
                        <p>Diseñamos e implementamos agentes inteligentes que automatizan y optimizan los procesos empresariales, permitiendo a tu organización operar de manera más eficiente y enfocarse en actividades de mayor valor añadido.</p>
                        
                        <h4>Nuestro Proceso de Creación de Agentes IA</h4>
                        
                        <div class="process-step">
                            <h4>1. Análisis y Modelado de Procesos</h4>
                            <p>Realizamos un análisis detallado de los procesos empresariales existentes para identificar oportunidades de automatización y optimización mediante agentes de IA.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>2. Diseño de Arquitecturas de Agentes</h4>
                            <p>Diseñamos la arquitectura de los agentes inteligentes, definiendo sus capacidades, comportamientos y mecanismos de interacción con los sistemas existentes y los usuarios.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>3. Desarrollo e Implementación de Soluciones</h4>
                            <p>Desarrollamos e implementamos los agentes de IA utilizando las últimas tecnologías y mejores prácticas, asegurando su correcto funcionamiento y rendimiento.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>4. Integración con Sistemas Existentes</h4>
                            <p>Integramos los agentes de IA con los sistemas y plataformas existentes en tu empresa, garantizando una comunicación fluida y una operación coordinada.</p>
                        </div>
                        
                        <div class="process-step">
                            <h4>5. Monitorización y Mejora Continua</h4>
                            <p>Implementamos sistemas de monitorización para evaluar el rendimiento de los agentes y realizamos mejoras continuas basadas en los resultados obtenidos y el feedback de los usuarios.</p>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>
                        </div>
                    `;
                    break;
            }
            
            modalBody.innerHTML = content;
            modal.style.display = 'flex';
        }
        
        function closePillarModal() {
            document.getElementById('pillarModal').style.display = 'none';
        }
        
        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('pillarModal');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }
        
        // Contact form submission with Supabase
        const contactForm = document.getElementById('contactForm');
        const formMessage = document.getElementById('form-message');
        const submitBtn = document.getElementById('submitBtn');
        
        contactForm.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            // Show loading state
            submitBtn.disabled = true;
            submitBtn.innerHTML = 'Enviando... <span class="spinner"></span>';
            
            // Get form data
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const company = document.getElementById('company').value;
            const message = document.getElementById('message').value;
            
            try {
                console.log('Enviando datos a Supabase...');
                
                // Insert data into Supabase table "formulario de contacto"
                const { data, error } = await supabase
                    .from('formulario_de_contacto')  // Usar guiones bajos en lugar de espacios
                    .insert([
                        { 
                            nombre: name, 
                            email: email, 
                            empresa: company, 
                            mensaje: message,
                            created_at: new Date().toISOString()
                        }
                    ]);
                
                if (error) {
                    console.error('Error de Supabase:', error);
                    throw error;
                }
                
                console.log('Datos enviados correctamente:', data);
                
                // Show success message
                formMessage.textContent = `¡Gracias ${name}! Tu mensaje ha sido enviado correctamente. Te contactaremos pronto en ${email}.`;
                formMessage.className = 'form-message success';
                formMessage.style.display = 'block';
                
                // Show notification
                showNotification(`Gracias ${name}, tu mensaje ha sido enviado. Te contactaremos pronto en ${email}.`);
                
                // Reset form after a short delay to ensure data is sent
                setTimeout(() => {
                    contactForm.reset();
                    console.log('Formulario reseteado');
                }, 1000);
                
                // Hide success message after 5 seconds
                setTimeout(() => {
                    formMessage.style.display = 'none';
                }, 5000);
                
            } catch (error) {
                console.error('Error completo:', error);
                
                // Show error message
                formMessage.textContent = 'Ha ocurrido un error. Por favor, inténtalo de nuevo más tarde.';
                formMessage.className = 'form-message error';
                formMessage.style.display = 'block';
                
                // Hide error message after 5 seconds
                setTimeout(() => {
                    formMessage.style.display = 'none';
                }, 5000);
            } finally {
                // Reset button state
                submitBtn.disabled = false;
                submitBtn.innerHTML = 'Enviar Mensaje';
            }
        });
        
        // Subscribe form with Supabase
        document.getElementById('subscribeForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            // Get email value
            const email = document.getElementById('subscribeEmail').value;
            
            try {
                // Insert data into Supabase
                const { data, error } = await supabase
                    .from('suscripciones')
                    .insert([
                        { 
                            email: email,
                            created_at: new Date().toISOString()
                        }
                    ]);
                
                if (error) throw error;
                
                // Show notification
                showNotification(`Gracias por suscribirte con el email ${email}. Recibirás nuestras novedades pronto.`);
                
                // Reset form
                this.reset();
            } catch (error) {
                console.error('Error:', error);
                
                // Show error notification
                showNotification('Ha ocurrido un error al suscribirte. Por favor, inténtalo de nuevo más tarde.');
            }
        });
        
        // Show notification
        function showNotification(message) {
            // Create notification element if it doesn't exist
            let notification = document.getElementById('notification');
            if (!notification) {
                notification = document.createElement('div');
                notification.id = 'notification';
                notification.style.position = 'fixed';
                notification.style.bottom = '20px';
                notification.style.right = '20px';
                notification.style.backgroundColor = '#2a9d8f';
                notification.style.color = 'white';
                notification.style.padding = '15px 25px';
                notification.style.borderRadius = '5px';
                notification.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';
                notification.style.transform = 'translateY(100px)';
                notification.style.transition = 'transform 0.3s ease';
                notification.style.zIndex = '3000';
                document.body.appendChild(notification);
            }
            
            // Set message and show notification
            notification.innerHTML = `<p>${message}</p>`;
            notification.style.transform = 'translateY(0)';
            
            // Hide notification after 5 seconds
            setTimeout(() => {
                notification.style.transform = 'translateY(100px)';
            }, 5000);
        }
        
        // Change header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.backgroundColor = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.backgroundColor = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';
            }
        });
        
        // Animate elements on scroll
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.section-title, .pillar-card, .service-card, .testimonial-card');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.2;
                
                if (elementPosition < screenPosition) {
                    element.classList.add('visible');
                }
            });
        };
        
        // Run animation on load and scroll
        window.addEventListener('load', animateOnScroll);
        window.addEventListener('scroll', animateOnScroll);
    </script>
</body>
</html>
