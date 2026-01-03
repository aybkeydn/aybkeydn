<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aybüke Aydın - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            font-family: 'Fira Code', monospace;
            color: #fff;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .header {
            text-align: center;
            margin-bottom: 50px;
            animation: fadeInDown 0.8s ease;
        }

        .header h1 {
            font-size: 3.5em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff66c4, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .typing-text {
            font-size: 1.3em;
            color: #fff;
            min-height: 40px;
        }

        .status-badge {
            display: inline-block;
            padding: 8px 16px;
            background: rgba(255, 102, 196, 0.3);
            border: 2px solid #ff66c4;
            border-radius: 20px;
            margin-top: 15px;
            font-size: 0.9em;
            animation: pulse 2s infinite;
        }

        .status-badge::before {
            content: '● ';
            color: #4ade80;
            margin-right: 5px;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 25px;
            animation: fadeInUp 0.8s ease;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 102, 196, 0.3);
        }

        .card h2 {
            color: #ff66c4;
            margin-bottom: 15px;
            font-size: 1.5em;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 15px;
        }

        .stat-box {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            border-left: 3px solid #ffd700;
        }

        .stat-number {
            font-size: 2em;
            font-weight: bold;
            color: #ffd700;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 0.9em;
            color: #ccc;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .tech-badge {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .activity-timeline {
            position: relative;
            padding: 20px 0;
        }

        .timeline-item {
            display: flex;
            margin-bottom: 20px;
            padding-left: 40px;
            position: relative;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: 5px;
            top: 0;
            width: 15px;
            height: 15px;
            background: #ff66c4;
            border-radius: 50%;
            border: 3px solid #667eea;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            left: 12px;
            top: 15px;
            width: 2px;
            height: 100%;
            background: rgba(255, 102, 196, 0.3);
        }

        .timeline-item:last-child::after {
            display: none;
        }

        .timeline-content {
            flex: 1;
        }

        .timeline-title {
            color: #ffd700;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .timeline-desc {
            color: #ccc;
            font-size: 0.9em;
        }

        .github-graphs {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }

        .graph-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 25px;
            animation: fadeInUp 0.8s ease;
        }

        .graph-card h2 {
            color: #ff66c4;
            margin-bottom: 20px;
            font-size: 1.3em;
        }

        .contribution-graph {
            background: rgba(0, 0, 0, 0.3);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 15px;
            overflow-x: auto;
        }

        .contribution-week {
            display: inline-flex;
            flex-direction: column;
            margin-right: 3px;
            gap: 2px;
        }

        .contribution-day {
            width: 12px;
            height: 12px;
            border-radius: 2px;
            background: rgba(255, 255, 255, 0.1);
        }

        .contribution-day.active {
            background: linear-gradient(135deg, #ff66c4, #ffd700);
        }

        .stats-row {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 20px;
        }

        .streak-card {
            background: rgba(255, 215, 0, 0.1);
            padding: 15px;
            border-radius: 10px;
            border-left: 3px solid #ffd700;
            text-align: center;
        }

        .streak-number {
            font-size: 2.5em;
            color: #ffd700;
            font-weight: bold;
        }

        .streak-label {
            color: #ccc;
            margin-top: 5px;
        }

        .languages {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 15px;
        }

        .language {
            background: rgba(255, 255, 255, 0.05);
            padding: 12px;
            border-radius: 8px;
            border-left: 3px solid #ff66c4;
        }

        .lang-name {
            color: #ffd700;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .lang-bar {
            background: rgba(255, 255, 255, 0.1);
            height: 6px;
            border-radius: 3px;
            overflow: hidden;
            margin-top: 5px;
        }

        .lang-fill {
            height: 100%;
            background: linear-gradient(90deg, #ff66c4, #ffd700);
        }

        .footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
        }

        .social-links {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 15px;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background: rgba(255, 102, 196, 0.2);
            border: 1px solid #ff66c4;
            border-radius: 50%;
            color: #ff66c4;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.3em;
        }

        .social-link:hover {
            background: #ff66c4;
            color: #667eea;
            transform: translateY(-3px);
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            .main-grid {
                grid-template-columns: 1fr;
            }

            .stats-row {
                grid-template-columns: 1fr;
            }

            .languages {
                grid-template-columns: 1fr;
            }

            .header h1 {
                font-size: 2em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>👋 Aybüke Aydın</h1>
            <div class="typing-text">Full Stack Developer | Design Enthusiast | Code Artist</div>
            <div class="status-badge">Available for Freelance & Full-time</div>
        </div>

        <!-- Main Grid -->
        <div class="main-grid">
            <!-- About Card -->
            <div class="card">
                <h2>🎨 About Me</h2>
                <p style="line-height: 1.6;">Passionate full-stack developer combining elegant design with powerful code. Currently mastering ASP.NET, C#, and modern web technologies. Creating user-friendly applications that make a difference.</p>
                <div class="tech-stack">
                    <span class="tech-badge">ASP.NET</span>
                    <span class="tech-badge">C#</span>
                    <span class="tech-badge">JavaScript</span>
                    <span class="tech-badge">MSSQL</span>
                    <span class="tech-badge">MongoDB</span>
                </div>
            </div>

            <!-- Stats Card -->
            <div class="card">
                <h2>📊 Quick Stats</h2>
                <div class="stats-grid">
                    <div class="stat-box">
                        <div class="stat-number">47+</div>
                        <div class="stat-label">Repositories</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">1.2K+</div>
                        <div class="stat-label">Total Commits</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">15+</div>
                        <div class="stat-label">Projects</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">8</div>
                        <div class="stat-label">Tech Stacks</div>
                    </div>
                </div>
            </div>

            <!-- Current Status Card -->
            <div class="card">
                <h2>🔄 Current Status</h2>
                <div class="activity-timeline">
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">🚀 Working On</div>
                            <div class="timeline-desc">E-Commerce Platform with ASP.NET</div>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">📚 Learning</div>
                            <div class="timeline-desc">Advanced Full-Stack Development</div>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">🎯 Goal</div>
                            <div class="timeline-desc">Build Amazing Portfolio Projects</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tech Stack Card -->
            <div class="card">
                <h2>💻 Tech Stack</h2>
                <div style="margin-top: 15px;">
                    <strong style="color: #ff66c4;">Languages:</strong>
                    <div class="tech-stack" style="margin-top: 8px;">
                        <span class="tech-badge">C#</span>
                        <span class="tech-badge">JavaScript</span>
                        <span class="tech-badge">HTML5</span>
                        <span class="tech-badge">CSS3</span>
                    </div>
                </div>
                <div style="margin-top: 15px;">
                    <strong style="color: #ff66c4;">Databases:</strong>
                    <div class="tech-stack" style="margin-top: 8px;">
                        <span class="tech-badge">MSSQL</span>
                        <span class="tech-badge">MongoDB</span>
                        <span class="tech-badge">Dapper</span>
                    </div>
                </div>
                <div style="margin-top: 15px;">
                    <strong style="color: #ff66c4;">Tools & Design:</strong>
                    <div class="tech-stack" style="margin-top: 8px;">
                        <span class="tech-badge">Figma</span>
                        <span class="tech-badge">Adobe PS</span>
                        <span class="tech-badge">Git</span>
                        <span class="tech-badge">GitHub</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- GitHub Stats Section -->
        <div class="github-graphs">
            <!-- Contribution Stats -->
            <div class="graph-card">
                <h2>🔥 GitHub Contribution Streak</h2>
                <div class="stats-row">
                    <div class="streak-card">
                        <div class="streak-number">42</div>
                        <div class="streak-label">Current Streak</div>
                    </div>
                    <div class="streak-card">
                        <div class="streak-number">1,247</div>
                        <div class="streak-label">Total Commits</div>
                    </div>
                    <div class="streak-card">
                        <div class="streak-number">156</div>
                        <div class="streak-label">Contributions</div>
                    </div>
                </div>
            </div>

            <!-- Languages -->
            <div class="graph-card">
                <h2>📝 Top Languages</h2>
                <div class="languages">
                    <div class="language">
                        <div class="lang-name">JavaScript</div>
                        <div class="lang-bar">
                            <div class="lang-fill" style="width: 85%"></div>
                        </div>
                        <small>85%</small>
                    </div>
                    <div class="language">
                        <div class="lang-name">C#</div>
                        <div class="lang-bar">
                            <div class="lang-fill" style="width: 70%"></div>
                        </div>
                        <small>70%</small>
                    </div>
                    <div class="language">
                        <div class="lang-name">HTML/CSS</div>
                        <div class="lang-bar">
                            <div class="lang-fill" style="width: 80%"></div>
                        </div>
                        <small>80%</small>
                    </div>
                    <div class="language">
                        <div class="lang-name">SQL</div>
                        <div class="lang-bar">
                            <div class="lang-fill" style="width: 75%"></div>
                        </div>
                        <small>75%</small>
                    </div>
                </div>
            </div>

            <!-- Recent Activity -->
            <div class="graph-card">
                <h2>⚡ Recent Activity</h2>
                <div class="activity-timeline">
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">Pushed to E-Commerce API</div>
                            <div class="timeline-desc">Implemented user authentication system • 5 hours ago</div>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">Merged Pull Request</div>
                            <div class="timeline-desc">Design System Components Update • 1 day ago</div>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">Created New Repository</div>
                            <div class="timeline-desc">Portfolio Website Project Started • 2 days ago</div>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-title">Code Review Complete</div>
                            <div class="timeline-desc">Reviewed 3 pull requests with suggestions • 3 days ago</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <h3 style="color: #ff66c4; margin-bottom: 10px;">Let's Connect! 🚀</h3>
            <p>Always open to exciting projects and collaborations</p>
            <div class="social-links">
                <a href="https://github.com/aybkeydn" class="social-link" title="GitHub">
                    <span>🐙</span>
                </a>
                <a href="https://linkedin.com/in/aybüke-aydin-568a89240/" class="social-link" title="LinkedIn">
                    <span>in</span>
                </a>
                <a href="mailto:your@email.com" class="social-link" title="Email">
                    <span>✉️</span>
                </a>
            </div>
            <p style="margin-top: 20px; color: #999; font-size: 0.9em;">Made with 💜 by Aybüke Aydın</p>
        </div>
    </div>
</body>
</html>
