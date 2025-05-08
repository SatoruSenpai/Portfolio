<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Portfólio</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #007bff;
            --secondary-color: #6c757d;
            --accent-color: #ff6b6b;
            --dark-color: #1a1a2e;
            --light-color: #f8f9fa;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.8;
            background-color: var(--light-color);
            color: #333;
            position: relative;
        }

        /* Header with Animated Gradient Background */
        header {
            min-height: 500px;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(-45deg, var(--primary-color), var(--accent-color), #4facfe, #00f2fe);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .header-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.4);
            z-index: 1;
        }

        /* Particle Canvas */
        #particles-js {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: 2;
        }

        .header-content {
            position: relative;
            z-index: 3;
        }

        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 8px solid white;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            color: #aaa;
            transition: transform 0.5s ease;
        }

        .profile-img:hover {
            transform: scale(1.1);
        }

        /* Section Backgrounds */
        #about {
            background: linear-gradient(to bottom, #ffffff, #f1f5f9);
            position: relative;
        }

        #skills {
            background: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 80 80" width="80" height="80"%3E%3Cpath fill="%23e9ecef" fill-opacity="0.1" d="M0 0h80v80H0zm40 40a20 20 0 1 0 0-40 20 20 0 0 0 0 40z"/%3E%3C/svg%3E');
            background-size: 80px 80px;
        }

        #projects {
            background: linear-gradient(to bottom, #f1f5f9, #ffffff);
        }

        #experience {
            background: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"%3E%3Cpath fill="%23e9ecef" fill-opacity="0.15" d="M0 0h100v100H0zm50 50a25 25 0 1 0 0-50 25 25 0 0 0 0 50z"/%3E%3C/svg%3E');
            background-size: 100px 100px;
        }

        #contact {
            background: linear-gradient(to bottom, #ffffff, #f1f5f9);
        }

        footer {
            background: linear-gradient(45deg, var(--dark-color), #2c3e50);
            position: relative;
            overflow: hidden;
        }

        /* Navbar */
        .navbar {
            background: white;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: background 0.3s;
        }

        .navbar.scrolled {
            background: rgba(255, 255, 255, 0.95);
        }

        .navbar-nav .nav-link {
            color: var(--dark-color);
            font-weight: 500;
            padding: 15px 20px;
            position: relative;
        }

        .navbar-nav .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s;
        }

        .navbar-nav .nav-link:hover::after,
        .navbar-nav .nav-link.active::after {
            width: 100%;
        }

        .navbar-nav .nav-link:hover,
        .navbar-nav .nav-link.active {
            color: var(--primary-color);
        }

        /* Section Title */
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            font-size: 2.5rem;
            font-weight: 700;
            position: relative;
            color: var(--dark-color);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            margin: 15px auto 0;
            border-radius: 2px;
        }

        /* Cards */
        .card {
            border: none;
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            background: white;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15) !important;
        }

        .project-img {
            height: 200px;
            background-color: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #aaa;
            font-size: 2.5rem;
            position: relative;
            overflow: hidden;
        }

        .project-img::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.3));
            opacity: 0;
            transition: opacity 0.3s;
        }

        .project-img:hover::after {
            opacity: 1;
        }

        .project-tag {
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        /* Timeline */
        .timeline {
            position: relative;
            max-width: 900px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 6px;
            background: linear-gradient(to bottom, var(--primary-color), var(--accent-color));
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
            border-radius: 3px;
        }

        .timeline-item {
            padding: 20px 50px;
            position: relative;
            width: 50%;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .timeline-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 24px;
            height: 24px;
            right: -12px;
            background: white;
            border: 4px solid var(--primary-color);
            top: 20px;
            border-radius: 50%;
            z-index: 1;
            transition: border-color 0.3s;
        }

        .timeline-item:hover::after {
            border-color: var(--accent-color);
        }

        .left {
            left: 0;
        }

        .right {
            left: 50%;
        }

        .left::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 26px;
            width: 0;
            z-index: 1;
            right: 40px;
            border: medium solid white;
            border-width: 12px 0 12px 12px;
            border-color: transparent transparent transparent white;
        }

        .right::after {
            left: -12px;
        }

        .right::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 26px;
            width: 0;
            z-index: 1;
            left: 40px;
            border: medium solid white;
            border-width: 12px 12px 12px 0;
            border-color: transparent white transparent transparent;
        }

        .timeline-date {
            font-weight: 600;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
        }

        /* Contact */
        .contact-icon {
            font-size: 1.8rem;
            color: var(--primary-color);
            transition: color 0.3s;
        }

        .contact-item:hover .contact-icon {
            color: var(--accent-color);
        }

        .form-control {
            border-radius: 10px;
            border: 2px solid #e9ecef;
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        .form-control:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 10px rgba(0, 123, 255, 0.2);
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            border: none;
            border-radius: 10px;
            padding: 12px 30px;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 123, 255, 0.3);
            background: linear-gradient(45deg, var(--accent-color), var(--primary-color));
        }

        /* Footer */
        .footer-links a {
            position: relative;
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-color);
            transition: width 0.3s;
        }

        .footer-links a:hover::after {
            width: 100%;
        }

        .footer-links a:hover {
            color: var(--accent-color);
        }

        .footer-social a {
            transition: transform 0.3s, color 0.3s;
        }

        .footer-social a:hover {
            transform: translateY(-5px);
            color: var(--accent-color);
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

        .animate-on-scroll {
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }

        /* Responsive */
        @media (max-width: 768px) {
            header {
                min-height: 400px;
            }

            .timeline::after {
                left: 31px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 80px;
                padding-right: 30px;
            }

            .timeline-item::before {
                left: 60px;
                border-width: 12px 12px 12px 0;
                border-color: transparent white transparent transparent;
            }

            .left::after, .right::after {
                left: 15px;
            }

            .right {
                left: 0%;
            }

            .profile-img {
                width: 150px;
                height: 150px;
                font-size: 60px;
            }
        }
    </style>
</head>
<body>
    <!-- Cabeçalho -->
    <header id="home" class="text-white">
        <div class="header-overlay"></div>
        <div id="particles-js"></div>
        <div class="container text-center header-content">
            <div class="profile-img mx-auto mb-4 animate-on-scroll" style="animation-delay: 0.2s">
                <i class="fas fa-user"></i>
            </div>
            <h1 class="display-4 fw-bold animate-on-scroll" style="animation-delay: 0.4s">Seu Nome</h1>
            <p class="lead mb-4 animate-on-scroll" style="animation-delay: 0.6s">Desenvolvedor Web</p>
            <div class="d-flex justify-content-center gap-4 animate-on-scroll" style="animation-delay: 0.8s">
                <a href="#" class="text-white fs-4"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-github"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-instagram"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-twitter"></i></a>
            </div>
        </div>
    </header>

    <!-- Navegação -->
    <nav class="navbar navbar-expand-lg sticky-top">
        <div class="container">
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse justify-content-center" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item"><a class="nav-link active" href="#home">Início</a></li>
                    <li class="nav-item"><a class="nav-link" href="#about">Sobre</a></li>
                    <li class="nav-item"><a class="nav-link" href="#skills">Habilidades</a></li>
                    <li class="nav-item"><a class="nav-link" href="#projects">Projetos</a></li>
                    <li class="nav-item"><a class="nav-link" href="#experience">Experiência</a></li>
                    <li class="nav-item"><a class="nav-link" href="#contact">Contato</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Sobre -->
    <section id="about" class="py-5">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Sobre Mim</h2>
            <div class="row align-items-center">
                <div class="col-md-6 mb-4 mb-md-0 animate-on-scroll" style="animation-delay: 0.2s">
                    <p>Olá! Sou um desenvolvedor web apaixonado por criar soluções digitais elegantes e eficientes. Com experiência em desenvolvimento front-end e back-end, busco sempre aprender novas tecnologias e aprimorar minhas habilidades.</p>
                    <p>Meu objetivo é desenvolver aplicações web que não apenas atendam às necessidades dos usuários, mas também proporcionem uma experiência agradável e intuitiva. Sou dedicado, criativo e sempre disposto a enfrentar novos desafios.</p>
                    <p>Quando não estou codificando, gosto de [seus hobbies e interesses]. Acredito que manter um equilíbrio entre vida profissional e pessoal é essencial para a criatividade e produtividade.</p>
                </div>
                <div class="col-md-6 text-center animate-on-scroll" style="animation-delay: 0.4s">
                    <img src="/api/placeholder/500/300" alt="Sobre mim" class="img-fluid rounded-3 shadow-lg">
                </div>
            </div>
        </div>
    </section>

    <!-- Habilidades -->
    <section id="skills" class="py-5">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Minhas Habilidades</h2>
            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
                <div class="col animate-on-scroll" style="animation-delay: 0.2s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fab fa-html5 fa-4x mb-4" style="color: #e34f26;"></i>
                            <h3 class="card-title fs-4 fw-bold">HTML5</h3>
                            <p class="card-text">Desenvolvimento de estruturas web semânticas e acessíveis, garantindo compatibilidade com diferentes navegadores.</p>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.3s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fab fa-css3-alt fa-4x mb-4" style="color: #1572b6;"></i>
                            <h3 class="card-title fs-4 fw-bold">CSS3</h3>
                            <p class="card-text">Estilização avançada com foco em design responsivo, animações e layouts modernos usando Flexbox e Grid.</p>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.4s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fab fa-js fa-4x mb-4" style="color: #f7df1e;"></i>
                            <h3 class="card-title fs-4 fw-bold">JavaScript</h3>
                            <p class="card-text">Programação client-side para criar interatividade e dinamismo em aplicações web, manipulação do DOM e consumo de APIs.</p>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.5s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fab fa-react fa-4x mb-4" style="color: #61dafb;"></i>
                            <h3 class="card-title fs-4 fw-bold">React</h3>
                            <p class="card-text">Desenvolvimento de interfaces de usuário modernas e reativas com componentização e gerenciamento de estado.</p>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.6s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fab fa-node-js fa-4x mb-4" style="color: #339933;"></i>
                            <h3 class="card-title fs-4 fw-bold">Node.js</h3>
                            <p class="card-text">Criação de servidores e APIs RESTful com Express, integração com bancos de dados e autenticação.</p>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.7s">
                    <div class="card h-100 shadow-sm">
                        <div class="card-body text-center">
                            <i class="fas fa-database fa-4x mb-4" style="color: var(--primary-color);"></i>
                            <h3 class="card-title fs-4 fw-bold">Banco de Dados</h3>
                            <p class="card-text">Modelagem e gerenciamento de bancos de dados SQL e NoSQL, incluindo MySQL, PostgreSQL e MongoDB.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projetos -->
    <section id="projects" class="py-5">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Meus Projetos</h2>
            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
                <div class="col animate-on-scroll" style="animation-delay: 0.2s">
                    <div class="card h-100 shadow-sm">
                        <div class="project-img">
                            <i class="fas fa-laptop-code"></i>
                        </div>
                        <div class="card-body">
                            <h3 class="card-title fs-4 fw-bold">E-commerce Responsivo</h3>
                            <p class="card-text">Plataforma de comércio eletrônico com design responsivo, sistema de carrinho e integração com gateway de pagamento.</p>
                            <div class="d-flex flex-wrap gap-2 mb-4">
                                <span class="project-tag">HTML</span>
                                <span class="project-tag">CSS</span>
                                <span class="project-tag">JavaScript</span>
                                <span class="project-tag">Node.js</span>
                            </div>
                            <div class="d-flex justify-content-end gap-3">
                                <a href="#" class="text-primary fw-medium"><i class="fab fa-github me-1"></i> GitHub</a>
                                <a href="#" class="text-primary fw-medium"><i class="fas fa-external-link-alt me-1"></i> Demo</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.3s">
                    <div class="card h-100 shadow-sm">
                        <div class="project-img">
                            <i class="fas fa-mobile-alt"></i>
                        </div>
                        <div class="card-body">
                            <h3 class="card-title fs-4 fw-bold">Aplicativo de Gestão de Tarefas</h3>
                            <p class="card-text">Sistema para organização e gerenciamento de tarefas com categorização, prioridades e notificações.</p>
                            <div class="d-flex flex-wrap gap-2 mb-4">
                                <span class="project-tag">React</span>
                                <span class="project-tag">CSS</span>
                                <span class="project-tag">Firebase</span>
                            </div>
                            <div class="d-flex justify-content-end gap-3">
                                <a href="#" class="text-primary fw-medium"><i class="fab fa-github me-1"></i> GitHub</a>
                                <a href="#" class="text-primary fw-medium"><i class="fas fa-external-link-alt me-1"></i> Demo</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col animate-on-scroll" style="animation-delay: 0.4s">
                    <div class="card h-100 shadow-sm">
                        <div class="project-img">
                            <i class="fas fa-chart-line"></i>
                        </div>
                        <div class="card-body">
                            <h3 class="card-title fs-4 fw-bold">Dashboard Analítico</h3>
                            <p class="card-text">Painel de controle para visualização de dados e métricas de negócios com gráficos interativos e relatórios personalizados.</p>
                            <div class="d-flex flex-wrap gap-2 mb-4">
                                <span class="project-tag">JavaScript</span>
                                <span class="project-tag">Chart.js</span>
                                <span class="project-tag">Node.js</span>
                                <span class="project-tag">MongoDB</span>
                            </div>
                            <div class="d-flex justify-content-end gap-3">
                                <a href="#" class="text-primary fw-medium"><i class="fab fa-github me-1"></i> GitHub</a>
                                <a href="#" class="text-primary fw-medium"><i class="fas fa-external-link-alt me-1"></i> Demo</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experiência -->
    <section id="experience" class="py-5">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Experiência Profissional</h2>
            <div class="timeline">
                <div class="timeline-item left">
                    <div class="card shadow-sm">
                        <div class="card-body">
                            <div class="timeline-date">2022 - Presente</div>
                            <h3 class="card-title fs-4 fw-bold">Desenvolvedor Full Stack</h3>
                            <h4 class="card-subtitle mb-3 text-muted">Empresa Inovadora Ltda.</h4>
                            <p class="card-text">Desenvolvimento e manutenção de aplicações web utilizando React, Node.js e MongoDB. Implementação de novas funcionalidades e otimização de performance.</p>
                        </div>
                    </div>
                </div>
                <div class="timeline-item right">
                    <div class="card shadow-sm">
                        <div class="card-body">
                            <div class="timeline-date">2020 - 2022</div>
                            <h3 class="card-title fs-4 fw-bold">Desenvolvedor Front-end</h3>
                            <h4 class="card-subtitle mb-3 text-muted">Web Solutions S.A.</h4>
                            <p class="card-text">Criação de interfaces responsivas e acessíveis com HTML, CSS e JavaScript. Integração com APIs RESTful e implementação de testes automatizados.</p>
                        </div>
                    </div>
                </div>
                <div class="timeline-item left">
                    <div class="card shadow-sm">
                        <div class="card-body">
                            <div class="timeline-date">2018 - 2020</div>
                            <h3 class="card-title fs-4 fw-bold">Estagiário de Desenvolvimento</h3>
                            <h4 class="card-subtitle mb-3 text-muted">Digital Tech</h4>
                            <p class="card-text">Auxílio no desenvolvimento de sites e aplicações web. Manutenção de código legado e documentação de projetos.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contato -->
    <section id="contact" class="py-5">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Entre em Contato</h2>
            <div class="row">
                <div class="col-md-6 mb-4 mb-md-0">
                    <div class="d-flex flex-column gap-5">
                        <div class="contact-item d-flex gap-4 animate-on-scroll" style="animation-delay: 0.2s">
                            <i class="fas fa-envelope contact-icon"></i>
                            <div>
                                <h3 class="fs-5 fw-bold">Email</h3>
                                <p><a href="mailto:seuemail@exemplo.com" class="text-decoration-none">seuemail@exemplo.com</a></p>
                            </div>
                        </div>
                        <div class="contact-item d-flex gap-4 animate-on-scroll" style="animation-delay: 0.3s">
                            <i class="fas fa-phone contact-icon"></i>
                            <div>
                                <h3 class="fs-5 fw-bold">Telefone</h3>
                                <p>(XX) XXXXX-XXXX</p>
                            </div>
                        </div>
                        <div class="contact-item d-flex gap-4 animate-on-scroll" style="animation-delay: 0.4s">
                            <i class="fas fa-map-marker-alt contact-icon"></i>
                            <div>
                                <h3 class="fs-5 fw-bold">Localização</h3>
                                <p>Sua Cidade, Estado</p>
                            </div>
                        </div>
                        <div class="contact-item d-flex gap-4 animate-on-scroll" style="animation-delay: 0.5s">
                            <i class="fas fa-clock contact-icon"></i>
                            <div>
                                <h3 class="fs-5 fw-bold">Disponibilidade</h3>
                                <p>Segunda a Sexta, 9h às 18h</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 animate-on-scroll" style="animation-delay: 0.6s">
                    <form id="contactForm">
                        <div class="mb-4">
                            <label for="name" class="form-label fw-medium">Nome</label>
                            <input type="text" class="form-control" id="name" name="name" required>
                        </div>
                        <div class="mb-4">
                            <label for="email" class="form-label fw-medium">Email</label>
                            <input type="email" class="form-control" id="email" name="email" required>
                        </div>
                        <div class="mb-4">
                            <label for="subject" class="form-label fw-medium">Assunto</label>
                            <input type="text" class="form-control" id="subject" name="subject" required>
                        </div>
                        <div class="mb-4">
                            <label for="message" class="form-label fw-medium">Mensagem</label>
                            <textarea class="form-control" id="message" name="message" rows="6" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Enviar Mensagem</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Rodapé -->
    <footer class="text-white py-5">
        <div class="container text-center">
            <h3 class="fw-bold animate-on-scroll">Seu Nome</h3>
            <p class="mb-4 animate-on-scroll" style="animation-delay: 0.2s">Desenvolvedor Web apaixonado por criar soluções digitais inovadoras e funcionais.</p>
            <div class="footer-social d-flex justify-content-center gap-4 mb-4 animate-on-scroll" style="animation-delay: 0.4s">
                <a href="#" class="text-white fs-4"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-github"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-instagram"></i></a>
                <a href="#" class="text-white fs-4"><i class="fab fa-twitter"></i></a>
            </div>
            <div class="footer-links d-flex justify-content-center gap-5 mb-4 animate-on-scroll" style="animation-delay: 0.6s">
                <a href="#home">Início</a>
                <a href="#about">Sobre</a>
                <a href="#projects">Projetos</a>
                <a href="#contact">Contato</a>
            </div>
            <p class="animate-on-scroll" style="animation-delay: 0.8s">© 2025 - Todos os direitos reservados</p>
        </div>
    </footer>

    <!-- Particles.js -->
    <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Initialize Particles.js
        particlesJS('particles-js', {
            particles: {
                number: { value: 80, density: { enable: true, value_area: 800 } },
                color: { value: '#ffffff' },
                shape: { type: 'circle' },
                opacity: { value: 0.5, random: false },
                size: { value: 3, random: true },
                line_linked: { enable: true, distance: 150, color: '#ffffff', opacity: 0.4, width: 1 },
                move: { enable: true, speed: 2, direction: 'none', random: false, straight: false, out_mode: 'out', bounce: false }
            },
            interactivity: {
                detect_on: 'canvas',
                events: { onhover: { enable: true, mode: 'grab' }, onclick: { enable: true, mode: 'push' }, resize: true },
                modes: { grab: { distance: 140, line_linked: { opacity: 1 } }, push: { particles_nb: 4 } }
            },
            retina_detect: true
        });

        // Navegação suave
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
                document.querySelectorAll('.nav-link').forEach(link => {
                    link.classList.remove('active');
                });
                this.classList.add('active');
            });
        });

        // Destacar menu ativo e navbar scroll
        window.addEventListener('scroll', function() {
            let current = '';
            const sections = document.querySelectorAll('section');
            const navHeight = document.querySelector('nav').offsetHeight;
            const navbar = document.querySelector('.navbar');

            sections.forEach(section => {
                const sectionTop = section.offsetTop - navHeight - 50;
                if (pageYOffset >= sectionTop) {
                    current = section.getAttribute('id');
                }
            });

            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });

            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Animações de scroll
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    if (entry.target.classList.contains('animate-on-scroll')) {
                        entry.target.style.animationPlayState = 'running';
                    }
                }
            });
        }, { threshold: 0.2 });

        document.querySelectorAll('.timeline-item, .animate-on-scroll').forEach(element => {
            observer.observe(element);
        });

        // Formulário de contato
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('name').value;
            alert(`Obrigado, ${name}! Sua mensagem foi enviada com sucesso.`);
            this.reset();
        });
    </script>
</body>
</html>
