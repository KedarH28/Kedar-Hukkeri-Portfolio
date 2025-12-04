<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kedar Hukkeri - Aspiring Electronics Engineer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }
        
        /* Animated Gradient Background */
        .hero {
            height: 100vh;
            background: linear-gradient(-45deg, #667eea, #764ba2, #f093fb, #f5576c, #4facfe, #00f2fe);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        /* Floating Particles */
        .particles {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }
        
        .particle {
            position: absolute;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }
        
        .hero-content {
            text-align: center;
            color: white;
            z-index: 2;
            position: relative;
            max-width: 800px;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            margin-bottom: 1rem;
            text-shadow: 0 4px 20px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease-out;
        }
        
        .hero p {
            font-size: clamp(1.1rem, 2.5vw, 1.5rem);
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 1s ease-out 0.2s both;
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
        
        /* Navigation */
        .nav {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
        }
        
        .nav-btn {
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.3);
            color: white;
            padding: 12px 24px;
            margin: 0 5px;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .nav-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }
        
        /* Sections */
        section {
            padding: 100px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section-title {
            font-size: clamp(2rem, 4vw, 3rem);
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .skill-card {
            background: rgba(255,255,255,0.95);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            transition: all 0.4s ease;
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            overflow: hidden;
        }
        
        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: left 0.5s;
        }
        
        .skill-card:hover::before {
            left: 100%;
        }
        
        .skill-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 30px 60px rgba(0,0,0,0.2);
        }
        
        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }
        
        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .project-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2.5rem;
            border-radius: 25px;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            transition: all 0.6s ease;
            opacity: 0;
        }
        
        .project-card:hover::before {
            opacity: 1;
            transform: rotate(45deg);
        }
        
        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 35px 70px rgba(102, 126, 234, 0.4);
        }
        
        .project-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }
        
        /* Achievements */
        .achievements {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
            margin-top: 3rem;
        }
        
        .achievement {
            background: linear-gradient(45deg, #f093fb, #f5576c);
            color: white;
            padding: 1.5rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            position: relative;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(240,147,251,0.3);
        }
        
        .achievement:hover {
            transform: scale(1.05) translateY(-5px);
            box-shadow: 0 20px 40px rgba(240,147,251,0.4);
        }
        
        /* Contact */
        .contact {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            color: white;
            text-align: center;
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }
        
        .contact-link {
            color: white;
            text-decoration: none;
            padding: 1rem 2rem;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 50px;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .contact-link:hover {
            background: white;
            color: #00f2fe;
            transform: translateY(-3px);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .nav {
                top: 10px;
                left: 50%;
                transform: translateX(-50%);
            }
            
            .nav-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <div class="nav">
        <button class="nav-btn" onclick="scrollToSection('about')">About</button>
        <button class="nav-btn" onclick="scrollToSection('skills')">Skills</button>
        <button class="nav-btn" onclick="scrollToSection('projects')">Projects</button>
        <button class="nav-btn" onclick="scrollToSection('achievements')">Achievements</button>
        <button class="nav-btn" onclick="scrollToSection('contact')">Contact</button>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="hero">
        <div class="particles" id="particles"></div>
        <div class="hero-content">
            <h1>Kedar Hukkeri</h1>
            <p>Aspiring Electronics & Communication Engineer<br>Building IoT Solutions | Embedded Systems Enthusiast | Hackathon Champion</p>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title">About Me</h2>
        <div style="max-width: 800px; margin: 0 auto; text-align: center; font-size: 1.2rem; line-height: 1.8;">
            <p>An enthusiastic 3rd year B.E. Electronics and Communication Engineering student at BVBCET Hubli with CGPA 9.23. Passionate about IoT, embedded systems, and signal processing. National hackathon champion and global finalist seeking opportunities to innovate and create impactful solutions.</p>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2 class="section-title">Technical Skills</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <div class="skill-icon">⚡</div>
                <h3>Programming</h3>
                <p>C, C++, Python, DSA, Arduino IDE</p>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🔧</div>
                <h3>Hardware</h3>
                <p>Microcontrollers, Cadence, Embedded Systems</p>
            </div>
            <div class="skill-card">
                <div class="skill-icon">📶</div>
                <h3>IoT & Networks</h3>
                <p>IoT Protocols, Networking, Wireless Communication</p>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🎯</div>
                <h3>Soft Skills</h3>
                <p>Team Management, Documentation, Communication</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <h3 class="project-title">Medicine Dispenser IoT</h3>
                <p>Smart automated medicine dispensing system using ESP32 with mobile app integration for elderly care.</p>
            </div>
            <div class="project-card">
                <h3 class="project-title">Smart Helmet Detection</h3>
                <p>IoT-based accident detection helmet with GPS tracking and emergency notification system.</p>
            </div>
            <div class="project-card">
                <h3 class="project-title">Early Guard Warning</h3>
                <p>Community disaster warning system using sensor networks and real-time alerts.</p>
            </div>
            <div class="project-card">
                <h3 class="project-title">CPR Democratization</h3>
                <p>Affordable CPR training device with real-time feedback for mass training programs.</p>
            </div>
        </div>
    </section>

    <!-- Achievements Section -->
    <section id="achievements">
        <h2 class="section-title">Achievements</h2>
        <div class="achievements">
            <div class="achievement">🥇 1st National Hackathon - GIT</div>
            <div class="achievement">🌍 Global Finalist - Infosys</div>
            <div class="achievement">🏆 Incubate Medtech Finalist - IIT Bombay</div>
            <div class="achievement">📚 CGPA 9.23/10</div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <h2 class="section-title" style="color: white;">Let's Connect</h2>
        <p style="font-size: 1.3rem; margin-bottom: 2rem;">Ready to build innovative solutions together?</p>
        <div class="contact-links">
            <a href="mailto:kedarhukkeri2004@gmail.com" class="contact-link">📧 Email</a>
            <a href="tel:+919148368218" class="contact-link">📱 +91 9148368218</a>
            <a href="https://linkedin.com/in/kedarhukkeri" class="contact-link">💼 LinkedIn</a>
            <a href="#" class="contact-link" onclick="scrollToTop()">⬆️ Top</a>
        </div>
        <p style="margin-top: 3rem; opacity: 0.8;">Dharwad, Karnataka, India</p>
    </section>

    <script>
        // Smooth scrolling navigation
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ 
                behavior: 'smooth',
                block: 'start'
            });
        }

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = particle.style.height = (Math.random() * 10 + 5) + 'px';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 4) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Auto-scroll to hero on load
        window.addEventListener('load', () => {
            createParticles();
            
            // Observe all cards for animation
            document.querySelectorAll('.skill-card, .project-card, .achievement').forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(30px)';
                el.style.transition = 'all 0.6s ease';
                observer.observe(el);
            });
        });

        // Parallax effect on scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.hero');
            if (parallax) {
                parallax.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
