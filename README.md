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

        body {
            background-color: #050505;
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
            background-color: #0d0d0d;
            border: 1px solid #262626;
            border-radius: 12px;
            padding: 48px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            box-shadow: 0 20px 40px rgba(0,0,0,0.8);
            overflow: hidden;
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
            color: #ffffff;
        }

        .slide-number {
            font-size: 0.85rem;
            color: #525252;
            font-weight: 600;
        }

        /* Typography Essentials */
        .hero-title {
            font-size: 2.5rem;
            font-weight: 700;
            line-height: 1.15;
            letter-spacing: -0.5px;
            color: #ffffff;
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 8px;
        }

        .subtitle {
            font-size: 0.95rem;
            color: #a3a3a3;
        }

        /* Buttons & Callout Graphics */
        .btn-pill {
            display: inline-block;
            background-color: #ffffff;
            color: #000000;
            padding: 10px 24px;
            font-size: 0.85rem;
            font-weight: 700;
            border-radius: 20px;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none;
            width: fit-content;
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
            height: 220px;
            background-color: #171717;
            border: 2px solid #262626;
            border-radius: 16px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 8px;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.5);
        }

        .mockup-grid {
            display: grid;
            grid-template-columns: repeat(3, 40px);
            gap: 6px;
        }

        .mockup-item {
            width: 40px;
            height: 40px;
            background-color: #262626;
            border-radius: 4px;
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
            background-color: #171717;
            border: 1px solid #262626;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #525252;
            font-size: 0.85rem;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-top: 24px;
        }

        .stat-card {
            background-color: #171717;
            padding: 12px;
            border-radius: 6px;
            border: 1px solid #262626;
            text-align: center;
        }

        .stat-card h4 {
            font-size: 0.95rem;
            color: #ffffff;
        }

        .stat-card p {
            font-size: 0.75rem;
            color: #737373;
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
            background-color: #171717;
            border: 1px solid #262626;
            border-radius: 8px;
            padding: 20px;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .service-card h3 {
            font-size: 1rem;
            color: #ffffff;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .service-card ul {
            list-style: none;
            color: #a3a3a3;
            font-size: 0.8rem;
            line-height: 1.8;
        }

        .service-impact {
            margin-top: 12px;
            padding-top: 12px;
            border-top: 1px solid #262626;
            font-size: 0.75rem;
            color: #ffffff;
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
            background-color: #171717;
            border: 1px solid #262626;
            border-radius: 8px;
            height: 240px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #525252;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        .case-details {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .detail-box {
            background-color: #171717;
            border-left: 2px solid #ffffff;
            padding: 10px 16px;
        }

        .detail-box h5 {
            font-size: 0.75rem;
            color: #737373;
            text-transform: uppercase;
        }

        .detail-box p {
            font-size: 0.85rem;
            color: #d4d4d4;
        }

        /* Slide 5: Tech Stack Tag Cloud */
        .stack-container {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 24px;
        }

        .tag-pill {
            background-color: #171717;
            border: 1px solid #262626;
            padding: 12px 20px;
            border-radius: 30px;
            font-size: 0.85rem;
            color: #e5e5e5;
            font-weight: 500;
        }

        /* Slide 6: Process & Contact CTA */
        .process-row {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            margin: 20px 0;
        }

        .process-step {
            background-color: #171717;
            border: 1px solid #262626;
            border-radius: 8px;
            padding: 16px;
        }

        .step-num {
            font-size: 1.2rem;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 4px;
        }

        .step-title {
            font-size: 0.85rem;
            font-weight: 600;
            color: #d4d4d4;
        }

        .step-desc {
            font-size: 0.75rem;
            color: #737373;
        }

        .contact-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #171717;
            padding: 16px 24px;
            border-radius: 8px;
            border: 1px solid #262626;
            font-size: 0.85rem;
            color: #a3a3a3;
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
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">01 / 06</span>
        </div>
        <div class="cover-content">
            <div>
                <h1 class="hero-title">TURNING DIGITAL NOISE INTO BRAND AUTHORITY.</h1>
                <p class="subtitle" style="margin-top: 12px; margin-bottom: 24px;">Social Media Management & Brand Strategy</p>
                <a href="mailto:juliet.binas.pandroutsourcing@gmail.com" class="btn-pill">Book Discovery Call</a>
            </div>
            <div class="device-mockup">
                <span style="font-size: 0.7rem; color: #525252; text-transform: uppercase; letter-spacing: 1px;">Live Grid Mockup</span>
                <div class="mockup-grid">
                    <div class="mockup-item"></div>
                    <div class="mockup-item"></div>
                    <div class="mockup-item"></div>
                    <div class="mockup-item"></div>
                    <div class="mockup-item"></div>
                    <div class="mockup-item"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 2: ABOUT / PHILOSOPHY -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">02 / 06</span>
        </div>
        <div class="split-layout">
            <div class="portrait-frame">
                Editorial Image
            </div>
            <div>
                <h2 class="section-title">THE APPROACH</h2>
                <p class="subtitle">I combine storytelling, short-form video strategy, and data-driven systems to help premium brands build presence, capture attention, and scale organic reach.</p>
                
                <div class="stats-grid">
                    <div class="stat-card">
                        <h4>100%</h4>
                        <p>Organic Focus</p>
                    </div>
                    <div class="stat-card">
                        <h4>High-Ticket</h4>
                        <p>Positioning</p>
                    </div>
                    <div class="stat-card">
                        <h4>End-to-End</h4>
                        <p>Execution</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 3: SERVICES GRID -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">03 / 06</span>
        </div>
        <div>
            <h2 class="section-title">CORE SERVICES</h2>
            <p class="subtitle">Structured solutions designed for high-ticket growth.</p>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <div>
                    <h3>Social Media Mgmt</h3>
                    <ul>
                        <li>• Account Optimization</li>
                        <li>• Content Publishing</li>
                        <li>• Community Engagement</li>
                        <li>• Monthly Performance</li>
                    </ul>
                </div>
                <div class="service-impact">Outcome: Brand Authority</div>
            </div>
            <div class="service-card">
                <div>
                    <h3>Content Creation</h3>
                    <ul>
                        <li>• Short-Form Reels/TikToks</li>
                        <li>• Minimalist Graphic Design</li>
                        <li>• SEO Captions & Copy</li>
                        <li>• Visual Feed Curation</li>
                    </ul>
                </div>
                <div class="service-impact">Outcome: Organic Reach</div>
            </div>
            <div class="service-card">
                <div>
                    <h3>Brand Consulting</h3>
                    <ul>
                        <li>• 1-on-1 Strategy Calls</li>
                        <li>• Content System Setup</li>
                        <li>• Workflow Audits</li>
                        <li>• Team Roadmaps</li>
                    </ul>
                </div>
                <div class="service-impact">Outcome: Execution Plan</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 4: CASE STUDY -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">04 / 06</span>
        </div>
        <h2 class="section-title">FEATURED CASE STUDY</h2>
        <div class="case-study-layout">
            <div class="case-visual">
                [ Feed Overhaul Preview ]
            </div>
            <div class="case-details">
                <div class="detail-box">
                    <h5>Challenge</h5>
                    <p>Inconsistent brand aesthetic and stagnant audience interaction across channels.</p>
                </div>
                <div class="detail-box">
                    <h5>Strategy</h5>
                    <p>Implemented a sleek monochrome design system paired with value-first Reel hooks.</p>
                </div>
                <div class="detail-box">
                    <h5>Result</h5>
                    <p>+140% organic profile interactions and unified brand authority within 90 days.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- SLIDE 5: TOOLKIT -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">05 / 06</span>
        </div>
        <div>
            <h2 class="section-title">SYSTEMS & TECH STACK</h2>
            <p class="subtitle">Industry-standard tools utilized for seamless execution.</p>
            <div class="stack-container">
                <div class="tag-pill">CapCut Pro</div>
                <div class="tag-pill">Canva Pro</div>
                <div class="tag-pill">Meta Business Suite</div>
                <div class="tag-pill">Notion Workspaces</div>
                <div class="tag-pill">Adobe Creative Suite</div>
                <div class="tag-pill">AI Prompt Engineering</div>
                <div class="tag-pill">SEO Copywriting</div>
            </div>
        </div>
    </div>

    <!-- SLIDE 6: CTA & PROCESS -->
    <div class="slide">
        <div class="slide-header">
            <span class="brand-name">Juliet Binas</span>
            <span class="slide-number">06 / 06</span>
        </div>
        <div>
            <h2 class="section-title">READY TO ELEVATE YOUR BRAND?</h2>
            <p class="subtitle">A simple 3-step process to get started.</p>
            
            <div class="process-row">
                <div class="process-step">
                    <div class="step-num">01</div>
                    <div class="step-title">Discovery Call</div>
                    <div class="step-desc">15-minute alignment session</div>
                </div>
                <div class="process-step">
                    <div class="step-num">02</div>
                    <div class="step-title">Custom Proposal</div>
                    <div class="step-desc">Tailored strategy & roadmap</div>
                </div>
                <div class="process-step">
                    <div class="step-num">03</div>
                    <div class="step-title">Launch & Scale</div>
                    <div class="step-desc">Seamless execution</div>
                </div>
            </div>

            <div class="contact-bar">
                <span>📧 juliet.binas.pandroutsourcing@gmail.com</span>
                <span>📱 09530792114</span>
            </div>
        </div>
    </div>

</body>
</html>
