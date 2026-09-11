<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juliet Binas | Visual Portfolio Presentation</title>
    <style>
        /* CSS Reset & Dark Mode Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        :root {
            --bg-color: #050505;
            --card-bg: #0d0d0d;
            --card-surface: #141414;
            --border-color: #262626;
            --accent-color: #3b82f6;
            --accent-glow: rgba(59, 130, 246, 0.15);
            --text-primary: #ffffff;
            --text-secondary: #a3a3a3;
            --text-muted: #525252;
        }

        body {
            background-color: var(--bg-color);
            color: #f2f2f2;
            padding: 40px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 40px;
        }

        /* Slide Container Setup */
        .slide {
            width: 100%;
            max-width: 960px;
            aspect-ratio: 16 / 9;
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 40px 48px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            box-shadow: 0 20px 50px rgba(0,0,0,0.8);
            overflow: hidden;
            transition: border-color 0.3s ease;
        }

        .slide:hover {
            border-color: #404040;
        }

        /* Ambient Light Graphic Accent */
        .slide::before {
            content: '';
            position: absolute;
            top: -100px;
            right: -100px;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, var(--accent-glow) 0%, rgba(0,0,0,0) 70%);
            pointer-events: none;
            z-index: 0;
        }

        .slide > * {
            position: relative;
            z-index: 1;
        }

        /* Header / Meta Elements */
        .slide-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #1a1a1a;
            padding-bottom: 16px;
        }

        .brand-name {
            font-size: 0.85rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .brand-dot {
            width: 8px;
            height: 8px;
            background-color: var(--accent-color);
            border-radius: 50%;
            box-shadow: 0 0 8px var(--accent-color);
        }

        .slide-number {
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 600;
        }

        /* Typography Essentials */
        .hero-title {
            font-size: 2.3rem;
            font-weight: 800;
            line-height: 1.15;
            letter-spacing: -0.5px;
            color: var(--text-primary);
            background: linear-gradient(180deg, #ffffff 0%, #a3a3a3 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 8px;
        }

        .subtitle {
            font-size: 0.95rem;
            color: var(--text-secondary);
            line-height: 1.5;
        }

        /* Buttons & Callout Graphics */
        .btn-pill {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background-color: var(--text-primary);
            color: #000000;
            padding: 10px 24px;
            font-size: 0.85rem;
            font-weight: 700;
            border-radius: 20px;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none;
            width: fit-content;
            transition: all 0.3s ease;
        }

        .btn-pill:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255,255,255,0.2);
        }

        /* Slide 1: Cover Layout */
        .cover-content {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 24px;
            align-items: center;
            height: 100%;
        }

        .device-mockup {
            width: 100%;
            height: 240px;
            background-color: var(--card-surface);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 16px;
            display: flex;
            flex-direction: column;
            gap: 12px;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.5);
            position: relative;
        }

        .mockup-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.7rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .status-dots {
            display: flex;
            gap: 4px;
        }

        .status-dot {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background-color: #333;
        }

        .mockup-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 8px;
            height: 100%;
        }

        .mockup-item {
            background-color: #1a1a1a;
            border-radius: 6px;
            border: 1px solid #262626;
            overflow: hidden;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.2s ease;
        }

        .mockup-item:hover {
            transform: scale(1.02);
            border-color: var(--accent-color);
        }

        .mockup-item svg {
            width: 24px;
            height: 24px;
            fill: #404040;
        }

        /* Slide 2: Split Columns */
        .split-layout {
            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 32px;
            align-items: center;
            height: 100%;
        }

        .portrait-frame {
            width: 100%;
            height: 240px;
            background: linear-gradient(135deg, #171717 0%, #0d0d0d 100%);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 12px;
            color: var(--text-muted);
            position: relative;
            overflow: hidden;
        }

        .portrait-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: #262626;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid #404040;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-top: 24px;
        }

        .stat-card {
            background-color: var(--card-surface);
            padding: 12px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            text-align: center;
        }

        .stat-card h4 {
            font-size: 1.1rem;
            color: var(--text-primary);
            font-weight: 700;
        }

        .stat-card p {
            font-size: 0.72rem;
            color: var(--text-muted);
            margin-top: 2px;
        }

        /* Slide 3: Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            height: 100%;
            align-items: center;
        }

        .service-card {
            background-color: var(--card-surface);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 20px;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.3s ease;
        }

        .service-card:hover {
            border-color: #404040;
            transform: translateY(-4px);
        }

        .service-icon {
            width: 32px;
            height: 32px;
            margin-bottom: 12px;
            stroke: var(--accent-color);
            stroke-width: 2;
            fill: none;
        }

        .service-card h3 {
            font-size: 0.95rem;
            color: var(--text-primary);
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .service-card ul {
            list-style: none;
            color: var(--text-secondary);
            font-size: 0.78rem;
            line-height: 1.7;
        }

        .service-card ul li::before {
            content: "• ";
            color: var(--accent-color);
        }

        .service-impact {
            margin-top: 12px;
            padding-top: 12px;
            border-top: 1px solid var(--border-color);
            font-size: 0.75rem;
            color: var(--text-primary);
            font-weight: 600;
        }

        /* Slide 4: Case Study Split */
        .case-study-layout {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 24px;
            height: 100%;
            align-items: center;
        }

        .case-visual {
            background-color: var(--card-surface);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            height: 240px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .chart-graphic {
            width: 100%;
            height: 140px;
        }

        .case-details {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .detail-box {
            background-color: var(--card-surface);
            border-left: 3px solid var(--accent-color);
            padding: 10px 14px;
            border-radius: 0 8px 8px 0;
        }

        .detail-box h5 {
            font-size: 0.7rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .detail-box p {
            font-size: 0.82rem;
            color: #d4d4d4;
            margin-top: 2px;
        }

        /* Slide 5: Tech Stack Tag Cloud */
        .stack-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 20px;
        }

        .tag-pill {
            background-color: var(--card-surface);
            border: 1px solid var(--border-color);
            padding: 10px 18px;
            border-radius: 30px;
            font-size: 0.82rem;
            color: #e5e5e5;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s ease;
        }

        .tag-pill:hover {
            border-color: var(--accent-color);
            color: #ffffff;
            background-color: #1a1a1a;
        }

        .tag-dot {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background-color: var(--accent-color);
        }

        /* Slide 6: Process & Contact CTA */
        .process-row {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            margin: 16px 0;
        }

        .process-step {
            background-color: var(--card-surface);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 16px;
            position: relative;
        }

        .step-num {
            font-size: 1.1rem;
            font-weight: 800;
            color: var(--accent-color);
            margin-bottom: 4px;
        }

        .step-title {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-primary);
        }

        .step-desc {
            font-size: 0.73rem;
            color: var(--text-muted);
            margin-top: 4px;
            line-height: 1.4;
        }

        .contact-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: var(--card-surface);
            padding: 14px 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            font-size: 0.82rem;
            color: var(--text-secondary);
        }

        /* Responsive Scaling for Smaller Viewports */
        @media (max-width: 800px) {
            .slide {
                aspect-ratio: auto;
                height: auto;
                padding: 24px;
            }
            .cover-content, .split-layout, .services-grid, .case-study-layout, .process-row {
                grid-template-columns: 1fr;
            }
            .contact-bar {
                flex-direction: column;
                gap: 12px;
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <!-- SLIDE 1: COVER -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">01 / 06</span>
        </div>
        <div class="cover-content">
            <div>
                <h1 class="hero-title">TURNING DIGITAL NOISE INTO BRAND AUTHORITY.</h1>
                <p class="subtitle" style="margin-top: 12px; margin-bottom: 24px;">Social Media Management & Brand Strategy</p>
                <a href="mailto:juliet.binas.pandroutsourcing@gmail.com" class="btn-pill">
                    Book Discovery Call
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
                </a>
            </div>
            <div class="device-mockup">
                <div class="mockup-header">
                    <span>Live Content Grid</span>
                    <div class="status-dots">
                        <div class="status-dot"></div>
                        <div class="status-dot"></div>
                        <div class="status-dot"></div>
                    </div>
                </div>
                <div class="mockup-grid">
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
                    </div>
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><polygon points="23 7 16 12 23 17 23 7"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg>
                    </div>
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
                    </div>
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>
                    </div>
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
                    </div>
                    <div class="mockup-item">
                        <svg viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 2: ABOUT / PHILOSOPHY -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">02 / 06</span>
        </div>
        <div class="split-layout">
            <div class="portrait-frame">
                <div class="portrait-avatar">
                    <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="#737373" stroke-width="1.5"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                </div>
                <span style="font-size: 0.75rem; letter-spacing: 1px; text-transform: uppercase;">Visual Strategist</span>
            </div>
            <div>
                <h2 class="section-title">THE APPROACH</h2>
                <p class="subtitle">I combine visual storytelling, aesthetic content creation, and tailored positioning strategy to help brands build a distinctive presence and cultivate lasting audience authority.</p>
                <div class="stats-grid">
                    <div class="stat-card">
                        <h4>100%</h4>
                        <p>Custom Content</p>
                    </div>
                    <div class="stat-card">
                        <h4>Tailored</h4>
                        <p>Visual Style</p>
                    </div>
                    <div class="stat-card">
                        <h4>Strategic</h4>
                        <p>Growth Focus</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 3: SERVICES GRID -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">03 / 06</span>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2" ry="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
                    <h3>Visual Branding</h3>
                    <ul>
                        <li>Feed aesthetic design</li>
                        <li>Custom graphic templates</li>
                        <li>Brand color direction</li>
                    </ul>
                </div>
                <div class="service-impact">Elevates Visual Identity</div>
            </div>
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><path d="M23 7l-7 5 7 5V7z"/><rect x="1" y="5" width="15" height="14" rx="2" ry="2"/></svg>
                    <h3>Content Strategy</h3>
                    <ul>
                        <li>Short-form video concepts</li>
                        <li>Editorial content planning</li>
                        <li>Copywriting & captions</li>
                    </ul>
                </div>
                <div class="service-impact">Drives Audience Engagement</div>
            </div>
            <div class="service-card">
                <div>
                    <svg class="service-icon" viewBox="0 0 24 24"><path d="M18 20V10"/><path d="M12 20V4"/><path d="M6 20v-6"/></svg>
                    <h3>Growth Management</h3>
                    <ul>
                        <li>Platform optimization</li>
                        <li>Analytics & reporting</li>
                        <li>Community interaction</li>
                    </ul>
                </div>
                <div class="service-impact">Sustains Long-Term Authority</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 4: CASE STUDY SPLIT -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">04 / 06</span>
        </div>
        <div class="case-study-layout">
            <div class="case-visual">
                <span style="font-size: 0.75rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px;">Performance Growth Trend</span>
                <svg class="chart-graphic" viewBox="0 0 300 120" preserveAspectRatio="none">
                    <defs>
                        <linearGradient id="chartGrad" x1="0" y1="0" x2="0" y2="1">
                            <stop offset="0%" stop-color="#3b82f6" stop-opacity="0.4"/>
                            <stop offset="100%" stop-color="#3b82f6" stop-opacity="0.0"/>
                        </linearGradient>
                    </defs>
                    <path d="M0,100 Q60,80 120,60 T240,20 T300,10 L300,120 L0,120 Z" fill="url(#chartGrad)"/>
                    <path d="M0,100 Q60,80 120,60 T240,20 T300,10" fill="none" stroke="#3b82f6" stroke-width="3"/>
                </svg>
                <div style="display: flex; justify-content: space-between; font-size: 0.7rem; color: var(--text-muted);">
                    <span>Phase 1: Audit</span>
                    <span>Phase 2: Redesign</span>
                    <span>Phase 3: Growth</span>
                </div>
            </div>
            <div class="case-details">
                <h2 class="section-title">CAMPAIGN HIGHLIGHTS</h2>
                <div class="detail-box">
                    <h5>The Challenge</h5>
                    <p>Inconsistent brand aesthetic and low engagement across primary social channels.</p>
                </div>
                <div class="detail-box">
                    <h5>The Strategy</h5>
                    <p>Cohesive visual overhaul, high-value educational carousels, and strategic posting schedules.</p>
                </div>
                <div class="detail-box">
                    <h5>The Outcome</h5>
                    <p>Enhanced audience retention, unified brand presentation, and increased direct inquiries.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 5: TECH STACK TAG CLOUD -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">05 / 06</span>
        </div>
        <div style="display: flex; flex-direction: column; justify-content: center; height: 100%;">
            <h2 class="section-title">TOOLKIT & CORE SKILLS</h2>
            <p class="subtitle">Equipped with industry-standard platforms for design, organization, and analytical tracking.</p>
            <div class="stack-container">
                <div class="tag-pill"><span class="tag-dot"></span>Canva Pro</div>
                <div class="tag-pill"><span class="tag-dot"></span>Adobe Photoshop</div>
                <div class="tag-pill"><span class="tag-dot"></span>CapCut / Premiere</div>
                <div class="tag-pill"><span class="tag-dot"></span>Meta Business Suite</div>
                <div class="tag-pill"><span class="tag-dot"></span>Notion & Planning Tools</div>
                <div class="tag-pill"><span class="tag-dot"></span>Content Scheduling</div>
                <div class="tag-pill"><span class="tag-dot"></span>Brand Identity Design</div>
                <div class="tag-pill"><span class="tag-dot"></span>Copywriting</div>
                <div class="tag-pill"><span class="tag-dot"></span>Analytics & Insights</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 6: PROCESS & CONTACT CTA -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name"><span class="brand-dot"></span>Juliet Binas</span>
            <span class="slide-number">06 / 06</span>
        </div>
        <div style="display: flex; flex-direction: column; justify-content: space-between; height: 100%;">
            <div>
                <h2 class="section-title">HOW WE WORK TOGETHER</h2>
                <p class="subtitle">A simple, transparent process to elevate your brand presence.</p>
                <div class="process-row">
                    <div class="process-step">
                        <div class="step-num">01</div>
                        <div class="step-title">Discovery</div>
                        <div class="step-desc">Audit your brand presence, align on goals, and outline the core creative direction.</div>
                    </div>
                    <div class="process-step">
                        <div class="step-num">02</div>
                        <div class="step-title">Execution</div>
                        <div class="step-desc">Design custom templates, draft high-impact copy, and structure your content pipeline.</div>
                    </div>
                    <div class="process-step">
                        <div class="step-num">03</div>
                        <div class="step-title">Optimization</div>
                        <div class="step-desc">Monitor performance metrics, refine strategies, and consistently scale reach.</div>
                    </div>
                </div>
            </div>
            <div class="contact-bar">
                <span>Ready to transform your digital presence?</span>
                <a href="mailto:juliet.binas.pandroutsourcing@gmail.com" class="btn-pill" style="padding: 8px 16px; font-size: 0.75rem;">Get In Touch</a>
            </div>
        </div>
    </div>

</body>
</html>
