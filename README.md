
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Hyper Flux Studio | Premium Editing Asset Packs</title>
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Font: Plus Jakarta Sans - modern, clean, Proxima-like -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', 'Segoe UI', 'Inter', system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
            background: #0a0a0f;
            color: #f0f0f8;
            line-height: 1.5;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        /* Smooth animated background with blue/pinkish blends - lightweight */
        .bg-smooth {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: radial-gradient(circle at 20% 30%, #0b0b1a, #03030a);
        }

        .bg-smooth::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 40%, rgba(255, 80, 120, 0.2), transparent 60%),
                        radial-gradient(circle at 30% 80%, rgba(80, 150, 255, 0.2), transparent 70%);
            filter: blur(60px);
            opacity: 0.8;
            animation: gentlePulse 12s ease infinite alternate;
            will-change: opacity;
        }

        @keyframes gentlePulse {
            0% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        .subtle-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
            background-image: radial-gradient(rgba(255, 77, 125, 0.06) 1px, transparent 1px);
            background-size: 48px 48px;
        }

        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 1.5rem 1.25rem 3rem;
            position: relative;
            z-index: 2;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            margin-bottom: 2rem;
            margin-top: 0.5rem;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: linear-gradient(135deg, rgba(255, 80, 120, 0.2), rgba(80, 150, 255, 0.2));
            backdrop-filter: blur(8px);
            border-radius: 100px;
            padding: 0.4rem 1.4rem;
            font-size: 0.75rem;
            font-weight: 600;
            border: 1px solid rgba(255, 120, 160, 0.4);
            margin-bottom: 1.2rem;
        }

        h1 {
            font-size: clamp(1.8rem, 6vw, 3.2rem);
            font-weight: 800;
            background: linear-gradient(135deg, #FFFFFF, #ffb3c6, #a0c4ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.02em;
            margin-bottom: 0.6rem;
            line-height: 1.2;
        }

        .hero p {
            font-size: clamp(0.9rem, 4vw, 1.2rem);
            color: #ccccf0;
            max-width: 600px;
            margin: 0 auto;
            padding: 0 0.5rem;
        }

        .offer-sub {
            text-align: center;
            margin-bottom: 2.5rem;
            font-weight: 500;
            font-size: clamp(0.8rem, 3.5vw, 0.95rem);
            color: #cfcfef;
            background: rgba(255, 255, 255, 0.02);
            width: fit-content;
            margin-left: auto;
            margin-right: auto;
            padding: 0.45rem 1.2rem;
            border-radius: 60px;
            backdrop-filter: blur(4px);
        }

        /* Pricing cards grid - fully responsive */
        .pricing-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .card {
            background: rgba(12, 12, 25, 0.7);
            backdrop-filter: blur(12px);
            border-radius: 1.8rem;
            padding: 1.5rem 1.2rem;
            width: min(100%, 320px);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 100, 140, 0.3);
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.5);
            text-align: center;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: rgba(255, 120, 180, 0.7);
            box-shadow: 0 25px 40px -12px rgba(255, 80, 120, 0.25);
            background: rgba(20, 20, 40, 0.8);
        }

        .plan-icon {
            font-size: 2.2rem;
            margin-bottom: 0.4rem;
            background: linear-gradient(145deg, #ff9fbd, #84b4ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .plan-name {
            font-size: clamp(1.4rem, 5vw, 1.8rem);
            font-weight: 700;
            margin-bottom: 0.2rem;
        }

        /* UGX ONLY pricing */
        .price-wrapper {
            margin: 0.6rem 0 0.2rem;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .price-ugx {
            font-size: clamp(1.8rem, 6vw, 2.4rem);
            font-weight: 800;
            background: linear-gradient(135deg, #FFE6A3, #FFB347);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            line-height: 1.2;
            letter-spacing: -0.5px;
        }
        .ugx-symbol {
            font-size: 0.9rem;
            font-weight: 600;
            background: none;
            -webkit-background-clip: unset;
            color: #FFD966;
            margin-right: 4px;
        }
        .price-period {
            font-size: 0.65rem;
            font-weight: 400;
            color: #b9b9e6;
            margin-top: 4px;
            margin-bottom: 0.3rem;
        }
        .bundle-size {
            background: rgba(255, 120, 160, 0.18);
            border-radius: 40px;
            padding: 0.2rem 0.8rem;
            display: inline-block;
            font-size: 0.65rem;
            font-weight: 600;
            color: #ffbfd5;
            margin: 0.5rem 0 0.7rem;
        }
        .feature-list {
            list-style: none;
            text-align: left;
            margin: 0.7rem 0 1rem;
        }
        .feature-list li {
            margin-bottom: 0.5rem;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .feature-list li i {
            width: 18px;
            color: #ff7b9c;
            font-size: 0.75rem;
            flex-shrink: 0;
        }

        /* Installation guide row */
        .install-guide {
            margin-top: 0.7rem;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 1rem;
            padding: 0.45rem 0.3rem;
            font-size: 0.65rem;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            border: 1px solid rgba(255, 140, 170, 0.3);
        }
        .install-guide span {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            color: #ddddff;
            white-space: nowrap;
        }
        .install-guide i {
            font-size: 0.7rem;
            color: #ff9fbd;
        }

        /* Order Now button */
        .order-btn {
            background: linear-gradient(95deg, #ff4d7d, #a05eff);
            border: none;
            padding: 0.65rem 0;
            border-radius: 2rem;
            font-weight: 700;
            font-size: 0.85rem;
            color: white;
            cursor: pointer;
            transition: 0.25s;
            width: 100%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            text-decoration: none;
            box-shadow: 0 6px 14px rgba(255, 77, 125, 0.3);
            margin-top: 0.5rem;
        }
        .order-btn:hover {
            transform: scale(1.02);
            background: linear-gradient(95deg, #ff6b94, #b77aff);
            box-shadow: 0 10px 20px rgba(255, 77, 125, 0.5);
        }

        /* Contact Info Table - fully responsive */
        .contact-table-wrapper {
            margin: 2rem 0 1.2rem;
            background: rgba(10, 10, 25, 0.5);
            backdrop-filter: blur(10px);
            border-radius: 1.5rem;
            padding: 1rem;
            border: 1px solid rgba(255, 120, 160, 0.25);
        }
        .section-title {
            text-align: center;
            font-size: clamp(1rem, 5vw, 1.3rem);
            font-weight: 700;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            background: linear-gradient(135deg, #fff, #ffb7ce);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        .contact-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.8rem;
        }
        .contact-item {
            background: rgba(0, 0, 0, 0.45);
            border-radius: 1rem;
            padding: 0.6rem 1rem;
            min-width: 160px;
            flex: 1 0 auto;
            max-width: 210px;
            display: flex;
            align-items: center;
            gap: 12px;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 100, 150, 0.3);
            transition: 0.2s;
        }
        .contact-item i {
            font-size: 1.4rem;
            background: linear-gradient(145deg, #ff9fbd, #84b4ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            width: 28px;
            text-align: center;
        }
        .contact-info h4 {
            font-size: 0.65rem;
            font-weight: 500;
            opacity: 0.8;
            letter-spacing: 0.3px;
        }
        .contact-info p, .contact-info a {
            font-size: 0.8rem;
            font-weight: 600;
            color: #f0f0ff;
            text-decoration: none;
            word-break: break-word;
        }
        .contact-info a:hover {
            text-decoration: underline;
            color: #ff9fbd;
        }

        .assets-note {
            text-align: center;
            margin: 1rem auto;
            font-size: clamp(0.7rem, 3vw, 0.85rem);
            color: #b5b5e6;
            background: rgba(0, 0, 0, 0.3);
            padding: 0.5rem 1rem;
            border-radius: 2rem;
            width: fit-content;
            backdrop-filter: blur(5px);
            max-width: 90%;
        }
        .footer-note {
            text-align: center;
            font-size: 0.65rem;
            opacity: 0.7;
            margin-top: 1.2rem;
            padding: 0 0.5rem;
            line-height: 1.4;
        }

        /* Extra small devices */
        @media (max-width: 480px) {
            .container {
                padding: 1rem 0.9rem 2rem;
            }
            .card {
                padding: 1.2rem 1rem;
            }
            .feature-list li {
                font-size: 0.75rem;
            }
            .install-guide {
                gap: 6px;
            }
            .install-guide span {
                font-size: 0.6rem;
                white-space: normal;
            }
            .contact-item {
                min-width: 140px;
                padding: 0.5rem 0.8rem;
            }
            .contact-info p, .contact-info a {
                font-size: 0.7rem;
            }
            .order-btn {
                font-size: 0.8rem;
                padding: 0.55rem 0;
            }
        }

        /* Tablet and desktop fine-tuning */
        @media (min-width: 1024px) {
            .pricing-grid {
                gap: 2rem;
            }
            .card {
                padding: 1.8rem 1.5rem;
            }
        }

        /* Landscape mode fix */
        @media (max-height: 500px) and (orientation: landscape) {
            .container {
                padding: 0.8rem 1rem 1.5rem;
            }
            .hero {
                margin-bottom: 1rem;
            }
            .pricing-grid {
                margin-bottom: 0.8rem;
            }
        }

        .reveal-on-scroll {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }
        .reveal-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* No lag, smooth performance */
        .card, .order-btn, .contact-item {
            will-change: transform;
        }
    </style>
</head>
<body>
<div class="bg-smooth"></div>
<div class="subtle-grid"></div>

<div class="container">
    <div class="hero reveal-on-scroll">
        <div class="badge">
            <i class="fas fa-crown"></i> HYPER FLUX STUDIO — PRO ASSETS
        </div>
        <h1>Get Full Access to our <br>Premium Editing Assets</h1>
        <p>Create Stunning & Unique Video Productions!</p>
    </div>
    <div class="offer-sub reveal-on-scroll">
        <i class="fas fa-layer-group"></i> 4K+ LUTs · SFX · Transitions · Motion Graphics · 3D Elements
    </div>

    <div class="pricing-grid">
        <!-- Pack 1: Motion Starter (75k UGX) -->
        <div class="card reveal-on-scroll">
            <div class="plan-icon"><i class="fas fa-bolt"></i></div>
            <div class="plan-name">Motion Starter</div>
            <div class="price-wrapper">
                <div class="price-ugx"><span class="ugx-symbol">UGX</span> 75k</div>
                <div class="price-period">one-time payment · lifetime access</div>
            </div>
            <div class="bundle-size"><i class="fas fa-charging-station"></i> 35GB · Dynamic Motion Pack</div>
            <ul class="feature-list">
                <li><i class="fas fa-check-circle"></i> Motion titles & kinetic transitions</li>
                <li><i class="fas fa-check-circle"></i> Essential SFX & cinematic LUTs</li>
                <li><i class="fas fa-check-circle"></i> Drag & drop presets (Ae/Pr/FCP/DaVinci)</li>
                <li><i class="fas fa-check-circle"></i> Commercial license included</li>
            </ul>
            <div class="install-guide">
                <span><i class="fab fa-apple"></i> Mac Install</span>
                <span><i class="fab fa-windows"></i> Windows Install</span>
                <span><i class="fas fa-file-alt"></i> PDF Guide</span>
            </div>
            <a href="https://wa.me/256771794634?text=Hello%21%20I%20want%20the%20Motion%20Starter%20Pack%20%2875k%20UGX%29%20-%2035GB%20Motion%20Assets.%20Please%20share%20payment%20details%20and%20installation%20guide." class="order-btn" target="_blank" rel="noopener noreferrer">
                <i class="fas fa-shopping-cart"></i> Order Now
            </a>
        </div>

        <!-- Pack 2: Pro Pack (120k UGX) -->
        <div class="card reveal-on-scroll">
            <div class="plan-icon"><i class="fas fa-star"></i></div>
            <div class="plan-name">Pro Pack</div>
            <div class="price-wrapper">
                <div class="price-ugx"><span class="ugx-symbol">UGX</span> 120k</div>
                <div class="price-period">one-time payment · lifetime access</div>
            </div>
            <div class="bundle-size"><i class="fas fa-database"></i> 100GB · Ultimate Creator Bundle</div>
            <ul class="feature-list">
                <li><i class="fas fa-check-circle"></i> 100GB: 4K overlays, transitions, SFX, LUTs</li>
                <li><i class="fas fa-check-circle"></i> Advanced motion graphics pack</li>
                <li><i class="fas fa-check-circle"></i> Sound FX library & Foley pack</li>
                <li><i class="fas fa-check-circle"></i> Full commercial & social media license</li>
            </ul>
            <div class="install-guide">
                <span><i class="fab fa-apple"></i> Mac + Win</span>
                <span><i class="fas fa-video"></i> Video Tutorials</span>
            </div>
            <a href="https://wa.me/256771794634?text=I%20want%20the%20Pro%20Pack%20%28120k%20UGX%29%20-%20100GB%20Bundle.%20Send%20payment%20details%20and%20installation%20guide." class="order-btn" target="_blank" rel="noopener noreferrer">
                <i class="fas fa-shopping-cart"></i> Order Now
            </a>
        </div>

        <!-- Pack 3: Expert Vault (250k UGX) -->
        <div class="card reveal-on-scroll">
            <div class="plan-icon"><i class="fas fa-crown"></i></div>
            <div class="plan-name">Expert Vault</div>
            <div class="price-wrapper">
                <div class="price-ugx"><span class="ugx-symbol">UGX</span> 250k</div>
                <div class="price-period">one-time payment · full access + future updates</div>
            </div>
            <div class="bundle-size"><i class="fas fa-hard-drive"></i> 600GB · Complete Professional Suite</div>
            <ul class="feature-list">
                <li><i class="fas fa-check-circle"></i> Full 600GB assets: all packs + motion library</li>
                <li><i class="fas fa-check-circle"></i> Lifetime updates</li>
                <li><i class="fas fa-check-circle"></i> Extended multi-user license (team)</li>
                <li><i class="fas fa-trophy"></i> Priority support + custom asset requests</li>
            </ul>
            <div class="install-guide">
                <span><i class="fab fa-apple"></i> Mac Setup</span>
                <span><i class="fab fa-windows"></i> Win Setup</span>
                <span><i class="fas fa-headset"></i> 1-on-1 Help</span>
            </div>
            <a href="https://wa.me/256771794634?text=I%20need%20the%20Expert%20Vault%20%28250k%20UGX%29%20-%20600GB%20Complete%20Suite.%20Please%20share%20payment%20and%20installation%20details." class="order-btn" target="_blank" rel="noopener noreferrer">
                <i class="fas fa-shopping-cart"></i> Order Now
            </a>
        </div>
    </div>

    <!-- installation guide blurb -->
    <div class="assets-note reveal-on-scroll">
        <i class="fas fa-microchip"></i> Building a professional workflow with latest features — AI tools, 3D assets, motion array style. 
        <strong>Installation guides included for both Mac & Windows (PDF + video).</strong>
    </div>

    <!-- Contact Info Table (WhatsApp, Telegram, Call) -->
    <div class="contact-table-wrapper reveal-on-scroll">
        <div class="section-title">
            <i class="fas fa-address-card"></i> Get in touch — instant support
        </div>
        <div class="contact-grid">
            <div class="contact-item">
                <i class="fab fa-whatsapp"></i>
                <div class="contact-info">
                    <h4>WHATSAPP</h4>
                    <a href="https://wa.me/256771794634" target="_blank" rel="noopener noreferrer">+256 771 794 634</a>
                </div>
            </div>
            <div class="contact-item">
                <i class="fab fa-telegram-plane"></i>
                <div class="contact-info">
                    <h4>TELEGRAM</h4>
                    <a href="https://t.me/habra_edits" target="_blank" rel="noopener noreferrer">@habra_edits</a>
                </div>
            </div>
            <div class="contact-item">
                <i class="fas fa-phone-alt"></i>
                <div class="contact-info">
                    <h4>CALL / SUPPORT</h4>
                    <a href="tel:+256200927763">+256 200 927 763</a>
                </div>
            </div>
            <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <div class="contact-info">
                    <h4>EMAIL</h4>
                    <p>assets@hyperflux.studio</p>
                </div>
            </div>
        </div>
    </div>

    <div class="footer-note reveal-on-scroll">
        <i class="fas fa-shield-alt"></i> Secure checkout via WhatsApp · Instant delivery after payment · Accepting Mobile Money (MTN, Airtel) & Bank Transfer
        <br>© Hyper Flux Studio — elevate every frame. Installation guides included for each pack.
    </div>
</div>

<!-- scroll reveal lightweight with Intersection Observer -->
<script>
    (function() {
        const elements = document.querySelectorAll('.reveal-on-scroll');
        if (elements.length) {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.08, rootMargin: "0px 0px -15px 0px" });
            elements.forEach(el => observer.observe(el));
            // Also trigger for any already visible
            window.addEventListener('load', () => {
                elements.forEach(el => {
                    const rect = el.getBoundingClientRect();
                    if (rect.top < window.innerHeight - 40) {
                        el.classList.add('visible');
                    }
                });
            });
        }
    })();
</script>
</body>
</html>
