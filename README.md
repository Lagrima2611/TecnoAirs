<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TecnoAir - Portafolio de Servicios</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        .header {
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            color: white;
            padding: 3rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="20" cy="20" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="80" cy="40" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="40" cy="80" r="1" fill="rgba(255,255,255,0.1)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .logo {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: fadeInDown 1s ease-out;
        }

        .subtitle {
            font-size: 1.3rem;
            opacity: 0.9;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .header-title {
            font-size: 2.5rem;
            font-weight: bold;
            margin-top: 2rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        /* Navigation */
        .nav {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .nav-list {
            display: flex;
            justify-content: center;
            list-style: none;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .nav-item {
            padding: 0.5rem 1.5rem;
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: all 0.3s ease;
            font-weight: 500;
            cursor: pointer;
        }

        .nav-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(247, 147, 30, 0.4);
        }

        /* Main content */
        .main-content {
            background: white;
            margin: 2rem 0;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .section {
            padding: 3rem;
            border-bottom: 1px solid #eee;
        }

        .section:last-child {
            border-bottom: none;
        }

        .section-title {
            font-size: 2.5rem;
            color: #ff6b35;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            border-radius: 2px;
        }

        .intro-text {
            font-size: 1.1rem;
            line-height: 1.8;
            text-align: justify;
            margin-bottom: 2rem;
            color: #555;
        }

        /* How we work section */
        .work-process {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .process-item {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 2rem;
            border-radius: 15px;
            border-left: 4px solid #ff6b35;
            transition: all 0.3s ease;
        }

        .process-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .process-title {
            font-size: 1.3rem;
            color: #ff6b35;
            margin-bottom: 1rem;
            font-weight: bold;
        }

        .process-description {
            color: #666;
            line-height: 1.6;
        }

        /* Services sections */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .service-card {
            background: white;
            border: 2px solid #f0f0f0;
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            border-color: #ff6b35;
        }

        .service-category {
            font-size: 1.4rem;
            color: #ff6b35;
            margin-bottom: 1.5rem;
            font-weight: bold;
        }

        .service-list {
            list-style: none;
        }

        .service-item {
            padding: 0.8rem 0;
            border-bottom: 1px solid #f0f0f0;
            position: relative;
            padding-left: 1.5rem;
        }

        .service-item::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #28a745;
            font-weight: bold;
        }

        .service-item:last-child {
            border-bottom: none;
        }

        .service-sublist {
            list-style: none;
            margin-left: 1rem;
            margin-top: 0.5rem;
        }

        .service-subitem {
            padding: 0.3rem 0;
            color: #666;
            font-size: 0.9rem;
            position: relative;
            padding-left: 1rem;
        }

        .service-subitem::before {
            content: '•';
            position: absolute;
            left: 0;
            color: #ff6b35;
        }

        /* Contact section */
        .contact {
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            color: white;
            text-align: center;
            padding: 3rem;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            min-width: 250px;
        }

        .contact-item:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.2);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .contact-text {
            font-size: 1.2rem;
            font-weight: bold;
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

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

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .logo {
                font-size: 2.5rem;
            }
            
            .header-title {
                font-size: 2rem;
            }
            
            .section {
                padding: 2rem 1rem;
            }
            
            .nav-list {
                gap: 1rem;
            }
            
            .contact-info {
                flex-direction: column;
                align-items: center;
            }

            .snowflake-img {
                height: 5rem;
                margin-right: 1rem;
            }

            .ramirez {
                font-size: 2rem;
            }
        }

        /* Scroll to top button */
        .scroll-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            color: white;
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 1.5rem;
            cursor: pointer;
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(100px);
            z-index: 1000;
        }

        .scroll-top.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .scroll-top:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(247, 147, 30, 0.4);
        }

        .snowflake-img {
            height: 8.5rem; /* Ajusta este valor según el alto total del bloque de texto */
            margin-right: 2.5rem;
            margin-left: 0;
            display: block;
        }

        .ramirez {
            font-size: 2.5rem;
            font-weight: 600;
            text-align: center;
            margin-bottom: 0.5rem;
            line-height: 1.1;
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="container" style="display: flex; align-items: center; justify-content: center;">
            <!-- Copo de nieve a la izquierda -->
            <img src="img/copo de nieve.png" alt="Copo de nieve" class="snowflake-img">
            <!-- Bloque de texto -->
            <div class="header-content">
                <h1 class="logo">TECNOAIR</h1>
                <div class="ramirez">Ramirez</div>
                <p class="subtitle">Prestadora de servicios en refrigeración y aires acondicionados</p>
                <h2 class="header-title">PORTAFOLIO DE SERVICIOS</h2>
            </div>
        </div>
    </header>

    <nav class="nav">
        <div class="container">
            <ul class="nav-list">
                <li><a href="#introduccion" class="nav-item">Introducción</a></li>
                <li><a href="#como-trabajamos" class="nav-item">Cómo Trabajamos</a></li>
                <li><a href="#aire-acondicionado" class="nav-item">Aire Acondicionado</a></li>
                <li><a href="#pintura" class="nav-item">Pintura</a></li>
                <li><a href="#seguridad" class="nav-item">Seguridad</a></li>
                <li><a href="#contacto" class="nav-item">Contacto</a></li>
            </ul>
        </div>
    </nav>

    <div class="main-content">
        <div class="container">
            <section id="introduccion" class="section fade-in">
                <h2 class="section-title">INTRODUCCIÓN</h2>
                <p class="intro-text">
                    En TecnoAir, nos especializamos en brindar soluciones profesionales y confiables en diversas áreas clave para el confort y seguridad de su hogar o negocio. Ofrecemos servicios integrales de refrigeración y aire acondicionado, incluyendo mantenimiento preventivo y correctivo, para asegurar el rendimiento óptimo y la eficiencia de sus equipos.
                </p>
                <p class="intro-text">
                    Además, somos expertos en trabajos de pintura para apartamentos y casas, comprometidos en entregar acabados de alta calidad que renuevan y embellecen cualquier espacio. También proporcionamos soluciones avanzadas de seguridad a través de la instalación de cámaras de videovigilancia, garantizando la protección de sus propiedades con la más alta tecnología.
                </p>
                <p class="intro-text">
                    Nuestro enfoque está basado en la excelencia, la puntualidad y la satisfacción del cliente, ofreciendo servicios personalizados y realizados por un equipo técnico altamente capacitado. Con TecnoAir, usted puede confiar en un portafolio de servicios que combina confort, seguridad y estética para su bienestar.
                </p>
            </section>

            <section id="como-trabajamos" class="section fade-in">
                <h2 class="section-title">¿CÓMO TRABAJAMOS?</h2>
                <p class="intro-text">
                    En TecnoAir, nos enorgullecemos de ofrecer un servicio integral y profesional en cada uno de nuestros proyectos, desde la primera consulta hasta la finalización del trabajo. Nos guiamos por un enfoque basado en la calidad, la transparencia y la satisfacción del cliente.
                </p>
                <div class="work-process">
                    <div class="process-item">
                        <h3 class="process-title">Asesoría Personalizada</h3>
                        <p class="process-description">
                            Todo comienza con una evaluación detallada de sus necesidades. Nuestro equipo técnico realiza una inspección inicial, ya sea para sistemas de aire acondicionado, refrigeración, pintura o cámaras de seguridad. Escuchamos sus requerimientos, identificamos las áreas de mejora y le brindamos una solución personalizada que se ajuste a su presupuesto y expectativas.
                        </p>
                    </div>
                    <div class="process-item">
                        <h3 class="process-title">Planificación y Presupuesto</h3>
                        <p class="process-description">
                            Después de la evaluación, desarrollamos un plan de trabajo detallado. Le presentamos un presupuesto transparente, sin costos ocultos, donde especificamos cada paso del proyecto. Nuestra prioridad es que usted esté informado en todo momento y se sienta cómodo con la inversión que está realizando.
                        </p>
                    </div>
                    <div class="process-item">
                        <h3 class="process-title">Ejecución Eficiente</h3>
                        <p class="process-description">
                            Nuestro equipo está compuesto por técnicos altamente capacitados y especializados en cada área de servicio. Ya sea que estemos realizando mantenimiento preventivo o correctivo de su sistema de aire acondicionado, refrigeración aplicando pintura en su hogar, o instalando cámaras de seguridad, trabajamos con precisión, utilizando materiales y equipos de alta calidad para asegurar resultados duraderos.
                        </p>
                    </div>
                    <div class="process-item">
                        <h3 class="process-title">Finalización y Revisión</h3>
                        <p class="process-description">
                            Una vez que se completa el proyecto, realizamos una revisión final junto con el cliente. Verificamos que todo funcione correctamente, que los acabados sean los esperados y que las instalaciones estén en perfectas condiciones. No nos vamos hasta que usted esté completamente satisfecho.
                        </p>
                    </div>
                    <div class="process-item">
                        <h3 class="process-title">Soporte Post-servicio</h3>
                        <p class="process-description">
                            En TecnoAir, nuestro compromiso no termina con la entrega del proyecto. Ofrecemos soporte post-servicio y estamos disponibles para resolver cualquier duda o atender cualquier imprevisto que pueda surgir después de la instalación o reparación.
                        </p>
                    </div>
                    <div class="process-item">
                        <h3 class="process-title">Supervisión Continua</h3>
                        <p class="process-description">
                            Durante todo el proceso, supervisamos de cerca el trabajo realizado, garantizando que se cumplan los plazos establecidos y que los estándares de calidad sean siempre los más altos. Nos aseguramos de minimizar cualquier inconveniente durante el proceso para que el impacto en su hogar o negocio sea el menor posible.
                        </p>
                    </div>
                </div>
            </section>

            <section id="aire-acondicionado" class="section fade-in">
                <h2 class="section-title">SERVICIOS DE AIRE ACONDICIONADO</h2>
                <div class="services-grid">
                    <div class="service-card">
                        <h3 class="service-category">Mantenimiento</h3>
                        <ul class="service-list">
                            <li class="service-item">
                                Servicio Básico de Limpieza
                                <ul class="service-sublist">
                                    <li class="service-subitem">1 unidad</li>
                                    <li class="service-subitem">2 unidades</li>
                                    <li class="service-subitem">3 unidades en adelante</li>
                                </ul>
                            </li>
                            <li class="service-item">
                                Visita Técnica
                                <ul class="service-sublist">
                                    <li class="service-subitem">Diagnóstico y evaluación del estado del equipo, identificando posibles fallos o recomendaciones.</li>
                                </ul>
                            </li>
                            <li class="service-item">
                                Recarga de Gas con Reparación de Fuga
                                <ul class="service-sublist">
                                    <li class="service-subitem">Incluye la reparación de la fuga, con el gas no incluido en el costo.</li>
                                </ul>
                            </li>
                        </ul>
                    </div>

                    <div class="service-card">
                        <h3 class="service-category">Instalación de Equipos (Sin Materiales)</h3>
                        <ul class="service-list">
                            <li class="service-item">
                                Instalación con Preinstalación Realizada
                                <ul class="service-sublist">
                                    <li class="service-subitem">Montaje de equipos en un sistema de climatización preexistente.</li>
                                </ul>
                            </li>
                            <li class="service-item">
                                Instalación sin Preinstalación (Sin Arreglos de Albañilería)
                                <ul class="service-sublist">
                                    <li class="service-subitem">Equipos hasta 2900 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 4600 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 6500 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 8000 frigorías</li>
                                    <li class="service-subitem">Instalación de equipos hasta 3 TR</li>
                                    <li class="service-subitem">Instalación de equipos hasta 6 TR</li>
                                </ul>
                            </li>
                            <li class="service-item">
                                Adicional por Metro de Cañería
                                <ul class="service-sublist">
                                    <li class="service-subitem">Se adiciona por cada metro de cañería extra, sin incluir materiales.</li>
                                </ul>
                            </li>
                        </ul>
                    </div>

                    <div class="service-card">
                        <h3 class="service-category">Desinstalación de Equipos</h3>
                        <ul class="service-list">
                            <li class="service-item">
                                Desinstalación de Equipos (Sin Arreglos de Albañilería)
                                <ul class="service-sublist">
                                    <li class="service-subitem">Equipos hasta 2900 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 4600 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 6500 frigorías</li>
                                    <li class="service-subitem">Equipos hasta 8000 frigorías</li>
                                </ul>
                            </li>
                        </ul>
                    </div>

                    <div class="service-card">
                        <h3 class="service-category">Repuestos y Cambios de Componentes</h3>
                        <ul class="service-list">
                            <li class="service-item">Cambio de Filtro Molecular</li>
                            <li class="service-item">Cambio de Válvula de Expansión</li>
                            <li class="service-item">Cambio de Serpentina</li>
                            <li class="service-item">Cambio de Válvula Inversora</li>
                            <li class="service-item">Cambio de Capacitor</li>
                            <li class="service-item">Cambio de Plaqueta Universal</li>
                            <li class="service-item">Cambio de Compresor</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section id="pintura" class="section fade-in">
                <h2 class="section-title">SERVICIOS DE PINTURA PARA APARTAMENTOS Y CASAS</h2>
                <p class="intro-text">
                    Transformamos sus espacios con trabajos de pintura de alta calidad, realizados por profesionales con amplia experiencia.
                </p>
                <div class="services-grid">
                    <div class="service-card">
                        <h3 class="service-category">Pintura Interior y Exterior</h3>
                        <p class="process-description">
                            Realizamos proyectos de pintura para renovar paredes interiores y exteriores, usando materiales de primera calidad y técnicas especializadas.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Preparación de Superficies</h3>
                        <p class="process-description">
                            Limpieza, lijado y reparación de paredes para asegurar un acabado perfecto.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Personalización de Colores y Acabados</h3>
                        <p class="process-description">
                            Ofrecemos una amplia gama de colores y acabados para satisfacer sus preferencias estéticas.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Cumplimiento de Plazos</h3>
                        <p class="process-description">
                            Nos comprometemos a finalizar el trabajo dentro de los tiempos acordados, minimizando molestias para usted.
                        </p>
                    </div>
                </div>
            </section>

            <section id="seguridad" class="section fade-in">
                <h2 class="section-title">INSTALACIÓN DE CÁMARAS DE SEGURIDAD</h2>
                <p class="intro-text">
                    Proteja su hogar o negocio con la instalación de sistemas de videovigilancia de última tecnología. Nuestro equipo garantiza una instalación eficiente y segura, adaptada a sus necesidades.
                </p>
                <div class="services-grid">
                    <div class="service-card">
                        <h3 class="service-category">Instalación de Cámaras de Seguridad</h3>
                        <p class="process-description">
                            Instalación de cámaras de seguridad con alta resolución y sistema de monitoreo remoto.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Asesoramiento Técnico</h3>
                        <p class="process-description">
                            Evaluamos su espacio para determinar las mejores ubicaciones para las cámaras, garantizando una cobertura óptima.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Mantenimiento y Reparación</h3>
                        <p class="process-description">
                            Ofrecemos mantenimiento periódico y servicio técnico para asegurar el funcionamiento continuo y sin fallos de su sistema de seguridad.
                        </p>
                    </div>
                    <div class="service-card">
                        <h3 class="service-category">Integración de Sistemas</h3>
                        <p class="process-description">
                            Instalación de sistemas integrados para monitoreo a través de aplicaciones móviles o software especializado.
                        </p>
                    </div>
                </div>
            </section>
        </div>
    </div>

    <section id="contacto" class="contact">
        <div class="container">
            <h2 class="section-title" style="color: white;">CONTACTO</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">✉️</div>
                    <p style="font-size: 0.9rem; margin-bottom: 0.5rem;">ESCRÍBENOS A:</p>
                    <p class="contact-text">ramireztecnoair@gmail.com</p>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">📞</div>
                    <p style="font-size: 0.9rem; margin-bottom: 0.5rem;">LLÁMANOS A:</p>
                    <p class="contact-text">+54 9 11 2819-9870</p>
                </div>
            </div>
        </div>
    </section>

    <button class="scroll-top" onclick="scrollToTop()">↑</button>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('.nav-item').forEach(item => {
            item.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href').substring(1);
                const targetSection = document.getElementById(targetId);
                if (targetSection) {
                    targetSection.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all fade-in elements
        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Scroll to top functionality
        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // Show/hide scroll to top button
        window.addEventListener('scroll', function() {
            const scrollButton = document.querySelector('.scroll-top');
            if (window.pageYOffset > 300) {
                scrollButton.classList.add('visible');
            } else {
                scrollButton.classList.remove('visible');
            }
        });

        // Add hover effects to service cards
        document.querySelectorAll('.service-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Add parallax effect to header
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const header = document.querySelector('.header');
            if (header) {
                header.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });

        // Add loading animation
        window.addEventListener('load', function() {
            document.body.style.opacity = '1';
        });

        // Contact button animations
        document.querySelectorAll('.contact-item').forEach(item => {
            item.addEventListener('click', function() {
                this.style.transform = 'scale(0.95)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 150);
            });
        });
    </script>
</body>
</html>
