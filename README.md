<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <style>
        @keyframes glitch {
            0% {
                transform: translate(0);
                text-shadow: -2px 2px #0ff;
            }
            25% {
                transform: translate(-2px, 2px);
                text-shadow: 2px -2px #f0f;
            }
            50% {
                transform: translate(2px, -2px);
                text-shadow: 2px 2px #0ff;
            }
            75% {
                transform: translate(-2px, -2px);
                text-shadow: -2px -2px #f0f;
            }
            100% {
                transform: translate(0);
                text-shadow: -2px 2px #0ff;
            }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        body {
            background: #0a0a0a;
            color: #fff;
            font-family: 'Courier New', monospace;
            line-height: 1.6;
            margin: 0;
            padding: 40px;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
        }

        .header {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .title {
            font-size: 3.5em;
            margin: 0;
            animation: glitch 3s infinite;
            color: #0ff;
            text-transform: uppercase;
            letter-spacing: 5px;
        }

        .subtitle {
            font-size: 1.2em;
            color: #f0f;
            margin-top: 10px;
            overflow: hidden;
            white-space: nowrap;
            animation: typing 3.5s steps(40, end);
        }

        .section {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 40px;
            border: 1px solid #0ff;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.2);
            transition: transform 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.3);
        }

        .section-title {
            color: #0ff;
            font-size: 1.8em;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill-card {
            background: rgba(0, 255, 255, 0.05);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #0ff;
            animation: pulse 2s infinite;
        }

        .project-card {
            background: rgba(255, 0, 255, 0.05);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border: 1px solid #f0f;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: scale(1.02);
            box-shadow: 0 0 20px rgba(255, 0, 255, 0.2);
        }

        .stats {
            display: flex;
            justify-content: space-around;
            margin-top: 40px;
        }

        .stat-item {
            text-align: center;
            animation: float 6s ease-in-out infinite;
        }

        .stat-number {
            font-size: 2.5em;
            color: #0ff;
            margin: 0;
        }

        .contact {
            text-align: center;
            margin-top: 60px;
        }

        .contact-button {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, #0ff, #f0f);
            color: #000;
            text-decoration: none;
            border-radius: 25px;
            font-weight: bold;
            transition: all 0.3s ease;
            margin: 10px;
        }

        .contact-button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }

        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrixCanvas"></canvas>
    <div class="container">
        <header class="header">
            <h1 class="title">Focus</h1>
            <p class="subtitle">Cybersécurité • Innovation • Détermination</p>
        </header>

        <section class="section">
            <h2 class="section-title">🌟 Vision</h2>
            <p>Explorer l'inexploré, repousser les limites de la sécurité numérique, et forger un avenir plus sûr pour tous.</p>
            <div class="stats">
                <div class="stat-item">
                    <h3 class="stat-number">1.5K+</h3>
                    <p>Membres de la communauté</p>
                </div>
                <div class="stat-item">
                    <h3 class="stat-number">4K+</h3>
                    <p>Menaces détectées</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🔧 Arsenal Technique</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>Langages</h3>
                    <p>Python • C++ • HTML/CSS</p>
                </div>
                <div class="skill-card">
                    <h3>Outils</h3>
                    <p>Nmap • SQLmap • Wireshark • Burp Suite</p>
                </div>
                <div class="skill-card">
                    <h3>Spécialités</h3>
                    <p>Analyse de vulnérabilités • Bug Bounty • IA de sécurité</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🚀 Projets Phares</h2>
            <div class="project-card">
                <h3>🤖 Robot Détecteur de Vulnérabilités SQL</h3>
                <p>Solution automatisée pour la détection des failles de sécurité dans les applications web.</p>
            </div>
            <div class="project-card">
                <h3>🌐 Bot LinkedIn Intelligent</h3>
                <p>Système d'engagement automatisé connecté à Telegram pour optimiser la visibilité professionnelle.</p>
            </div>
            <div class="project-card">
                <h3>🛡️ Base de Données Anti-Scam</h3>
                <p>Système de protection comprenant plus de 4 000 profils malveillants identifiés et documentés.</p>
            </div>
        </section>

        <div class="contact">
            <a href="https://t.me/lighitmook" class="contact-button">📱 Telegram</a>
        </div>
    </div>

    <script>
        // Matrix rain effect
        const canvas = document.getElementById('matrixCanvas');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const chars = "01";
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = new Array(Math.floor(columns)).fill(1);

        function draw() {
            ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = "#0F0";
            ctx.font = fontSize + "px monospace";
            
            for (let i = 0; i < drops.length; i++) {
                const text = chars.charAt(Math.floor(Math.random() * chars.length));
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        window.setInterval(draw, 33);

        // Responsive canvas
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>
