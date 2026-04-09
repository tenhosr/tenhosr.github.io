
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notes</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #0a0a0a;
            --bg-secondary: #141414;
            --bg-tertiary: #1a1a1a;
            --text-primary: #ffffff;
            --text-secondary: #a0a0a0;
            --text-tertiary: #6b6b6b;
            --accent: #4f9ff0;
            --accent-subtle: rgba(79, 159, 240, 0.1);
            --border: rgba(255, 255, 255, 0.08);
            --border-subtle: rgba(255, 255, 255, 0.04);
            --spacing-xs: 0.5rem;
            --spacing-sm: 1rem;
            --spacing-md: 1.5rem;
            --spacing-lg: 2.5rem;
            --spacing-xl: 4rem;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: "SF Pro Text", -apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            font-size: 15px;
            -webkit-font-smoothing: antialiased;
            letter-spacing: -0.3px;
        }

        /* Header */
        header {
            padding: var(--spacing-lg) 0;
            border-bottom: 1px solid var(--border);
            background: var(--bg-primary);
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
            background: rgba(10, 10, 10, 0.8);
        }

        .header-content {
            max-width: 700px;
            margin: 0 auto;
            padding: 0 var(--spacing-lg);
        }

        .logo {
            font-size: 0.95rem;
            font-weight: 500;
            letter-spacing: 0.8px;
            color: var(--text-primary);
            text-transform: uppercase;
        }

        nav {
            display: none;
        }

        /* Hero */
        .hero {
            max-width: 700px;
            margin: 0 auto;
            padding: calc(var(--spacing-xl) * 1.5) var(--spacing-lg) var(--spacing-xl);
            animation: fadeInUp 0.8s ease-out 0.1s both;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 2.8rem;
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: var(--spacing-md);
            letter-spacing: -0.5px;
            color: var(--text-primary);
        }

        .hero p {
            font-size: 1rem;
            color: var(--text-secondary);
            line-height: 1.7;
            margin: 0;
        }

        /* Featured Post */
        .featured {
            max-width: 700px;
            margin: var(--spacing-xl) auto;
            padding: 0 var(--spacing-lg);
        }

        .featured-card {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
            animation: fadeInUp 0.8s ease-out 0.2s both;
            backdrop-filter: blur(10px);
            position: relative;
        }

        .featured-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, var(--accent-subtle) 0%, transparent 100%);
            pointer-events: none;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .featured-card:hover {
            border-color: var(--accent);
            box-shadow: 0 20px 60px rgba(79, 159, 240, 0.1);
        }

        .featured-card:hover::before {
            opacity: 1;
        }

        .featured-image {
            display: none;
        }

        .featured-content {
            padding: var(--spacing-lg);
            position: relative;
            z-index: 2;
        }

        .featured-tag {
            display: none;
        }

        .featured-content h2 {
            font-size: 1.4rem;
            margin-bottom: var(--spacing-md);
            line-height: 1.3;
            font-weight: 600;
        }

        .featured-content p {
            color: var(--text-secondary);
            margin-bottom: var(--spacing-md);
            line-height: 1.7;
            font-size: 0.95rem;
        }

        .featured-meta {
            display: flex;
            gap: var(--spacing-md);
            font-size: 0.8rem;
            color: var(--text-tertiary);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* Posts Section */
        .posts-section {
            max-width: 700px;
            margin: var(--spacing-xl) auto;
            padding: 0 var(--spacing-lg);
        }

        .section-title {
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: var(--spacing-lg);
            color: var(--text-secondary);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .posts-grid {
            display: flex;
            flex-direction: column;
            gap: var(--spacing-md);
        }

        .post-card {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-left: 2px solid transparent;
            border-radius: 8px;
            overflow: hidden;
            transition: all 0.2s ease;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
            padding: var(--spacing-md);
            cursor: pointer;
            position: relative;
            backdrop-filter: blur(10px);
        }

        .post-card::before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--accent);
            opacity: 0;
            transition: opacity 0.2s ease;
        }

        .post-card:nth-child(1) { animation-delay: 0.3s; }
        .post-card:nth-child(2) { animation-delay: 0.4s; }
        .post-card:nth-child(3) { animation-delay: 0.5s; }

        .post-card:hover {
            border-color: var(--border);
            background: var(--bg-tertiary);
            transform: translateX(2px);
        }

        .post-card:hover::before {
            opacity: 1;
        }

        .post-thumbnail {
            display: none;
        }

        .post-body {
            padding: 0;
            position: relative;
            z-index: 2;
        }

        .post-card h3 {
            font-size: 1.05rem;
            margin-bottom: var(--spacing-sm);
            line-height: 1.4;
            font-weight: 600;
        }

        .post-card p {
            font-size: 0.9rem;
            color: var(--text-secondary);
            margin-bottom: var(--spacing-md);
            line-height: 1.6;
        }

        .post-date {
            font-size: 0.75rem;
            color: var(--text-tertiary);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* Footer */
        footer {
            background: transparent;
            border-top: 1px solid var(--border);
            margin-top: var(--spacing-xl);
            padding: var(--spacing-xl) var(--spacing-lg);
        }

        .footer-content {
            display: none;
        }

        .footer-bottom {
            max-width: 700px;
            margin: 0 auto;
            text-align: center;
            padding: 0;
            border-top: none;
            color: var(--text-secondary);
            font-size: 0.85rem;
            line-height: 1.6;
        }

        .footer-bottom a {
            color: var(--accent);
            text-decoration: none;
            transition: opacity 0.2s;
            border-bottom: 1px solid rgba(79, 159, 240, 0.3);
            padding-bottom: 1px;
        }

        .footer-bottom a:hover {
            opacity: 0.8;
            border-bottom-color: var(--accent);
        }

        /* Responsive */
        @media (max-width: 640px) {
            .hero h1 {
                font-size: 2rem;
            }

            .featured-content {
                padding: var(--spacing-md);
            }

            .post-card {
                padding: var(--spacing-md);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-content">
            <div class="logo">letters</div>
        </div>
    </header>

    <!-- Hero -->
    <section class="hero" id="home">
        <h1>Letters</h1>
        <p>thoughts, observations, and small discoveries</p>
    </section>

    <!-- Featured Post -->
    <section class="featured" id="posts">
        <div class="featured-card">
            <div class="featured-content">
                <h2>The Art of Writing Without an Audience</h2>
                <p>Why some of the best writing happens when you stop worrying about who's reading. A reflection on authenticity, vulnerability, and finding your voice.</p>
                <div class="featured-meta">
                    <span>March 28</span>
                    <span>8 min</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Posts Grid -->
    <section class="posts-section">
        <h2 class="section-title">Recent</h2>
        <div class="posts-grid">
            <div class="post-card">
                <div class="post-body">
                    <h3>Morning Rituals That Changed My Life</h3>
                    <p>Three small habits that somehow made everything better. Not the usual productivity tips—just things that stuck.</p>
                    <div class="post-date">March 22 • 6 min</div>
                </div>
            </div>

            <div class="post-card">
                <div class="post-body">
                    <h3>On Slowing Down in a Fast World</h3>
                    <p>A love letter to quiet moments. Why less is actually more, and how I finally learned to sit still.</p>
                    <div class="post-date">March 15 • 7 min</div>
                </div>
            </div>

            <div class="post-card">
                <div class="post-body">
                    <h3>Creating Space for Creativity</h3>
                    <p>What I learned about making things when you remove the pressure to be perfect. Messy, honest, and real.</p>
                    <div class="post-date">March 8 • 9 min</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-bottom">
            <p>you can find me on <a href="#">twitter</a> or <a href="#">email</a></p>
        </div>
    </footer>

    <script>
        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');
                if (href !== '#' && document.querySelector(href)) {
                    e.preventDefault();
                    document.querySelector(href).scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Stagger card animations on scroll
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

        document.querySelectorAll('.post-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>