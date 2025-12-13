<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GameHub - Your Gaming Universe</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            color: #fff;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #4ecdc4;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%231a1a2e" width="1200" height="800"/><circle cx="200" cy="200" r="3" fill="%23fff" opacity="0.8"/><circle cx="800" cy="300" r="2" fill="%23fff" opacity="0.6"/><circle cx="600" cy="150" r="4" fill="%23fff" opacity="0.9"/><circle cx="1000" cy="400" r="2" fill="%23fff" opacity="0.7"/></svg>') no-repeat center;
            background-size: cover;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px #ff6b6b; }
            to { text-shadow: 0 0 30px #4ecdc4, 0 0 40px #4ecdc4; }
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.2rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        /* Games Section */
        .games {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .game-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            backdrop-filter: blur(10px);
        }

        .game-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .game-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
        }

        .game-info {
            padding: 1.5rem;
        }

        .game-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .game-description {
            opacity: 0.8;
            margin-bottom: 1rem;
        }

        .play-button {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            color: white;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .play-button:hover {
            transform: scale(1.05);
        }

        /* Features Section */
        .features {
            background: rgba(0, 0, 0, 0.5);
            padding: 5rem 2rem;
        }

        .features-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .feature {
            text-align: center;
            padding: 2rem;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        /* Footer */
        footer {
            background: #000;
            padding: 3rem 2rem;
            text-align: center;
        }

        .social-links {
            margin-bottom: 2rem;
        }

        .social-links a {
            color: #fff;
            font-size: 2rem;
            margin: 0 1rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #4ecdc4;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">🎮 GameHub</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#games">Games</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Welcome to GameHub</h1>
            <p>Discover amazing games and join millions of players</p>
            <a href="#games" class="cta-button">Explore Games</a>
        </div>
    </section>

    <!-- Games Section -->
    <section class="games" id="games">
        <h2 class="section-title">Popular Games</h2>
        <div class="games-grid">
            <div class="game-card">
                <div class="game-image">🚀</div>
                <div class="game-info">
                    <h3 class="game-title">Space Adventure</h3>
                    <p class="game-description">Explore the galaxy in this epic space adventure game.</p>
                    <button class="play-button" onclick="playGame('space')">Play Now</button>
                </div>
            </div>
            
            <div class="game-card">
                <div class="game-image">⚔️</div>
                <div class="game-info">
                    <h3 class="game-title">Knight's Quest</h3>
                    <p class="game-description">Embark on a medieval adventure filled with dragons and magic.</p>
                    <button class="play-button" onclick="playGame('knight')">Play Now</button>
                </div>
            </div>
            
            <div class="game-card">
                <div class="game-image">🏎️</div>
                <div class="game-info">
                    <h3 class="game-title">Racing Thunder</h3>
                    <p class="game-description">Feel the speed in this high-octane racing experience.</p>
                    <button class="play-button" onclick="playGame('racing')">Play Now</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <h2 class="section-title">Why Choose GameHub?</h2>
        <div class="features-grid">
            <div class="feature">
                <div class="feature-icon">🎯</div>
                <h3>Wide Selection</h3>
                <p>Hundreds of games across all genres</p>
            </div>
            <div class="feature">
                <div class="feature-icon">⚡</div>
                <h3>Instant Play</h3>
                <p>No downloads required - play instantly</p>
            </div>
            <div class="feature">
                <div class="feature-icon">🏆</div>
                <h3>Leaderboards</h3>
                <p>Compete with players worldwide</p>
            </div>
            <div class="feature">
                <div class="feature-icon">🎮</div>
                <h3>Multiplayer</h3>
                <p>Play with friends or make new ones</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="social-links">
            <a href="#">📘</a>
            <a href="#">🐦</a>
            <a href="#">📷</a>
            <a href="#">🎥</a>
        </div>
        <p>&copy; 2025 GameHub. All rights reserved. | Contact: info@gamehub.com</p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Game play function
        function playGame(gameType) {
            alert(`🎮 Starting ${gameType} game... This would normally load your game!`);
            // Here you would typically redirect to the actual game or load it
            console.log(`Game loaded: ${gameType}`);
        }

        // Add parallax effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            hero.style.transform = `translateY(${scrolled * 0.5}px)`;
        });

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.game-card, .feature').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
