<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ayoub Aissa · front-end architect</title>
    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Fonts (Inter + Space Grotesk) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300..700&family=Space+Grotesk:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0b0d10;
            font-family: "Inter", sans-serif;
            color: #eef2f5;
            line-height: 1.5;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        /* custom gradient / animated background */
        .bg-aura {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 30% 30%, rgba(45, 85, 255, 0.08) 0%, transparent 50%),
                        radial-gradient(circle at 80% 70%, rgba(170, 90, 255, 0.06) 0%, transparent 50%),
                        #0b0d10;
            z-index: -2;
        }

        .grid-lines {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background-image: 
                linear-gradient(rgba(75, 130, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(75, 130, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: -1;
            pointer-events: none;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 5;
        }

        /* navbar */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 0 1.5rem 0;
            flex-wrap: wrap;
            border-bottom: 1px solid rgba(255,255,255,0.03);
        }

        .logo {
            font-size: 2rem;
            font-weight: 600;
            letter-spacing: -0.02em;
            background: linear-gradient(130deg, #fff, #b0c8ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .logo span {
            font-weight: 300;
            background: none;
            -webkit-text-fill-color: #6c7a9a;
            color: #6c7a9a;
        }

        .nav-links {
            display: flex;
            gap: 3rem;
            font-weight: 400;
        }
        .nav-links a {
            color: #b5c2d9;
            text-decoration: none;
            font-size: 1rem;
            transition: 0.2s;
            letter-spacing: 0.3px;
            border-bottom: 1px solid transparent;
            padding-bottom: 4px;
        }
        .nav-links a:hover {
            color: white;
            border-bottom-color: #3d7eff;
        }

        /* buttons / tags */
        .pill {
            background: rgba(20, 30, 55, 0.7);
            backdrop-filter: blur(4px);
            padding: 0.4rem 1.1rem;
            border-radius: 40px;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.04);
            color: #ccddf8;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s;
        }
        .pill i {
            color: #3d7eff;
            font-size: 0.8rem;
        }

        /* hero section */
        .hero {
            padding: 3rem 0 5rem 0;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 3rem;
        }

        .hero-left {
            flex: 1 1 350px;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(61, 126, 255, 0.12);
            border: 1px solid rgba(61, 126, 255, 0.3);
            border-radius: 60px;
            padding: 0.3rem 1.2rem;
            font-size: 0.85rem;
            font-weight: 500;
            color: #b0cdff;
            margin-bottom: 2rem;
            backdrop-filter: blur(4px);
        }

        .hero-left h1 {
            font-size: clamp(2.8rem, 6vw, 4.2rem);
            font-weight: 600;
            line-height: 1.1;
            letter-spacing: -0.02em;
            background: linear-gradient(140deg, #ffffff, #b5d0ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1.2rem;
        }

        .hero-left h1 i {
            color: #3d7eff;
            font-size: 3rem;
            background: none;
            -webkit-text-fill-color: #3d7eff;
        }

        .hero-desc {
            font-size: 1.2rem;
            color: #a5b9da;
            max-width: 550px;
            margin-bottom: 2.5rem;
            border-left: 3px solid #3d7eff;
            padding-left: 1.5rem;
        }

        .hero-stats {
            display: flex;
            gap: 2.5rem;
            margin-bottom: 2rem;
        }
        .stat-item h3 {
            font-size: 2rem;
            font-weight: 500;
            color: white;
        }
        .stat-item p {
            color: #8193b2;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .hero-right {
            flex: 1 1 350px;
            display: flex;
            justify-content: center;
            position: relative;
        }

        .profile-frame {
            width: 340px;
            height: 340px;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            background: linear-gradient(145deg, #1e2a47, #0d1424);
            padding: 12px;
            box-shadow: 0 30px 40px -20px rgba(0,80,255,0.5);
            animation: float 8s ease-in-out infinite;
        }
        .profile-frame img {
            width: 100%;
            height: 100%;
            border-radius: inherit;
            object-fit: cover;
            border: 3px solid rgba(255,255,255,0.05);
            filter: grayscale(0.2) contrast(1.1);
        }
        @keyframes float {
            0% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
            50% { border-radius: 50% 50% 50% 50% / 40% 60% 40% 60%; transform: translateY(-12px); }
            100% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
        }

        /* tech stack marquee (pro animation) */
        .marquee-section {
            margin: 2rem 0 3rem 0;
            overflow: hidden;
            mask-image: linear-gradient(90deg, transparent, black 10%, black 90%, transparent);
        }
        .marquee {
            display: flex;
            gap: 4rem;
            animation: scrollTech 22s linear infinite;
            width: max-content;
        }
        .marquee span {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.2rem;
            color: #bbcbe9;
            background: rgba(20, 30, 45, 0.5);
            padding: 0.5rem 2rem;
            border-radius: 60px;
            border: 1px solid rgba(61, 126, 255, 0.2);
            backdrop-filter: blur(6px);
            font-weight: 500;
        }
        .marquee span i {
            font-size: 1.8rem;
            color: #3d7eff;
        }
        @keyframes scrollTech {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* section titles */
        .section-title {
            font-size: 2.2rem;
            font-weight: 500;
            letter-spacing: -0.5px;
            margin: 4rem 0 2.5rem 0;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .section-title i {
            color: #3d7eff;
            font-size: 2rem;
            background: rgba(61,126,255,0.1);
            padding: 10px;
            border-radius: 50%;
        }

        /* skill cards */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
        }
        .skill-card {
            background: rgba(18, 25, 40, 0.7);
            backdrop-filter: blur(6px);
            border: 1px solid rgba(255,255,255,0.02);
            padding: 1.8rem 1rem;
            border-radius: 38px;
            text-align: center;
            transition: 0.25s ease;
            box-shadow: 0 10px 20px -10px rgba(0,0,0,0.8);
        }
        .skill-card:hover {
            border-color: rgba(61, 126, 255, 0.3);
            transform: translateY(-6px);
            background: rgba(30, 40, 65, 0.8);
        }
        .skill-card i {
            font-size: 2.6rem;
            background: linear-gradient(145deg, #89b4ff, #3d7eff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.8rem;
        }
        .skill-card h3 {
            font-weight: 500;
            font-size: 1.3rem;
        }
        .skill-card p {
            color: #8096c0;
            font-size: 0.85rem;
            margin-top: 0.2rem;
        }

        /* project cards */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        .project-card {
            background: rgba(16, 22, 38, 0.8);
            backdrop-filter: blur(8px);
            border-radius: 32px;
            border: 1px solid rgba(255,255,255,0.02);
            overflow: hidden;
            transition: all 0.3s;
            box-shadow: 0 15px 25px -15px #00000080;
        }
        .project-card:hover {
            border-color: rgba(61, 126, 255, 0.5);
            transform: scale(1.02) translateY(-6px);
        }
        .project-img {
            width: 100%;
            height: 200px;
            background: #19213a;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: rgba(255,255,255,0.2);
        }
        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.9;
        }
        .project-overlay {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 30% 30%, rgba(61,126,255,0.2), transparent 70%);
        }
        .project-card h4 {
            font-size: 1.5rem;
            font-weight: 500;
            padding: 1.2rem 1.5rem 0.3rem;
        }
        .project-tags {
            padding: 0 1.5rem 1.2rem;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .project-tags span {
            background: rgba(61,126,255,0.08);
            border-radius: 30px;
            padding: 0.3rem 1rem;
            font-size: 0.8rem;
            color: #a3c2ff;
            border: 1px solid rgba(61,126,255,0.2);
        }

        /* contact / footer */
        .contact-area {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            padding: 3rem 0;
            border-top: 1px solid rgba(255,255,255,0.04);
            margin-top: 3rem;
        }
        .social-links {
            display: flex;
            gap: 2rem;
        }
        .social-links a {
            color: #b5c9f0;
            font-size: 1.8rem;
            transition: 0.2s;
        }
        .social-links a:hover {
            color: #3d7eff;
            transform: scale(1.1);
        }
        .footer-email {
            font-size: 1.2rem;
            background: rgba(255,255,255,0.02);
            padding: 0.8rem 2rem;
            border-radius: 80px;
            border: 1px solid rgba(61,126,255,0.2);
        }
        .footer-email i {
            margin-right: 10px;
            color: #3d7eff;
        }

        /* scroll reveal simulation (pure css + intersection observer fallback friendly) */
        .reveal {
            opacity: 0;
            transform: translateY(28px);
            transition: all 0.8s cubic-bezier(0.2, 0.9, 0.3, 1);
        }
        .reveal.show {
            opacity: 1;
            transform: translateY(0);
        }

        /* responsiveness */
        @media (max-width: 700px) {
            .navbar { flex-direction: column; gap: 1rem; }
            .nav-links { gap: 2rem; }
            .hero-stats { gap: 1.5rem; flex-wrap: wrap; }
            .contact-area { flex-direction: column; gap: 2rem; align-items: flex-start; }
        }
    </style>
</head>
<body>
    <div class="bg-aura"></div>
    <div class="grid-lines"></div>

    <div class="container">
        <!-- navigation -->
        <nav class="navbar">
            <div class="logo">Ayoub <span>Aissa</span></div>
            <div class="nav-links">
                <a href="#">Work</a>
                <a href="#">Stack</a>
                <a href="#">Contact</a>
            </div>
            <div class="pill"><i class="fas fa-code"></i> front-end mastery</div>
        </nav>

        <!-- hero section -->
        <div class="hero">
            <div class="hero-left reveal">
                <div class="hero-badge"><i class="fas fa-bolt" style="margin-right: 8px;"></i> available for collab</div>
                <h1>crafting <i>pixel-perfect</i> interfaces with speed & soul</h1>
                <div class="hero-desc">
                    Ayoub Aissa — front-end architect who masters <strong>HTML, CSS, JavaScript, Tailwind, Bootstrap & Python</strong>. I build digital experiences that breathe.
                </div>
                <div class="hero-stats">
                    <div class="stat-item"><h3>4+</h3><p>years craft</p></div>
                    <div class="stat-item"><h3>6</h3><p>core tools</p></div>
                    <div class="stat-item"><h3>24</h3><p>projects</p></div>
                </div>
                <div class="pill" style="font-size: 1rem; gap: 12px; padding: 0.8rem 2rem;">
                    <i class="fas fa-paper-plane"></i> ayoub.aissa@dev.pro
                </div>
            </div>
            <div class="hero-right reveal">
                <div class="profile-frame">
                    <!-- pro image placeholder (you can replace src) -->
                    <img src="https://images.unsplash.com/photo-1531427186627-4fd839c3c904?w=400&auto=format&fit=crop&q=80" alt="Ayoub Aissa">
                </div>
            </div>
        </div>

        <!-- infinite tech marquee (pro animation) -->
        <div class="marquee-section">
            <div class="marquee">
                <!-- first set -->
                <span><i class="fab fa-html5" style="color: #f16529;"></i> HTML5</span>
                <span><i class="fab fa-css3-alt" style="color: #33a9dc;"></i> CSS3</span>
                <span><i class="fab fa-js" style="color: #f7df1e;"></i> JavaScript</span>
                <span><i class="fab fa-python" style="color: #ffd845;"></i> Python</span>
                <span><i class="fab fa-bootstrap" style="color: #8711fa;"></i> Bootstrap</span>
                <span><i class="fa-solid fa-wind"></i> Tailwind</span>
                <!-- duplicate for seamless loop -->
                <span><i class="fab fa-html5"></i> HTML5</span>
                <span><i class="fab fa-css3-alt"></i> CSS3</span>
                <span><i class="fab fa-js"></i> JavaScript</span>
                <span><i class="fab fa-python"></i> Python</span>
                <span><i class="fab fa-bootstrap"></i> Bootstrap</span>
                <span><i class="fa-solid fa-wind"></i> Tailwind</span>
            </div>
        </div>

        <!-- skills mastered (cards) -->
        <div class="section-title reveal">
            <i class="fas fa-crown"></i> 
            <span>mastered technologies</span>
        </div>
        <div class="skills-grid reveal">
            <div class="skill-card"><i class="fab fa-html5"></i><h3>HTML5</h3><p>semantic, accessible</p></div>
            <div class="skill-card"><i class="fab fa-css3-alt"></i><h3>CSS3</h3><p>flex, grid, animation</p></div>
            <div class="skill-card"><i class="fab fa-js"></i><h3>JavaScript</h3><p>ES6+, DOM, async</p></div>
            <div class="skill-card"><i class="fa-solid fa-wind"></i><h3>Tailwind</h3><p>utility-first, fast</p></div>
            <div class="skill-card"><i class="fab fa-bootstrap"></i><h3>Bootstrap</h3><p>responsive, components</p></div>
            <div class="skill-card"><i class="fab fa-python"></i><h3>Python</h3><p>flask, scripting</p></div>
        </div>

        <!-- featured projects (with pro images) -->
        <div class="section-title reveal">
            <i class="fas fa-rocket"></i>
            <span>signature work</span>
        </div>
        <div class="projects-grid">
            <div class="project-card reveal">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?w=600&auto=format&fit=crop&q=80" alt="Fintech dashboard">
                    <div class="project-overlay"></div>
                </div>
                <h4>Fintech dash</h4>
                <div class="project-tags"><span>React</span><span>Tailwind</span><span>chart.js</span></div>
            </div>
            <div class="project-card reveal">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=600&auto=format&fit=crop&q=80" alt="AI tool">
                    <div class="project-overlay"></div>
                </div>
                <h4>AI content studio</h4>
                <div class="project-tags"><span>Python</span><span>Flask</span><span>Bootstrap</span></div>
            </div>
            <div class="project-card reveal">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=600&auto=format&fit=crop&q=80" alt="E-commerce">
                    <div class="project-overlay"></div>
                </div>
                <h4>Urban store</h4>
                <div class="project-tags"><span>HTML/CSS</span><span>JavaScript</span><span>Tailwind</span></div>
            </div>
        </div>

        <!-- contact / footer area -->
        <div class="contact-area reveal">
            <div class="social-links">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-x-twitter"></i></a>
                <a href="#"><i class="fab fa-codepen"></i></a>
            </div>
            <div class="footer-email">
                <i class="fas fa-envelope"></i> ayoub.aissa@dev.pro
            </div>
            <div class="pill" style="background: transparent; border-color: #3d7eff40;">
                <i class="fas fa-map-pin"></i> casablanca / remote
            </div>
        </div>
    </div>

    <!-- tiny script for scroll reveal (simple intersection observer) -->
    <script>
        (function() {
            const reveals = document.querySelectorAll('.reveal');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('show');
                    } else {
                        // optional: remove class if you want repeat animation (commented for subtlety)
                        // entry.target.classList.remove('show');
                    }
                });
            }, { threshold: 0.2, rootMargin: '0px 0px -30px 0px' });
            
            reveals.forEach(r => observer.observe(r));
            
            // manually add show to hero elements after tiny delay (first impression)
            window.addEventListener('load', () => {
                document.querySelectorAll('.hero .reveal').forEach(el => el.classList.add('show'));
            });
        })();
    </script>
    <!-- extra smoothness for marquee -->
    <style>
        .marquee-section {
            mask-image: linear-gradient(90deg, transparent, black 8%, black 92%, transparent);
        }
        /* pro image effect */
        .profile-frame img {
            transition: 0.4s;
        }
        .profile-frame img:hover {
            filter: grayscale(0) contrast(1.1);
            transform: scale(1.02);
        }
        /* tailor scroll */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #121827; }
        ::-webkit-scrollbar-thumb { background: #2a3a60; border-radius: 10px; }
    </style>
</body>
</html>
