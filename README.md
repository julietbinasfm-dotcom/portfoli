<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juliet Binas | Artistic Visual Portfolio</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-color: #0b070e;
            --card-bg: rgba(23, 16, 28, 0.75);
            --card-surface: rgba(35, 24, 44, 0.5);
            --glass-border: rgba(244, 114, 182, 0.15);
            --glass-border-hover: rgba(244, 114, 182, 0.4);
            --accent-pink: #f472b6;
            --accent-rose: #e11d48;
            --accent-gold: #fbbf24;
            --accent-purple: #c084fc;
            --accent-gradient: linear-gradient(135deg, #f472b6 0%, #e11d48 50%, #c084fc 100%);
            --text-primary: #fff0f6;
            --text-secondary: #d8c4dd;
            --text-muted: #8e7898;
            --font-serif: 'Cormorant Garamond', Georgia, serif;
            --font-sans: 'Plus Jakarta Sans', -apple-system, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            font-family: var(--font-sans);
            padding: 60px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 50px;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(192, 132, 252, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(244, 114, 182, 0.08) 0%, transparent 40%);
        }

        /* Slide Container */
        .slide {
            width: 100%;
            max-width: 960px;
            aspect-ratio: 16 / 9;
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 28px;
            padding: 44px 52px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.8), inset 0 1px 1px rgba(255, 255, 255, 0.1);
            overflow: hidden;
            transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .slide:hover {
            border-color: var(--glass-border-hover);
            box-shadow: 0 35px 70px rgba(244, 114, 182, 0.12), inset 0 1px 2px rgba(255, 255, 255, 0.2);
        }

        /* Ambient Lighting Accents */
        .slide::before {
            content: '';
            position: absolute;
            top: -120px;
            right: -120px;
            width: 450px;
            height: 450px;
            background: radial-gradient(circle, rgba(244, 114, 182, 0.18) 0%, rgba(11, 7, 14, 0) 70%);
            pointer-events: none;
            z-index: 0;
        }

        .slide::after {
            content: '';
            position: absolute;
            bottom: -100px;
            left: -100px;
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, rgba(192, 132, 252, 0.12) 0%, rgba(11, 7, 14, 0) 70%);
            pointer-events: none;
            z-index: 0;
        }

        .slide > * {
            position: relative;
            z-index: 1;
        }

        /* Header Elements */
        .slide-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(244, 114, 182, 0.12);
            padding-bottom: 18px;
        }

        .brand-name {
            font-family: var(--font-serif);
            font-size: 1.15rem;
            font-weight: 600;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .brand-dot {
            width: 7px;
            height: 7px;
            background: var(--accent-gradient);
            border-radius: 50%;
            box-shadow: 0 0 12px var(--accent-pink);
        }

        .slide-number {
            font-family: var(--font-sans);
            font-size: 0.8rem;
            color: var(--text-muted);
            letter-spacing: 2px;
            font-weight: 500;
        }

        /* Typography */
        .hero-title {
            font-family: var(--font-serif);
            font-size: 3.2rem;
            font-weight: 400;
            line-height: 1.05;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #ffffff 20%, #fbcfe8 60%, #c084fc 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-title i {
            font-family: var(--font-serif);
            font-style: italic;
            font-weight: 300;
            background: linear-gradient(135deg, #f472b6 0%, #fbbf24 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-title {
            font-family: var(--font-serif);
            font-size: 2.1rem;
            font-weight: 600;
            letter-spacing: 0.5px;
            color: var(--text-primary);
            margin-bottom: 6px;
        }

        .subtitle {
            font-size: 0.88rem;
            color: var(--text-secondary);
            line-height: 1.6;
            font-weight: 300;
            letter-spacing: 0.2px;
        }

        /* Artistic Pill Buttons */
        .btn-pill {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 12px 28px;
            font-size: 0.75rem;
            font-weight: 700;
            border-radius: 40px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-decoration: none;
            width: fit-content;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            box-shadow: 0 8px 25px rgba(225, 29, 72, 0.35);
        }

        .btn-pill:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 12px 30px rgba(244, 114, 182, 0.5);
        }

        /* Slide 1: Cover Layout */
        .cover-content {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 30px;
            align-items: center;
            height: 100%;
        }

        .artistic-frame {
            position: relative;
            width: 100%;
            height: 250px;
            border-radius: 20px;
            background: linear-gradient(145deg, rgba(35, 24, 44, 0.8), rgba(15, 10, 20, 0.9));
            border: 1px solid var(--glass-border);
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-shadow: inset 0 0 30px rgba(0,0,0,0.5);
        }

        .frame-canvas {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            height: 100%;
            margin-top: 10px;
        }

        .canvas-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.08);
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 8px;
            transition: all 0.3s ease;
        }

        .canvas-card:hover {
            background: rgba(244, 114, 182, 0.1);
            border-color: var(--accent-pink);
            transform: translateY(-2px);
        }

        .canvas-card svg {
            width: 26px;
            height: 26px;
            stroke: var(--accent-pink);
            stroke-width: 1.5;
            fill: none;
        }

        .canvas-card span {
            font-size: 0.65rem;
            color: var(--text-secondary);
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        /* Slide 2: About / Split */
        .split-layout {
            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 36px;
            align-items: center;
            height: 100%;
        }

        .portrait-container {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, rgba(244, 114, 182, 0.1) 0%, rgba(192, 132, 252, 0.05) 100%);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 14px;
            position: relative;
        }

        .portrait-circle {
            width: 90px;
            height: 90px;
            border-radius: 50%;
            background: rgba(23, 16, 28, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid var(--accent-pink);
            box-shadow: 0 0 25px rgba(244, 114, 182, 0.4);
        }

        .stats-row {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-top: 24px;
        }

        .stat-box {
            background: var(--card-surface);
            padding: 14px;
            border-radius: 14px;
            border: 1px solid var(--glass-border);
            text-align: center;
        }

        .stat-box h4 {
            font-family: var(--font-serif);
            font-size: 1.4rem;
            color: var(--accent-pink);
            font-weight: 600;
        }

        .stat-box p {
            font-size: 0.7rem;
            color: var(--text-secondary);
            margin-top: 2px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Slide 3: Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 18px;
            height: 100%;
            align-items: center;
        }

        .service-card {
            background: var(--card-surface);
            border: 1px solid var(--glass-border);
            border-radius: 18px;
            padding: 24px 20px;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.4s ease;
        }

        .service-card:hover {
            border-color: var(--accent-pink);
            transform: translateY(-5px);
            background: rgba(35, 24, 44, 0.8);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5);
        }

        .service-icon {
            width: 34px;
            height: 34px;
            margin-bottom: 14px;
            stroke: var(--accent-pink);
            stroke-width: 1.5;
            fill: none;
        }

        .service-card h3 {
            font-family: var(--font-serif);
            font-size: 1.25rem;
            color: var(--text-primary);
            margin-bottom: 10px;
            font-weight: 600;
        }

        .service-card ul {
            list-style: none;
            color: var(--text-secondary);
            font-size: 0.76rem;
            line-height: 1.8;
            font-weight: 300;
        }

        .service-card ul li::before {
            content: "✦ ";
            color: var(--accent-pink);
            font-size: 0.65rem;
        }

        .service-tag {
            margin-top: 14px;
            padding-top: 12px;
            border-top: 1px solid rgba(244, 114, 182, 0.12);
            font-size: 0.72rem;
            color: var(--accent-gold);
            letter-spacing: 0.5px;
            font-weight: 500;
        }

        /* Slide 4: Case Study */
        .case-layout {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 28px;
            height: 100%;
            align-items: center;
        }

        .case-visual-box {
            background: var(--card-surface);
            border: 1px solid var(--glass-border);
            border-radius: 18px;
            height: 240px;
            padding: 22px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .chart-art {
            width: 100%;
            height: 130px;
        }

        .detail-card {
            background: var(--card-surface);
            border-left: 2px solid var(--accent-pink);
            padding: 12px 16px;
            border-radius: 0 12px 12px 0;
            margin-bottom: 10px;
        }

        .detail-card h5 {
            font-size: 0.68rem;
            color: var(--accent-pink);
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .detail-card p {
            font-size: 0.82rem;
            color: var(--text-primary);
            margin-top: 3px;
            font-weight: 300;
        }

        /* SLIDE 5: SAMPLE WORKS (ARTISTIC) */
        .sample-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 18px;
            margin-top: 16px;
            height: 100%;
            align-items: stretch;
        }

        .sample-card {
            background: var(--card-surface);
            border: 1px solid var(--glass-border);
            border-radius: 18px;
            padding: 22px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            transition: all 0.4s ease;
        }

        .sample-card:hover {
            border-color: var(--accent-pink);
            transform: translateY(-4px);
            background: rgba(35, 24, 44, 0.85);
            box-shadow: 0 15px 35px rgba(244, 114, 182, 0.15);
        }

        .sample-badge {
            align-self: flex-start;
            background: linear-gradient(135deg, rgba(244, 114, 182, 0.15), rgba(192, 132, 252, 0.15));
            color: var(--accent-pink);
            font-size: 0.65rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            padding: 5px 12px;
            border-radius: 20px;
            border: 1px solid var(--glass-border);
            margin-bottom: 12px;
        }

        .sample-card h3 {
            font-family: var(--font-serif);
            font-size: 1.2rem;
            color: var(--text-primary);
            margin-bottom: 10px;
            font-weight: 600;
        }

        .sample-card ul {
            list-style: none;
            color: var(--text-secondary);
            font-size: 0.76rem;
            line-height: 1.7;
            font-weight: 300;
        }

        .sample-card ul li::before {
            content: "✦ ";
            color: var(--accent-pink);
            font-size: 0.65rem;
        }

        .sample-tools {
            margin-top: 14px;
            font-size: 0.7rem;
            color: var(--text-muted);
            border-top: 1px dashed rgba(244, 114, 182, 0.15);
            padding-top: 10px;
            letter-spacing: 0.5px;
        }

        /* Slide 6: Toolkit Cloud */
        .tag-cloud {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 24px;
        }

        .tag-item {
            background: var(--card-surface);
            border: 1px solid var(--glass-border);
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 0.8rem;
            color: var(--text-primary);
            font-weight: 400;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
        }

        .tag-item:hover {
            border-color: var(--accent-pink);
            color: #ffffff;
            background: rgba(244, 114, 182, 0.15);
            transform: translateY(-2px);
        }

        .tag-dot {
            width: 5px;
            height: 5px;
            border-radius: 50%;
            background: var(--accent-pink);
            box-shadow: 0 0 8px var(--accent-pink);
        }

        /* Slide 7: Process & CTA */
        .process-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            margin: 20px 0;
        }

        .process-card {
            background: var(--card-surface);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 18px;
            position: relative;
        }

        .step-number {
            font-family: var(--font-serif);
            font-size: 1.6rem;
            color: var(--accent-pink);
            font-style: italic;
            margin-bottom: 2px;
        }

        .step-title {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-primary);
            letter-spacing: 0.5px;
        }

        .step-desc {
            font-size: 0.72rem;
            color: var(--text-secondary);
            margin-top: 6px;
            line-height: 1.5;
            font-weight: 300;
        }

        .cta-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--card-surface);
            padding: 16px 24px;
            border-radius: 16px;
            border: 1px solid var(--glass-border);
            font-size: 0.85rem;
            color: var(--text-secondary);
        }

        /* Responsive Breakpoints */
        @media (max-width: 800px) {
            .slide {
                aspect-ratio: auto;
                height: auto;
                padding: 30px;
            }
            .cover-content, .split-layout, .services-grid, .case-layout, .sample-grid, .process-grid {
                grid-template-columns: 1fr;
            }
            .cta-bar {
                flex-direction: column;
                gap: 14px;
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <!-- SLIDE 1: ARTISTIC COVER -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">01 / 07</span>
        </div>
        <div class="cover-content">
            <div>
                <h1 class="hero-title">CRAFTING <i>VISUAL</i> ELEGANCE & STRATEGY.</h1>
                <p class="subtitle" style="margin-top: 14px; margin-bottom: 28px;">Editorial Brand Direction & Content Curation</p>
                <a href="mailto:juliet.binas.pandroutsourcing@gmail.com" class="btn-pill">
                    Initiate Collaboration
                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
                </a>
            </div>
            <div class="artistic-frame">
                <div style="display: flex; justify-content: space-between; align-items: center;">
                    <span style="font-size: 0.65rem; letter-spacing: 2px; color: var(--text-muted); text-transform: uppercase;">Creative Portfolio</span>
                    <span style="font-size: 0.65rem; color: var(--accent-pink);">✦ 2026 EDITION</span>
                </div>
                <div class="frame-canvas">
                    <div class="canvas-card">
                        <svg viewBox="0 0 24 24"><path d="M12 2a10 10 0 1 0 10 10A10 10 0 0 0 12 2zm0 18a8 8 0 1 1 8-8 8 8 0 0 1-8 8z"/><circle cx="12" cy="12" r="3"/></svg>
                        <span>AI Visuals</span>
                    </div>
                    <div class="canvas-card">
                        <svg viewBox="0 0 24 24"><path d="M12 19l7-7 3 3-7 7-3-3z"/><path d="M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z"/></svg>
                        <span>Graphics</span>
                    </div>
                    <div class="canvas-card">
                        <svg viewBox="0 0 24 24"><polygon points="23 7 16 12 23 17 23 7"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg>
                        <span>Reels</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 2: PHILOSOPHY -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">02 / 07</span>
        </div>
        <div class="split-layout">
            <div class="portrait-container">
                <div class="portrait-circle">
                    <svg width="42" height="42" viewBox="0 0 24 24" fill="none" stroke="#f472b6" stroke-width="1.5"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                </div>
                <span style="font-size: 0.7rem; letter-spacing: 2px; text-transform: uppercase; color: var(--text-secondary);">Visual Director</span>
            </div>
            <div>
                <h2 class="section-title">THE CREATIVE PHILOSOPHY</h2>
                <p class="subtitle">Where precision strategy meets high-end editorial aesthetics. I transform digital presence into curated visual experiences that capture attention and build brand prestige.</p>
                <div class="stats-row">
                    <div class="stat-box">
                        <h4>100%</h4>
                        <p>Bespoke</p>
                    </div>
                    <div class="stat-box">
                        <h4>High</h4>
                        <p>Aesthetic</p>
                    </div>
                    <div class="stat-box">
                        <h4>Focused</h4>
                        <p>Impact</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 3: SERVICES -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">03 / 07</span>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18"/><path d="M9 21V9"/></svg>
                    <h3>Visual Curation</h3>
                    <ul>
                        <li>Editorial feed aesthetics</li>
                        <li>Bespoke graphic layouts</li>
                        <li>Typography & color palettes</li>
                    </ul>
                </div>
                <div class="service-tag">✦ Refined Brand Presence</div>
            </div>
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><path d="M23 7l-7 5 7 5V7z"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg>
                    <h3>Motion & Video</h3>
                    <ul>
                        <li>Short-form reel direction</li>
                        <li>Rhythmic video editing</li>
                        <li>High-converting motion ads</li>
                    </ul>
                </div>
                <div class="service-tag">✦ Drives Audience Reach</div>
            </div>
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
                    <h3>AI Visual Strategy</h3>
                    <ul>
                        <li>Generative product imagery</li>
                        <li>Studio avatar photography</li>
                        <li>Synthetic shoot direction</li>
                    </ul>
                </div>
                <div class="service-tag">✦ Unlocks Creative Limits</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 4: CASE STUDY -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">04 / 07</span>
        </div>
        <div class="case-layout">
            <div class="case-visual-box">
                <span style="font-size: 0.7rem; color: var(--text-secondary); letter-spacing: 1.5px; text-transform: uppercase;">Reach & Engagement Scaling</span>
                <svg class="chart-art" viewBox="0 0 300 120" preserveAspectRatio="none">
                    <defs>
                        <linearGradient id="artGrad" x1="0" y1="0" x2="0" y2="1">
                            <stop offset="0%" stop-color="#f472b6" stop-opacity="0.4"/>
                            <stop offset="100%" stop-color="#f472b6" stop-opacity="0.0"/>
                        </linearGradient>
                    </defs>
                    <path d="M0,100 C60,90 100,50 180,40 C240,30 260,10 300,5 L300,120 L0,120 Z" fill="url(#artGrad)"/>
                    <path d="M0,100 C60,90 100,50 180,40 C240,30 260,10 300,5" fill="none" stroke="#f472b6" stroke-width="2.5"/>
                </svg>
                <div style="display: flex; justify-content: space-between; font-size: 0.68rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px;">
                    <span>Audit & Concept</span>
                    <span>Visual Refresh</span>
                    <span>Scalable Reach</span>
                </div>
            </div>
            <div>
                <h2 class="section-title">CASE HIGHLIGHTS</h2>
                <div class="detail-card">
                    <h5>The Challenge</h5>
                    <p>Inconsistent aesthetic output and low visual engagement across platforms.</p>
                </div>
                <div class="detail-card">
                    <h5>The Creative Solution</h5>
                    <p>Cohesive luxury makeover combining synthetic AI assets with motion reels.</p>
                </div>
                <div class="detail-card">
                    <h5>The Result</h5>
                    <p>Elevated brand prestige, high organic retention, and increased conversions.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 5: SAMPLE WORKS (NEW & ARTISTIC) -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">05 / 07</span>
        </div>
        <div style="display: flex; flex-direction: column; height: 100%;">
            <h2 class="section-title">CURATED SAMPLE WORKS</h2>
            <p class="subtitle">A blend of synthetic AI imagery, handcrafted vector typography, and short-form video motion.</p>
            
            <div class="sample-grid">
                <!-- Card 1: AI Imagery -->
                <div class="sample-card">
                    <div>
                        <span class="sample-badge">AI Visual Assets</span>
                        <h3>Studio & Editorial Imagery</h3>
                        <ul>
                            <li>High-key studio beauty portraits</li>
                            <li>Ghost mannequin product shots</li>
                            <li>Luxury swimwear & footwear assets</li>
                            <li>3-Step visual product user guides</li>
                        </ul>
                    </div>
                    <div class="sample-tools">Tools: Midjourney / AI Imagery Generators</div>
                </div>

                <!-- Card 2: Manual Graphics -->
                <div class="sample-card">
                    <div>
                        <span class="sample-badge">Handcrafted Graphics</span>
                        <h3>Branding & Apparel Design</h3>
                        <ul>
                            <li>Minimalist typography & logotypes</li>
                            <li>Custom sans-serif apparel branding</li>
                            <li>Cohesive social carousel graphics</li>
                            <li>Vector apparel & graphic overlays</li>
                        </ul>
                    </div>
                    <div class="sample-tools">Tools: Photoshop / Illustrator / Canva Pro</div>
                </div>

                <!-- Card 3: Video & Reels -->
                <div class="sample-card">
                    <div>
                        <span class="sample-badge">Motion & Video</span>
                        <h3>Short-Form Reels Direction</h3>
                        <ul>
                            <li>Dynamic cuts & rhythmic transitions</li>
                            <li>Aesthetic product feature highlights</li>
                            <li>On-trend audio & text overlay sync</li>
                            <li>High-converting video ad edits</li>
                        </ul>
                    </div>
                    <div class="sample-tools">Tools: CapCut Pro / Premiere / Meta Suite</div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 6: TOOLKIT -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">06 / 07</span>
        </div>
        <div style="display: flex; flex-direction: column; justify-content: center; height: 100%;">
            <h2 class="section-title">CREATIVE TOOLKIT</h2>
            <p class="subtitle">Mastery over premier editing, AI design, and visual suite platforms.</p>
            <div class="tag-cloud">
                <div class="tag-item"><span class="tag-dot"></span>Midjourney & AI Image Generators</div>
                <div class="tag-item"><span class="tag-dot"></span>Adobe Photoshop</div>
                <div class="tag-item"><span class="tag-dot"></span>CapCut Pro & Premiere</div>
                <div class="tag-item"><span class="tag-dot"></span>Canva Pro</div>
                <div class="tag-item"><span class="tag-dot"></span>Meta Business Suite</div>
                <div class="tag-item"><span class="tag-dot"></span>Grid Curation & Aesthetics</div>
                <div class="tag-item"><span class="tag-dot"></span>Typography & Logo Design</div>
                <div class="tag-item"><span class="tag-dot"></span>Copywriting & Narrative</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 7: PROCESS & CTA -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">07 / 07</span>
        </div>
        <div style="display: flex; flex-direction: column; justify-content: space-between; height: 100%;">
            <div>
                <h2 class="section-title">THE WORKFLOW</h2>
                <p class="subtitle">An intentional, seamless approach to crafting your brand's digital presence.</p>
                <div class="process-grid">
                    <div class="process-card">
                        <div class="step-number">01.</div>
                        <div class="step-title">Discovery</div>
                        <div class="step-desc">Aesthetic audit, brand story alignment, and visual trajectory mapping.</div>
                    </div>
                    <div class="process-card">
                        <div class="step-number">02.</div>
                        <div class="step-title">Creation</div>
                        <div class="step-desc">Crafting AI imagery, vector graphics, and rhythmic video motion.</div>
                    </div>
                    <div class="process-card">
                        <div class="step-number">03.</div>
                        <div class="step-title">Elevation</div>
                        <div class="step-desc">Deploying curated feed visuals and scaling audience engagement.</div>
                    </div>
                </div>
            </div>
            <div class="cta-bar">
                <span>Ready to transform your visual identity?</span>
                <a href="mailto:juliet.binas.pandroutsourcing@gmail.com" class="btn-pill" style="padding: 10px 22px; font-size: 0.7rem;">Book Consultation</a>
            </div>
        </div>
    </div>

</body>
</html>
