<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alaka Sutar - Senior Frontend Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700&family=Space+Mono:wght@400;700&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --accent-gradient: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            --dark-bg: #0a0e27;
            --darker-bg: #050812;
            --card-bg: rgba(20, 25, 50, 0.6);
            --text-primary: #f1f5f9;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            --border-color: rgba(148, 163, 184, 0.1);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, var(--dark-bg) 0%, #1a1f3a 50%, var(--darker-bg) 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(102, 126, 234, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(245, 87, 108, 0.1) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            backdrop-filter: blur(20px);
            background: rgba(10, 14, 39, 0.85);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .navbar {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-family: 'Syne', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
        }

        nav {
            display: flex;
            gap: 2.5rem;
        }

        nav a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            position: relative;
            transition: color 0.3s ease;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-gradient);
            transition: width 0.3s ease;
        }

        nav a:hover {
            color: var(--text-primary);
        }

        nav a:hover::after {
            width: 100%;
        }

        .hero {
            margin-top: 80px;
            padding: 120px 2rem 100px;
            max-width: 1400px;
            margin-left: auto;
            margin-right: auto;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 10%;
            right: -200px;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(40px);
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: 10%;
            left: -200px;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(245, 87, 108, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(40px);
        }

        .hero-content {
            animation: slideInUp 1s ease-out;
            position: relative;
            z-index: 10;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(102, 126, 234, 0.15);
            border: 1px solid rgba(102, 126, 234, 0.3);
            padding: 8px 16px;
            border-radius: 50px;
            color: #a5b4fc;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            animation: fadeIn 1s ease-out;
        }

        .hero h1 {
            font-family: 'Syne', sans-serif;
            font-size: 4.5rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -2px;
            animation: slideInUp 1s ease-out;
        }

        .hero-subtitle {
            font-size: 1.8rem;
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            font-weight: 300;
            letter-spacing: 0.5px;
            animation: slideInUp 1s ease-out 0.1s both;
        }

        .hero-description {
            max-width: 700px;
            color: var(--text-secondary);
            font-size: 1.15rem;
            line-height: 1.9;
            margin-bottom: 3rem;
            animation: slideInUp 1s ease-out 0.2s both;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1.5rem;
            margin: 3rem 0;
            animation: slideInUp 1s ease-out 0.3s both;
        }

        .stat-item {
            background: rgba(102, 126, 234, 0.1);
            border: 1px solid rgba(102, 126, 234, 0.2);
            padding: 1.5rem;
            border-radius: 12px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateY(-5px);
            border-color: rgba(102, 126, 234, 0.4);
        }

        .stat-number {
            font-family: 'Space Mono', monospace;
            font-size: 2.5rem;
            font-weight: 700;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 0.9rem;
            font-weight: 500;
            margin-top: 0.5rem;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            margin-top: 2rem;
            flex-wrap: wrap;
            animation: slideInUp 1s ease-out 0.4s both;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            font-size: 1rem;
            letter-spacing: 0.5px;
        }

        .btn-primary {
            background: var(--primary-gradient);
            color: white;
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
            position: relative;
            overflow: hidden;
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s ease;
        }

        .btn-primary:hover::before {
            left: 100%;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.5);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-primary);
            border: 2px solid rgba(102, 126, 234, 0.5);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(102, 126, 234, 0.1);
            border-color: rgba(102, 126, 234, 0.8);
            transform: translateY(-3px);
        }

        .section {
            padding: 100px 2rem;
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
        }

        .section-title {
            font-family: 'Syne', sans-serif;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--text-primary);
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: var(--secondary-gradient);
            border-radius: 2px;
        }

        .section-subtitle {
            color: var(--text-secondary);
            font-size: 1.1rem;
            margin-bottom: 3rem;
            max-width: 600px;
        }

        /* ===== HIGHLIGHTS SECTION ===== */
        .highlights-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2.5rem;
            margin-bottom: 4rem;
        }

        .highlight-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 2.5rem;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
        }

        .highlight-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            transition: all 0.3s ease;
        }

        .highlight-card:hover {
            border-color: rgba(102, 126, 234, 0.4);
            transform: translateY(-10px);
            box-shadow: 0 30px 60px rgba(102, 126, 234, 0.2);
        }

        .highlight-card:hover::before {
            top: -25%;
            right: -25%;
        }

        .highlight-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: inline-block;
        }

        .highlight-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
            font-weight: 700;
            position: relative;
            z-index: 2;
        }

        .highlight-card p {
            color: var(--text-secondary);
            line-height: 1.8;
            position: relative;
            z-index: 2;
        }

        .highlight-stat {
            background: rgba(102, 126, 234, 0.1);
            padding: 1rem;
            border-radius: 10px;
            margin-top: 1.5rem;
            border-left: 3px solid #667eea;
        }

        .highlight-stat-value {
            font-family: 'Space Mono', monospace;
            font-size: 1.5rem;
            font-weight: 700;
            color: #a5b4fc;
            margin-bottom: 0.25rem;
        }

        .highlight-stat-label {
            color: var(--text-secondary);
            font-size: 0.85rem;
        }

        /* ===== PROJECT SHOWCASE ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 2.5rem;
        }

        .project-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            overflow: hidden;
            transition: all 0.4s ease;
            backdrop-filter: blur(10px);
            position: relative;
            height: 100%;
            display: flex;
            flex-direction: column;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--primary-gradient);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }

        .project-card:hover {
            border-color: rgba(102, 126, 234, 0.4);
            transform: translateY(-12px);
            box-shadow: 0 40px 80px rgba(102, 126, 234, 0.2);
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-header {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(240, 147, 251, 0.05));
            padding: 2rem;
            border-bottom: 1px solid var(--border-color);
            position: relative;
        }

        .project-badge {
            display: inline-block;
            background: rgba(245, 87, 108, 0.15);
            color: #fca5ac;
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .project-title {
            font-size: 1.5rem;
            color: var(--text-primary);
            margin-bottom: 0.5rem;
            font-weight: 700;
        }

        .project-client {
            color: #a5b4fc;
            font-size: 0.95rem;
            font-weight: 600;
        }

        .project-content {
            padding: 2rem;
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .project-description {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .project-metrics {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .metric {
            background: rgba(102, 126, 234, 0.08);
            padding: 1rem;
            border-radius: 10px;
            border-left: 2px solid #667eea;
        }

        .metric-value {
            font-family: 'Space Mono', monospace;
            font-size: 1.3rem;
            font-weight: 700;
            color: #a5b4fc;
        }

        .metric-label {
            color: var(--text-secondary);
            font-size: 0.8rem;
            margin-top: 0.25rem;
        }

        .project-highlights {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .project-highlights li {
            color: var(--text-secondary);
            padding-left: 1.5rem;
            margin-bottom: 0.75rem;
            position: relative;
            font-size: 0.95rem;
        }

        .project-highlights li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: #667eea;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .tech-stack {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-top: auto;
        }

        .tech-tag {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(240, 147, 251, 0.1));
            color: #a5b4fc;
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 500;
            border: 1px solid rgba(102, 126, 234, 0.3);
        }

        /* ===== EXPERIENCE SECTION ===== */
        .experience-grid {
            display: grid;
            gap: 2rem;
        }

        .experience-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 2.5rem;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            position: relative;
            border-left: 4px solid transparent;
            background: linear-gradient(135deg, var(--card-bg) 0%, rgba(30, 41, 59, 0.4) 100%);
        }

        .experience-card:nth-child(1) {
            border-left-color: #667eea;
        }

        .experience-card:nth-child(2) {
            border-left-color: #f093fb;
        }

        .experience-card:nth-child(3) {
            border-left-color: #f5576c;
        }

        .experience-card:nth-child(4) {
            border-left-color: #4facfe;
        }

        .experience-card:hover {
            transform: translateX(8px);
            border-color: var(--border-color);
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 1rem;
        }

        .experience-card h3 {
            color: var(--text-primary);
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .company-name {
            color: #a5b4fc;
            font-weight: 600;
            font-size: 0.95rem;
        }

        .experience-meta {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-bottom: 1.5rem;
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .experience-description {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .experience-achievements {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .experience-achievements li {
            color: var(--text-secondary);
            padding-left: 1.5rem;
            margin-bottom: 0.5rem;
            position: relative;
            font-size: 0.95rem;
        }

        .experience-achievements li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #667eea;
            font-weight: bold;
        }

        /* ===== SKILLS SECTION ===== */
        .skills-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 2.5rem;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            border-color: rgba(102, 126, 234, 0.4);
            transform: translateY(-5px);
        }

        .skill-category h3 {
            color: #a5b4fc;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .skill-category h3::before {
            content: '';
            width: 4px;
            height: 24px;
            background: var(--primary-gradient);
            border-radius: 2px;
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            color: var(--text-secondary);
            padding: 0.7rem 0;
            font-size: 0.95rem;
            position: relative;
            padding-left: 1rem;
        }

        .skill-list li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: #667eea;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-list li:hover::before {
            opacity: 1;
        }

        .skill-list li:hover {
            color: var(--text-primary);
            transform: translateX(5px);
            transition: all 0.3s ease;
        }

        /* ===== CONTACT SECTION ===== */
        .contact-section {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(240, 147, 251, 0.05) 100%);
            border: 1px solid rgba(102, 126, 234, 0.3);
            padding: 4rem 3rem;
            border-radius: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .contact-section::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
            border-radius: 50%;
        }

        .contact-section h2 {
            color: var(--text-primary);
            margin-bottom: 1.5rem;
            font-size: 2.5rem;
            font-weight: 700;
            position: relative;
            z-index: 2;
        }

        .contact-section p {
            color: var(--text-secondary);
            margin-bottom: 2.5rem;
            font-size: 1.1rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            position: relative;
            z-index: 2;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2.5rem;
            flex-wrap: wrap;
            position: relative;
            z-index: 2;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background: transparent;
            border: 2px solid rgba(102, 126, 234, 0.5);
            border-radius: 50%;
            color: var(--text-primary);
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.5rem;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--primary-gradient);
            z-index: -1;
            transition: left 0.3s ease;
        }

        .social-link:hover {
            color: white;
            border-color: #667eea;
            transform: translateY(-5px);
        }

        .social-link:hover::before {
            left: 0;
        }

        footer {
            text-align: center;
            padding: 3rem 2rem;
            color: var(--text-secondary);
            border-top: 1px solid var(--border-color);
            margin-top: 80px;
            backdrop-filter: blur(10px);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .awards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .award-item {
            background: linear-gradient(135deg, rgba(245, 87, 108, 0.1) 0%, rgba(102, 126, 234, 0.1) 100%);
            border: 1px solid rgba(245, 87, 108, 0.3);
            padding: 2rem;
            border-radius: 12px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .award-item:hover {
            border-color: rgba(245, 87, 108, 0.6);
            transform: translateY(-5px);
        }

        .award-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .award-title {
            color: var(--text-primary);
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .award-org {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        @media (max-width: 1024px) {
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .hero h1 {
                font-size: 3.5rem;
            }

            .highlights-container {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .hero {
                padding: 100px 1.5rem 60px;
            }

            .hero h1 {
                font-size: 2.8rem;
            }

            .hero-subtitle {
                font-size: 1.3rem;
            }

            nav {
                display: none;
            }

            .section {
                padding: 60px 1.5rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 1rem;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                text-align: center;
            }

            .skills-section {
                grid-template-columns: 1fr;
            }

            .contact-section {
                padding: 2.5rem 1.5rem;
            }

            .contact-section h2 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="navbar">
            <div class="logo">AS</div>
            <nav>
                <a href="#about">About</a>
                <a href="#highlights">Highlights</a>
                <a href="#projects">Projects</a>
                <a href="#experience">Experience</a>
                <a href="#skills">Skills</a>
                <a href="#contact">Contact</a>
            </nav>
        </div>
    </header>

    <section class="hero" id="about">
        <div class="hero-content">
            <div class="hero-badge">🚀 Senior Frontend Developer</div>
            <h1>Alaka Sutar</h1>
            <div class="hero-subtitle">Crafting Beautiful, Scalable Web Experiences</div>
            <p class="hero-description">
                9+ years architecting high-performance web applications for global fintech & banking giants including HSBC and ACI Worldwide. 
                Expert in Angular (v4–v19), React 18, and modern architecture patterns. 
                Passionate about translating pixel-perfect designs into WCAG 2.1-accessible, production-ready interfaces.
            </p>

            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number">9+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Projects Shipped</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">25%</div>
                    <div class="stat-label">Faster Integration</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2</div>
                    <div class="stat-label">Major Awards</div>
                </div>
            </div>

            <div class="cta-buttons">
                <a href="#contact" class="btn btn-primary">💌 Get In Touch</a>
                <a href="https://linkedin.com/in/alka-sutar-6a5587a4" class="btn btn-secondary" target="_blank">LinkedIn Profile</a>
                <a href="mailto:alakasutar02@gmail.com" class="btn btn-secondary">📧 Send Email</a>
            </div>
        </div>
    </section>

    <section class="section" id="highlights">
        <h2 class="section-title">Highlights & Abilities</h2>
        <p class="section-subtitle">Proven expertise in architecture, performance optimization, and team leadership across enterprise-grade applications</p>

        <div class="highlights-container">
            <div class="highlight-card">
                <div class="highlight-icon">⚡</div>
                <h3>Performance & Architecture</h3>
                <p>Expert in designing scalable SPA architectures with lazy loading, NgRx state management, and RxJS reactive streams. Reduced initial bundle sizes by up to 40% and improved load performance across distributed teams.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">40%</div>
                    <div class="highlight-stat-label">Bundle Size Reduction</div>
                </div>
            </div>

            <div class="highlight-card">
                <div class="highlight-icon">🎨</div>
                <h3>Design to Code Excellence</h3>
                <p>Translating Figma designs into pixel-perfect, WCAG 2.1-accessible interfaces. Component-driven development approach with custom directive libraries and composable components reducing integration time by 25%.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">25%</div>
                    <div class="highlight-stat-label">Integration Time Saved</div>
                </div>
            </div>

            <div class="highlight-card">
                <div class="highlight-icon">🔐</div>
                <h3>Security & Best Practices</h3>
                <p>Implemented JWT token handling, CORS configuration, OWASP-aligned input validation, and secure coding patterns. Enforced code hygiene standards and established security best practices across distributed teams.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">0</div>
                    <div class="highlight-stat-label">Security Incidents</div>
                </div>
            </div>

            <div class="highlight-card">
                <div class="highlight-icon">🚀</div>
                <h3>Team Leadership & Mentoring</h3>
                <p>Led technical initiatives, mentored junior developers, and managed CI/CD release pipelines for 40+ person teams. Introduced GitHub Copilot AI tooling, accelerating sprint velocity and reducing repetitive boilerplate effort.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">40+</div>
                    <div class="highlight-stat-label">Team Size Managed</div>
                </div>
            </div>

            <div class="highlight-card">
                <div class="highlight-icon">🏢</div>
                <h3>Enterprise Domain Expertise</h3>
                <p>Deep experience in Banking & Capital Markets, Digital Payments, and Fintech. Built systems processing millions in transactions with fault-tolerant architecture and high-availability requirements.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">$B+</div>
                    <div class="highlight-stat-label">Transaction Volume</div>
                </div>
            </div>

            <div class="highlight-card">
                <div class="highlight-icon">🎯</div>
                <h3>Full Stack Framework Mastery</h3>
                <p>Expert across Angular ecosystem (v4–v19), React 18, TypeScript, RxJS, NgRx, and modern testing frameworks. Proficient in Jasmine, Karma, Playwright E2E testing, and automated test generation with AI.</p>
                <div class="highlight-stat">
                    <div class="highlight-stat-value">15+</div>
                    <div class="highlight-stat-label">Technologies Mastered</div>
                </div>
            </div>
        </div>

        <h2 class="section-title" style="margin-top: 4rem;">Awards & Recognition</h2>
        <div class="awards-container">
            <div class="award-item">
                <div class="award-icon">🌟</div>
                <div class="award-title">Star Award</div>
                <div class="award-org">Synechron Technologies</div>
                <p style="color: var(--text-secondary); font-size: 0.9rem; margin-top: 0.5rem;">For exceptional technical delivery and measurable client impact on the HSBC DCM engagement.</p>
            </div>
            <div class="award-item">
                <div class="award-icon">🏆</div>
                <div class="award-title">Surpass Award</div>
                <div class="award-org">Synechron Technologies</div>
                <p style="color: var(--text-secondary); font-size: 0.9rem; margin-top: 0.5rem;">Outstanding performance recognition for delivering above and beyond expectations.</p>
            </div>
            <div class="award-item">
                <div class="award-icon">🎓</div>
                <div class="award-title">Namaste JS & React</div>
                <div class="award-org">Advanced JavaScript & React Certification</div>
                <p style="color: var(--text-secondary); font-size: 0.9rem; margin-top: 0.5rem;">Advanced certification from Namaste Dev demonstrating expertise in modern frameworks.</p>
            </div>
        </div>
    </section>

    <section class="section" id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <p class="section-subtitle">Showcase of high-impact work across fintech, banking, and enterprise domains</p>
        
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-header">
                    <div>
                        <div class="project-badge">⚡ Production</div>
                        <div class="project-title">Speed Pay Platform</div>
                        <div class="project-client">ACI Worldwide • Global Payments</div>
                    </div>
                </div>
                <div class="project-content">
                    <p class="project-description">
                        Architected and shipped production Angular 19 SPAs enabling one-time payments, recurring billing, and digital disbursements across multinational banking infrastructure.
                    </p>

                    <div class="project-metrics">
                        <div class="metric">
                            <div class="metric-value">40+</div>
                            <div class="metric-label">Countries Supported</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">99.9%</div>
                            <div class="metric-label">Uptime SLA</div>
                        </div>
                    </div>

                    <ul class="project-highlights">
                        <li>NgRx state management with reactive RxJS streams</li>
                        <li>JWT authentication & CORS configuration</li>
                        <li>WCAG 2.1 accessibility compliance</li>
                        <li>Playwright E2E test automation</li>
                        <li>40% bundle size optimization</li>
                    </ul>

                    <div class="tech-stack">
                        <span class="tech-tag">Angular 19</span>
                        <span class="tech-tag">NgRx</span>
                        <span class="tech-tag">RxJS</span>
                        <span class="tech-tag">TypeScript</span>
                        <span class="tech-tag">Playwright</span>
                        <span class="tech-tag">Azure DevOps</span>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-header">
                    <div>
                        <div class="project-badge">💰 Enterprise</div>
                        <div class="project-title">DCM Blotter Dashboard</div>
                        <div class="project-client">HSBC Global Banking & Markets</div>
                    </div>
                </div>
                <div class="project-content">
                    <p class="project-description">
                        Senior management MI reporting dashboard with real-time deal blotter, P&L tracking, and allocation views. Adopted as daily operational tool by GBM leadership across 3+ divisions.
                    </p>

                    <div class="project-metrics">
                        <div class="metric">
                            <div class="metric-value">v10→v19</div>
                            <div class="metric-label">Angular Migration</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">3+</div>
                            <div class="metric-label">Modules Impacted</div>
                        </div>
                    </div>

                    <ul class="project-highlights">
                        <li>Complete Angular v10 → v19 migration</li>
                        <li>25% component integration time reduction</li>
                        <li>Reusable component library design</li>
                        <li>Real-time data visualization</li>
                        <li>Advanced filtering & analytics</li>
                    </ul>

                    <div class="tech-stack">
                        <span class="tech-tag">Angular 19</span>
                        <span class="tech-tag">Prime NG</span>
                        <span class="tech-tag">RxJS</span>
                        <span class="tech-tag">Storybook</span>
                        <span class="tech-tag">Figma</span>
                        <span class="tech-tag">Jest</span>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-header">
                    <div>
                        <div class="project-badge">🏦 Fintech</div>
                        <div class="project-title">Loan Origination System</div>
                        <div class="project-client">CRIF Solutions • Italian Banking</div>
                    </div>
                </div>
                <div class="project-content">
                    <p class="project-description">
                        Complete UI layer for Loan Origination System deployed across Italian banking sector. Micro-frontend architecture isolating UI logic per loan domain with zero-downtime releases.
                    </p>

                    <div class="project-metrics">
                        <div class="metric">
                            <div class="metric-value">10+</div>
                            <div class="metric-label">Banks Deployed</div>
                        </div>
                        <div class="metric">
                            <div class="metric-value">$M+</div>
                            <div class="metric-label">Loans Processed</div>
                        </div>
                    </div>

                    <ul class="project-highlights">
                        <li>Micro-frontend architecture (Angular Brick)</li>
                        <li>Reusable component & form-validator library</li>
                        <li>Responsive SCSS & Material design</li>
                        <li>Jenkins CI/CD automation</li>
                        <li>Multi-domain loan processing support</li>
                    </ul>

                    <div class="tech-stack">
                        <span class="tech-tag">Angular 8</span>
                        <span class="tech-tag">Material Design</span>
                        <span class="tech-tag">SCSS</span>
                        <span class="tech-tag">TypeScript</span>
                        <span class="tech-tag">REST APIs</span>
                        <span class="tech-tag">Jenkins</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="experience">
        <h2 class="section-title">Professional Experience</h2>
        <p class="section-subtitle">Career progression across fintech, banking, and enterprise software</p>
        
        <div class="experience-grid">
            <div class="experience-card">
                <div class="experience-header">
                    <div>
                        <h3>Senior UI Developer</h3>
                        <div class="company-name">IEnergizer IT Services Pvt. Ltd.</div>
                    </div>
                </div>
                <div class="experience-meta">
                    <span>📅 Jul 2025 – Present</span>
                    <span>📍 Pune, India</span>
                    <span>👥 Team: 40</span>
                </div>
                <p class="experience-description">
                    Architecting production Angular 19 SPAs for ACI Worldwide's Speed Pay platform. Leading technical initiatives and managing CI/CD release pipelines for distributed engineering teams.
                </p>
                <ul class="experience-achievements">
                    <li>Built NgRx state management with lazy-loaded modules</li>
                    <li>40% bundle optimization through code-splitting</li>
                    <li>Introduced GitHub Copilot for sprint acceleration</li>
                    <li>Mentored junior developers on best practices</li>
                    <li>Enforced WCAG 2.1 accessibility across modules</li>
                </ul>
                <div class="tech-stack">
                    <span class="tech-tag">Angular 19</span>
                    <span class="tech-tag">NgRx</span>
                    <span class="tech-tag">Playwright</span>
                    <span class="tech-tag">Azure DevOps</span>
                </div>
            </div>

            <div class="experience-card">
                <div class="experience-header">
                    <div>
                        <h3>Senior Technology Associate</h3>
                        <div class="company-name">Synechron Technologies Pvt. Ltd.</div>
                    </div>
                </div>
                <div class="experience-meta">
                    <span>📅 Jul 2021 – Jul 2025</span>
                    <span>📍 Pune, India</span>
                    <span>👥 Team: 20</span>
                </div>
                <p class="experience-description">
                    Led end-to-end Angular v10 → v19 migration. Built MI reporting dashboard & reusable component library adopted across 3+ platform modules, reducing integration time by 25%.
                </p>
                <ul class="experience-achievements">
                    <li>Complete v10 → v19 Angular migration</li>
                    <li>25% component integration time reduction</li>
                    <li>Real-time deal blotter with P&L tracking</li>
                    <li>⭐ Star Award for technical excellence</li>
                    <li>🏆 Surpass Award for client impact</li>
                </ul>
                <div class="tech-stack">
                    <span class="tech-tag">Angular 19</span>
                    <span class="tech-tag">React 18</span>
                    <span class="tech-tag">Prime NG</span>
                    <span class="tech-tag">Storybook</span>
                </div>
            </div>

            <div class="experience-card">
                <div class="experience-header">
                    <div>
                        <h3>Front End Developer</h3>
                        <div class="company-name">CRIF Solutions Pvt. Ltd.</div>
                    </div>
                </div>
                <div class="experience-meta">
                    <span>📅 Aug 2019 – Jul 2021</span>
                    <span>📍 Pune, India</span>
                    <span>👥 Team: 10</span>
                </div>
                <p class="experience-description">
                    Designed & built complete UI layer for Loan Origination System. Implemented micro-frontend architecture with reusable component libraries across multiple loan-processing modules.
                </p>
                <ul class="experience-achievements">
                    <li>Micro-frontend architecture design</li>
                    <li>Reusable component library creation</li>
                    <li>Zero-downtime Jenkins deployments</li>
                    <li>10+ banks deployment support</li>
                    <li>Responsive design across all breakpoints</li>
                </ul>
                <div class="tech-stack">
                    <span class="tech-tag">Angular 8</span>
                    <span class="tech-tag">Material Design</span>
                    <span class="tech-tag">SCSS</span>
                    <span class="tech-tag">Jenkins</span>
                </div>
            </div>

            <div class="experience-card">
                <div class="experience-header">
                    <div>
                        <h3>Software Engineer</h3>
                        <div class="company-name">KPIT Technologies Pvt. Ltd.</div>
                    </div>
                </div>
                <div class="experience-meta">
                    <span>📅 Jul 2016 – Apr 2019</span>
                    <span>📍 Pune, India</span>
                    <span>👥 Team: 8</span>
                </div>
                <p class="experience-description">
                    Developed web-based cybersecurity tool (KASAT) for ECU threat modeling. Built resource management dashboard (Copilot) with Chart.js visualizations for automotive and US clients.
                </p>
                <ul class="experience-achievements">
                    <li>Web-based cybersecurity tool development</li>
                    <li>Resource management dashboard with analytics</li>
                    <li>Chart.js data visualization implementation</li>
                    <li>10% user satisfaction improvement</li>
                    <li>Full deployment lifecycle management</li>
                </ul>
                <div class="tech-stack">
                    <span class="tech-tag">Angular 4</span>
                    <span class="tech-tag">JavaScript</span>
                    <span class="tech-tag">Chart.js</span>
                    <span class="tech-tag">Laravel</span>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="skills">
        <h2 class="section-title">Technical Arsenal</h2>
        <p class="section-subtitle">Comprehensive mastery across modern web technologies and enterprise architecture</p>
        
        <div class="skills-section">
            <div class="skill-category">
                <h3>Frontend Frameworks</h3>
                <ul class="skill-list">
                    <li>Angular (v4–v19)</li>
                    <li>React 18</li>
                    <li>TypeScript & ES6+</li>
                    <li>RxJS & Reactive Programming</li>
                    <li>NgRx State Management</li>
                    <li>Tailwind CSS & SCSS</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Component Libraries</h3>
                <ul class="skill-list">
                    <li>Prime NG & Prime React</li>
                    <li>Angular Material</li>
                    <li>Storybook</li>
                    <li>Custom Component Libraries</li>
                    <li>Composable Architecture</li>
                    <li>Design System Implementation</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Testing & Quality</h3>
                <ul class="skill-list">
                    <li>Jasmine & Karma</li>
                    <li>Jest & React Testing</li>
                    <li>Playwright E2E Testing</li>
                    <li>TDD & BDD Practices</li>
                    <li>GitHub Copilot AI Testing</li>
                    <li>Code Review Excellence</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>DevOps & Cloud</h3>
                <ul class="skill-list">
                    <li>AWS S3 & Cloud Services</li>
                    <li>Jenkins CI/CD Pipelines</li>
                    <li>Azure DevOps</li>
                    <li>Docker Containerization</li>
                    <li>Git & Bitbucket</li>
                    <li>Webpack & Vite Bundling</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Design & Accessibility</h3>
                <ul class="skill-list">
                    <li>WCAG 2.1 & AODA</li>
                    <li>ARIA & Semantic HTML</li>
                    <li>Figma Design-to-Code</li>
                    <li>Cross-browser Testing</li>
                    <li>Responsive Design</li>
                    <li>UI/UX Prototyping</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Architecture & Patterns</h3>
                <ul class="skill-list">
                    <li>SPA & Micro-Frontend</li>
                    <li>Lazy Loading & Code Splitting</li>
                    <li>Component-Driven Development</li>
                    <li>REST API Integration</li>
                    <li>JWT Authentication</li>
                    <li>Performance Optimization</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Domain Expertise</h3>
                <ul class="skill-list">
                    <li>Banking & Capital Markets</li>
                    <li>Digital Payments & Fintech</li>
                    <li>Loan Origination Systems</li>
                    <li>Enterprise Applications</li>
                    <li>High-Frequency Trading Dashboards</li>
                    <li>Cybersecurity Tools</li>
                </ul>
            </div>

            <div class="skill-category">
                <h3>Leadership & Soft Skills</h3>
                <ul class="skill-list">
                    <li>Team Mentoring & Development</li>
                    <li>Technical Leadership</li>
                    <li>Agile & Sprint Planning</li>
                    <li>Stakeholder Communication</li>
                    <li>Code Review Standards</li>
                    <li>Cross-functional Collaboration</li>
                </ul>
            </div>
        </div>
    </section>

    <section class="section" id="contact">
        <div class="contact-section">
            <h2>Let's Create Something Amazing</h2>
            <p>
                I'm always excited about new opportunities, challenging projects, and collaborative partnerships. 
                Whether you need a technical consultation, have an interesting project, or just want to connect—let's talk!
            </p>
            <a href="mailto:alakasutar02@gmail.com" class="btn btn-primary">💌 Send Me An Email</a>
            <div class="social-links">
                <a href="https://linkedin.com/in/alka-sutar-6a5587a4" class="social-link" target="_blank" title="LinkedIn">
                    <i class="fab fa-linkedin"></i>
                </a>
                <a href="mailto:alakasutar02@gmail.com" class="social-link" title="Email">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="https://github.com" class="social-link" target="_blank" title="GitHub">
                    <i class="fab fa-github"></i>
                </a>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Alaka Sutar. All rights reserved. | Engineering Excellence in Every Line of Code</p>
    </footer>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry, index) => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = `slideInUp 0.6s ease-out ${index * 0.1}s forwards`;
                    entry.target.style.opacity = '0';
                }
            });
        }, observerOptions);

        document.querySelectorAll(
            '.highlight-card, .project-card, .experience-card, .skill-category, .award-item'
        ).forEach(card => {
            observer.observe(card);
        });
    </script>
</body>
</html># github.io
