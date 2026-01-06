<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>East Wind Ltd - Premium Carpentry & Custom Furniture Manufacturing</title>
    <meta name="description" content="East Wind Ltd is a premium carpentry and furniture manufacturing company in Koforidua, Eastern Region, Ghana, specializing in sofas, dining tables, kitchen cabinets, and coffins.">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --wood-brown: #5c4033;
            --warm-beige: #f5e6d3;
            --charcoal: #2c2c2c;
            --cream: #faf8f3;
            --accent-gold: #c9a961;
            --light-gray: #f8f9fa;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.7;
            color: var(--charcoal);
            background-color: var(--cream);
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            font-weight: 700;
        }

        /* Enhanced Navigation with Glassmorphism */
        nav {
            background: rgba(92, 64, 51, 0.85);
            backdrop-filter: blur(20px) saturate(180%);
            -webkit-backdrop-filter: blur(20px) saturate(180%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border-bottom: 1px solid rgba(255,255,255,0.1);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        nav.scrolled {
            padding: 0.7rem 0;
            background: rgba(92, 64, 51, 0.95);
            box-shadow: 0 8px 40px rgba(0,0,0,0.2);
        }

        nav .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 1.7rem;
            font-weight: 700;
            letter-spacing: 3px;
            font-family: 'Playfair Display', serif;
            position: relative;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        nav .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-gold);
            transition: width 0.4s ease;
        }

        nav .logo:hover::after {
            width: 100%;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 0.5px;
            position: relative;
            padding: 0.5rem 0;
        }

        nav a::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 2px;
            background: var(--accent-gold);
            transition: all 0.3s ease;
            transform: translateX(-50%);
        }

        nav a:hover::before {
            width: 100%;
        }

        nav a:hover {
            color: var(--accent-gold);
            transform: translateY(-2px);
        }

        /* Mobile Menu Button */
        .mobile-menu-btn {
            display: none;
            flex-direction: column;
            gap: 6px;
            cursor: pointer;
            padding: 0.5rem;
        }

        .mobile-menu-btn span {
            width: 28px;
            height: 3px;
            background: white;
            border-radius: 3px;
            transition: all 0.3s ease;
        }

        .mobile-menu-btn.active span:nth-child(1) {
            transform: rotate(45deg) translate(8px, 8px);
        }

        .mobile-menu-btn.active span:nth-child(2) {
            opacity: 0;
        }

        .mobile-menu-btn.active span:nth-child(3) {
            transform: rotate(-45deg) translate(8px, -8px);
        }

        /* Enhanced Hero Section with Parallax Effect */
        .hero {
            background: linear-gradient(135deg, rgba(92, 64, 51, 0.88), rgba(44, 44, 44, 0.92)),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1600 900"><defs><linearGradient id="g" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" style="stop-color:%235c4033"/><stop offset="100%" style="stop-color:%232c2c2c"/></linearGradient></defs><rect fill="url(%23g)" width="1600" height="900"/><path opacity="0.15" fill="%23000" d="M0 450L133 400L267 480L400 420L533 500L667 450L800 520L933 470L1067 540L1200 490L1333 560L1467 510L1600 580V900H0Z"/></svg>');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            padding: 220px 2rem 160px;
            text-align: center;
            margin-top: 60px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 30% 50%, rgba(201, 169, 97, 0.15) 0%, transparent 50%);
            animation: pulseGlow 8s ease-in-out infinite;
        }

        @keyframes pulseGlow {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.6; }
        }

        .hero::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveGrid 20s linear infinite;
        }

        @keyframes moveGrid {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            animation: fadeInUp 1.2s ease-out;
        }

        .hero h1 {
            font-size: 4.5rem;
            margin-bottom: 1.5rem;
            text-shadow: 3px 6px 12px rgba(0,0,0,0.7);
            line-height: 1.2;
            letter-spacing: 2px;
            background: linear-gradient(135deg, #ffffff 0%, #f0e6d2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 3s ease-in-out infinite;
        }

        @keyframes shimmer {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.2); }
        }

        .hero .tagline {
            font-size: 1.7rem;
            margin-bottom: 1.5rem;
            color: var(--accent-gold);
            font-weight: 500;
            letter-spacing: 2px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.5);
            animation: fadeInUp 1.2s ease-out 0.2s backwards;
        }

        .hero .products {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            font-weight: 300;
            letter-spacing: 3px;
            animation: fadeInUp 1.2s ease-out 0.4s backwards;
        }

        .hero .description {
            max-width: 900px;
            margin: 0 auto 3rem;
            font-size: 1.15rem;
            line-height: 1.9;
            font-weight: 300;
            animation: fadeInUp 1.2s ease-out 0.6s backwards;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1.2s ease-out 0.8s backwards;
        }

        .btn {
            padding: 1.2rem 3rem;
            font-size: 1.05rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            display: inline-block;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255,255,255,0.2);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--accent-gold), #d4b76a);
            color: var(--charcoal);
            box-shadow: 0 8px 25px rgba(201, 169, 97, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 35px rgba(201, 169, 97, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: white;
            color: var(--wood-brown);
            transform: translateY(-4px);
            box-shadow: 0 8px 25px rgba(255,255,255,0.3);
        }

        /* Floating Scroll Indicator */
        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        .scroll-indicator::before {
            content: '↓';
            font-size: 2rem;
            color: rgba(255,255,255,0.7);
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-20px); }
            60% { transform: translateX(-50%) translateY(-10px); }
        }

        /* Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Section Styles with Intersection Observer Ready */
        section {
            padding: 120px 2rem;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .section-title {
            text-align: center;
            font-size: 3.2rem;
            margin-bottom: 1.5rem;
            color: var(--wood-brown);
            letter-spacing: 2px;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, transparent, var(--accent-gold), transparent);
            border-radius: 2px;
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.3rem;
            color: #666;
            margin-bottom: 5rem;
            font-weight: 300;
        }

        /* Enhanced Feature Cards with 3D Effect */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 4rem;
            perspective: 1000px;
        }

        .feature-card {
            background: white;
            padding: 3rem 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            text-align: center;
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(92, 64, 51, 0.05);
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(201, 169, 97, 0.1), transparent);
            transition: left 0.7s;
        }

        .feature-card:hover::before {
            left: 100%;
        }

        .feature-card:hover {
            transform: translateY(-15px) rotateX(5deg);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            border-color: var(--accent-gold);
        }

        .feature-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            filter: drop-shadow(0 5px 15px rgba(0,0,0,0.1));
            transition: transform 0.4s ease;
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.15) rotateY(360deg);
        }

        .feature-card h3 {
            color: var(--wood-brown);
            margin-bottom: 1rem;
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .feature-card:hover h3 {
            color: var(--accent-gold);
        }

        .feature-card p {
            color: #666;
            font-size: 1.05rem;
            line-height: 1.8;
        }

        /* Enhanced Gallery with Advanced Filters */
        .gallery-container {
            margin-top: 4rem;
        }

        .gallery-tabs {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .gallery-tab {
            padding: 1rem 2.5rem;
            background: white;
            border: 2px solid var(--wood-brown);
            color: var(--wood-brown);
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            font-weight: 600;
            font-size: 1rem;
            letter-spacing: 0.5px;
            position: relative;
            overflow: hidden;
        }

        .gallery-tab::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: var(--wood-brown);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.5s, height 0.5s;
            z-index: 0;
        }

        .gallery-tab:hover::before {
            width: 300px;
            height: 300px;
        }

        .gallery-tab:hover {
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(92, 64, 51, 0.3);
        }

        .gallery-tab span {
            position: relative;
            z-index: 1;
        }

        .gallery-tab.active {
            background: var(--wood-brown);
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(92, 64, 51, 0.4);
        }

        .gallery-tab.active::before {
            width: 300px;
            height: 300px;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .gallery-item {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.12);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
            aspect-ratio: 4/3;
            background: linear-gradient(135deg, #5c4033, #3d2b23);
        }

        .gallery-item.hidden {
            display: none;
        }

        .gallery-item:hover {
            transform: scale(1.05) translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.25);
            z-index: 10;
        }

        .gallery-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            filter: brightness(0.95);
        }

        .gallery-item:hover .gallery-image {
            transform: scale(1.15);
            filter: brightness(1.05);
        }

        .gallery-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.95), rgba(0,0,0,0.3));
            padding: 2.5rem 2rem 2rem;
            transform: translateY(100%);
            transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .gallery-item:hover .gallery-overlay {
            transform: translateY(0);
        }

        .gallery-overlay h4 {
            color: white;
            font-size: 1.4rem;
            margin-bottom: 0.7rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .gallery-overlay p {
            color: rgba(255,255,255,0.9);
            font-size: 1rem;
            line-height: 1.6;
        }

        /* Enhanced Products Section */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 3rem;
            margin-top: 5rem;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(92, 64, 51, 0.08);
            position: relative;
        }

        .product-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, transparent 0%, rgba(201, 169, 97, 0.05) 100%);
            opacity: 0;
            transition: opacity 0.4s;
            pointer-events: none;
        }

        .product-card:hover {
            transform: translateY(-12px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
        }

        .product-card:hover::after {
            opacity: 1;
        }

        .product-image {
            height: 300px;
            background: linear-gradient(135deg, var(--wood-brown), var(--charcoal));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 5rem;
            position: relative;
            overflow: hidden;
        }

        .product-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.15) 50%, transparent 70%);
            transform: rotate(45deg);
            transition: all 0.8s;
        }

        .product-card:hover .product-image::before {
            left: 100%;
        }

        .product-content {
            padding: 2.5rem;
        }

        .product-card h3 {
            color: var(--wood-brown);
            margin-bottom: 1.2rem;
            font-size: 1.7rem;
            transition: color 0.3s;
        }

        .product-card:hover h3 {
            color: var(--accent-gold);
        }

        .product-card p {
            color: #666;
            line-height: 1.9;
            font-size: 1.05rem;
        }

        /* Enhanced About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: start;
            margin-top: 5rem;
        }

        .about-text h3 {
            color: var(--wood-brown);
            margin-bottom: 2rem;
            font-size: 2.2rem;
            position: relative;
            padding-bottom: 1rem;
        }

        .about-text h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 4px;
            background: var(--accent-gold);
            border-radius: 2px;
        }

        .about-text p {
            margin-bottom: 1.8rem;
            line-height: 2;
            color: #555;
            font-size: 1.05rem;
        }

        .mission-vision-box {
            background: white;
            padding: 2.5rem;
            border-radius: 16px;
            margin-bottom: 2rem;
            box-shadow: 0 8px 30px rgba(0,0,0,0.08);
            border-left: 5px solid var(--accent-gold);
            transition: all 0.4s ease;
        }

        .mission-vision-box:hover {
            transform: translateX(10px);
            box-shadow: 0 12px 40px rgba(0,0,0,0.12);
        }

        .mission-vision-box strong {
            color: var(--wood-brown);
            font-size: 1.2rem;
            display: block;
            margin-bottom: 0.8rem;
        }

        .values-list {
            list-style: none;
            margin-top: 2rem;
        }

        .values-list li {
            padding: 1.2rem 0;
            padding-left: 3rem;
            position: relative;
            font-size: 1.05rem;
            color: #555;
            transition: all 0.3s ease;
        }

        .values-list li:hover {
            padding-left: 3.5rem;
            color: var(--wood-brown);
        }

        .values-list li:before {
            content: "✓";
            position: absolute;
            left: 0;
            color: var(--accent-gold);
            font-weight: bold;
            font-size: 1.8rem;
            transition: transform 0.3s ease;
        }

        .values-list li:hover:before {
            transform: scale(1.2) rotate(360deg);
        }

        /* Enhanced Contact Section */
        .contact-section {
            background: linear-gradient(135deg, var(--wood-brown), #4a3329);
            color: white;
            position: relative;
            overflow: hidden;
        }

        .contact-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1600 900"><path opacity="0.05" fill="%23fff" d="M0 450L133 400L267 480L400 420L533 500L667 450L800 520L933 470L1067 540L1200 490L1333 560L1467 510L1600 580V900H0Z"/></svg>');
            background-size: cover;
        }

        .contact-section .section-title {
            color: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 3rem;
            margin-top: 5rem;
            position: relative;
            z-index: 1;
        }

        .contact-card {
            background: rgba(255,255,255,0.12);
            backdrop-filter: blur(20px) saturate(180%);
            -webkit-backdrop-filter: blur(20px) saturate(180%);
            padding: 3rem;
            border-radius: 20px;
            text-align: center;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255,255,255,0.15);
            position: relative;
            overflow: hidden;
        }

        .contact-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 10%, transparent 50%);
            opacity: 0;
            transition: opacity 0.4s;
        }

        .contact-card:hover::before {
            opacity: 1;
        }

        .contact-card:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        .contact-card .icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            color: var(--accent-gold);
            filter: drop-shadow(0 5px 15px rgba(0,0,0,0.3));
            transition: transform 0.4s ease;
        }

        .contact-card:hover .icon {
            transform: scale(1.15) rotateY(360deg);
        }

        .contact-card h3 {
            margin-bottom: 1.2rem;
            font-size: 1.6rem;
        }

        .contact-card a {
            color: white;
            text-decoration: none;
            transition: all 0.3s;
            position: relative;
        }

        .contact-card a::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-gold);
            transition: width 0.3s;
        }

        .contact-card a:hover::after {
            width: 100%;
        }

        .contact-card a:hover {
            color: var(--accent-gold);
        }

        /* Enhanced Custom Order Section */
        .custom-order-section {
            background: white;
            padding: 5rem 3rem;
            border-radius: 24px;
            margin-top: 5rem;
            text-align: center;
            box-shadow: 0 15px 60px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }

        .custom-order-section::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(201, 169, 97, 0.08) 0%, transparent 70%);
        }

        .custom-order-section h3 {
            color: var(--wood-brown);
            margin-bottom: 2rem;
            font-size: 2.5rem;
            position: relative;
            z-index: 1;
        }

        .custom-order-section p {
            max-width: 800px;
            margin: 0 auto 3rem;
            line-height: 2;
            color: #555;
            font-size: 1.15rem;
            position: relative;
            z-index: 1;
        }

        /* Enhanced Footer */
        footer {
            background: var(--charcoal);
            color: white;
            padding: 5rem 2rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--accent-gold), transparent);
        }

        footer .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        footer h3 {
            color: var(--accent-gold);
            margin-bottom: 2rem;
            font-size: 2.2rem;
            letter-spacing: 3px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        footer p {
            margin-bottom: 1rem;
            opacity: 0.9;
            font-size: 1.05rem;
        }

        .footer-divider {
            border: none;
            border-top: 1px solid rgba(255,255,255,0.2);
            margin: 3rem 0 2rem;
        }

        /* Responsive Design */
        @media (max-width: 968px) {
            nav ul {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: rgba(92, 64, 51, 0.98);
                backdrop-filter: blur(20px);
                flex-direction: column;
                justify-content: flex-start;
                padding: 3rem 0;
                transition: left 0.4s cubic-bezier(0.4, 0, 0.2, 1);
                gap: 0;
            }

            nav ul.active {
                left: 0;
            }

            nav ul li {
                width: 100%;
                text-align: center;
                padding: 1.5rem 0;
                border-bottom: 1px solid rgba(255,255,255,0.1);
            }

            .mobile-menu-btn {
                display: flex;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .section-title {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            }

            .products-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 640px) {
            nav .container {
                padding: 0 1.5rem;
            }

            .hero {
                padding: 180px 1.5rem 120px;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .tagline {
                font-size: 1.3rem;
            }

            section {
                padding: 80px 1.5rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .features, .contact-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .cta-buttons {
                flex-direction: column;
                width: 100%;
            }

            .btn {
                width: 100%;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Enhanced Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            animation: fadeInUp 1s ease-out;
        }

        /* Loading Spinner */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Utility Classes */
        .text-gradient {
            background: linear-gradient(135deg, var(--wood-brown), var(--accent-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="container">
            <div class="logo">EAST WIND LTD</div>
            <div class="mobile-menu-btn" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
            <ul id="navMenu">
                <li><a href="#home" onclick="closeMenu()">Home</a></li>
                <li><a href="#products" onclick="closeMenu()">Products</a></li>
                <li><a href="#gallery" onclick="closeMenu()">Gallery</a></li>
                <li><a href="#about" onclick="closeMenu()">About</a></li>
                <li><a href="#contact" onclick="closeMenu()">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Timeless Woodcraft. Built to Last.</h1>
            <p class="tagline">Premium Carpentry & Custom Furniture Manufacturing</p>
            <p class="products">Sofas • Chairs • Dining Tables • Kitchen Cabinets • Coffins</p>
            <p class="description">At East Wind Ltd, we design and manufacture premium wood products that combine strength, comfort, and refined aesthetics. From bespoke living-room furniture to precision-fitted kitchen cabinets and dignified coffin craftsmanship, every piece is made with care, accuracy, and durability in mind.</p>
            <div class="cta-buttons">
                <a href="#contact" class="btn btn-primary">Visit Our Showroom</a>
                <a href="https://wa.me/233208280559" class="btn btn-secondary" target="_blank">Request a Quote</a>
            </div>
        </div>
        <div class="scroll-indicator"></div>
    </section>

    <!-- Why Choose Us -->
    <section>
        <div class="container">
            <h2 class="section-title">Why Clients Choose East Wind Ltd</h2>
            <p class="section-subtitle">Excellence in every detail</p>
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">👨‍🔧</div>
                    <h3>Master Craftsmen</h3>
                    <p>Expert carpenters with years of hands-on experience and meticulous attention to every detail of your project</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌳</div>
                    <h3>Quality Materials</h3>
                    <p>Carefully selected, premium-grade wood and finishing materials for exceptional durability and aesthetics</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">✏️</div>
                    <h3>Custom Designs</h3>
                    <p>Tailored solutions designed specifically to fit your unique space, personal style, and budget requirements</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">✨</div>
                    <h3>Clean Finishing</h3>
                    <p>Impeccable attention to structural integrity, smooth surfaces, and flawless aesthetic presentation</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">⏱️</div>
                    <h3>Reliable Service</h3>
                    <p>Timely project completion, transparent communication, and dedicated professional customer support</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title">Our Portfolio</h2>
            <p class="section-subtitle">Explore our craftsmanship through our completed projects</p>

            <div class="gallery-container">
                <div class="gallery-tabs">
                    <button class="gallery-tab active" onclick="filterGallery('all')"><span>All Products</span></button>
                    <button class="gallery-tab" onclick="filterGallery('furniture')"><span>Furniture</span></button>
                    <button class="gallery-tab" onclick="filterGallery('kitchen')"><span>Kitchen & Cabinets</span></button>
                    <button class="gallery-tab" onclick="filterGallery('coffins')"><span>Coffins</span></button>
                </div>

                <div class="gallery-grid" id="galleryGrid">
                    <!-- Kitchen Cabinet Items -->
                    <div class="gallery-item" data-category="kitchen">
                        <img src="https://i.imgur.com/EXYTTRt.jpeg" alt="Modern Kitchen Cabinet" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Contemporary Kitchen Cabinets</h4>
                            <p>Full kitchen installation with upper and lower cabinets in rich wood finish</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="kitchen">
                        <img src="https://i.imgur.com/Z5CmV5U.jpeg" alt="Kitchen Cabinet Design" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Custom Kitchen Storage</h4>
                            <p>Elegant cabinet design with modern hardware and finishes</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="kitchen">
                        <img src="https://i.imgur.com/uIjfODQ.jpeg" alt="Kitchen Cabinets" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Premium Kitchen Cabinetry</h4>
                            <p>High-quality wooden cabinets with precision craftsmanship</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="kitchen">
                        <img src="https://i.imgur.com/j5w6Pp9.jpeg" alt="Kitchen Cabinet System" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Complete Kitchen Solution</h4>
                            <p>Comprehensive cabinet system with ample storage space</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="kitchen">
                        <img src="https://i.imgur.com/kTEOTkx.jpeg" alt="Modern Kitchen Cabinets" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Modern Kitchen Installation</h4>
                            <p>Sleek and functional kitchen cabinet design</p>
                        </div>
                    </div>

                    <!-- Dining Table Items -->
                    <div class="gallery-item" data-category="furniture">
                        <img src="https://i.imgur.com/8DNlu6j.jpeg" alt="Elegant Dining Table" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Luxury Dining Table Set</h4>
                            <p>Beautifully crafted dining table with matching upholstered chairs</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="furniture">
                        <img src="https://i.imgur.com/zoLIE8d.jpeg" alt="Dining Table" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Classic Dining Collection</h4>
                            <p>Solid wood dining table with elegant chair design</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="furniture">
                        <img src="https://i.imgur.com/Xnoquh7.jpeg" alt="Modern Dining Set" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Contemporary Dining Set</h4>
                            <p>Modern dining furniture perfect for family gatherings</p>
                        </div>
                    </div>

                    <!-- Coffin Items -->
                    <div class="gallery-item" data-category="coffins">
                        <img src="https://i.imgur.com/C6KTJxs.jpeg" alt="Premium Coffin" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Luxury Mahogany Coffin</h4>
                            <p>Hand-polished solid wood with premium interior lining</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="coffins">
                        <img src="https://i.imgur.com/JbMGrTg.jpeg" alt="Designer Coffin" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Custom Designer Coffin</h4>
                            <p>Beautifully crafted with attention to detail and dignity</p>
                        </div>
                    </div>

                    <div class="gallery-item" data-category="coffins">
                        <img src="https://i.imgur.com/91NyXME.jpeg" alt="Classic Coffin" class="gallery-image" loading="lazy">
                        <div class="gallery-overlay">
                            <h4>Premium Classic Coffin</h4>
                            <p>Traditional design with quality finish and respectful craftsmanship</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products">
        <div class="container">
            <h2 class="section-title">Our Product Range</h2>
            <p class="section-subtitle">From concept to completion, we craft it all</p>

            <div class="products-grid">
                <div class="product-card">
                    <div class="product-image">🛋️</div>
                    <div class="product-content">
                        <h3>Living Room Furniture</h3>
                        <p>Elegant sofas, chairs, and entertainment units crafted for comfort and style. Each piece combines structural strength with luxurious upholstery and timeless design.</p>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🍽️</div>
                    <div class="product-content">
                        <h3>Dining Tables & Chairs</h3>
                        <p>Solid hardwood dining sets that become the heart of your home. Built to accommodate family gatherings with grace and durability for generations.</p>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🗄️</div>
                    <div class="product-content">
                        <h3>Kitchen Cabinets</h3>
                        <p>Custom-fitted kitchen solutions with precision measurements, quality hinges, and beautiful finishes. Maximize your storage with style and functionality.</p>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🪦</div>
                    <div class="product-content">
                        <h3>Premium Coffins</h3>
                        <p>Respectfully crafted coffins with meticulous attention to detail. We honor your loved ones with dignified craftsmanship and beautiful finishing.</p>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🚪</div>
                    <div class="product-content">
                        <h3>Doors & Windows</h3>
                        <p>Solid wood doors and window frames built for security and elegance. Custom designs that complement your architectural vision.</p>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">📚</div>
                    <div class="product-content">
                        <h3>Custom Shelving</h3>
                        <p>Bespoke shelving systems, bookcases, and storage solutions tailored to your space. Functional art that organizes and beautifies your interiors.</p>
                    </div>
                </div>
            </div>

            <div class="custom-order-section">
                <h3>Need Something Custom?</h3>
                <p>Every space is unique, and so are your needs. Whether you have a specific design in mind or need expert guidance, our team is ready to bring your vision to life with precision and care.</p>
                <a href="https://wa.me/233208280559" class="btn btn-primary" target="_blank">Start Your Custom Project</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title">About East Wind Ltd</h2>
            <p class="section-subtitle">Crafting excellence since inception</p>

            <div class="about-content">
                <div class="about-text">
                    <h3>Our Story</h3>
                    <p>East Wind Ltd was founded on a simple principle: exceptional craftsmanship never goes out of style. Located in Koforidua, Eastern Region, Ghana, we've built our reputation on quality, integrity, and attention to detail.</p>

                    <p>Our workshop combines traditional woodworking techniques with modern precision tools, ensuring each piece meets the highest standards of quality and durability. From family dining tables to complete kitchen installations, we approach every project with the same dedication to excellence.</p>

                    <div class="mission-vision-box">
                        <strong>Our Mission</strong>
                        <p>To deliver premium wood products that enhance living spaces and stand the test of time, while maintaining honest relationships with our clients.</p>
                    </div>

                    <div class="mission-vision-box">
                        <strong>Our Vision</strong>
                        <p>To be the most trusted name in carpentry and furniture manufacturing across Ghana, recognized for uncompromising quality and customer satisfaction.</p>
                    </div>
                </div>

                <div class="about-values">
                    <h3>Our Values</h3>
                    <ul class="values-list">
                        <li><strong>Quality First:</strong> We never compromise on materials or craftsmanship</li>
                        <li><strong>Customer Focused:</strong> Your satisfaction is our primary measure of success</li>
                        <li><strong>Integrity:</strong> Transparent pricing and honest communication always</li>
                        <li><strong>Innovation:</strong> Blending traditional craftsmanship with modern techniques</li>
                        <li><strong>Sustainability:</strong> Responsible sourcing and minimal waste practices</li>
                        <li><strong>Reliability:</strong> Delivering on our promises, every single time</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <p class="section-subtitle" style="color: rgba(255,255,255,0.9);">Visit our showroom or reach out today</p>

            <div class="contact-grid">
                <div class="contact-card">
                    <div class="icon">📍</div>
                    <h3>Visit Us</h3>
                    <p>Koforidua<br>Eastern Region, Ghana</p>
                </div>

                <div class="contact-card">
                    <div class="icon">📞</div>
                    <h3>Call Us</h3>
                    <p><a href="tel:+233208280559">+233 20 828 0559</a></p>
                </div>

                <div class="contact-card">
                    <div class="icon">💬</div>
                    <h3>WhatsApp</h3>
                    <p><a href="https://wa.me/233208280559" target="_blank">Message Us Now</a></p>
                </div>

                <div class="contact-card">
                    <div class="icon">⏰</div>
                    <h3>Business Hours</h3>
                    <p>Monday - Saturday<br>8:00 AM - 6:00 PM</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <h3>EAST WIND LTD</h3>
            <p>Premium Carpentry & Custom Furniture Manufacturing</p>
            <p>Koforidua, Eastern Region, Ghana</p>

            <hr class="footer-divider">

            <p>&copy; 2025 East Wind Ltd. All rights reserved. | Crafted with excellence</p>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        function toggleMenu() {
            const navMenu = document.getElementById('navMenu');
            const menuBtn = document.querySelector('.mobile-menu-btn');
            navMenu.classList.toggle('active');
            menuBtn.classList.toggle('active');
        }

        function closeMenu() {
            const navMenu = document.getElementById('navMenu');
            const menuBtn = document.querySelector('.mobile-menu-btn');
            navMenu.classList.remove('active');
            menuBtn.classList.remove('active');
        }

        // Gallery filter function with smooth transitions
        function filterGallery(category) {
            const items = document.querySelectorAll('.gallery-item');
            const tabs = document.querySelectorAll('.gallery-tab');

            // Update active tab
            tabs.forEach(tab => tab.classList.remove('active'));
            event.target.closest('.gallery-tab').classList.add('active');

            // Filter items with fade effect
            items.forEach(item => {
                const itemCategory = item.getAttribute('data-category');

                if (category === 'all' || itemCategory === category) {
                    item.style.display = 'block';
                    setTimeout(() => {
                        item.style.opacity = '1';
                        item.style.transform = 'scale(1)';
                    }, 10);
                } else {
                    item.style.opacity = '0';
                    item.style.transform = 'scale(0.9)';
                    setTimeout(() => {
                        item.style.display = 'none';
                    }, 300);
                }
            });
        }

        // Initialize gallery items
        document.querySelectorAll('.gallery-item').forEach(item => {
            item.style.transition = 'opacity 0.3s ease, transform 0.3s ease';
        });

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all sections
        document.querySelectorAll('section').forEach(section => {
            observer.observe(section);
        });

        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add loading animation for images
        document.querySelectorAll('.gallery-image').forEach(img => {
            img.addEventListener('load', function() {
                this.style.opacity = '1';
            });
        });

        // Parallax effect for hero section
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            if (hero) {
                hero.style.transform = 'translateY(' + scrolled * 0.5 + 'px)';
            }
        });
    </script>
</body>
</html>
