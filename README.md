<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kedar Hukkeri | Electronics Engineer | IoT Specialist</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            overflow-x: hidden;
        }
        
        /* Neon Gradient Background */
        .hero {
            min-height: 100vh;
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
            background-attachment: fixed;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 80%, rgba(120,119,198,0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255,119,198,0.3) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(120,219,255,0.2) 0%, transparent 50%);
            animation: pulse 20s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.05); }
        }
        
        /* Navigation */
        .nav {
            position: fixed;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 1000;
            backdrop-filter: blur(20px);
            background: rgba(255,255,255,0.1);
            border-radius: 50px;
            padding: 12px 24px;
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .nav-btn {
            background: transparent;
            color: #fff;
            border: none;
            padding: 12px 20px;
            margin: 0 8px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 500;
            font-size: 14px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .nav-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }
        
        .nav-btn:hover::before {
            left: 100%;
        }
        
        .nav-btn:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }
        
        /* Hero Content */
        .hero-content {
            text-align: center;
            z-index: 2;
            max-width: 900px;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 800;
            background: linear-gradient(45deg, #00f5ff, #ff00ff, #00ff88);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #00f5ff); }
            to { filter: drop-shadow(0 0 30px #ff00ff); }
        }
        
        .hero-subtitle {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: rgba(255,255,255,0.9);
            margin-bottom: 2rem;
            font-weight: 400;
        }
        
        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .cta-btn {
            padding: 16px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .cta-primary {
            background: linear-gradient(45deg, #00f5ff, #0099ff);
            color: #000;
            box-shadow: 0 10px 30px rgba(0,245,255,0.4);
        }
        
        .cta-secondary {
            background: transparent;
            color: #fff;
            border: 2px solid rgba(255,255,255,0.3);
        }
        
        .cta-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        /* Sections */
        section {
            padding: 120px 20px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .section-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            text-align: center;
            margin-bottom: 4rem;
            font-weight: 700;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Stats */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .stat {
            text-align: center;
            padding: 2rem;
        }
        
        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(45deg, #00f5ff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: block;
        }
        
        /* Timeline */
        .timeline {
            display: grid;
            gap: 3rem;
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .timeline-item {
            display: grid;
            grid-template-columns: 80px 1fr;
            gap: 2rem;
            align-items: start;
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s ease;
        }
        
        .timeline-item.visible {
            opacity: 1;
            transform: translateX(0);
        }
        
        .timeline-dot {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00f5ff, #ff00ff);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
            color: #000;
            box-shadow: 0 10px 30px rgba(0,245,255,0.4);
        }
        
        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: rgba(255,255,255,0.95);
            border-radius: 24px;
            padding: 2.5rem;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            border: 1px solid rgba(0,0,0,0.1);
            backdrop-filter: blur(10px);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #00f5ff, #ff00ff, #00ff88, #00f5ff);
            background-size: 300% 100%;
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0% { background-position: 0% 0; }
            100% { background-position: 300% 0; }
        }
        
        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 40px 80px rgba(0,0,0,0.2);
        }
        
        .project-tech {
            display: flex;
            gap: 8px;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }
        
        .tech-tag {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        /* Achievements */
        .achievements {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .achievement-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2.5rem;
            border-radius: 24px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .achievement-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            transition: all 0.6s ease;
        }
        
        .achievement-card:hover::before {
            transform: rotate(90deg);
        }
        
        /* Contact */
        .contact {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 100%);
            color: white;
            text-align: center;
        }
        
        .contact-links {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .contact-link {
            color: white;
            text-decoration: none;
            padding: 2rem;
            border: 2px solid rgba(255,255,255,0.2);
            border-radius: 20px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .contact-link:hover {
            background: rgba(255,255,255,0.1);
            border-color: #00f5ff;
            transform: translateY(-5px);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .timeline {
                grid-template-columns: 1fr;
            }
            
            .timeline-item {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .timeline-dot {
                margin: 0 auto 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="nav">
        <button class="nav-btn" onclick="scrollToSection('hero')">Home</button>
        <button class="nav-btn" onclick="scrollToSection('timeline')">Journey</button>
        <button class="nav-btn" onclick="scrollToSection('projects')">Projects</button>
        <button class="nav-btn" onclick="scrollToSection('achievements')">Achievements</button>
        <button class="nav-btn" onclick="scrollToSection('contact')">Contact</button>
    </nav>

    <!-- Hero -->
    <section class="hero" id="hero">
        <div class="hero-content">
            <h1>Kedar Hukkeri</h1>
            <p class="hero-subtitle">
                Electronics & Communication Engineering | CGPA 9.23<br>
                IoT Specialist | Hackathon Champion | ESP32 Expert
            </p>
            <div class="cta-buttons">
                <a href="#projects" class="cta-btn cta-primary" onclick="scrollToSection('projects')">View Projects</a>
                <a href="assets/My-Resume.pdf" class="cta-btn cta-secondary" download>Download Resume</a>
            </div>
        </div>
    </section>

    <!-- Stats -->
    <section style="padding: 80px 20px;">
        <div class="stats">
            <div class="stat">
                <span class="stat-number">9.23</span>
                CGPA
            </div>
            <div class="stat">
                <span class="stat-number">4+</span>
                Major Projects
            </div>
            <div class="stat">
                <span class="stat-number">3</span>
                Hackathon Wins
            </div>
            <div class="stat">
                <span class="stat-number">50+</span>
                Technologies
            </div>
        </div>
    </section>

    <!-- Engineering Journey Timeline -->
    <section id="timeline">
        <h2 class="section-title">Engineering Journey</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-dot">📚</div>
                <div>
                    <h3>B.E. Electronics & Communication</h3>
                    <p><strong>BVBCET Hubli</strong> | 3rd Year | CGPA <strong>9.23/10</strong><br>
                    Active member of BVB Dance Club & UPSC Club</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot">🏆</div>
                <div>
                    <h3>National Hackathon Champion</h3>
                    <p><strong>1st Place</strong> - Gogte Institute of Technology<br>
                    Finalist in <strong>Infosys Global Hackathon</strong> & <strong>IIT Bombay Incubate Medtech</strong></p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot">🔬</div>
                <div>
                    <h3>Technical Expertise</h3>
                    <p>C, C++, Python, DSA, Arduino IDE, Cadence, Microcontrollers<br>
                    <strong>Strengths:</strong> Team Management, Documentation, Communication</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Projects -->
    <section id="projects" style="background: #f8f9ff;">
        <h2 class="section-title">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-tech">
                    <span class="tech-tag">ESP32</span>
                    <span class="tech-tag">IoT</span>
                    <span class="tech-tag">Solar</span>
                    <span class="tech-tag">SIH 2025</span>
                </div>
                <h3>🌞 Hybrid Solar Dewatering System</h3>
                <p><strong>Smart India Hackathon 2025 Finalist (Team ID: 91403)</strong><br>
                Solar-powered mining water removal with diesel backup, IoT monitoring, AI predictive maintenance. 
                Reduces diesel usage by 60% and operational costs by 30-40%.</p>
                <div style="margin-top: 1.5rem;">
                    <a href="assets/SIH_2025_FINAL.pdf" class="cta-btn cta-primary" style="width: 100%; text-align: center; margin-bottom: 0.5rem;" download>📄 SIH Submission</a>
                    <a href="assets/Smart-Natural-Disaster-Detection-and-Alert-System-Using-ESP32.pptx" class="cta-btn cta-secondary" style="width: 100%; text-align: center;" download>📊 Presentation</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-tech">
                    <span class="tech-tag">ESP32</span>
                    <span class="tech-tag">Accelerometer</span>
                    <span class="tech-tag">GSM</span>
                    <span class="tech-tag">GPS</span>
                </div>
                <h3>🪖 Smart Helmet for Accident Detection</h3>
                <p>Crash detection with GPS location sharing, vital health monitoring (pulse, SpO2), 
                emergency SMS/calls to contacts & ambulance. Features ADXL335, SIM800L, MAX30100.</p>
                <div style="margin-top: 1.5rem;">
                    <a href="assets/IoT_2-1.pptx" class="cta-btn cta-primary" style="width: 100%; text-align: center;" download>📊 Technical Presentation</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-tech">
                    <span class="tech-tag">ESP32</span>
                    <span class="tech-tag">Multi-Sensor</span>
                    <span class="tech-tag">Blynk IoT</span>
                    <span class="tech-tag">Twilio</span>
                </div>
                <h3>🚨 Early Guard Disaster Warning</h3>
                <p>Real-time flood, earthquake, gas leak detection with SMS/email alerts, mesh networking. 
                Features HC-SR04, MPU6050, MQ-135 sensors with centralized Blynk dashboard.</p>
                <div style="margin-top: 1.5rem;">
                    <a href="#" class="cta-btn cta-primary" style="width: 100%; text-align: center;">🔗 Live Demo</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-tech">
                    <span class="tech-tag">IoT</span>
                    <span class="tech-tag">Medicine</span>
                    <span class="tech-tag">ESP32</span>
                </div>
                <h3>💊 Medicine Dispenser Prototype</h3>
                <p>Automated elderly care solution with scheduled dispensing, mobile app integration, 
                and caregiver notifications for medication adherence.</p>
                <div style="margin-top: 1.5rem;">
                    <a href="#" class="cta-btn cta-primary" style="width: 100%; text-align: center;">📱 App Demo</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Achievements -->
    <section id="achievements">
        <h2 class="section-title">Achievements & Recognition</h2>
        <div class="achievements">
            <div class="achievement-card">
                <h3>🥇 1st Place</h3>
                <p>National Level Hackathon<br><strong>Gogte Institute of Technology</strong></p>
            </div>
            <div class="achievement-card">
                <h3>🌍 Global Finalist</h3>
                <p>Infosys Global Hackathon<br><strong>Top Teams Worldwide</strong></p>
            </div>
            <div class="achievement-card">
                <h3>🎯 SIH 2025 Finalist</h3>
                <p>Smart India Hackathon<br><strong>Team ID: 91403 | Aqua Logic</strong></p>
            </div>
            <div class="achievement-card">
                <h3>🏆 IIT Bombay Finalist</h3>
                <p>Incubate Medtech Hackathon<br><strong>Medical Innovation</strong></p>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="contact">
        <h2 class="section-title" style="color: white;">Let's Collaborate</h2>
        <p style="font-size: 1.3rem; max-width: 600px; margin: 0 auto 3rem; opacity: 0.9;">
            Ready to build innovative IoT solutions? Let's connect!
        </p>
        <div class="contact-links">
            <a href="mailto:kedarhukkeri2004@gmail.com" class="contact-link">
                📧 kedarhukkeri2004@gmail.com
            </a>
            <a href="tel:+919148368218" class="contact-link">
                📱 +91 9148368218
            </a>
            <a href="https://www.linkedin.com/in/kedarhukkeri/" class="contact-link" target="_blank">
                💼 LinkedIn
            </a>
            <a href="https://sites.google.com/view/kedar-hukkeri/home" class="contact-link" target="_blank">
                🌐 Portfolio Site
            </a>
            <a href="assets/My-Resume.pdf" class="contact-link" download>
                📄 Resume PDF
            </a>
        </div>
        <p style="margin-top: 4rem; opacity: 0.7;">Dharwad, Karnataka, India | Open for Placements 2026</p>
    </section>

    <script>
        // Smooth scrolling
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        // Timeline animation
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.timeline-item').forEach(item => {
            observer.observe(item);
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const nav = document.querySelector('.nav');
            nav.style.background = `rgba(255,255,255,${Math.min(0.2, scrolled * 0.001)})`;
        });

        // Download counters (placeholder)
        document.querySelectorAll('a[download]').forEach(link => {
            link.addEventListener('click', () => {
                // Add analytics here
                console.log('Download clicked:', link.href);
            });
        });
    </script>
</body>
</html>
