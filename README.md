<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kaushal Kishore - DevOps Engineer & Cloud Architect</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #00d9ff;
            --secondary: #ff006e;
            --accent: #8338ec;
            --dark-bg: #0a0e27;
            --darker-bg: #050812;
            --card-bg: #1a1f3a;
            --text-primary: #e0e0ff;
            --text-secondary: #a0a0d0;
            --success: #06ffa5;
            --warning: #ffb703;
        }

        body {
            background: linear-gradient(135deg, var(--darker-bg) 0%, var(--dark-bg) 100%);
            color: var(--text-primary);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(0, 217, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 80%, rgba(131, 56, 236, 0.1) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0%, 100% {
                background: radial-gradient(circle at 20% 50%, rgba(0, 217, 255, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 80% 80%, rgba(131, 56, 236, 0.1) 0%, transparent 50%);
            }
            50% {
                background: radial-gradient(circle at 80% 20%, rgba(0, 217, 255, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 20% 80%, rgba(131, 56, 236, 0.1) 0%, transparent 50%);
            }
        }

        /* Grid pattern */
        body::after {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 217, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 217, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 4rem;
            animation: slideInDown 0.8s ease;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 3.5rem;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 900;
            letter-spacing: -1px;
        }

        .header .subtitle {
            font-size: 1.3rem;
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            font-weight: 300;
        }

        .status-badge {
            display: inline-block;
            padding: 0.6rem 1.5rem;
            background: rgba(6, 255, 165, 0.15);
            border: 1px solid var(--success);
            border-radius: 50px;
            color: var(--success);
            font-size: 0.9rem;
            margin-bottom: 2rem;
            animation: pulse 2s ease infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        /* Hero Section */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            margin-bottom: 4rem;
            align-items: center;
        }

        .hero-content h2 {
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .hero-content p {
            font-size: 1.05rem;
            margin-bottom: 1.5rem;
            color: var(--text-secondary);
            line-height: 1.8;
        }

        .cta-button {
            display: inline-block;
            padding: 0.95rem 2.5rem;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: var(--darker-bg);
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            text-decoration: none;
            margin-right: 1rem;
            margin-bottom: 1rem;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.3);
        }

        .hero-visual {
            perspective: 1000px;
        }

        .code-block {
            background: rgba(10, 14, 39, 0.8);
            border: 1px solid rgba(0, 217, 255, 0.3);
            border-radius: 10px;
            padding: 2rem;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            color: var(--primary);
            overflow-x: auto;
            animation: slideInRight 0.8s ease;
            box-shadow: 0 20px 60px rgba(0, 217, 255, 0.1);
            line-height: 1.6;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Skills Section */
        .section {
            margin-bottom: 4rem;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 2.5rem;
            color: var(--primary);
            position: relative;
            padding-bottom: 1rem;
            border-bottom: 2px solid rgba(0, 217, 255, 0.2);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            animation: expandWidth 0.8s ease;
        }

        @keyframes expandWidth {
            from { width: 0; }
            to { width: 100px; }
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(26, 31, 58, 0.8), rgba(26, 31, 58, 0.4));
            border: 1px solid rgba(0, 217, 255, 0.2);
            border-radius: 12px;
            padding: 2rem;
            transition: all 0.3s ease;
            animation: fadeInUp 0.6s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 217, 255, 0.2) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(0, 217, 255, 0.2);
        }

        .skill-card:hover::before {
            opacity: 1;
        }

        .skill-category {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            padding: 0.5rem 0;
            color: var(--text-secondary);
            position: relative;
            padding-left: 1.5rem;
        }

        .skill-list li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
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

        /* Expertise Cards */
        .expertise-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .expertise-card {
            background: linear-gradient(135deg, rgba(131, 56, 236, 0.15), rgba(0, 217, 255, 0.05));
            border: 1px solid rgba(131, 56, 236, 0.3);
            border-radius: 12px;
            padding: 2.5rem;
            transition: all 0.3s ease;
            animation: fadeInUp 0.6s ease;
        }

        .expertise-card h3 {
            color: var(--accent);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .expertise-card p {
            color: var(--text-secondary);
            line-height: 1.7;
            font-size: 0.95rem;
        }

        .expertise-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent);
            background: linear-gradient(135deg, rgba(131, 56, 236, 0.25), rgba(0, 217, 255, 0.1));
        }

        /* Timeline */
        .timeline {
            position: relative;
            margin: 3rem 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 100%;
            background: linear-gradient(180deg, var(--primary), var(--accent));
        }

        .timeline-item {
            margin-bottom: 3rem;
            width: 48%;
            animation: fadeInUp 0.6s ease;
        }

        .timeline-item:nth-child(odd) {
            margin-left: 0;
            text-align: right;
            padding-right: 4%;
        }

        .timeline-item:nth-child(even) {
            margin-left: 52%;
            text-align: left;
            padding-left: 4%;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            width: 15px;
            height: 15px;
            background: var(--primary);
            border: 3px solid var(--darker-bg);
            border-radius: 50%;
            left: 50%;
            transform: translateX(-50%);
            transition: all 0.3s ease;
        }

        .timeline-item:hover::before {
            width: 20px;
            height: 20px;
            background: var(--accent);
            box-shadow: 0 0 20px var(--accent);
        }

        .timeline-content {
            background: rgba(26, 31, 58, 0.8);
            border: 1px solid rgba(0, 217, 255, 0.2);
            border-radius: 10px;
            padding: 2rem;
        }

        .timeline-content h4 {
            color: var(--primary);
            margin-bottom: 0.5rem;
        }

        .timeline-content p {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Stats */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat {
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1), rgba(131, 56, 236, 0.1));
            border: 1px solid rgba(0, 217, 255, 0.2);
            border-radius: 10px;
            animation: fadeInUp 0.6s ease;
        }

        .stat-number {
            font-size: 2.5rem;
            color: var(--primary);
            font-weight: 900;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            padding: 3rem;
            background: linear-gradient(135deg, rgba(131, 56, 236, 0.15), rgba(0, 217, 255, 0.1));
            border: 1px solid rgba(0, 217, 255, 0.3);
            border-radius: 15px;
            margin-top: 4rem;
        }

        .contact-section h2 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 2rem;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .contact-link {
            padding: 0.8rem 1.8rem;
            border: 2px solid var(--accent);
            border-radius: 50px;
            color: var(--accent);
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .contact-link:hover {
            background: var(--accent);
            color: var(--darker-bg);
            transform: scale(1.05);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.2rem;
            }

            .hero {
                grid-template-columns: 1fr;
            }

            .timeline::before {
                left: 20px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 60px !important;
                padding-right: 0 !important;
                text-align: left !important;
                margin-left: 0 !important;
            }

            .timeline-item::before {
                left: 0;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Scroll animation */
        .fade-in {
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }

        /* Loading animation */
        .skill-progress {
            width: 100%;
            height: 6px;
            background: rgba(0, 217, 255, 0.1);
            border-radius: 3px;
            overflow: hidden;
            margin-top: 0.8rem;
        }

        .skill-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            border-radius: 3px;
            animation: expandWidth 1.5s ease;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            color: var(--text-secondary);
            border-top: 1px solid rgba(0, 217, 255, 0.1);
            margin-top: 4rem;
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
            margin: 3rem 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="status-badge">🟢 Open to Opportunities</div>
            <h1>KAUSHAL KISHORE</h1>
            <p class="subtitle">DevOps Engineer & Cloud Infrastructure Architect</p>
            <p style="color: var(--text-secondary); font-size: 1rem;">Building resilient, scalable cloud systems that empower teams</p>
        </div>

        <div class="divider"></div>

        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-content">
                <h2>Infrastructure Automation at Scale</h2>
                <p>I design and deploy production-grade cloud infrastructure. Every pipeline, every deployment, every system is architected with one principle: reliability first, velocity second.</p>
                <p>From containerized applications on Kubernetes to infrastructure as code across AWS, Azure, and GCP—I transform complex infrastructure challenges into elegant, repeatable solutions.</p>
                <a href="https://github.com/kaushalacts" class="cta-button">View GitHub</a>
                <a href="mailto:kaushalkishoremnt2000@gmail.com" class="cta-button">Get in Touch</a>
            </div>
            <div class="hero-visual">
                <div class="code-block">
<span style="color: var(--accent);">$</span> devops-workflow
<span style="color: var(--accent);">→</span> Code committed
<span style="color: var(--accent);">→</span> Tests pass
<span style="color: var(--accent);">→</span> Security scan OK
<span style="color: var(--accent);">→</span> Terraform plan review
<span style="color: var(--accent);">→</span> Deploy to staging
<span style="color: var(--accent);">→</span> Smoke tests pass
<span style="color: var(--accent);">→</span> Blue-green deploy
<span style="color: var(--accent);">→</span> Health checks OK
<span style="color: var(--accent);">→</span> Production live ✓</div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Stats -->
        <section class="stats">
            <div class="stat">
                <div class="stat-number">2+</div>
                <div class="stat-label">Years DevOps Experience</div>
            </div>
            <div class="stat">
                <div class="stat-number">3</div>
                <div class="stat-label">Cloud Platforms Mastered</div>
            </div>
            <div class="stat">
                <div class="stat-number">100+</div>
                <div class="stat-label">Infrastructure Deployments</div>
            </div>
            <div class="stat">
                <div class="stat-number">24/7</div>
                <div class="stat-label">System Reliability Focus</div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Core Expertise -->
        <section class="section">
            <h2 class="section-title">🎯 Core Expertise</h2>
            <div class="expertise-grid">
                <div class="expertise-card">
                    <h3>⚡ CI/CD Pipeline Architecture</h3>
                    <p>Designing multi-stage deployment pipelines with automated testing, security scanning, and intelligent rollback strategies using GitHub Actions, GitLab CI/CD, and ArgoCD.</p>
                </div>
                <div class="expertise-card">
                    <h3>🐳 Kubernetes & Containers</h3>
                    <p>Running production Kubernetes clusters with expertise in networking, storage, security policies, resource management, and comprehensive observability at scale.</p>
                </div>
                <div class="expertise-card">
                    <h3>🏗️ Infrastructure as Code</h3>
                    <p>Writing reusable, testable, documented Terraform modules that deploy consistent cloud infrastructure across AWS, Azure, and Google Cloud environments.</p>
                </div>
                <div class="expertise-card">
                    <h3>📊 Observability & Monitoring</h3>
                    <p>Building comprehensive monitoring ecosystems using Prometheus, Grafana, ELK Stack, and Loki with intelligent alerting and custom dashboards.</p>
                </div>
                <div class="expertise-card">
                    <h3>🔐 DevSecOps Implementation</h3>
                    <p>Embedding security practices into infrastructure pipelines from day one—secrets management, container scanning, IAM policies, and compliance-as-code.</p>
                </div>
                <div class="expertise-card">
                    <h3>☁️ Multi-Cloud Architecture</h3>
                    <p>Designing scalable, cost-optimized infrastructure across AWS, Azure, and GCP with disaster recovery, failover strategies, and global deployments.</p>
                </div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Skills -->
        <section class="section">
            <h2 class="section-title">🛠️ Technical Proficiency</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-category">☁️ Cloud Platforms</div>
                    <ul class="skill-list">
                        <li>AWS (EC2, RDS, S3, Lambda, ECS)</li>
                        <li>Azure (VMs, App Service, AKS)</li>
                        <li>Google Cloud (Compute Engine, GKE)</li>
                        <li>VPC & Network Architecture</li>
                        <li>IAM & Access Management</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 90%; animation-duration: 1.8s;"></div>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-category">📦 Containers & Orchestration</div>
                    <ul class="skill-list">
                        <li>Docker (multi-stage builds, optimization)</li>
                        <li>Kubernetes (advanced patterns)</li>
                        <li>Helm Chart Management</li>
                        <li>StatefulSets & DaemonSets</li>
                        <li>Network Policies & Security</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 85%; animation-duration: 2s;"></div>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-category">🔧 Infrastructure Automation</div>
                    <ul class="skill-list">
                        <li>Terraform (module design)</li>
                        <li>CloudFormation</li>
                        <li>Ansible Playbooks</li>
                        <li>Infrastructure Testing</li>
                        <li>State Management</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 88%; animation-duration: 1.9s;"></div>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-category">🚀 CI/CD Platforms</div>
                    <ul class="skill-list">
                        <li>GitHub Actions</li>
                        <li>GitLab CI/CD</li>
                        <li>ArgoCD (GitOps)</li>
                        <li>Jenkins Pipelines</li>
                        <li>Artifact Management</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 92%; animation-duration: 1.7s;"></div>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-category">📊 Observability Stack</div>
                    <ul class="skill-list">
                        <li>Prometheus & Alerting</li>
                        <li>Grafana Dashboards</li>
                        <li>ELK Stack (Elasticsearch, Kibana)</li>
                        <li>Loki for Log Aggregation</li>
                        <li>Custom Metrics & SLOs</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 87%; animation-duration: 1.85s;"></div>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-category">💻 Languages & Tools</div>
                    <ul class="skill-list">
                        <li>Python (automation, scripting)</li>
                        <li>Bash Shell Scripting</li>
                        <li>Go (performance tools)</li>
                        <li>YAML & HCL</li>
                        <li>Git & Version Control</li>
                    </ul>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 84%; animation-duration: 2.1s;"></div>
                    </div>
                </div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Achievements Timeline -->
        <section class="section">
            <h2 class="section-title">✨ Key Achievements</h2>
            <div class="timeline">
                <div class="timeline-item" style="position: relative;">
                    <div class="timeline-content">
                        <h4>Infrastructure Reliability</h4>
                        <p>Architected and maintained Kubernetes clusters supporting production workloads. Designed CI/CD pipelines reducing deployment time and human error. Implemented comprehensive monitoring reducing incident detection time significantly.</p>
                    </div>
                </div>

                <div class="timeline-item" style="position: relative;">
                    <div class="timeline-content">
                        <h4>Automation Impact</h4>
                        <p>Created reusable Terraform modules accelerating infrastructure provisioning. Developed CI/CD workflows automating testing, security scanning, and deployments. Implemented GitOps patterns enabling safer infrastructure changes at scale.</p>
                    </div>
                </div>

                <div class="timeline-item" style="position: relative;">
                    <div class="timeline-content">
                        <h4>Cloud Architecture</h4>
                        <p>Multi-cloud infrastructure design across AWS, Azure, and GCP. Cost optimization strategies through resource right-sizing and automation. Security-hardened cloud environments with proper isolation and access control mechanisms.</p>
                    </div>
                </div>

                <div class="timeline-item" style="position: relative;">
                    <div class="timeline-content">
                        <h4>DevSecOps Integration</h4>
                        <p>Embedded security practices into infrastructure pipelines from ground up. Implemented container scanning, vulnerability management, and compliance automation. Built secrets management and rotation strategies across environments.</p>
                    </div>
                </div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Engineering Philosophy -->
        <section class="section">
            <h2 class="section-title">💡 Engineering Philosophy</h2>
            <div class="expertise-grid">
                <div class="expertise-card">
                    <h3>Automation > Manual Work</h3>
                    <p>If something happens more than twice, it gets automated. Manual processes are error-prone, slow, and don't scale. Intelligent automation frees teams to focus on innovation.</p>
                </div>
                <div class="expertise-card">
                    <h3>Reliability > Velocity</h3>
                    <p>Fast systems that break are worse than slow systems that work. Reliability is built in from day one through comprehensive testing, monitoring, and failover strategies.</p>
                </div>
                <div class="expertise-card">
                    <h3>Observability > Guessing</h3>
                    <p>What you can't measure, you can't optimize. Comprehensive monitoring, logging, and metrics provide visibility into system behavior before problems become incidents.</p>
                </div>
                <div class="expertise-card">
                    <h3>Security > Convenience</h3>
                    <p>Security isn't bolted on—it's woven into every layer. DevSecOps means security decisions are made early, embedded in pipelines, and enforced automatically.</p>
                </div>
                <div class="expertise-card">
                    <h3>Simple > Complex</h3>
                    <p>The simplest solution that solves the problem wins. Complex infrastructure that breaks is worse than simple infrastructure that works reliably.</p>
                </div>
                <div class="expertise-card">
                    <h3>Documentation > Tribal Knowledge</h3>
                    <p>Good documentation is as valuable as good code. Clear explanations prevent knowledge silos and enable teams to maintain systems with confidence.</p>
                </div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Contact -->
        <div class="contact-section">
            <h2>Let's Build Something Great</h2>
            <p style="color: var(--text-secondary); margin-bottom: 2rem; font-size: 1.05rem;">
                I'm interested in discussing DevOps challenges, cloud architecture, Kubernetes best practices, and infrastructure automation. Let's connect.
            </p>
            <div class="contact-links">
                <a href="mailto:kaushalkishoremnt2000@gmail.com" class="contact-link">📧 Email</a>
                <a href="https://linkedin.com/in/kaushalacts" class="contact-link">💼 LinkedIn</a>
                <a href="https://github.com/kaushalacts" class="contact-link">🐙 GitHub</a>
                <a href="https://twitter.com/kaushalacts" class="contact-link">🐦 Twitter</a>
            </div>
        </div>

        <!-- Footer -->
        <footer>
            <p>Based in Gurugram, Haryana, India 🇮🇳</p>
            <p>2+ years of DevOps & Cloud Infrastructure experience</p>
            <p style="margin-top: 1.5rem; font-size: 0.85rem;">Last updated: December 2024 | Building resilient infrastructure, one container at a time 🚀</p>
        </footer>
    </div>

    <script>
        // Smooth scroll animation
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

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.skill-card, .expertise-card, .stat, .timeline-item').forEach(el => {
            observer.observe(el);
        });

        // Animate skill progress bars on scroll
        const progressObserver = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'expandWidth ' + 
                        (1.5 + Math.random() * 0.5) + 's ease forwards';
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.skill-progress-bar').forEach(bar => {
            progressObserver.observe(bar);
        });
    </script>
</body>
</html>
