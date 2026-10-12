<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>S. Abinaya | Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #0b0f19;
            --card-bg: #111827;
            --accent-green: #00ff66;
            --accent-cyan: #00e5ff;
            --text-main: #f3f4f6;
            --text-muted: #9ca3af;
            --border-color: #1f2937;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        /* Cyberpunk Grid Background Effect */
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background-image: linear-gradient(rgba(0, 255, 102, 0.03) 1px, transparent 1px),
                              linear-gradient(90deg, rgba(0, 255, 102, 0.03) 1px, transparent 1px);
            background-size: 30px 30px;
            z-index: -1;
        }

        header {
            position: fixed;
            top: 0; left: 0; width: 100%;
            background-color: rgba(11, 15, 25, 0.85);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 5%;
            z-index: 1000;
        }

        .logo {
            font-family: 'Fira Code', monospace;
            font-size: 1.2rem;
            color: var(--accent-green);
            font-weight: 600;
        }

        .logo span {
            color: var(--accent-cyan);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            text-decoration: none;
            color: var(--text-muted);
            font-size: 0.95rem;
            transition: color 0.3s;
            font-family: 'Fira Code', monospace;
        }

        nav a:hover {
            color: var(--accent-green);
        }

        section {
            padding: 7rem 10% 4rem 10%;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        /* Hero Section */
        #hero {
            text-align: left;
        }

        .terminal-box {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 2.5rem;
            max-width: 850px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            position: relative;
        }

        .terminal-header {
            display: flex;
            gap: 8px;
            margin-bottom: 1.5rem;
        }

        .dot {
            width: 12px; height: 12px;
            border-radius: 50%;
        }
        .dot-red { background-color: #ff5f56; }
        .dot-yellow { background-color: #ffbd2e; }
        .dot-green { background-color: #27c93f; }

        .hero-title {
            font-size: clamp(2rem, 4vw, 3.2rem);
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #fff;
        }

        .hero-title span {
            color: var(--accent-green);
        }

        .hero-subtitle {
            font-family: 'Fira Code', monospace;
            font-size: 1.1rem;
            color: var(--accent-cyan);
            margin-bottom: 1.5rem;
        }

        .hero-desc {
            color: var(--text-muted);
            font-size: 1.05rem;
            line-height: 1.6;
            margin-bottom: 2rem;
        }

        .btn-group {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95rem;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
            font-family: 'Fira Code', monospace;
        }

        .btn-primary {
            background-color: transparent;
            border: 1px solid var(--accent-green);
            color: var(--accent-green);
        }

        .btn-primary:hover {
            background-color: var(--accent-green);
            color: var(--bg-color);
            box-shadow: 0 0 15px rgba(0, 255, 102, 0.4);
        }

        .btn-secondary {
            background-color: transparent;
            border: 1px solid var(--accent-cyan);
            color: var(--accent-cyan);
        }

        .btn-secondary:hover {
            background-color: var(--accent-cyan);
            color: var(--bg-color);
            box-shadow: 0 0 15px rgba(0, 229, 255, 0.4);
        }

        /* Section Titles */
        .section-title {
            font-family: 'Fira Code', monospace;
            font-size: 2rem;
            margin-bottom: 2.5rem;
            color: #fff;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title span {
            color: var(--accent-green);
            font-size: 1.5rem;
        }

        /* About & Education Grid */
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 2rem;
            border-radius: 8px;
            transition: transform 0.3s, border-color 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-green);
        }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #fff;
        }

        .card p, .card li {
            color: var(--text-muted);
            line-height: 1.6;
            font-size: 0.95rem;
        }

        .card ul {
            list-style-type: none;
            padding-left: 0;
        }

        .card ul li {
            position: relative;
            padding-left: 20px;
            margin-bottom: 0.5rem;
        }

        .card ul li::before {
            content: "▹";
            position: absolute;
            left: 0;
            color: var(--accent-green);
        }

        /* Skills Matrix */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .skill-category {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 1.5rem;
            border-radius: 8px;
        }

        .skill-category h4 {
            font-family: 'Fira Code', monospace;
            color: var(--accent-cyan);
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tag {
            background: rgba(0, 255, 102, 0.05);
            border: 1px solid rgba(0, 255, 102, 0.2);
            color: var(--accent-green);
            padding: 0.4rem 0.8rem;
            border-radius: 4px;
            font-size: 0.85rem;
            font-family: 'Fira Code', monospace;
        }

        /* Contact Section */
        .contact-container {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 3rem;
            border-radius: 8px;
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
            width: 100%;
        }

        .contact-container p {
            color: var(--text-muted);
            margin-bottom: 2rem;
            line-height: 1.6;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        footer {
            text-align: center;
            padding: 2rem;
            background-color: var(--bg-color);
            border-top: 1px solid var(--border-color);
            color: var(--text-muted);
            font-family: 'Fira Code', monospace;
            font-size: 0.85rem;
        }

        @media (max-width: 768px) {
            nav ul { display: none; }
            section { padding: 6rem 5% 3rem 5%; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">S.Abinaya<span>()</span></div>
        <nav>
            <ul>
                <li><a href="#hero">&lt;Home&gt;</a></li>
                <li><a href="#about">&lt;About&gt;</a></li>
                <li><a href="#skills">&lt;Skills&gt;</a></li>
                <li><a href="#contact">&lt;Contact&gt;</a></li>
            </ul>
        </nav>
    </header>

    <section id="hero">
        <div class="terminal-box">
            <div class="terminal-header">
                <div class="dot dot-red"></div>
                <div class="dot dot-yellow"></div>
                <div class="dot dot-green"></div>
            </div>
            <p class="hero-subtitle">status: ready_to_compile</p>
            <h1 class="hero-title">Hi, I'm <span>S. Abinaya</span></h1>
            <p class="hero-desc">Aspiring Software Developer & Cybersecurity Enthusiast. Passionate about writing robust code, exploring ethical hacking methodologies, and crafting secure software solutions.</p>
            <div class="btn-group">
                <a href="#contact" class="btn btn-primary"><i class="fas fa-terminal"></i> Initialize Contact</a>
                <a href="https://www.linkedin.com/in/abinaya-s-428371424?utm_source=share_via&utm_content=profile&utm_medium=member_android" target="_blank" class="btn btn-secondary"><i class="fab fa-linkedin"></i> LinkedIn Profile</a>
            </div>
        </div>
    </section>

    <section id="about">
        <h2 class="section-title"><span>01.</span> Background & Education</h2>
        <div class="grid-2">
            <div class="card">
                <h3><i class="fas fa-graduation-cap" style="color: var(--accent-green);"></i> Education</h3>
                <p><strong>Bishop Heber College</strong></p>
                <p>Bachelor of Science (B.Sc.) in Computer Science</p>
                <p style="font-family: 'Fira Code', monospace; color: var(--accent-cyan); margin-top: 0.5rem;">2026 – 2029</p>
            </div>
            <div class="card">
                <h3><i class="fas fa-shield-alt" style="color: var(--accent-cyan);"></i> Core Focus & Ambition</h3>
                <p>Driven by an intense curiosity for system security and software engineering. Aiming to pioneer safe digital infrastructures as a Software Developer with a specialized mastery in Cyber Security.</p>
            </div>
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title"><span>02.</span> Skill Arsenal</h2>
        <div class="skills-grid">
            <div class="skill-category">
                <h4>Languages</h4>
                <div class="skill-tags">
                    <span class="tag">Python</span>
                    <span class="tag">C++</span>
                </div>
            </div>
            <div class="skill-category">
                <h4>Core Concepts</h4>
                <div class="skill-tags">
                    <span class="tag">Computer Science Fundamentals</span>
                    <span class="tag">Technical Coding</span>
                </div>
            </div>
            <div class="skill-category">
                <h4>Security & Domains</h4>
                <div class="skill-tags">
                    <span class="tag">Ethical Hacking</span>
                    <span class="tag">Secure Coding</span>
                    <span class="tag">Cyber Security</span>
                </div>
            </div>
            <div class="skill-category">
                <h4>Professional Traits</h4>
                <div class="skill-tags">
                    <span class="tag">Interpersonal Soft Skills</span>
                    <span class="tag">Problem Solving</span>
                    <span class="tag">Continuous Learning</span>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2 class="section-title" style="justify-content: center;"><span>03.</span> Get In Touch</h2>
        <div class="contact-container">
            <p>I am actively looking for opportunities to grow, collaborate, and build secure solutions. Let's connect!</p>
            <div class="contact-links">
                <a href="mailto:abinaya4468@gmail.com" class="btn btn-primary"><i class="fas fa-envelope"></i> abinaya4468@gmail.com</a>
                <a href="https://www.linkedin.com/in/abinaya-s-428371424?utm_source=share_via&utm_content=profile&utm_medium=member_android" target="_blank" class="btn btn-secondary"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 S. Abinaya. Secure Code, Secure Future.</p>
    </footer>

</body>
</html>
# portfolio-