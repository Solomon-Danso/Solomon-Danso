<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solomon Danso | Full Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto+Mono:wght@300;400;500&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
    <style>
        :root {
            --primary: #6366f1;
            --primary-light: #818cf8;
            --secondary: #10b981;
            --dark: #0f172a;
            --darker: #0a0e1a;
            --light: #f1f5f9;
            --gray: #94a3b8;
            --accent: #f43f5e;
            --card-bg: rgba(30, 41, 59, 0.4);
            --glow: 0 0 10px rgba(99, 102, 241, 0.7);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
        }

        .greeting {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .typing-container {
            min-height: 80px;
            margin-bottom: 30px;
        }

        .typing-text {
            font-size: 2rem;
            font-weight: 600;
            color: var(--light);
        }

        .cursor {
            display: inline-block;
            width: 3px;
            height: 40px;
            background-color: var(--primary);
            margin-left: 5px;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .description {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 40px;
            max-width: 600px;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(to right, var(--primary), var(--primary-light));
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 500;
            transition: all 0.3s;
            box-shadow: var(--glow);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: var(--glow);
        }

        .skill-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .skill-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .badge {
            padding: 8px 15px;
            background: rgba(99, 102, 241, 0.2);
            border-radius: 20px;
            font-size: 0.9rem;
            color: var(--light);
            transition: all 0.3s;
        }

        .badge:hover {
            background: var(--primary);
            transform: scale(1.05);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--glow);
        }

        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .project-content {
            padding: 20px;
        }

        .project-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .project-desc {
            color: var(--gray);
            margin-bottom: 20px;
        }

        .project-link {
            display: inline-block;
            padding: 8px 20px;
            background: var(--primary);
            color: white;
            text-decoration: none;
            border-radius: 20px;
            font-size: 0.9rem;
            transition: all 0.3s;
        }

        .project-link:hover {
            background: var(--primary-light);
            transform: scale(1.05);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .contact-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .contact-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--glow);
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .contact-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .contact-info {
            color: var(--gray);
        }

        .contact-link {
            color: var(--primary);
            text-decoration: none;
            transition: color 0.3s;
        }

        .contact-link:hover {
            color: var(--primary-light);
            text-decoration: underline;
        }

        footer {
            background: var(--darker);
            padding: 40px 0;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: var(--card-bg);
            color: var(--light);
            border-radius: 50%;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .social-link:hover {
            background: var(--primary);
            transform: translateY(-5px);
        }

        .copyright {
            color: var(--gray);
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .typing-text {
                font-size: 1.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .projects-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animation utilities */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s, transform 0.5s;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Stats section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .stat-card {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        .stat-label {
            color: var(--gray);
            font-size: 1rem;
        }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    
    <header>
        <div class="container">
            <nav>
                <div class="logo">Solomon.D</div>
                <div class="nav-links">
                    <a href="#about">About</a>
                    <a href="#skills">Skills</a>
                    <a href="#projects">Projects</a>
                    <a href="#contact">Contact</a>
                </div>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="greeting">Hi there 👋</div>
                <h1>Solomon Danso</h1>
                <div class="typing-container">
                    <span class="typing-text"></span>
                    <span class="cursor"></span>
                </div>
                <p class="description">I love providing solutions to business through technology. Here's a glimpse of my favorite tools, languages, and frameworks that I love working with!</p>
                <a href="#contact" class="btn">Get in Touch</a>
            </div>
        </div>
    </section>

    <section id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <p>I'm a passionate full-stack developer with expertise in various technologies and frameworks. I enjoy creating innovative solutions and bringing ideas to life through code.</p>
            </div>
        </div>
    </section>

    <section id="skills">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-grid">
                <div class="skill-category fade-in">
                    <h3 class="skill-title">Programming Languages</h3>
                    <div class="skill-badges">
                        <span class="badge">C</span>
                        <span class="badge">C++</span>
                        <span class="badge">C#</span>
                        <span class="badge">Java</span>
                        <span class="badge">JavaScript</span>
                        <span class="badge">Python</span>
                        <span class="badge">PHP</span>
                        <span class="badge">SQL</span>
                        <span class="badge">HTML</span>
                        <span class="badge">CSS</span>
                    </div>
                </div>

                <div class="skill-category fade-in">
                    <h3 class="skill-title">Frameworks & Libraries</h3>
                    <div class="skill-badges">
                        <span class="badge">React</span>
                        <span class="badge">React Native</span>
                        <span class="badge">Next.js</span>
                        <span class="badge">Express.js</span>
                        <span class="badge">Laravel</span>
                        <span class="badge">Spring Boot</span>
                        <span class="badge">.NET</span>
                        <span class="badge">Electron</span>
                    </div>
                </div>

                <div class="skill-category fade-in">
                    <h3 class="skill-title">Databases & Cloud</h3>
                    <div class="skill-badges">
                        <span class="badge">MongoDB</span>
                        <span class="badge">MySQL</span>
                        <span class="badge">Oracle</span>
                        <span class="badge">SQLite</span>
                        <span class="badge">MSSQL</span>
                        <span class="badge">phpMyAdmin</span>
                        <span class="badge">cPanel</span>
                    </div>
                </div>

                <div class="skill-category fade-in">
                    <h3 class="skill-title">Tools & Software</h3>
                    <div class="skill-badges">
                        <span class="badge">Git</span>
                        <span class="badge">Docker</span>
                        <span class="badge">Kubernetes</span>
                        <span class="badge">Android Studio</span>
                        <span class="badge">VS Code</span>
                        <span class="badge">Postman</span>
                        <span class="badge">Linux</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects">
        <div class="container">
            <h2 class="section-title">My Projects</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <img src="https://mainapi.hydottech.com/storage/SN3giQXsccOwGy5RbmFleXcrzpdYjNGgZ5ZwVVMi.png" alt="Hydot Commerce System" class="project-img">
                    <div class="project-content">
                        <h3 class="project-title">Hydot Commerce System</h3>
                        <p class="project-desc">A complete payment-enabled e-commerce system with modern UI and robust functionality.</p>
                        <a href="https://web.commerce.hydottech.com/" class="project-link">View Project</a>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <img src="https://via.placeholder.com/600x400/6366f1/ffffff?text=Project+2" alt="Project 2" class="project-img">
                    <div class="project-content">
                        <h3 class="project-title">Mobile App Development</h3>
                        <p class="project-desc">Cross-platform mobile applications built with React Native for various business needs.</p>
                        <a href="#" class="project-link">View Project</a>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <img src="https://via.placeholder.com/600x400/10b981/ffffff?text=Project+3" alt="Project 3" class="project-img">
                    <div class="project-content">
                        <h3 class="project-title">WebRTC Solutions</h3>
                        <p class="project-desc">Real-time communication applications leveraging WebRTC technology for seamless video and audio calls.</p>
                        <a href="#" class="project-link">View Project</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="stats">
        <div class="container">
            <h2 class="section-title">My GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-card fade-in">
                    <div class="stat-number">117+</div>
                    <div class="stat-label">Public Repositories</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-number">1.5M+</div>
                    <div class="stat-label">Lines of Code</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-card fade-in">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-grid">
                <div class="contact-card fade-in">
                    <div class="contact-icon">
                        <i class="fas fa-phone"></i>
                    </div>
                    <h3 class="contact-title">Phone</h3>
                    <p class="contact-info">
                        <a href="https://wa.me/233599626272" class="contact-link">+233 599626272</a>
                    </p>
                </div>

                <div class="contact-card fade-in">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <h3 class="contact-title">Email</h3>
                    <p class="contact-info">
                        <a href="mailto:solomondanso2023@gmail.com" class="contact-link">solomondanso2023@gmail.com</a>
                    </p>
                </div>

                <div class="contact-card fade-in">
                    <div class="contact-icon">
                        <i class="fas fa-globe"></i>
                    </div>
                    <h3 class="contact-title">Website</h3>
                    <p class="contact-info">
                        <a href="https://hydottech.com" class="contact-link">hydottech.com</a>
                    </p>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                <a href="#" class="social-link"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
            </div>
            <p class="copyright">© 2023 Solomon Danso. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Particles.js configuration
        particlesJS('particles-js', {
            particles: {
                number: { value: 80, density: { enable: true, value_area: 800 } },
                color: { value: "#6366f1" },
                shape: { type: "circle" },
                opacity: { value: 0.5, random: true },
                size: { value: 3, random: true },
                line_linked: {
                    enable: true,
                    distance: 150,
                    color: "#6366f1",
                    opacity: 0.4,
                    width: 1
                },
                move: {
                    enable: true,
                    speed: 2,
                    direction: "none",
                    random: true,
                    straight: false,
                    out_mode: "out",
                    bounce: false
                }
            },
            interactivity: {
                detect_on: "canvas",
                events: {
                    onhover: { enable: true, mode: "repulse" },
                    onclick: { enable: true, mode: "push" },
                    resize: true
                }
            },
            retina_detect: true
        });

        // Typing animation
        const typingText = document.querySelector('.typing-text');
        const phrases = [
            'Frontend Developer',
            'Backend Developer',
            'FullStack Developer',
            'Mobile App Developer'
        ];
        let phraseIndex = 0;
        let letterIndex = 0;
        let currentPhrase = '';
        let isDeleting = false;
        let isEnd = false;

        function type() {
            isEnd = false;
            typingText.textContent = currentPhrase;

            if (!isDeleting && letterIndex < phrases[phraseIndex].length) {
                currentPhrase += phrases[phraseIndex].charAt(letterIndex);
                letterIndex++;
                typingText.textContent = currentPhrase;
            }

            if (isDeleting && letterIndex > 0) {
                currentPhrase = currentPhrase.slice(0, -1);
                letterIndex--;
                typingText.textContent = currentPhrase;
            }

            if (!isDeleting && letterIndex === phrases[phraseIndex].length) {
                isEnd = true;
                isDeleting = true;
                setTimeout(type, 1500);
            } else if (isDeleting && letterIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                setTimeout(type, 500);
            } else {
                const typeSpeed = isDeleting ? 80 : 150;
                setTimeout(type, isEnd ? typeSpeed * 3 : typeSpeed);
            }
        }

        // Start typing animation
        setTimeout(type, 1000);

        // Scroll animations
        function checkFade() {
            const fadeElements = document.querySelectorAll('.fade-in');
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementBottom = element.getBoundingClientRect().bottom;
                const isVisible = (elementTop < window.innerHeight - 100) && (elementBottom > 0);
                if (isVisible) {
                    element.classList.add('visible');
                }
            });
        }

        window.addEventListener('scroll', checkFade);
        window.addEventListener('load', checkFade);
    </script>
</body>
</html>
