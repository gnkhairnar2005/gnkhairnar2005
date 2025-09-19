<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ganesh Khairnar - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0f23, #1a1a2e, #16213e);
            color: #e0e6ed;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .hero-section {
            text-align: center;
            padding: 100px 20px;
            position: relative;
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #00d4ff, #ff0080, #00ff80);
            background-size: 200% 200%;
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 20px;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #a0a9c0;
            margin-bottom: 40px;
            opacity: 0;
            animation: fadeInUp 1s ease-out 0.5s forwards;
        }

        .wave-emoji {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
            font-size: 3rem;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-20deg); }
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 50px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: slideInUp 0.8s ease-out;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.3);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #00d4ff;
            margin-bottom: 10px;
        }

        .skills-section {
            margin: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: #fff;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.08);
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            cursor: pointer;
        }

        .skill-item:hover {
            background: rgba(0, 212, 255, 0.1);
            transform: scale(1.05);
            border-color: #00d4ff;
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        .contact-section {
            background: rgba(255, 255, 255, 0.03);
            padding: 60px 40px;
            border-radius: 20px;
            text-align: center;
            margin: 50px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .contact-button {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(45deg, #00d4ff, #0080ff);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            margin: 10px;
            border: none;
            cursor: pointer;
        }

        .contact-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 128, 255, 0.4);
        }

        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #00d4ff;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
            opacity: 0.6;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px) rotate(0deg);
                opacity: 0.6;
            }
            50% {
                transform: translateY(-100px) rotate(180deg);
                opacity: 1;
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

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .github-stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 50px 0;
        }

        .github-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease;
            min-width: 250px;
        }

        .github-card:hover {
            transform: scale(1.02);
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 15px;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
                gap: 15px;
            }
        }

        .typing-animation {
            border-right: 3px solid #00d4ff;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: transparent; }
            51%, 100% { border-color: #00d4ff; }
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #00d4ff;
            margin: 0 auto 30px;
            background: linear-gradient(45deg, #0f0f23, #1a1a2e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
    </style>
</head>
<body>
    <div class="floating-particles" id="particles"></div>
    
    <div class="container">
        <section class="hero-section">
            <div class="profile-image">
                👨‍💻
            </div>
            <h1 class="hero-title">Hi <span class="wave-emoji">👋</span>, I'm Ganesh Khairnar</h1>
            <p class="hero-subtitle typing-animation" id="subtitle">A passionate frontend developer from India</p>
        </section>

        <section class="stats-grid">
            <div class="stat-card">
                <div class="stat-number" data-target="15">0</div>
                <div>Programming Languages</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="50">0</div>
                <div>Projects Completed</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="100">0</div>
                <div>GitHub Contributions</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="2">0</div>
                <div>Years Experience</div>
            </div>
        </section>

        <section class="skills-section">
            <h2 class="section-title">Technologies & Tools</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-icon">📱</span>
                    <div>Android</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🅰️</span>
                    <div>Angular</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚡</span>
                    <div>C/C++</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">☕</span>
                    <div>Java</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🟨</span>
                    <div>JavaScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐧</span>
                    <div>Linux</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🍃</span>
                    <div>MongoDB</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🗄️</span>
                    <div>SQL Server</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐬</span>
                    <div>MySQL</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">💚</span>
                    <div>Node.js</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐍</span>
                    <div>Python</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔥</span>
                    <div>Svelte</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🧠</span>
                    <div>TensorFlow</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">💚</span>
                    <div>Vue.js</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">📊</span>
                    <div>CanvasJS</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔧</span>
                    <div>Git</div>
                </div>
            </div>
        </section>

        <section class="github-stats">
            <div class="github-card">
                <h3>GitHub Activity</h3>
                <p>Building amazing projects and contributing to open source</p>
            </div>
            <div class="github-card">
                <h3>Latest Focus</h3>
                <p>Frontend Development & Modern Web Technologies</p>
            </div>
        </section>

        <section class="contact-section">
            <h2 class="section-title">Let's Connect!</h2>
            <p style="margin-bottom: 30px; font-size: 1.2rem;">Ready to collaborate on amazing projects?</p>
            <a href="mailto:gnkhairnar2005@gmail.com" class="contact-button">📧 Email Me</a>
            <a href="https://linkedin.com/in/ganesh khairnar" target="_blank" class="contact-button">💼 LinkedIn</a>
            <a href="https://github.com/gnkhairnar2005" target="_blank" class="contact-button">🐱 GitHub</a>
        </section>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particleContainer = document.getElementById('particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 4 + 4) + 's';
                particleContainer.appendChild(particle);
            }
        }

        // Animate counter numbers
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-target'));
                const increment = target / 50;
                let current = 0;
                
                const updateCounter = () => {
                    if (current < target) {
                        current += increment;
                        counter.textContent = Math.ceil(current);
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target;
                    }
                };
                
                updateCounter();
            });
        }

        // Typing animation for subtitle
        function typeWriter() {
            const text = "A passionate frontend developer from India";
            const subtitle = document.getElementById('subtitle');
            subtitle.innerHTML = '';
            subtitle.classList.remove('typing-animation');
            
            let i = 0;
            function type() {
                if (i < text.length) {
                    subtitle.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, 100);
                } else {
                    subtitle.classList.add('typing-animation');
                }
            }
            type();
        }

        // Intersection Observer for animations
        function setupScrollAnimations() {
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -100px 0px'
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                    }
                });
            }, observerOptions);

            document.querySelectorAll('.stat-card, .skill-item').forEach(el => {
                el.style.animationPlayState = 'paused';
                observer.observe(el);
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            setTimeout(animateCounters, 1000);
            setTimeout(typeWriter, 2000);
            setupScrollAnimations();
        });

        // Add hover effects to skill items
        document.querySelectorAll('.skill-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.1) rotate(5deg)';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });

        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
