<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alex Chen - Professional Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            overflow-x: hidden;
        }

        .hero-section {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow: hidden;
        }

        .floating-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .shape {
            position: absolute;
            opacity: 0.1;
            animation: float 6s ease-in-out infinite;
        }

        .shape:nth-child(1) {
            width: 80px;
            height: 80px;
            background: #fff;
            border-radius: 50%;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            width: 60px;
            height: 60px;
            background: #fff;
            top: 60%;
            right: 10%;
            animation-delay: 2s;
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
        }

        .shape:nth-child(3) {
            width: 100px;
            height: 100px;
            background: #fff;
            top: 40%;
            left: 80%;
            animation-delay: 4s;
            clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            animation: slideInUp 1s ease-out;
        }

        .profile-pic {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 60px;
            color: white;
            font-weight: bold;
            position: relative;
            animation: pulse 2s infinite;
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .profile-pic::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            border-radius: 50%;
            z-index: -1;
            animation: rotate 4s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 700;
            color: white;
            margin-bottom: 10px;
            animation: fadeInLeft 1s ease-out 0.3s both;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: rgba(255,255,255,0.9);
            margin-bottom: 30px;
            animation: fadeInRight 1s ease-out 0.6s both;
        }

        .typing-effect {
            font-size: 1.2rem;
            color: rgba(255,255,255,0.8);
            border-right: 2px solid white;
            animation: typing 3s steps(40) infinite, blink 1s infinite;
            white-space: nowrap;
            overflow: hidden;
            display: inline-block;
        }

        @keyframes typing {
            0% { width: 0; }
            50% { width: 100%; }
            100% { width: 0; }
        }

        @keyframes blink {
            0%, 50% { border-color: white; }
            51%, 100% { border-color: transparent; }
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            animation: fadeInUp 1s ease-out 0.9s both;
        }

        .social-btn {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            font-size: 24px;
            transition: all 0.3s ease;
            border: 2px solid rgba(255,255,255,0.3);
        }

        .social-btn:hover {
            transform: translateY(-10px) scale(1.1);
            background: rgba(255,255,255,0.3);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .content-section {
            background: white;
            padding: 80px 20px;
            position: relative;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .skill-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #333;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            animation: slideInTag 0.5s ease-out;
        }

        @keyframes slideInTag {
            0% { transform: translateX(-20px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            position: relative;
            overflow: hidden;
        }

        .project-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .project-content {
            padding: 25px;
        }

        .project-title {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: #333;
        }

        .project-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }

        .tech-badge {
            background: #f0f0f0;
            color: #666;
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
        }

        .project-links {
            display: flex;
            gap: 15px;
        }

        .project-link {
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .primary-link {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
        }

        .primary-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
        }

        .secondary-link {
            background: transparent;
            color: #667eea;
            border: 2px solid #667eea;
        }

        .secondary-link:hover {
            background: #667eea;
            color: white;
        }

        .stats-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 80px 20px;
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            text-align: center;
        }

        .stat-item {
            animation: countUp 2s ease-out;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            display: block;
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        @keyframes countUp {
            0% { transform: translateY(20px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        .contact-section {
            background: #2c3e50;
            color: white;
            padding: 80px 20px;
            text-align: center;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            display: grid;
            gap: 20px;
        }

        .form-group {
            position: relative;
        }

        .form-input {
            width: 100%;
            padding: 15px 20px;
            background: rgba(255,255,255,0.1);
            border: 2px solid rgba(255,255,255,0.2);
            border-radius: 10px;
            color: white;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-input:focus {
            outline: none;
            border-color: #667eea;
            background: rgba(255,255,255,0.15);
            transform: translateY(-2px);
        }

        .form-input::placeholder {
            color: rgba(255,255,255,0.7);
        }

        .submit-btn {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 15px 40px;
            border: none;
            border-radius: 25px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }

        @keyframes slideInUp {
            0% { transform: translateY(50px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        @keyframes fadeInLeft {
            0% { transform: translateX(-50px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        @keyframes fadeInRight {
            0% { transform: translateX(50px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        @keyframes fadeInUp {
            0% { transform: translateY(30px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        .scroll-arrow {
            width: 30px;
            height: 30px;
            border: 2px solid white;
            border-top: none;
            border-left: none;
            transform: rotate(45deg);
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-10px); }
            60% { transform: translateX(-50%) translateY(-5px); }
        }

        @media (max-width: 768px) {
            .hero-title { font-size: 2.5rem; }
            .hero-subtitle { font-size: 1.2rem; }
            .skills-grid, .projects-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero-section">
        <div class="floating-shapes">
            <div class="shape"></div>
            <div class="shape"></div>
            <div class="shape"></div>
        </div>
        
        <div class="hero-content">
            <div class="profile-pic">AC</div>
            <h1 class="hero-title">Alex Chen</h1>
            <p class="hero-subtitle">Full Stack Developer & UI/UX Designer</p>
            <div class="typing-effect">Building amazing digital experiences...</div>
            
            <div class="social-links">
                <a href="#" class="social-btn">💼</a>
                <a href="#" class="social-btn">🐱</a>
                <a href="#" class="social-btn">📧</a>
                <a href="#" class="social-btn">🐦</a>
            </div>
        </div>
        
        <div class="scroll-indicator">
            <div class="scroll-arrow"></div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="content-section">
        <div class="container">
            <h2 class="section-title">🛠️ Tech Stack</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>💻 Frontend</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">Vue.js</span>
                        <span class="skill-tag">TypeScript</span>
                        <span class="skill-tag">Next.js</span>
                        <span class="skill-tag">Tailwind CSS</span>
                    </div>
                </div>
                
                <div class="skill-card">
                    <h3>⚙️ Backend</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">Django</span>
                        <span class="skill-tag">PostgreSQL</span>
                        <span class="skill-tag">MongoDB</span>
                    </div>
                </div>
                
                <div class="skill-card">
                    <h3>☁️ DevOps</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">AWS</span>
                        <span class="skill-tag">Docker</span>
                        <span class="skill-tag">Kubernetes</span>
                        <span class="skill-tag">CI/CD</span>
                        <span class="skill-tag">Terraform</span>
                    </div>
                </div>
                
                <div class="skill-card">
                    <h3>🎨 Design</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Figma</span>
                        <span class="skill-tag">Adobe XD</span>
                        <span class="skill-tag">Photoshop</span>
                        <span class="skill-tag">Illustrator</span>
                        <span class="skill-tag">Prototyping</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="content-section" style="background: #f8f9fa;">
        <div class="container">
            <h2 class="section-title">🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">🌐</div>
                    <div class="project-content">
                        <h3 class="project-title">E-Commerce Platform</h3>
                        <p class="project-description">Full-stack e-commerce solution with real-time inventory, payment processing, and admin dashboard.</p>
                        <div class="project-tech">
                            <span class="tech-badge">React</span>
                            <span class="tech-badge">Node.js</span>
                            <span class="tech-badge">MongoDB</span>
                            <span class="tech-badge">Stripe</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link primary-link">Live Demo</a>
                            <a href="#" class="project-link secondary-link">Source Code</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🎵</div>
                    <div class="project-content">
                        <h3 class="project-title">Music Streaming App</h3>
                        <p class="project-description">Spotify-like streaming platform with playlist management, social features, and audio visualization.</p>
                        <div class="project-tech">
                            <span class="tech-badge">Vue.js</span>
                            <span class="tech-badge">Django</span>
                            <span class="tech-badge">PostgreSQL</span>
                            <span class="tech-badge">AWS S3</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link primary-link">Live Demo</a>
                            <a href="#" class="project-link secondary-link">Source Code</a>
                        </div>
               
