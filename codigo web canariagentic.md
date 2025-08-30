git remote add origin https://github.com/franchut76-hub/web-canariagentic.git

git branch -M main

git push -u origin main
<!DOCTYPE html>

<html lang="es">

<head>

&nbsp;   <meta charset="UTF-8">

&nbsp;   <meta name="viewport" content="width=device-width, initial-scale=1.0">

&nbsp;   <meta name="description" content="CanarIAgentic - Agencia líder en soluciones de inteligencia artificial para empresas. Formación, consultoría y desarrollo de agentes IA.">

&nbsp;   <meta name="keywords" content="inteligencia artificial, IA, consultoría IA, formación IA, agentes IA, transformación digital">

&nbsp;   <meta name="author" content="CanarIAgentic">

&nbsp;   <title>CanarIAgentic - Agencia de Inteligencia Artificial</title>

&nbsp;   

&nbsp;   <!-- Preload critical resources -->

&nbsp;   <link rel="preload" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700\&display=swap" as="style">

&nbsp;   <link rel="preload" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" as="style">

&nbsp;   

&nbsp;   <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700\&display=swap" rel="stylesheet">

&nbsp;   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

&nbsp;   

&nbsp;   <!-- Supabase JS -->

&nbsp;   <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2.39.7"></script>

&nbsp;   

&nbsp;   <style>

&nbsp;       :root {

&nbsp;           --primary-color: #0a2463;

&nbsp;           --secondary-color: #3e92cc;

&nbsp;           --accent-color: #00b4d8;

&nbsp;           --light-color: #f8f9fa;

&nbsp;           --dark-color: #212529;

&nbsp;           --success-color: #2a9d8f;

&nbsp;           --gradient: linear-gradient(135deg, var(--primary-color), var(--secondary-color));

&nbsp;       }

&nbsp;       

&nbsp;       \* {

&nbsp;           margin: 0;

&nbsp;           padding: 0;

&nbsp;           box-sizing: border-box;

&nbsp;       }

&nbsp;       

&nbsp;       body {

&nbsp;           font-family: 'Montserrat', sans-serif;

&nbsp;           line-height: 1.6;

&nbsp;           color: var(--dark-color);

&nbsp;           background-color: #f5f7fa;

&nbsp;           overflow-x: hidden;

&nbsp;       }

&nbsp;       

&nbsp;       .container {

&nbsp;           width: 90%;

&nbsp;           max-width: 1200px;

&nbsp;           margin: 0 auto;

&nbsp;           padding: 0 15px;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Header Styles \*/

&nbsp;       header {

&nbsp;           background-color: rgba(255, 255, 255, 0.95);

&nbsp;           box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);

&nbsp;           position: fixed;

&nbsp;           width: 100%;

&nbsp;           top: 0;

&nbsp;           z-index: 1000;

&nbsp;           transition: all 0.3s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .navbar {

&nbsp;           display: flex;

&nbsp;           justify-content: space-between;

&nbsp;           align-items: center;

&nbsp;           padding: 15px 0;

&nbsp;       }

&nbsp;       

&nbsp;       .logo {

&nbsp;           display: flex;

&nbsp;           align-items: center;

&nbsp;           font-size: 1.5rem;

&nbsp;           font-weight: 700;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .logo i {

&nbsp;           margin-right: 10px;

&nbsp;           color: var(--accent-color);

&nbsp;           font-size: 2rem;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links {

&nbsp;           display: flex;

&nbsp;           list-style: none;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links li {

&nbsp;           margin-left: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links a {

&nbsp;           text-decoration: none;

&nbsp;           color: var(--dark-color);

&nbsp;           font-weight: 500;

&nbsp;           transition: color 0.3s ease;

&nbsp;           position: relative;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links a::after {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           width: 0;

&nbsp;           height: 2px;

&nbsp;           bottom: -5px;

&nbsp;           left: 0;

&nbsp;           background-color: var(--accent-color);

&nbsp;           transition: width 0.3s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links a:hover {

&nbsp;           color: var(--accent-color);

&nbsp;       }

&nbsp;       

&nbsp;       .nav-links a:hover::after {

&nbsp;           width: 100%;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Mobile Menu \*/

&nbsp;       .mobile-menu-btn {

&nbsp;           display: none;

&nbsp;           background: none;

&nbsp;           border: none;

&nbsp;           font-size: 1.5rem;

&nbsp;           color: var(--primary-color);

&nbsp;           cursor: pointer;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Hero Section \*/

&nbsp;       .hero {

&nbsp;           background: var(--gradient);

&nbsp;           color: white;

&nbsp;           padding: 150px 0 100px;

&nbsp;           text-align: center;

&nbsp;           position: relative;

&nbsp;           overflow: hidden;

&nbsp;       }

&nbsp;       

&nbsp;       .hero::before {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           top: -50px;

&nbsp;           right: -50px;

&nbsp;           width: 300px;

&nbsp;           height: 300px;

&nbsp;           border-radius: 50%;

&nbsp;           background: rgba(255, 255, 255, 0.1);

&nbsp;           z-index: 1;

&nbsp;       }

&nbsp;       

&nbsp;       .hero::after {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           bottom: -100px;

&nbsp;           left: -100px;

&nbsp;           width: 400px;

&nbsp;           height: 400px;

&nbsp;           border-radius: 50%;

&nbsp;           background: rgba(255, 255, 255, 0.05);

&nbsp;           z-index: 1;

&nbsp;       }

&nbsp;       

&nbsp;       .hero-content {

&nbsp;           position: relative;

&nbsp;           z-index: 2;

&nbsp;       }

&nbsp;       

&nbsp;       .hero h1 {

&nbsp;           font-size: 3.5rem;

&nbsp;           margin-bottom: 20px;

&nbsp;           font-weight: 700;

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           animation: fadeInUp 0.8s forwards;

&nbsp;       }

&nbsp;       

&nbsp;       .hero p {

&nbsp;           font-size: 1.2rem;

&nbsp;           max-width: 700px;

&nbsp;           margin: 0 auto 30px;

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           animation: fadeInUp 0.8s 0.2s forwards;

&nbsp;       }

&nbsp;       

&nbsp;       .hero-buttons {

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           animation: fadeInUp 0.8s 0.4s forwards;

&nbsp;       }

&nbsp;       

&nbsp;       @keyframes fadeInUp {

&nbsp;           to {

&nbsp;               opacity: 1;

&nbsp;               transform: translateY(0);

&nbsp;           }

&nbsp;       }

&nbsp;       

&nbsp;       .btn {

&nbsp;           display: inline-block;

&nbsp;           padding: 12px 30px;

&nbsp;           background-color: var(--accent-color);

&nbsp;           color: white;

&nbsp;           border: none;

&nbsp;           border-radius: 50px;

&nbsp;           font-size: 1rem;

&nbsp;           font-weight: 600;

&nbsp;           cursor: pointer;

&nbsp;           transition: all 0.3s ease;

&nbsp;           text-decoration: none;

&nbsp;           margin: 10px;

&nbsp;           position: relative;

&nbsp;           overflow: hidden;

&nbsp;           z-index: 1;

&nbsp;       }

&nbsp;       

&nbsp;       .btn::before {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           top: 0;

&nbsp;           left: 0;

&nbsp;           width: 100%;

&nbsp;           height: 100%;

&nbsp;           background: rgba(255, 255, 255, 0.2);

&nbsp;           transform: translateX(-100%);

&nbsp;           transition: transform 0.3s ease;

&nbsp;           z-index: -1;

&nbsp;       }

&nbsp;       

&nbsp;       .btn:hover::before {

&nbsp;           transform: translateX(0);

&nbsp;       }

&nbsp;       

&nbsp;       .btn:hover {

&nbsp;           background-color: #0096c7;

&nbsp;           transform: translateY(-3px);

&nbsp;           box-shadow: 0 10px 20px rgba(0, 180, 216, 0.2);

&nbsp;       }

&nbsp;       

&nbsp;       .btn-outline {

&nbsp;           background-color: transparent;

&nbsp;           border: 2px solid white;

&nbsp;       }

&nbsp;       

&nbsp;       .btn-outline:hover {

&nbsp;           background-color: white;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       /\* Pillars Section \*/

&nbsp;       .pillars {

&nbsp;           padding: 100px 0;

&nbsp;           background-color: white;

&nbsp;       }

&nbsp;       

&nbsp;       .section-title {

&nbsp;           text-align: center;

&nbsp;           margin-bottom: 60px;

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           transition: all 0.6s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .section-title.visible {

&nbsp;           opacity: 1;

&nbsp;           transform: translateY(0);

&nbsp;       }

&nbsp;       

&nbsp;       .section-title h2 {

&nbsp;           font-size: 2.5rem;

&nbsp;           color: var(--primary-color);

&nbsp;           margin-bottom: 15px;

&nbsp;           position: relative;

&nbsp;           display: inline-block;

&nbsp;       }

&nbsp;       

&nbsp;       .section-title h2::after {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           width: 60px;

&nbsp;           height: 4px;

&nbsp;           background-color: var(--accent-color);

&nbsp;           bottom: -10px;

&nbsp;           left: 50%;

&nbsp;           transform: translateX(-50%);

&nbsp;       }

&nbsp;       

&nbsp;       .section-title p {

&nbsp;           font-size: 1.1rem;

&nbsp;           color: #6c757d;

&nbsp;           max-width: 700px;

&nbsp;           margin: 20px auto 0;

&nbsp;       }

&nbsp;       

&nbsp;       .pillars-container {

&nbsp;           display: flex;

&nbsp;           flex-wrap: wrap;

&nbsp;           justify-content: center;

&nbsp;           gap: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card {

&nbsp;           flex: 1;

&nbsp;           min-width: 300px;

&nbsp;           background-color: #fff;

&nbsp;           border-radius: 10px;

&nbsp;           padding: 30px;

&nbsp;           box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);

&nbsp;           transition: all 0.3s ease;

&nbsp;           border-top: 4px solid var(--accent-color);

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           transition: all 0.6s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card.visible {

&nbsp;           opacity: 1;

&nbsp;           transform: translateY(0);

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card:nth-child(1) {

&nbsp;           transition-delay: 0.1s;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card:nth-child(2) {

&nbsp;           transition-delay: 0.2s;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card:nth-child(3) {

&nbsp;           transition-delay: 0.3s;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card:hover {

&nbsp;           transform: translateY(-10px);

&nbsp;           box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-icon {

&nbsp;           font-size: 3rem;

&nbsp;           color: var(--accent-color);

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card h3 {

&nbsp;           font-size: 1.5rem;

&nbsp;           margin-bottom: 15px;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .pillar-card p {

&nbsp;           color: #6c757d;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Services Section \*/

&nbsp;       .services {

&nbsp;           padding: 100px 0;

&nbsp;           background-color: #f8f9fa;

&nbsp;       }

&nbsp;       

&nbsp;       .services-container {

&nbsp;           display: grid;

&nbsp;           grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));

&nbsp;           gap: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .service-card {

&nbsp;           background-color: white;

&nbsp;           border-radius: 10px;

&nbsp;           overflow: hidden;

&nbsp;           box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);

&nbsp;           transition: all 0.3s ease;

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           transition: all 0.6s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .service-card.visible {

&nbsp;           opacity: 1;

&nbsp;           transform: translateY(0);

&nbsp;       }

&nbsp;       

&nbsp;       .service-card:nth-child(1) {

&nbsp;           transition-delay: 0.1s;

&nbsp;       }

&nbsp;       

&nbsp;       .service-card:nth-child(2) {

&nbsp;           transition-delay: 0.2s;

&nbsp;       }

&nbsp;       

&nbsp;       .service-card:nth-child(3) {

&nbsp;           transition-delay: 0.3s;

&nbsp;       }

&nbsp;       

&nbsp;       .service-card:hover {

&nbsp;           transform: translateY(-10px);

&nbsp;           box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);

&nbsp;       }

&nbsp;       

&nbsp;       .service-img {

&nbsp;           height: 200px;

&nbsp;           background: var(--gradient);

&nbsp;           display: flex;

&nbsp;           align-items: center;

&nbsp;           justify-content: center;

&nbsp;           color: white;

&nbsp;           font-size: 3rem;

&nbsp;       }

&nbsp;       

&nbsp;       .service-content {

&nbsp;           padding: 25px;

&nbsp;       }

&nbsp;       

&nbsp;       .service-content h3 {

&nbsp;           font-size: 1.3rem;

&nbsp;           margin-bottom: 15px;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .service-content p {

&nbsp;           color: #6c757d;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .service-features {

&nbsp;           list-style: none;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .service-features li {

&nbsp;           margin-bottom: 8px;

&nbsp;           display: flex;

&nbsp;           align-items: flex-start;

&nbsp;       }

&nbsp;       

&nbsp;       .service-features li i {

&nbsp;           color: var(--accent-color);

&nbsp;           margin-right: 10px;

&nbsp;           font-size: 0.9rem;

&nbsp;           margin-top: 5px;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Testimonials Section \*/

&nbsp;       .testimonials {

&nbsp;           padding: 100px 0;

&nbsp;           background-color: white;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonials-container {

&nbsp;           display: flex;

&nbsp;           flex-wrap: wrap;

&nbsp;           justify-content: center;

&nbsp;           gap: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card {

&nbsp;           flex: 1;

&nbsp;           min-width: 300px;

&nbsp;           max-width: 500px;

&nbsp;           background-color: #f8f9fa;

&nbsp;           border-radius: 10px;

&nbsp;           padding: 30px;

&nbsp;           box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);

&nbsp;           position: relative;

&nbsp;           opacity: 0;

&nbsp;           transform: translateY(20px);

&nbsp;           transition: all 0.6s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card.visible {

&nbsp;           opacity: 1;

&nbsp;           transform: translateY(0);

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card:nth-child(1) {

&nbsp;           transition-delay: 0.1s;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card:nth-child(2) {

&nbsp;           transition-delay: 0.2s;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card:nth-child(3) {

&nbsp;           transition-delay: 0.3s;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-card::before {

&nbsp;           content: '\\f10d';

&nbsp;           font-family: 'Font Awesome 6 Free';

&nbsp;           font-weight: 900;

&nbsp;           position: absolute;

&nbsp;           top: 20px;

&nbsp;           left: 20px;

&nbsp;           font-size: 2rem;

&nbsp;           color: rgba(10, 36, 99, 0.1);

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-content {

&nbsp;           margin-bottom: 20px;

&nbsp;           font-style: italic;

&nbsp;           color: #495057;

&nbsp;       }

&nbsp;       

&nbsp;       .testimonial-author {

&nbsp;           display: flex;

&nbsp;           align-items: center;

&nbsp;       }

&nbsp;       

&nbsp;       .author-img {

&nbsp;           width: 50px;

&nbsp;           height: 50px;

&nbsp;           border-radius: 50%;

&nbsp;           background-color: var(--accent-color);

&nbsp;           display: flex;

&nbsp;           align-items: center;

&nbsp;           justify-content: center;

&nbsp;           color: white;

&nbsp;           font-weight: 700;

&nbsp;           margin-right: 15px;

&nbsp;       }

&nbsp;       

&nbsp;       .author-info h4 {

&nbsp;           font-size: 1.1rem;

&nbsp;           margin-bottom: 5px;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .author-info p {

&nbsp;           font-size: 0.9rem;

&nbsp;           color: #6c757d;

&nbsp;       }

&nbsp;       

&nbsp;       .rating {

&nbsp;           color: #ffc107;

&nbsp;           margin-bottom: 15px;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Contact Section \*/

&nbsp;       .contact {

&nbsp;           padding: 100px 0;

&nbsp;           background: var(--gradient);

&nbsp;           color: white;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-container {

&nbsp;           display: flex;

&nbsp;           flex-wrap: wrap;

&nbsp;           gap: 50px;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-info, .contact-form {

&nbsp;           flex: 1;

&nbsp;           min-width: 300px;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-info h3 {

&nbsp;           font-size: 1.8rem;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-info p {

&nbsp;           margin-bottom: 30px;

&nbsp;           opacity: 0.9;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-item {

&nbsp;           display: flex;

&nbsp;           align-items: flex-start;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .contact-item i {

&nbsp;           font-size: 1.5rem;

&nbsp;           margin-right: 15px;

&nbsp;           color: var(--accent-color);

&nbsp;           margin-top: 5px;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group {

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group label {

&nbsp;           display: block;

&nbsp;           margin-bottom: 8px;

&nbsp;           font-weight: 500;

&nbsp;       }

&nbsp;       

&nbsp;       .form-control {

&nbsp;           width: 100%;

&nbsp;           padding: 12px 15px;

&nbsp;           border: none;

&nbsp;           border-radius: 5px;

&nbsp;           font-family: 'Montserrat', sans-serif;

&nbsp;           font-size: 1rem;

&nbsp;       }

&nbsp;       

&nbsp;       textarea.form-control {

&nbsp;           min-height: 150px;

&nbsp;           resize: vertical;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Footer \*/

&nbsp;       footer {

&nbsp;           background-color: var(--primary-color);

&nbsp;           color: white;

&nbsp;           padding: 50px 0 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-container {

&nbsp;           display: flex;

&nbsp;           flex-wrap: wrap;

&nbsp;           justify-content: space-between;

&nbsp;           gap: 30px;

&nbsp;           margin-bottom: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-col {

&nbsp;           flex: 1;

&nbsp;           min-width: 200px;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-col h4 {

&nbsp;           font-size: 1.2rem;

&nbsp;           margin-bottom: 20px;

&nbsp;           position: relative;

&nbsp;           padding-bottom: 10px;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-col h4::after {

&nbsp;           content: '';

&nbsp;           position: absolute;

&nbsp;           width: 40px;

&nbsp;           height: 2px;

&nbsp;           background-color: var(--accent-color);

&nbsp;           bottom: 0;

&nbsp;           left: 0;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-links {

&nbsp;           list-style: none;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-links li {

&nbsp;           margin-bottom: 10px;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-links a {

&nbsp;           color: rgba(255, 255, 255, 0.7);

&nbsp;           text-decoration: none;

&nbsp;           transition: color 0.3s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .footer-links a:hover {

&nbsp;           color: var(--accent-color);

&nbsp;       }

&nbsp;       

&nbsp;       .social-links {

&nbsp;           display: flex;

&nbsp;           gap: 15px;

&nbsp;           margin-top: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .social-links a {

&nbsp;           display: flex;

&nbsp;           align-items: center;

&nbsp;           justify-content: center;

&nbsp;           width: 40px;

&nbsp;           height: 40px;

&nbsp;           background-color: rgba(255, 255, 255, 0.1);

&nbsp;           border-radius: 50%;

&nbsp;           color: white;

&nbsp;           transition: all 0.3s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .social-links a:hover {

&nbsp;           background-color: var(--accent-color);

&nbsp;           transform: translateY(-3px);

&nbsp;       }

&nbsp;       

&nbsp;       .copyright {

&nbsp;           text-align: center;

&nbsp;           padding-top: 20px;

&nbsp;           border-top: 1px solid rgba(255, 255, 255, 0.1);

&nbsp;           font-size: 0.9rem;

&nbsp;           color: rgba(255, 255, 255, 0.7);

&nbsp;       }

&nbsp;       

&nbsp;       /\* Modal Styles \*/

&nbsp;       .modal {

&nbsp;           display: none;

&nbsp;           position: fixed;

&nbsp;           top: 0;

&nbsp;           left: 0;

&nbsp;           width: 100%;

&nbsp;           height: 100%;

&nbsp;           background-color: rgba(0, 0, 0, 0.7);

&nbsp;           z-index: 2000;

&nbsp;           justify-content: center;

&nbsp;           align-items: center;

&nbsp;       }

&nbsp;       

&nbsp;       .modal-content {

&nbsp;           background-color: white;

&nbsp;           border-radius: 10px;

&nbsp;           padding: 30px;

&nbsp;           max-width: 800px;

&nbsp;           width: 90%;

&nbsp;           max-height: 90vh;

&nbsp;           overflow-y: auto;

&nbsp;           position: relative;

&nbsp;       }

&nbsp;       

&nbsp;       .close-modal {

&nbsp;           position: absolute;

&nbsp;           top: 15px;

&nbsp;           right: 15px;

&nbsp;           font-size: 1.5rem;

&nbsp;           cursor: pointer;

&nbsp;           color: #6c757d;

&nbsp;           transition: color 0.3s ease;

&nbsp;       }

&nbsp;       

&nbsp;       .close-modal:hover {

&nbsp;           color: var(--dark-color);

&nbsp;       }

&nbsp;       

&nbsp;       .modal h3 {

&nbsp;           margin-bottom: 20px;

&nbsp;           color: var(--primary-color);

&nbsp;           font-size: 1.8rem;

&nbsp;       }

&nbsp;       

&nbsp;       .modal h4 {

&nbsp;           margin: 20px 0 10px;

&nbsp;           color: var(--secondary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .modal ul {

&nbsp;           margin-left: 20px;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .modal p {

&nbsp;           margin-bottom: 15px;

&nbsp;           color: #495057;

&nbsp;       }

&nbsp;       

&nbsp;       .process-step {

&nbsp;           background-color: #f8f9fa;

&nbsp;           border-radius: 8px;

&nbsp;           padding: 15px;

&nbsp;           margin-bottom: 15px;

&nbsp;           border-left: 4px solid var(--accent-color);

&nbsp;       }

&nbsp;       

&nbsp;       .process-step h4 {

&nbsp;           margin-top: 0;

&nbsp;           margin-bottom: 10px;

&nbsp;           color: var(--primary-color);

&nbsp;       }

&nbsp;       

&nbsp;       .modal-footer {

&nbsp;           margin-top: 30px;

&nbsp;           text-align: center;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Formspree Styles \*/

&nbsp;       .form-message {

&nbsp;           padding: 15px;

&nbsp;           margin-bottom: 20px;

&nbsp;           border-radius: 5px;

&nbsp;           display: none;

&nbsp;       }

&nbsp;       

&nbsp;       .form-message.success {

&nbsp;           background-color: #d4edda;

&nbsp;           color: #155724;

&nbsp;           border: 1px solid #c3e6cb;

&nbsp;       }

&nbsp;       

&nbsp;       .form-message.error {

&nbsp;           background-color: #f8d7da;

&nbsp;           color: #721c24;

&nbsp;           border: 1px solid #f5c6cb;

&nbsp;       }

&nbsp;       

&nbsp;       /\* Loading Spinner \*/

&nbsp;       .spinner {

&nbsp;           border: 4px solid rgba(255, 255, 255, 0.3);

&nbsp;           border-radius: 50%;

&nbsp;           border-top: 4px solid white;

&nbsp;           width: 20px;

&nbsp;           height: 20px;

&nbsp;           animation: spin 1s linear infinite;

&nbsp;           display: inline-block;

&nbsp;           margin-left: 10px;

&nbsp;           vertical-align: middle;

&nbsp;       }

&nbsp;       

&nbsp;       @keyframes spin {

&nbsp;           0% { transform: rotate(0deg); }

&nbsp;           100% { transform: rotate(360deg); }

&nbsp;       }

&nbsp;       

&nbsp;       /\* Responsive Styles \*/

&nbsp;       @media (max-width: 992px) {

&nbsp;           .hero h1 {

&nbsp;               font-size: 3rem;

&nbsp;           }

&nbsp;           

&nbsp;           .section-title h2 {

&nbsp;               font-size: 2.2rem;

&nbsp;           }

&nbsp;       }

&nbsp;       

&nbsp;       @media (max-width: 768px) {

&nbsp;           .nav-links {

&nbsp;               position: fixed;

&nbsp;               top: 70px;

&nbsp;               left: 0;

&nbsp;               width: 100%;

&nbsp;               background-color: white;

&nbsp;               flex-direction: column;

&nbsp;               align-items: center;

&nbsp;               padding: 20px 0;

&nbsp;               box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

&nbsp;               transform: translateY(-150%);

&nbsp;               transition: transform 0.3s ease;

&nbsp;               z-index: 999;

&nbsp;           }

&nbsp;           

&nbsp;           .nav-links.active {

&nbsp;               transform: translateY(0);

&nbsp;           }

&nbsp;           

&nbsp;           .nav-links li {

&nbsp;               margin: 10px 0;

&nbsp;           }

&nbsp;           

&nbsp;           .mobile-menu-btn {

&nbsp;               display: block;

&nbsp;           }

&nbsp;           

&nbsp;           .hero h1 {

&nbsp;               font-size: 2.5rem;

&nbsp;           }

&nbsp;           

&nbsp;           .section-title h2 {

&nbsp;               font-size: 2rem;

&nbsp;           }

&nbsp;           

&nbsp;           .contact-container {

&nbsp;               flex-direction: column;

&nbsp;           }

&nbsp;       }

&nbsp;       

&nbsp;       @media (max-width: 576px) {

&nbsp;           .hero h1 {

&nbsp;               font-size: 2rem;

&nbsp;           }

&nbsp;           

&nbsp;           .hero p {

&nbsp;               font-size: 1rem;

&nbsp;           }

&nbsp;           

&nbsp;           .section-title h2 {

&nbsp;               font-size: 1.8rem;

&nbsp;           }

&nbsp;           

&nbsp;           .pillar-card, .service-card, .testimonial-card {

&nbsp;               min-width: 100%;

&nbsp;           }

&nbsp;       }

&nbsp;   </style>

</head>

<body>

&nbsp;   <!-- Header -->

&nbsp;   <header>

&nbsp;       <div class="container">

&nbsp;           <nav class="navbar">

&nbsp;               <div class="logo">

&nbsp;                   <i class="fas fa-robot"></i>

&nbsp;                   <span>CanarIAgentic</span>

&nbsp;               </div>

&nbsp;               <ul class="nav-links">

&nbsp;                   <li><a href="#home">Inicio</a></li>

&nbsp;                   <li><a href="#pillars">Pilares</a></li>

&nbsp;                   <li><a href="#services">Servicios</a></li>

&nbsp;                   <li><a href="#testimonials">Testimonios</a></li>

&nbsp;                   <li><a href="#contact">Contacto</a></li>

&nbsp;               </ul>

&nbsp;               <button class="mobile-menu-btn" id="mobileMenuBtn">

&nbsp;                   <i class="fas fa-bars"></i>

&nbsp;               </button>

&nbsp;           </nav>

&nbsp;       </div>

&nbsp;   </header>

&nbsp;   

&nbsp;   <!-- Hero Section -->

&nbsp;   <section class="hero" id="home">

&nbsp;       <div class="container">

&nbsp;           <div class="hero-content">

&nbsp;               <h1>Transformando Empresas con Inteligencia Artificial</h1>

&nbsp;               <p>CanarIAgentic es la agencia líder en soluciones de IA que impulsa la innovación y eficiencia empresarial a través de tecnología vanguardista.</p>

&nbsp;               <div class="hero-buttons">

&nbsp;                   <a href="#contact" class="btn">Contactar Ahora</a>

&nbsp;                   <a href="#pillars" class="btn btn-outline">Conocer Más</a>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </section>

&nbsp;   

&nbsp;   <!-- Pillars Section -->

&nbsp;   <section class="pillars" id="pillars">

&nbsp;       <div class="container">

&nbsp;           <div class="section-title">

&nbsp;               <h2>Nuestros Pilares Fundamentales</h2>

&nbsp;               <p>En CanarIAgentic basamos nuestra estrategia en tres pilares que garantizan el éxito en la transformación digital de las empresas.</p>

&nbsp;           </div>

&nbsp;           <div class="pillars-container">

&nbsp;               <div class="pillar-card">

&nbsp;                   <div class="pillar-icon">

&nbsp;                       <i class="fas fa-graduation-cap"></i>

&nbsp;                   </div>

&nbsp;                   <h3>Formación Personalizada de IA</h3>

&nbsp;                   <p>Desarrollamos programas de capacitación a medida para que tu equipo domine las herramientas y conceptos de inteligencia artificial.</p>

&nbsp;                   <button class="btn" onclick="openPillarModal('formacion')">Ver Detalles</button>

&nbsp;               </div>

&nbsp;               <div class="pillar-card">

&nbsp;                   <div class="pillar-icon">

&nbsp;                       <i class="fas fa-lightbulb"></i>

&nbsp;                   </div>

&nbsp;                   <h3>Consultoría Vanguardista</h3>

&nbsp;                   <p>Ayudamos a las empresas a identificar oportunidades de mejora e innovación mediante el análisis estratégico con IA.</p>

&nbsp;                   <button class="btn" onclick="openPillarModal('consultoria')">Ver Detalles</button>

&nbsp;               </div>

&nbsp;               <div class="pillar-card">

&nbsp;                   <div class="pillar-icon">

&nbsp;                       <i class="fas fa-cogs"></i>

&nbsp;                   </div>

&nbsp;                   <h3>Creación de Agentes IA</h3>

&nbsp;                   <p>Diseñamos e implementamos agentes inteligentes que automatizan y optimizan los procesos empresariales.</p>

&nbsp;                   <button class="btn" onclick="openPillarModal('agentes')">Ver Detalles</button>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </section>

&nbsp;   

&nbsp;   <!-- Services Section -->

&nbsp;   <section class="services" id="services">

&nbsp;       <div class="container">

&nbsp;           <div class="section-title">

&nbsp;               <h2>Nuestros Servicios</h2>

&nbsp;               <p>Ofrecemos soluciones integrales de inteligencia artificial adaptadas a las necesidades específicas de cada cliente.</p>

&nbsp;           </div>

&nbsp;           <div class="services-container">

&nbsp;               <div class="service-card">

&nbsp;                   <div class="service-img">

&nbsp;                       <i class="fas fa-chalkboard-teacher"></i>

&nbsp;                   </div>

&nbsp;                   <div class="service-content">

&nbsp;                       <h3>Formación en IA</h3>

&nbsp;                       <p>Programas de capacitación personalizados para que tu equipo domine las herramientas y conceptos de inteligencia artificial.</p>

&nbsp;                       <ul class="service-features">

&nbsp;                           <li><i class="fas fa-check"></i> Diagnóstico inicial de competencias digitales</li>

&nbsp;                           <li><i class="fas fa-check"></i> Programas formativos a medida</li>

&nbsp;                           <li><i class="fas fa-check"></i> Talleres prácticos con casos de uso reales</li>

&nbsp;                           <li><i class="fas fa-check"></i> Acompañamiento en la implementación</li>

&nbsp;                       </ul>

&nbsp;                       <a href="#contact" class="btn">Más Información</a>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="service-card">

&nbsp;                   <div class="service-img">

&nbsp;                       <i class="fas fa-chart-line"></i>

&nbsp;                   </div>

&nbsp;                   <div class="service-content">

&nbsp;                       <h3>Consultoría de IA</h3>

&nbsp;                       <p>Análisis estratégico para identificar oportunidades de mejora e innovación mediante la implementación de inteligencia artificial.</p>

&nbsp;                       <ul class="service-features">

&nbsp;                           <li><i class="fas fa-check"></i> Análisis de madurez digital y de IA</li>

&nbsp;                           <li><i class="fas fa-check"></i> Identificación de casos de uso prioritarios</li>

&nbsp;                           <li><i class="fas fa-check"></i> Diseño de estrategias de implementación</li>

&nbsp;                           <li><i class="fas fa-check"></i> Evaluación de tecnologías y proveedores</li>

&nbsp;                       </ul>

&nbsp;                       <a href="#contact" class="btn">Más Información</a>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="service-card">

&nbsp;                   <div class="service-img">

&nbsp;                       <i class="fas fa-robot"></i>

&nbsp;                   </div>

&nbsp;                   <div class="service-content">

&nbsp;                       <h3>Desarrollo de Agentes IA</h3>

&nbsp;                       <p>Creación e implementación de agentes inteligentes que automatizan y optimizan los procesos empresariales.</p>

&nbsp;                       <ul class="service-features">

&nbsp;                           <li><i class="fas fa-check"></i> Análisis y modelado de procesos</li>

&nbsp;                           <li><i class="fas fa-check"></i> Diseño de arquitecturas de agentes</li>

&nbsp;                           <li><i class="fas fa-check"></i> Desarrollo e implementación de soluciones</li>

&nbsp;                           <li><i class="fas fa-check"></i> Integración con sistemas existentes</li>

&nbsp;                       </ul>

&nbsp;                       <a href="https://studio.pickaxe.co/STUDIOD9VCTFILPI7W0YP" target="\_blank" class="btn">Ver Demostración</a>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </section>

&nbsp;   

&nbsp;   <!-- Testimonials Section -->

&nbsp;   <section class="testimonials" id="testimonials">

&nbsp;       <div class="container">

&nbsp;           <div class="section-title">

&nbsp;               <h2>Testimonios de Clientes</h2>

&nbsp;               <p>Descubre lo que dicen las empresas que han confiado en nuestros servicios de inteligencia artificial.</p>

&nbsp;           </div>

&nbsp;           <div class="testimonials-container">

&nbsp;               <div class="testimonial-card">

&nbsp;                   <div class="rating">

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-content">

&nbsp;                       <p>"La formación en IA que recibimos de CanarIAgentic transformó completamente nuestra operación. Nuestro equipo ahora domina las herramientas de inteligencia artificial, lo que nos ha permitido aumentar nuestra productividad en un 40%."</p>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-author">

&nbsp;                       <div class="author-img">LG</div>

&nbsp;                       <div class="author-info">

&nbsp;                           <h4>Laura García</h4>

&nbsp;                           <p>CTO, Innovatech Systems</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="testimonial-card">

&nbsp;                   <div class="rating">

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-content">

&nbsp;                       <p>"Gracias a la consultoría de CanarIAgentic, identificamos oportunidades de mejora que ni imaginábamos. Su análisis vanguardista nos posicionó como líderes en nuestro sector, con un crecimiento del 35% en el último año."</p>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-author">

&nbsp;                       <div class="author-img">AR</div>

&nbsp;                       <div class="author-info">

&nbsp;                           <h4>Ana Rodríguez</h4>

&nbsp;                           <p>CEO, Global Retail Group</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="testimonial-card">

&nbsp;                   <div class="rating">

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                       <i class="fas fa-star"></i>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-content">

&nbsp;                       <p>"CanarIAgentic transformó por completo nuestra operación logística. Sus agentes IA redujeron nuestros tiempos de procesamiento en un 70% y los errores en un 95%. ¡Invertir con ellos fue la mejor decisión que hemos tomado!"</p>

&nbsp;                   </div>

&nbsp;                   <div class="testimonial-author">

&nbsp;                       <div class="author-img">CM</div>

&nbsp;                       <div class="author-info">

&nbsp;                           <h4>Carlos Méndez</h4>

&nbsp;                           <p>Director de Operaciones, LogiFast Solutions</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </section>

&nbsp;   

&nbsp;   <!-- Contact Section -->

&nbsp;   <section class="contact" id="contact">

&nbsp;       <div class="container">

&nbsp;           <div class="section-title" style="color: white;">

&nbsp;               <h2>Contacto</h2>

&nbsp;               <p>¿Listo para transformar tu empresa con inteligencia artificial? Contáctanos hoy mismo.</p>

&nbsp;           </div>

&nbsp;           <div class="contact-container">

&nbsp;               <div class="contact-info">

&nbsp;                   <h3>Información de Contacto</h3>

&nbsp;                   <p>Nuestro equipo de expertos está listo para ayudarte a encontrar las mejores soluciones de IA para tu empresa.</p>

&nbsp;                   <div class="contact-item">

&nbsp;                       <i class="fas fa-map-marker-alt"></i>

&nbsp;                       <div>

&nbsp;                           <h4>Dirección</h4>

&nbsp;                           <p>calle La Palma 52 Valle de Guerra 38270 Santa Cruz de Tenerife</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;                   <div class="contact-item">

&nbsp;                       <i class="fas fa-phone-alt"></i>

&nbsp;                       <div>

&nbsp;                           <h4>Teléfono</h4>

&nbsp;                           <p>+34 922 150 801</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;                   <div class="contact-item">

&nbsp;                       <i class="fas fa-envelope"></i>

&nbsp;                       <div>

&nbsp;                           <h4>Email</h4>

&nbsp;                           <p>franchut76business@gmail.com</p>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="contact-form">

&nbsp;                   <div id="form-message" class="form-message"></div>

&nbsp;                   <form id="contactForm">

&nbsp;                       <div class="form-group">

&nbsp;                           <label for="name">Nombre</label>

&nbsp;                           <input type="text" id="name" name="name" class="form-control" required>

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label for="email">Email</label>

&nbsp;                           <input type="email" id="email" name="email" class="form-control" required>

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label for="company">Empresa</label>

&nbsp;                           <input type="text" id="company" name="company" class="form-control" required>

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label for="message">Mensaje</label>

&nbsp;                           <textarea id="message" name="message" class="form-control" required></textarea>

&nbsp;                       </div>

&nbsp;                       <button type="submit" class="btn" id="submitBtn">Enviar Mensaje</button>

&nbsp;                   </form>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </section>

&nbsp;   

&nbsp;   <!-- Footer -->

&nbsp;   <footer>

&nbsp;       <div class="container">

&nbsp;           <div class="footer-container">

&nbsp;               <div class="footer-col">

&nbsp;                   <div class="logo" style="margin-bottom: 20px;">

&nbsp;                       <i class="fas fa-robot"></i>

&nbsp;                       <span>CanarIAgentic</span>

&nbsp;                   </div>

&nbsp;                   <p>Transformando empresas con inteligencia artificial de vanguardia.</p>

&nbsp;                   <div class="social-links">

&nbsp;                       <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>

&nbsp;                       <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>

&nbsp;                       <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>

&nbsp;                       <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               <div class="footer-col">

&nbsp;                   <h4>Enlaces Rápidos</h4>

&nbsp;                   <ul class="footer-links">

&nbsp;                       <li><a href="#home">Inicio</a></li>

&nbsp;                       <li><a href="#pillars">Pilares</a></li>

&nbsp;                       <li><a href="#services">Servicios</a></li>

&nbsp;                       <li><a href="#testimonials">Testimonios</a></li>

&nbsp;                       <li><a href="#contact">Contacto</a></li>

&nbsp;                   </ul>

&nbsp;               </div>

&nbsp;               <div class="footer-col">

&nbsp;                   <h4>Servicios</h4>

&nbsp;                   <ul class="footer-links">

&nbsp;                       <li><a href="#">Formación en IA</a></li>

&nbsp;                       <li><a href="#">Consultoría de IA</a></li>

&nbsp;                       <li><a href="#">Desarrollo de Agentes IA</a></li>

&nbsp;                       <li><a href="#">Análisis Predictivo</a></li>

&nbsp;                   </ul>

&nbsp;               </div>

&nbsp;               <div class="footer-col">

&nbsp;                   <h4>Suscríbete</h4>

&nbsp;                   <p>Recibe las últimas noticias y actualizaciones sobre inteligencia artificial.</p>

&nbsp;                   <form id="subscribeForm" style="margin-top: 15px;">

&nbsp;                       <div class="form-group" style="margin-bottom: 15px;">

&nbsp;                           <input type="email" class="form-control" id="subscribeEmail" placeholder="Tu email" required>

&nbsp;                       </div>

&nbsp;                       <button type="submit" class="btn">Suscribirse</button>

&nbsp;                   </form>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;           <div class="copyright">

&nbsp;               <p>\&copy; 2023 CanarIAgentic. Todos los derechos reservados.</p>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </footer>

&nbsp;   

&nbsp;   <!-- Modal -->

&nbsp;   <div id="pillarModal" class="modal">

&nbsp;       <div class="modal-content">

&nbsp;           <span class="close-modal" onclick="closePillarModal()" aria-label="Cerrar modal">\&times;</span>

&nbsp;           <div id="pillarModalBody">

&nbsp;               <!-- Content will be dynamically inserted here -->

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </div>

&nbsp;   

&nbsp;   <!-- Notification -->

&nbsp;   <div id="notification" style="position: fixed; bottom: 20px; right: 20px; background-color: #2a9d8f; color: white; padding: 15px 25px; border-radius: 5px; box-shadow: 0 5px 15px rgba(0,0,0,0.2); transform: translateY(100px); transition: transform 0.3s ease; z-index: 3000;">

&nbsp;       <p id="notification-text"></p>

&nbsp;   </div>

&nbsp;   

&nbsp;   <script>

&nbsp;       // Initialize Supabase with your project credentials

&nbsp;       const supabaseUrl = 'https://mfargfnhebhgmkjochyg.supabase.co';

&nbsp;       const supabaseKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im1mYXJnZm5oZWJoZ21ram9jaHlnIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDI5NTU0ODIsImV4cCI6MjAxODUzMTQ4Mn0.S7z6KzZQ8x8w9qY9X8x8w9qY9X8x8w9qY9X8x8w9qY9X';

&nbsp;       const supabase = window.supabase.createClient(supabaseUrl, supabaseKey);

&nbsp;       

&nbsp;       // Mobile menu toggle

&nbsp;       const mobileMenuBtn = document.getElementById('mobileMenuBtn');

&nbsp;       const navLinks = document.querySelector('.nav-links');

&nbsp;       

&nbsp;       mobileMenuBtn.addEventListener('click', () => {

&nbsp;           navLinks.classList.toggle('active');

&nbsp;           

&nbsp;           // Change icon

&nbsp;           const icon = mobileMenuBtn.querySelector('i');

&nbsp;           if (icon.classList.contains('fa-bars')) {

&nbsp;               icon.classList.remove('fa-bars');

&nbsp;               icon.classList.add('fa-times');

&nbsp;           } else {

&nbsp;               icon.classList.remove('fa-times');

&nbsp;               icon.classList.add('fa-bars');

&nbsp;           }

&nbsp;       });

&nbsp;       

&nbsp;       // Close mobile menu when clicking on a link

&nbsp;       document.querySelectorAll('.nav-links a').forEach(link => {

&nbsp;           link.addEventListener('click', () => {

&nbsp;               navLinks.classList.remove('active');

&nbsp;               const icon = mobileMenuBtn.querySelector('i');

&nbsp;               icon.classList.remove('fa-times');

&nbsp;               icon.classList.add('fa-bars');

&nbsp;           });

&nbsp;       });

&nbsp;       

&nbsp;       // Smooth scrolling for navigation links

&nbsp;       document.querySelectorAll('a\[href^="#"]').forEach(anchor => {

&nbsp;           anchor.addEventListener('click', function (e) {

&nbsp;               e.preventDefault();

&nbsp;               const target = document.querySelector(this.getAttribute('href'));

&nbsp;               if (target) {

&nbsp;                   window.scrollTo({

&nbsp;                       top: target.offsetTop - 80,

&nbsp;                       behavior: 'smooth'

&nbsp;                   });

&nbsp;               }

&nbsp;           });

&nbsp;       });

&nbsp;       

&nbsp;       // Modal functionality for pillars

&nbsp;       function openPillarModal(pillar) {

&nbsp;           const modal = document.getElementById('pillarModal');

&nbsp;           const modalBody = document.getElementById('pillarModalBody');

&nbsp;           

&nbsp;           let content = '';

&nbsp;           

&nbsp;           switch(pillar) {

&nbsp;               case 'formacion':

&nbsp;                   content = `

&nbsp;                       <h3>Formación Personalizada de IA</h3>

&nbsp;                       <p>Nuestro proceso de formación en inteligencia artificial está diseñado para adaptarse a las necesidades específicas de cada empresa, garantizando que tu equipo adquiera las competencias necesarias para aprovechar al máximo la tecnología de IA.</p>

&nbsp;                       

&nbsp;                       <h4>Nuestro Proceso de Formación</h4>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>1. Diagnóstico Inicial</h4>

&nbsp;                           <p>Realizamos una evaluación exhaustiva de las competencias digitales actuales de tu equipo y las necesidades específicas de tu empresa en materia de IA.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>2. Diseño del Programa Formativo</h4>

&nbsp;                           <p>Basándonos en el diagnóstico, diseñamos un programa de formación a medida que aborda las áreas de mejora identificadas y se alinea con los objetivos estratégicos de tu empresa.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>3. Implementación de la Formación</h4>

&nbsp;                           <p>Llevamos a cabo la formación a través de una combinación de sesiones teóricas, talleres prácticos y casos de uso reales, garantizando una experiencia de aprendizaje completa y aplicable.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>4. Acompañamiento y Seguimiento</h4>

&nbsp;                           <p>Proporcionamos acompañamiento continuo durante la implementación de los conocimientos adquiridos, asegurando que tu equipo pueda aplicar eficazmente lo aprendido en su día a día.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>5. Evaluación y Certificación</h4>

&nbsp;                           <p>Realizamos una evaluación final para medir el impacto de la formación y proporcionamos certificados que reconocen las nuevas competencias adquiridas por tu equipo.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="modal-footer">

&nbsp;                           <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>

&nbsp;                       </div>

&nbsp;                   `;

&nbsp;                   break;

&nbsp;               case 'consultoria':

&nbsp;                   content = `

&nbsp;                       <h3>Consultoría Vanguardista con IA</h3>

&nbsp;                       <p>Nuestro servicio de consultoría en inteligencia artificial ayuda a las empresas a identificar oportunidades de mejora e innovación, diseñando estrategias que aprovechan todo el potencial de la IA para transformar sus operaciones y modelos de negocio.</p>

&nbsp;                       

&nbsp;                       <h4>Nuestro Proceso de Consultoría</h4>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>1. Análisis de Madurez Digital</h4>

&nbsp;                           <p>Evaluamos el nivel actual de madurez digital y de adopción de IA en tu empresa, identificando fortalezas, debilidades y áreas de oportunidad.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>2. Identificación de Casos de Uso</h4>

&nbsp;                           <p>Trabajamos contigo para identificar y priorizar los casos de uso de IA con mayor potencial de impacto en tu negocio, considerando factores como viabilidad técnica, retorno de inversión y alineación estratégica.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>3. Diseño de la Estrategia de Implementación</h4>

&nbsp;                           <p>Desarrollamos una hoja de ruta detallada para la implementación de soluciones de IA, incluyendo objetivos, cronograma, recursos necesarios y métricas de éxito.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>4. Evaluación de Tecnologías y Proveedores</h4>

&nbsp;                           <p>Analizamos y recomendamos las tecnologías y proveedores más adecuados para tus necesidades específicas, asegurando que tomes decisiones informadas y estratégicas.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>5. Planificación de la Transformación Digital</h4>

&nbsp;                           <p>Elaboramos un plan integral de transformación digital que integra la IA en tu estrategia empresarial, preparando a tu organización para los desafíos y oportunidades del futuro.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="modal-footer">

&nbsp;                           <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>

&nbsp;                       </div>

&nbsp;                   `;

&nbsp;                   break;

&nbsp;               case 'agentes':

&nbsp;                   content = `

&nbsp;                       <h3>Creación de Agentes IA</h3>

&nbsp;                       <p>Diseñamos e implementamos agentes inteligentes que automatizan y optimizan los procesos empresariales, permitiendo a tu organización operar de manera más eficiente y enfocarse en actividades de mayor valor añadido.</p>

&nbsp;                       

&nbsp;                       <h4>Nuestro Proceso de Creación de Agentes IA</h4>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>1. Análisis y Modelado de Procesos</h4>

&nbsp;                           <p>Realizamos un análisis detallado de los procesos empresariales existentes para identificar oportunidades de automatización y optimización mediante agentes de IA.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>2. Diseño de Arquitecturas de Agentes</h4>

&nbsp;                           <p>Diseñamos la arquitectura de los agentes inteligentes, definiendo sus capacidades, comportamientos y mecanismos de interacción con los sistemas existentes y los usuarios.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>3. Desarrollo e Implementación de Soluciones</h4>

&nbsp;                           <p>Desarrollamos e implementamos los agentes de IA utilizando las últimas tecnologías y mejores prácticas, asegurando su correcto funcionamiento y rendimiento.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>4. Integración con Sistemas Existentes</h4>

&nbsp;                           <p>Integramos los agentes de IA con los sistemas y plataformas existentes en tu empresa, garantizando una comunicación fluida y una operación coordinada.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="process-step">

&nbsp;                           <h4>5. Monitorización y Mejora Continua</h4>

&nbsp;                           <p>Implementamos sistemas de monitorización para evaluar el rendimiento de los agentes y realizamos mejoras continuas basadas en los resultados obtenidos y el feedback de los usuarios.</p>

&nbsp;                       </div>

&nbsp;                       

&nbsp;                       <div class="modal-footer">

&nbsp;                           <button class="btn" onclick="closePillarModal(); document.getElementById('contact').scrollIntoView({behavior: 'smooth'});">Contactar para Más Información</button>

&nbsp;                       </div>

&nbsp;                   `;

&nbsp;                   break;

&nbsp;           }

&nbsp;           

&nbsp;           modalBody.innerHTML = content;

&nbsp;           modal.style.display = 'flex';

&nbsp;       }

&nbsp;       

&nbsp;       function closePillarModal() {

&nbsp;           document.getElementById('pillarModal').style.display = 'none';

&nbsp;       }

&nbsp;       

&nbsp;       // Close modal when clicking outside

&nbsp;       window.onclick = function(event) {

&nbsp;           const modal = document.getElementById('pillarModal');

&nbsp;           if (event.target == modal) {

&nbsp;               modal.style.display = 'none';

&nbsp;           }

&nbsp;       }

&nbsp;       

&nbsp;       // Contact form submission with Supabase

&nbsp;       const contactForm = document.getElementById('contactForm');

&nbsp;       const formMessage = document.getElementById('form-message');

&nbsp;       const submitBtn = document.getElementById('submitBtn');

&nbsp;       

&nbsp;       contactForm.addEventListener('submit', async function(e) {

&nbsp;           e.preventDefault();

&nbsp;           

&nbsp;           // Show loading state

&nbsp;           submitBtn.disabled = true;

&nbsp;           submitBtn.innerHTML = 'Enviando... <span class="spinner"></span>';

&nbsp;           

&nbsp;           // Get form data

&nbsp;           const name = document.getElementById('name').value;

&nbsp;           const email = document.getElementById('email').value;

&nbsp;           const company = document.getElementById('company').value;

&nbsp;           const message = document.getElementById('message').value;

&nbsp;           

&nbsp;           try {

&nbsp;               console.log('Enviando datos a Supabase...');

&nbsp;               

&nbsp;               // Insert data into Supabase table "formulario de contacto"

&nbsp;               const { data, error } = await supabase

&nbsp;                   .from('formulario\_de\_contacto')  // Usar guiones bajos en lugar de espacios

&nbsp;                   .insert(\[

&nbsp;                       { 

&nbsp;                           nombre: name, 

&nbsp;                           email: email, 

&nbsp;                           empresa: company, 

&nbsp;                           mensaje: message,

&nbsp;                           created\_at: new Date().toISOString()

&nbsp;                       }

&nbsp;                   ]);

&nbsp;               

&nbsp;               if (error) {

&nbsp;                   console.error('Error de Supabase:', error);

&nbsp;                   throw error;

&nbsp;               }

&nbsp;               

&nbsp;               console.log('Datos enviados correctamente:', data);

&nbsp;               

&nbsp;               // Show success message

&nbsp;               formMessage.textContent = `¡Gracias ${name}! Tu mensaje ha sido enviado correctamente. Te contactaremos pronto en ${email}.`;

&nbsp;               formMessage.className = 'form-message success';

&nbsp;               formMessage.style.display = 'block';

&nbsp;               

&nbsp;               // Show notification

&nbsp;               showNotification(`Gracias ${name}, tu mensaje ha sido enviado. Te contactaremos pronto en ${email}.`);

&nbsp;               

&nbsp;               // Reset form after a short delay to ensure data is sent

&nbsp;               setTimeout(() => {

&nbsp;                   contactForm.reset();

&nbsp;                   console.log('Formulario reseteado');

&nbsp;               }, 1000);

&nbsp;               

&nbsp;               // Hide success message after 5 seconds

&nbsp;               setTimeout(() => {

&nbsp;                   formMessage.style.display = 'none';

&nbsp;               }, 5000);

&nbsp;               

&nbsp;           } catch (error) {

&nbsp;               console.error('Error completo:', error);

&nbsp;               

&nbsp;               // Show error message

&nbsp;               formMessage.textContent = 'Ha ocurrido un error. Por favor, inténtalo de nuevo más tarde.';

&nbsp;               formMessage.className = 'form-message error';

&nbsp;               formMessage.style.display = 'block';

&nbsp;               

&nbsp;               // Hide error message after 5 seconds

&nbsp;               setTimeout(() => {

&nbsp;                   formMessage.style.display = 'none';

&nbsp;               }, 5000);

&nbsp;           } finally {

&nbsp;               // Reset button state

&nbsp;               submitBtn.disabled = false;

&nbsp;               submitBtn.innerHTML = 'Enviar Mensaje';

&nbsp;           }

&nbsp;       });

&nbsp;       

&nbsp;       // Subscribe form with Supabase

&nbsp;       document.getElementById('subscribeForm').addEventListener('submit', async function(e) {

&nbsp;           e.preventDefault();

&nbsp;           

&nbsp;           // Get email value

&nbsp;           const email = document.getElementById('subscribeEmail').value;

&nbsp;           

&nbsp;           try {

&nbsp;               // Insert data into Supabase

&nbsp;               const { data, error } = await supabase

&nbsp;                   .from('suscripciones')

&nbsp;                   .insert(\[

&nbsp;                       { 

&nbsp;                           email: email,

&nbsp;                           created\_at: new Date().toISOString()

&nbsp;                       }

&nbsp;                   ]);

&nbsp;               

&nbsp;               if (error) throw error;

&nbsp;               

&nbsp;               // Show notification

&nbsp;               showNotification(`Gracias por suscribirte con el email ${email}. Recibirás nuestras novedades pronto.`);

&nbsp;               

&nbsp;               // Reset form

&nbsp;               this.reset();

&nbsp;           } catch (error) {

&nbsp;               console.error('Error:', error);

&nbsp;               

&nbsp;               // Show error notification

&nbsp;               showNotification('Ha ocurrido un error al suscribirte. Por favor, inténtalo de nuevo más tarde.');

&nbsp;           }

&nbsp;       });

&nbsp;       

&nbsp;       // Show notification

&nbsp;       function showNotification(message) {

&nbsp;           // Create notification element if it doesn't exist

&nbsp;           let notification = document.getElementById('notification');

&nbsp;           if (!notification) {

&nbsp;               notification = document.createElement('div');

&nbsp;               notification.id = 'notification';

&nbsp;               notification.style.position = 'fixed';

&nbsp;               notification.style.bottom = '20px';

&nbsp;               notification.style.right = '20px';

&nbsp;               notification.style.backgroundColor = '#2a9d8f';

&nbsp;               notification.style.color = 'white';

&nbsp;               notification.style.padding = '15px 25px';

&nbsp;               notification.style.borderRadius = '5px';

&nbsp;               notification.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';

&nbsp;               notification.style.transform = 'translateY(100px)';

&nbsp;               notification.style.transition = 'transform 0.3s ease';

&nbsp;               notification.style.zIndex = '3000';

&nbsp;               document.body.appendChild(notification);

&nbsp;           }

&nbsp;           

&nbsp;           // Set message and show notification

&nbsp;           notification.innerHTML = `<p>${message}</p>`;

&nbsp;           notification.style.transform = 'translateY(0)';

&nbsp;           

&nbsp;           // Hide notification after 5 seconds

&nbsp;           setTimeout(() => {

&nbsp;               notification.style.transform = 'translateY(100px)';

&nbsp;           }, 5000);

&nbsp;       }

&nbsp;       

&nbsp;       // Change header background on scroll

&nbsp;       window.addEventListener('scroll', function() {

&nbsp;           const header = document.querySelector('header');

&nbsp;           if (window.scrollY > 100) {

&nbsp;               header.style.backgroundColor = 'rgba(255, 255, 255, 0.98)';

&nbsp;               header.style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';

&nbsp;           } else {

&nbsp;               header.style.backgroundColor = 'rgba(255, 255, 255, 0.95)';

&nbsp;               header.style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';

&nbsp;           }

&nbsp;       });

&nbsp;       

&nbsp;       // Animate elements on scroll

&nbsp;       const animateOnScroll = () => {

&nbsp;           const elements = document.querySelectorAll('.section-title, .pillar-card, .service-card, .testimonial-card');

&nbsp;           

&nbsp;           elements.forEach(element => {

&nbsp;               const elementPosition = element.getBoundingClientRect().top;

&nbsp;               const screenPosition = window.innerHeight / 1.2;

&nbsp;               

&nbsp;               if (elementPosition < screenPosition) {

&nbsp;                   element.classList.add('visible');

&nbsp;               }

&nbsp;           });

&nbsp;       };

&nbsp;       

&nbsp;       // Run animation on load and scroll

&nbsp;       window.addEventListener('load', animateOnScroll);

&nbsp;       window.addEventListener('scroll', animateOnScroll);

&nbsp;   </script>

</body>

</html>

