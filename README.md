<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vihanga Nilusha - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Fira Code', 'Courier New', monospace;
            background: linear-gradient(135deg, #0a0e27 0%, #16213e 50%, #0f3460 100%);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated background */
        @keyframes gradient-shift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: radial-gradient(circle, rgba(255,255,255,0.8), rgba(255,255,255,0));
            border-radius: 50%;
            animation: float linear infinite;
        }

        @keyframes float {
            0% {
                opacity: 0;
                transform: translateY(100vh) translateX(0);
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: translateY(-100vh) translateX(100px);
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 60px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 4em;
            background: linear-gradient(45deg, #00d4ff, #0099ff, #00ff88, #00d4ff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease infinite;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(0, 212, 255, 0.3);
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .typing-text {
            font-size: 1.5em;
            color: #00ff88;
            min-height: 40px;
            animation: typewriter 3s steps(40, end) infinite;
        }

        @keyframes typewriter {
            0%, 100% { width: 0; }
            50% { width: 100%; }
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px 30px;
            border-radius: 10px;
            border: 2px solid rgba(0, 212, 255, 0.3);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .stat-item:hover {
            background: rgba(0, 212, 255, 0.1);
            border-color: rgba(0, 212, 255, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
        }

        .stat-item strong {
            color: #00d4ff;
            font-size: 1.3em;
        }

        /* Section Headers */
        .section-header {
            font-size: 2em;
            margin: 50px 0 30px 0;
            color: #00ff88;
            display: flex;
            align-items: center;
            gap: 10px;
            animation: fadeInLeft 0.6s ease;
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .section-header::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(90deg, #00ff88, transparent);
        }

        /* About Me Section */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 50px;
            align-items: center;
        }

        .code-block {
            background: rgba(0, 0, 0, 0.4);
            border-left: 4px solid #00d4ff;
            padding: 20px;
            border-radius: 8px;
            font-size: 0.9em;
            overflow-x: auto;
            animation: fadeInUp 0.8s ease 0.2s both;
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

        .code-block code {
            color: #00ff88;
        }

        .about-text {
            animation: fadeInUp 0.8s ease 0.3s both;
        }

        .about-text h3 {
            color: #00d4ff;
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .about-text ul {
            list-style: none;
        }

        .about-text li {
            padding: 8px 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .about-text li::before {
            content: '▸';
            color: #00ff88;
            font-weight: bold;
        }

        /* Tech Stack */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .tech-category {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(0, 212, 255, 0.2);
            padding: 20px;
            border-radius: 10px;
            animation: scaleIn 0.6s ease;
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .tech-category h4 {
            color: #00ff88;
            margin-bottom: 15px;
            font-size: 1.1em;
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .badge {
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.4);
            color: #00d4ff;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .badge:hover {
            background: rgba(0, 212, 255, 0.2);
            border-color: rgba(0, 212, 255, 0.8);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 212, 255, 0.2);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.05), rgba(0, 255, 136, 0.05));
            border: 2px solid rgba(0, 212, 255, 0.2);
            padding: 25px;
            border-radius: 12px;
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease both;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.5s;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            border-color: rgba(0, 212, 255, 0.6);
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(0, 255, 136, 0.1));
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .project-card h3 {
            color: #00ff88;
            margin-bottom: 10px;
            font-size: 1.3em;
        }

        .project-card p {
            color: #b0b0b0;
            margin-bottom: 15px;
            font-size: 0.95em;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 12px;
        }

        .tech-tag {
            background: rgba(0, 255, 136, 0.1);
            color: #00ff88;
            padding: 4px 10px;
            border-radius: 15px;
            font-size: 0.8em;
            border: 1px solid rgba(0, 255, 136, 0.3);
        }

        .status-badge {
            display: inline-block;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: bold;
        }

        .status-active {
            background: rgba(0, 255, 136, 0.2);
            color: #00ff88;
            border: 1px solid rgba(0, 255, 136, 0.5);
        }

        .status-progress {
            background: rgba(0, 212, 255, 0.2);
            color: #00d4ff;
            border: 1px solid rgba(0, 212, 255, 0.5);
        }

        .status-planning {
            background: rgba(255, 200, 0, 0.2);
            color: #ffc800;
            border: 1px solid rgba(255, 200, 0, 0.5);
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .skill-box {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(0, 255, 136, 0.3);
            padding: 20px;
            border-radius: 10px;
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease both;
        }

        .skill-box:hover {
            background: rgba(0, 255, 136, 0.05);
            border-color: rgba(0, 255, 136, 0.6);
            transform: translateY(-5px);
        }

        .skill-box h4 {
            color: #00d4ff;
            margin-bottom: 12px;
        }

        .skill-box p {
            color: #a0a0a0;
            font-size: 0.95em;
            line-height: 1.6;
        }

        /* Connect Section */
        .connect-section {
            text-align: center;
            margin: 50px 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .social-btn {
            background: rgba(0, 212, 255, 0.1);
            border: 2px solid rgba(0, 212, 255, 0.4);
            color: #00d4ff;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .social-btn:hover {
            background: rgba(0, 212, 255, 0.2);
            border-color: rgba(0, 212, 255, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 212, 255, 0.3);
        }

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 60px;
            padding-top: 30px;
            border-top: 1px solid rgba(0, 212, 255, 0.2);
            animation: fadeInUp 0.8s ease 0.5s both;
        }

        .footer p {
            color: #808080;
            margin: 10px 0;
        }

        .footer strong {
            color: #00ff88;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5em;
            }

            .about-section {
                grid-template-columns: 1fr;
            }

            .stats {
                flex-direction: column;
            }

            .tech-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>👋 Hi, I'm Vihanga Nilusha</h1>
            <div class="typing-text">Full Stack Developer | UI/UX Designer | Mobile Developer</div>
            
            <div class="stats">
                <div class="stat-item">
                    <strong>🎓</strong> Computer Science Student
                </div>
                <div class="stat-item">
                    <strong>🚀</strong> University of Plymouth
                </div>
                <div class="stat-item">
                    <strong>💡</strong> Go Beyond The Boundaries
                </div>
            </div>
        </div>

        <!-- About Me -->
        <div class="section-header">📋 About Me</div>
        <div class="about-section">
            <div class="code-block">
                <code>
const vihanga = {<br>
&nbsp;&nbsp;name: "Vihanga Nilusha",<br>
&nbsp;&nbsp;education: "University of Plymouth 🎓",<br>
&nbsp;&nbsp;specializations: [<br>
&nbsp;&nbsp;&nbsp;&nbsp;"Full Stack Development 🚀",<br>
&nbsp;&nbsp;&nbsp;&nbsp;"UI/UX Design 🎨",<br>
&nbsp;&nbsp;&nbsp;&nbsp;"Mobile App Development 📱"<br>
&nbsp;&nbsp;],<br>
&nbsp;&nbsp;currentlyLearning: [<br>
&nbsp;&nbsp;&nbsp;&nbsp;"React Native", "Flutter", "Advanced React"<br>
&nbsp;&nbsp;],<br>
&nbsp;&nbsp;motto: "Go Beyond The Boundaries 🚀"<br>
}
                </code>
            </div>
            <div class="about-text">
                <h3>🎯 Current Focus</h3>
                <ul>
                    <li>Building full-stack web applications with modern frameworks</li>
                    <li>Creating intuitive UI/UX designs with Figma & Adobe XD</li>
                    <li>Developing cross-platform mobile applications</li>
                    <li>Contributing to open source projects</li>
                    <li>Learning advanced React patterns and Node.js best practices</li>
                    <li>Creating beautiful, functional experiences across all platforms! 💻📱🎨</li>
                </ul>
            </div>
        </div>

        <!-- Tech Stack -->
        <div class="section-header">💻 Tech Stack</div>
        <div class="tech-grid">
            <div class="tech-category">
                <h4>🎨 Frontend & UI/UX</h4>
                <div class="tech-badges">
                    <span class="badge">HTML5</span>
                    <span class="badge">CSS3</span>
                    <span class="badge">JavaScript</span>
                    <span class="badge">TypeScript</span>
                    <span class="badge">React</span>
                    <span class="badge">Next.js</span>
                    <span class="badge">TailwindCSS</span>
                    <span class="badge">Bootstrap</span>
                    <span class="badge">Sass</span>
                    <span class="badge">Figma</span>
                    <span class="badge">Adobe XD</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>⚡ Backend & Database</h4>
                <div class="tech-badges">
                    <span class="badge">Node.js</span>
                    <span class="badge">Express.js</span>
                    <span class="badge">Python</span>
                    <span class="badge">PHP</span>
                    <span class="badge">Java</span>
                    <span class="badge">MongoDB</span>
                    <span class="badge">MySQL</span>
                    <span class="badge">PostgreSQL</span>
                    <span class="badge">Firebase</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>📱 Mobile Development</h4>
                <div class="tech-badges">
                    <span class="badge">React Native</span>
                    <span class="badge">Flutter</span>
                    <span class="badge">Dart</span>
                    <span class="badge">Android</span>
                    <span class="badge">iOS</span>
                    <span class="badge">Expo</span>
                </div>
            </div>

            <div class="tech-category">
                <h4>🛠️ Tools & DevOps</h4>
                <div class="tech-badges">
                    <span class="badge">Git</span>
                    <span class="badge">GitHub</span>
                    <span class="badge">VS Code</span>
                    <span class="badge">Docker</span>
                    <span class="badge">Vercel</span>
                    <span class="badge">Netlify</span>
                    <span class="badge">Postman</span>
                </div>
            </div>
        </div>

        <!-- Projects -->
        <div class="section-header">🎯 Featured Projects</div>
        <div class="projects-grid">
            <div class="project-card">
                <h3>🛒 Full-Stack E-Commerce</h3>
                <p>Complete shopping platform with admin dashboard and payment integration</p>
                <div class="project-tech">
                    <span class="tech-tag">React</span>
                    <span class="tech-tag">Node.js</span>
                    <span class="tech-tag">MongoDB</span>
                    <span class="tech-tag">Stripe</span>
                </div>
                <span class="status-badge status-progress">🔄 In Progress</span>
            </div>

            <div class="project-card">
                <h3>✅ Mobile Task Manager</h3>
                <p>Cross-platform productivity app with real-time synchronization and offline support</p>
                <div class="project-tech">
                    <span class="tech-tag">React Native</span>
                    <span class="tech-tag">Firebase</span>
                    <span class="tech-tag">Redux</span>
                </div>
                <span class="status-badge status-active">✅ Active</span>
            </div>

            <div class="project-card">
                <h3>🍽️ Restaurant App</h3>
                <p>Full-featured dining platform with menu browsing, ordering, and payment integration</p>
                <div class="project-tech">
                    <span class="tech-tag">Flutter</span>
                    <span class="tech-tag">Node.js</span>
                    <span class="tech-tag">MySQL</span>
                    <span class="tech-tag">PayPal</span>
                </div>
                <span class="status-badge status-active">✅ Active</span>
            </div>

            <div class="project-card">
                <h3>🎨 UI/UX Portfolio</h3>
                <p>Comprehensive design showcase with interactive prototypes and design systems</p>
                <div class="project-tech">
                    <span class="tech-tag">Figma</span>
                    <span class="tech-tag">Adobe XD</span>
                    <span class="tech-tag">Framer</span>
                </div>
                <span class="status-badge status-planning">📋 Planning</span>
            </div>
        </div>

        <!-- Skills -->
        <div class="section-header">🌟 What I'm Good At</div>
        <div class="skills-container">
            <div class="skill-box">
                <h4>🌐 Web Development</h4>
                <p>Building responsive, scalable applications with modern frameworks and best practices. Expertise in React, Next.js, and full-stack architectures.</p>
            </div>
            <div class="skill-box">
                <h4>📱 Mobile Development</h4>
                <p>Creating seamless cross-platform experiences for iOS and Android using React Native and Flutter with native-like performance.</p>
            </div>
            <div class="skill-box">
                <h4>🎨 UI/UX Design</h4>
                <p>Designing intuitive interfaces that balance aesthetics with functionality. Proficient in Figma, Adobe XD, and design systems.</p>
            </div>
            <div class="skill-box">
                <h4>⚙️ Full-Stack Solutions</h4>
                <p>End-to-end development from database design to frontend implementation with scalable backend architectures.</p>
            </div>
        </div>

        <!-- Connect -->
        <div class="connect-section">
            <div class="section-header">🤝 Let's Connect</div>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/vihanga-nilusha" class="social-btn">💼 LinkedIn</a>
                <a href="https://github.com/Vihanga13" class="social-btn">🐙 GitHub</a>
                <a href="mailto:vihaax23@gmail.com" class="social-btn">📧 Email</a>
                <a href="https://discord.gg/yourdiscord" class="social-btn">💬 Discord</a>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>⭐ <strong>Don't forget to star my repositories if you find them interesting!</strong> ⭐</p>
            <p>Made with ❤️ and ☕ by Vihanga Nilusha</p>
            <p style="margin-top: 20px; font-size: 0.9em;">Go Beyond The Boundaries 🚀</p>
        </div>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                const size = Math.random() * 4 + 2;
                const duration = Math.random() * 20 + 10;
                const delay = Math.random() * 5;
                const xOffset = Math.random() * 200 - 100;

                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animation = `float ${duration}s linear ${delay}s infinite`;
                particle.style.filter = `blur(${Math.random() * 0.5}px)`;

                particlesContainer.appendChild(particle);
            }
        }

        // Initialize particles on load
        window.addEventListener('load', createParticles);

        // Add scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = entry.target.style.animation;
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section-header, .tech-category, .project-card, .skill-box').forEach(el => {
            observer.observe(el);
        });

        // Interactive badge hover effect
        document.querySelectorAll('.badge').forEach(badge => {
            badge.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.1) rotate(5deg)';
            });
            badge.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });
    </script>
</body>
</html>
