<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Project Manager Stephanie B. Adesola</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <style>
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }


        :root {
            --dark-blue: #0a192f;
            --accent-blue: #64ffda;
            --text-light: #ccd6f6;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: system-ui, -apple-system, sans-serif;
        }

        body {
            background-color: var(--dark-blue);
            color: var(--text-light);
            overflow-x: hidden;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(10, 25, 47, 0.85);
            backdrop-filter: blur(10px);
            z-index: 100;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: var(--accent-blue);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--accent-blue);
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            text-align: center;
            z-index: 1;
        }

        .hero-title {
            font-size: 4rem;
            margin-bottom: 1rem;
            opacity: 0;
            transform: translateY(30px);
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--accent-blue);
            margin-bottom: 2rem;
            opacity: 0;
            transform: translateY(30px);
        }

        .projects {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 2rem;
            transition: transform 0.3s ease;
            cursor: pointer;
            opacity: 0;
            transform: translateY(30px);
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-icon {
            width: 50px;
            height: 50px;
            background: var(--accent-blue);
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .orbital-circle {
            position: absolute;
            border: 2px solid rgba(100, 255, 218, 0.1);
            border-radius: 50%;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--accent-blue);
        }

        .about {
            padding: 5rem 2rem;
            background: rgba(255, 255, 255, 0.02);
        }

        .about-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-content {
            display: flex;
            gap: 2rem;
            margin-top: 2rem;
        }

        .about-text {
            flex: 1;
        }

        .about-description {
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 2rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            padding: 1.5rem;
            border-radius: 8px;
            transition: transform 0.3s ease;
        }

        .skill-category:hover {
            transform: translateY(-5px);
        }

        .skill-category h3 {
            color: var(--accent-blue);
            margin-bottom: 1rem;
        }

        .skill-category ul {
            list-style: none;
        }

        .skill-category li {
            margin-bottom: 0.5rem;
            position: relative;
            padding-left: 1.5rem;
        }

        .skill-category li:before {
            content: "▹";
            position: absolute;
            left: 0;
            color: var(--accent-blue);
        }

        .contact {
            padding: 5rem 2rem;
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .contact-form {
            margin-top: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            color: var(--text-light);
            font-size: 1rem;
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        .submit-btn {
            background: var(--accent-blue);
            color: var(--dark-blue);
            padding: 1rem 2rem;
            border: none;
            border-radius: 4px;
            font-size: 1rem;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
        }

        .footer {
            padding: 3rem 2rem;
            background: rgba(255, 255, 255, 0.02);
            margin-top: 2rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
        }

        .footer-social {
            display: flex;
            gap: 1.5rem;
        }

        .social-link {
            color: var(--text-light);
            transition: color 0.3s ease;
        }

        .social-link:hover {
            color: var(--accent-blue);
        }

        .footer-info {
            text-align: center;
            color: rgba(255, 255, 255, 0.5);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            overflow-y: auto;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal.active {
            display: block;
            opacity: 1;
        }

        .modal-content {
            background: var(--dark-blue);
            margin: 50px auto;
            padding: 2rem;
            width: 90%;
            max-width: 800px;
            border-radius: 10px;
            position: relative;
            transform: translateY(20px);
            transition: transform 0.3s ease;
        }

        .modal.active .modal-content {
            transform: translateY(0);
        }

        .close-modal {
            position: absolute;
            right: 1.5rem;
            top: 1rem;
            font-size: 2rem;
            cursor: pointer;
            color: var(--text-light);
            transition: color 0.3s ease;
        }

        .close-modal:hover {
            color: var(--accent-blue);
        }

        .modal-body {
            margin-top: 2rem;
        }

        .project-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
            text-align: center;
        }

        .stat {
            background: rgba(255, 255, 255, 0.05);
            padding: 1rem;
            border-radius: 8px;
        }

        .stat-number {
            display: block;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--accent-blue);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-light);
        }

        .project-details h3 {
            color: var(--accent-blue);
            margin: 1.5rem 0 1rem 0;
        }

        .project-details ul {
            list-style: none;
            padding-left: 1.5rem;
        }

        .project-details li {
            position: relative;
            margin-bottom: 0.5rem;
        }

        .project-details li:before {
            content: "▹";
            position: absolute;
            left: -1.5rem;
            color: var(--accent-blue);
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-top: 1rem;
        }

        .tech-stack span {
            background: rgba(100, 255, 218, 0.1);
            color: var(--accent-blue);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 3rem;
            }

            .about-content {
                flex-direction: column;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">PM</div>
        <div class="nav-links">
            <a href="#about">About</a>
            <a href="#work">Work</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <h1 class="hero-title">Project Management/Agile Scrum Master</h1>
            <h2 class="hero-subtitle">Agile | Scrum | Leadership</h2>
        </div>
    </section>

    <section class="projects" id="work">
        <h2 class="section-title">Featured Projects</h2>
        <div class="project-grid">
            <div class="project-card" data-project="digital-transformation">
                <div class="project-icon"></div>
                <h3>Digital Transformation</h3>
                <p>Led a team of 15 through an enterprise-wide digital transformation initiative</p>
            </div>
            <div class="project-card" data-project="agile-implementation">
                <div class="project-icon"></div>
                <h3>Agile Implementation</h3>
                <p>Successfully transformed traditional workflows into agile methodologies</p>
            </div>
            <div class="project-card" data-project="process-optimization">
                <div class="project-icon"></div>
                <h3>Process Optimization</h3>
                <p>Reduced project delivery time by 40% through process improvements</p>
            </div>
            <div class="project-card" data-project="team-leadership">
                <div class="project-icon"></div>
                <h3>Team Leadership</h3>
                <p>Managed distributed teams across 5 time zones for global projects</p>
            </div>

            <!-- Project Modals -->
            <div class="modal" id="modal-digital-transformation">
                <div class="modal-content">
                    <span class="close-modal">&times;</span>
                    <h2>Digital Transformation</h2>
                    <div class="modal-body">
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-number">15</span>
                                <span class="stat-label">Team Members</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">18</span>
                                <span class="stat-label">Months</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">$2.5M</span>
                                <span class="stat-label">Budget</span>
                            </div>
                        </div>
                        <div class="project-details">
                            <h3>Overview</h3>
                            <p>Led an enterprise-wide digital transformation initiative that revolutionized business processes across multiple departments.</p>
                            
                            <h3>Key Achievements</h3>
                            <ul>
                                <li>Implemented cloud-based solutions reducing operational costs by 30%</li>
                                <li>Automated 60% of manual processes</li>
                                <li>Increased team productivity by 45%</li>
                                <li>Successfully integrated 5 legacy systems</li>
                            </ul>

                            <h3>Technologies & Tools</h3>
                            <div class="tech-stack">
                                <span>Trello</span>
                                <span>Jira</span>
                                <span>ServiceNow</span>
                                <span>Power BI</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="modal" id="modal-agile-implementation">
                <div class="modal-content">
                    <span class="close-modal">&times;</span>
                    <h2>Agile Implementation</h2>
                    <div class="modal-body">
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-number">8</span>
                                <span class="stat-label">Teams</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">12</span>
                                <span class="stat-label">Months</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">35%</span>
                                <span class="stat-label">Efficiency Gain</span>
                            </div>
                        </div>
                        <div class="project-details">
                            <h3>Overview</h3>
                            <p>Spearheaded the transformation from traditional waterfall to agile methodologies across multiple development teams.</p>
                            
                            <h3>Key Achievements</h3>
                            <ul>
                                <li>Reduced time-to-market by 40%</li>
                                <li>Improved sprint velocity by 25%</li>
                                <li>Decreased defect rate by 60%</li>
                                <li>Established standardized agile practices</li>
                            </ul>

                            <h3>Methodologies & Tools</h3>
                            <div class="tech-stack">
                                <span>Scrum</span>
                                <span>Kanban</span>
                                <span>Jira</span>
                                <span>Confluence</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="modal" id="modal-process-optimization">
                <div class="modal-content">
                    <span class="close-modal">&times;</span>
                    <h2>Process Optimization</h2>
                    <div class="modal-body">
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-number">40%</span>
                                <span class="stat-label">Time Saved</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">6</span>
                                <span class="stat-label">Months</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">25%</span>
                                <span class="stat-label">Cost Reduction</span>
                            </div>
                        </div>
                        <div class="project-details">
                            <h3>Overview</h3>
                            <p>Led a comprehensive process optimization initiative that significantly improved project delivery efficiency.</p>
                            
                            <h3>Key Achievements</h3>
                            <ul>
                                <li>Streamlined approval workflows by 60%</li>
                                <li>Implemented automated testing reducing QA time by 45%</li>
                                <li>Optimized resource allocation</li>
                                <li>Established new best practices</li>
                            </ul>

                            <h3>Tools & Technologies</h3>
                            <div class="tech-stack">
                                <span>Process Street</span>
                                <span>Monday.com</span>
                                <span>Automation Tools</span>
                                <span>Analytics</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="modal" id="modal-team-leadership">
                <div class="modal-content">
                    <span class="close-modal">&times;</span>
                    <h2>Team Leadership</h2>
                    <div class="modal-body">
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-number">25</span>
                                <span class="stat-label">Team Members</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">5</span>
                                <span class="stat-label">Time Zones</span>
                            </div>
                            <div class="stat">
                                <span class="stat-number">95%</span>
                                <span class="stat-label">Success Rate</span>
                            </div>
                        </div>
                        <div class="project-details">
                            <h3>Overview</h3>
                            <p>Successfully managed and coordinated distributed teams across multiple time zones for global project delivery.</p>
                            
                            <h3>Key Achievements</h3>
                            <ul>
                                <li>Maintained 95% on-time delivery rate</li>
                                <li>Improved team satisfaction scores by 40%</li>
                                <li>Implemented effective communication protocols</li>
                                <li>Reduced meeting overhead by 30%</li>
                            </ul>

                            <h3>Tools & Approaches</h3>
                            <div class="tech-stack">
                                <span>Slack</span>
                                <span>MS Teams</span>
                                <span>Asana</span>
                                <span>Zoom</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="about" id="about">
        <div class="about-container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p class="about-description">
                        A dedicated Project Manager and Scrum Master with over 8 years of experience in delivering complex digital projects. 
                        Specializing in agile methodologies and digital transformation initiatives.
                    </p>
                    <div class="skills-grid">
                        <div class="skill-category">
                            <h3>Project Management</h3>
                            <ul>
                                <li>Agile & Scrum</li>
                                <li>Risk Management</li>
                                <li>Stakeholder Communication</li>
                                <li>Budget Control</li>
                            </ul>
                        </div>
                        <div class="skill-category">
                            <h3>Technical Skills</h3>
                            <ul>
                                <li>JIRA & Confluence</li>
                                <li>Microsoft Project</li>
                                <li>Trello</li>
                                <li>Azure DevOps</li>
                            </ul>
                        </div>
                        <div class="skill-category">
                            <h3>Certifications</h3>
                            <ul>
                                <li>PMP Certified</li>
                                <li>Certified Scrum Master</li>
                                <li>PRINCE2 Practitioner</li>
                                <li>SAFe Agilist</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <div class="contact-container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <form class="contact-form">
                    <div class="form-group">
                        <input type="text" placeholder="Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" placeholder="Email" required>
                    </div>
                    <div class="form-group">
                        <textarea placeholder="Message" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <footer class="footer">
        <div class="footer-content">
            <div class="footer-social">
                <a href="#" class="social-link">
                    <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                    </svg>
                </a>
                <a href="#" class="social-link">
                    <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
                <a href="#" class="social-link">
                    <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M23.998 12c0-6.628-5.372-12-11.999-12C5.372 0 0 5.372 0 12c0 5.988 4.388 10.952 10.124 11.852v-8.384H7.078v-3.469h3.046V9.356c0-3.008 1.792-4.669 4.532-4.669 1.313 0 2.686.234 2.686.234v2.953H15.83c-1.49 0-1.955.925-1.955 1.874V12h3.328l-.532 3.469h-2.796v8.384c5.736-.9 10.124-5.864 10.124-11.853z"/>
                    </svg>
                </a>
            </div>
            <div class="footer-info">
                <p>&copy; 2025 Project Management Portfolio. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Create orbital circles
        function createOrbitalCircles() {
            const hero = document.querySelector('.hero');
            for (let i = 0; i < 3; i++) {
                const circle = document.createElement('div');
                circle.className = 'orbital-circle';
                const size = 300 + (i * 200);
                circle.style.width = size + 'px';
                circle.style.height = size + 'px';
                circle.style.animation = `rotate ${20 + (i * 5)}s linear infinite`;
                circle.style.left = `calc(50% - ${size/2}px)`;
                circle.style.top = `calc(50% - ${size/2}px)`;
                hero.appendChild(circle);
            }
        }

        // Animate elements on load
        window.addEventListener('load', () => {
            createOrbitalCircles();
            
            gsap.to('.hero-title', {
                opacity: 1,
                y: 0,
                duration: 1,
                ease: 'power3.out'
            });

            gsap.to('.hero-subtitle', {
                opacity: 1,
                y: 0,
                duration: 1,
                delay: 0.2,
                ease: 'power3.out'
            });

            gsap.to('.project-card', {
                opacity: 1,
                y: 0,
                duration: 0.8,
                stagger: 0.2,
                ease: 'power3.out',
                scrollTrigger: {
                    trigger: '.project-grid',
                    start: 'top center+=100',
                }
            });
        });

        // Project card click handlers
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('click', () => {
                const projectId = card.getAttribute('data-project');
                const modal = document.getElementById(`modal-${projectId}`);
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
            });
        });

        // Close modal handlers
        document.querySelectorAll('.close-modal').forEach(closeBtn => {
            closeBtn.addEventListener('click', (e) => {
                e.stopPropagation();
                const modal = closeBtn.closest('.modal');
                modal.classList.remove('active');
                document.body.style.overflow = 'auto';
            });
        });

        // Close modal when clicking outside
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
        });

        // Smooth scroll for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
