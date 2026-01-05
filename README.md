<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ClarityFlow | Focus & Productivity Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, sans-serif;
        }

        :root {
            --primary: #4361ee;
            --primary-light: #4895ef;
            --secondary: #3f37c9;
            --accent: #4cc9f0;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --gray: #6c757d;
            --success: #4ade80;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            --transition: all 0.3s ease;
        }

        body {
            background-color: #f9fafc;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header & Navigation */
        header {
            background-color: white;
            box-shadow: var(--shadow);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo i {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-cta {
            background-color: var(--primary);
            color: white;
            padding: 10px 24px;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
        }

        .nav-cta:hover {
            background-color: var(--secondary);
            color: white;
        }

        .mobile-toggle {
            display: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 160px 0 100px;
            background: linear-gradient(135deg, #f0f4ff 0%, #e6f7ff 100%);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 3.5rem;
            color: var(--dark);
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero h1 span {
            color: var(--primary);
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto 40px;
        }

        .hero-btns {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-bottom: 60px;
        }

        .btn-primary {
            background-color: var(--primary);
            color: white;
            padding: 15px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            display: inline-block;
            border: 2px solid var(--primary);
        }

        .btn-primary:hover {
            background-color: var(--secondary);
            border-color: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 15px 25px rgba(67, 97, 238, 0.2);
        }

        .btn-secondary {
            background-color: white;
            color: var(--primary);
            padding: 15px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            display: inline-block;
            border: 2px solid var(--primary);
        }

        .btn-secondary:hover {
            background-color: #f0f4ff;
            transform: translateY(-3px);
        }

        .hero-image {
            max-width: 900px;
            margin: 0 auto;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            border: 1px solid rgba(0, 0, 0, 0.05);
        }

        .hero-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* Features Section */
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark);
            margin-bottom: 15px;
        }

        .section-title p {
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
            font-size: 1.1rem;
        }

        .section-padding {
            padding: 100px 0;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }

        .feature-card {
            background-color: white;
            padding: 40px 30px;
            border-radius: 15px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
            border-top: 5px solid var(--primary);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary-light), var(--primary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            color: white;
            font-size: 1.8rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .feature-card p {
            color: var(--gray);
            margin-bottom: 20px;
        }

        /* Testimonials */
        .testimonials {
            background-color: #f0f7ff;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .testimonial-card {
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: var(--shadow);
            position: relative;
        }

        .testimonial-card:before {
            content: '"';
            position: absolute;
            top: 20px;
            left: 25px;
            font-size: 4rem;
            color: var(--primary-light);
            opacity: 0.2;
            font-family: Georgia, serif;
        }

        .testimonial-content {
            margin-bottom: 20px;
            font-style: italic;
            color: #555;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: #e9ecef;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--primary);
        }

        .author-info h4 {
            color: var(--dark);
            margin-bottom: 5px;
        }

        .author-info p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Pricing Section */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .pricing-card {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .pricing-card:hover {
            transform: translateY(-10px);
        }

        .pricing-card.popular {
            border: 2px solid var(--primary);
            transform: scale(1.05);
        }

        .pricing-card.popular:hover {
            transform: scale(1.05) translateY(-10px);
        }

        .popular-tag {
            position: absolute;
            top: 0;
            right: 30px;
            background-color: var(--primary);
            color: white;
            padding: 8px 20px;
            border-radius: 0 0 10px 10px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .pricing-header {
            padding: 40px 30px 30px;
            text-align: center;
            background: linear-gradient(135deg, #f8f9ff, #f0f4ff);
        }

        .pricing-header h3 {
            font-size: 1.8rem;
            color: var(--dark);
            margin-bottom: 10px;
        }

        .pricing-header p {
            color: var(--gray);
        }

        .price {
            margin: 30px 0;
            color: var(--dark);
        }

        .price-amount {
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--primary);
        }

        .price-period {
            color: var(--gray);
            font-size: 1rem;
        }

        .pricing-features {
            padding: 0 30px 40px;
            list-style: none;
        }

        .pricing-features li {
            padding: 12px 0;
            border-bottom: 1px solid #eee;
            color: #555;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .pricing-features li i {
            color: var(--success);
        }

        .pricing-features li.disabled {
            color: #ccc;
        }

        .pricing-features li.disabled i {
            color: #ddd;
        }

        .pricing-card .btn-primary {
            display: block;
            margin: 30px;
            text-align: center;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 80px 0 40px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 50px;
            margin-bottom: 60px;
        }

        .footer-col h3 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            color: white;
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 15px;
        }

        .footer-col ul li a {
            color: #b0b7c3;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-col ul li a:hover {
            color: white;
            padding-left: 5px;
        }

        .footer-about p {
            color: #b0b7c3;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-5px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #b0b7c3;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .pricing-card.popular {
                transform: none;
            }
            
            .pricing-card.popular:hover {
                transform: translateY(-10px);
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: white;
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
                gap: 20px;
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .mobile-toggle {
                display: block;
            }
            
            .hero-btns {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header>
        <div class="container nav-container">
            <a href="#" class="logo">
                <i class="fas fa-wave-square"></i>
                <span>ClarityFlow</span>
            </a>
            
            <div class="mobile-toggle" id="mobileToggle">
                <i class="fas fa-bars"></i>
            </div>
            
            <div class="nav-links" id="navLinks">
                <a href="#features">Features</a>
                <a href="#testimonials">Testimonials</a>
                <a href="#pricing">Pricing</a>
                <a href="#about">About</a>
                <a href="#" class="nav-cta">Get Started</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Achieve More with <span>Focused Flow</span></h1>
            <p>ClarityFlow combines elegant design with powerful productivity tools to help individuals and teams achieve their most important work without distractions.</p>
            
            <div class="hero-btns">
                <a href="#pricing" class="btn-primary">Start Free Trial</a>
                <a href="#features" class="btn-secondary">See How It Works</a>
            </div>
            
            <div class="hero-image">
                <div style="background: linear-gradient(135deg, var(--primary-light), var(--accent)); height: 400px; display: flex; align-items: center; justify-content: center; color: white;">
                    <div style="text-align: center; padding: 20px;">
                        <i class="fas fa-desktop" style="font-size: 4rem; margin-bottom: 20px;"></i>
                        <h2 style="font-size: 2rem; margin-bottom: 10px;">ClarityFlow Dashboard</h2>
                        <p>Clean interface for focused work</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section-padding" id="features">
        <div class="container">
            <div class="section-title">
                <h2>Designed for Deep Work</h2>
                <p>Powerful features that help you concentrate, organize, and accomplish more in less time.</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>Focus Mode</h3>
                    <p>Block distractions and create the perfect environment for deep work with customizable focus sessions.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-tasks"></i>
                    </div>
                    <h3>Smart Task Manager</h3>
                    <p>Organize projects with intelligent prioritization, deadlines, and progress tracking all in one place.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-network"></i>
                    </div>
                    <h3>Flow Analytics</h3>
                    <p>Understand your work patterns with detailed insights on focus time, productivity peaks, and distractions.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section-padding testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Trusted by Professionals</h2>
                <p>See how ClarityFlow has transformed work habits for individuals and teams.</p>
            </div>
            
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <div class="testimonial-content">
                        "ClarityFlow has completely changed how I approach my workday. The focus mode alone has increased my productivity by 40%. It's like having a personal productivity coach."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">SR</div>
                        <div class="author-info">
                            <h4>Sarah Reynolds</h4>
                            <p>Software Developer</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-content">
                        "As a project manager with a remote team, ClarityFlow keeps us all aligned and focused. The analytics help us identify bottlenecks before they become problems."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">MJ</div>
                        <div class="author-info">
                            <h4>Marcus Johnson</h4>
                            <p>Project Manager</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-content">
                        "The clean interface and intelligent task prioritization help me stay on track with my writing projects. I've never been more consistently productive."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">EC</div>
                        <div class="author-info">
                            <h4>Elena Chen</h4>
                            <p>Content Strategist</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="section-padding" id="pricing">
        <div class="container">
            <div class="section-title">
                <h2>Simple, Transparent Pricing</h2>
                <p>Choose the plan that fits your workflow. All plans include a 14-day free trial.</p>
            </div>
            
            <div class="pricing-grid">
                <div class="pricing-card">
                    <div class="pricing-header">
                        <h3>Basic</h3>
                        <p>Perfect for individuals</p>
                        <div class="price">
                            <span class="price-amount">$9</span>
                            <span class="price-period">/month</span>
                        </div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Focus Mode Timer</li>
                        <li><i class="fas fa-check"></i> Basic Task Management</li>
                        <li><i class="fas fa-check"></i> 5 Projects</li>
                        <li><i class="fas fa-check"></i> Weekly Analytics</li>
                        <li class="disabled"><i class="fas fa-times"></i> Team Collaboration</li>
                        <li class="disabled"><i class="fas fa-times"></i> Advanced Reports</li>
                    </ul>
                    <a href="#" class="btn-primary">Start Free Trial</a>
                </div>
                
                <div class="pricing-card popular">
                    <div class="popular-tag">MOST POPULAR</div>
                    <div class="pricing-header">
                        <h3>Pro</h3>
                        <p>For serious professionals</p>
                        <div class="price">
                            <span class="price-amount">$19</span>
                            <span class="price-period">/month</span>
                        </div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Advanced Focus Tools</li>
                        <li><i class="fas fa-check"></i> Smart Task Management</li>
                        <li><i class="fas fa-check"></i> Unlimited Projects</li>
                        <li><i class="fas fa-check"></i> Daily Analytics & Reports</li>
                        <li><i class="fas fa-check"></i> Basic Team Features</li>
                        <li><i class="fas fa-check"></i> Priority Support</li>
                    </ul>
                    <a href="#" class="btn-primary">Start Free Trial</a>
                </div>
                
                <div class="pricing-card">
                    <div class="pricing-header">
                        <h3>Team</h3>
                        <p>For collaborative workflows</p>
                        <div class="price">
                            <span class="price-amount">$39</span>
                            <span class="price-period">/user/month</span>
                        </div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Everything in Pro</li>
                        <li><i class="fas fa-check"></i> Advanced Team Collaboration</li>
                        <li><i class="fas fa-check"></i> Admin Controls</li>
                        <li><i class="fas fa-check"></i> Real-time Analytics</li>
                        <li><i class="fas fa-check"></i> Custom Integrations</li>
                        <li><i class="fas fa-check"></i> Dedicated Account Manager</li>
                    </ul>
                    <a href="#" class="btn-primary">Start Free Trial</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="about">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col footer-about">
                    <a href="#" class="logo" style="color: white; margin-bottom: 20px; display: inline-block;">
                        <i class="fas fa-wave-square"></i>
                        <span>ClarityFlow</span>
                    </a>
                    <p>We build tools that help people do their most meaningful work with focus, clarity, and purpose.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h3>Product</h3>
                    <ul>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#pricing">Pricing</a></li>
                        <li><a href="#">Integrations</a></li>
                        <li><a href="#">Updates</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Resources</h3>
                    <ul>
                        <li><a href="#">Documentation</a></li>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Tutorials</a></li>
                        <li><a href="#">Support</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Company</h3>
                    <ul>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2026 ClarityFlow. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Navigation Toggle
        const mobileToggle = document.getElementById('mobileToggle');
        const navLinks = document.getElementById('navLinks');
        
        mobileToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            mobileToggle.innerHTML = navLinks.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Close mobile menu if open
                if (navLinks.classList.contains('active')) {
                    navLinks.classList.remove('active');
                    mobileToggle.innerHTML = '<i class="fas fa-bars"></i>';
                }
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Simple animation on scroll
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
        
        // Observe elements for animation
        document.querySelectorAll('.feature-card, .testimonial-card, .pricing-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
