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

/* Stephanie B. Adesola */
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

.hero-title {*/ Agile Project Manager/Scrum Master/Virtual Assistant/Social Media Manager */
  font-size: 4rem;
  margin-bottom: 1rem;
  opacity: 0;
  transform: translateY(30px);
}

.hero-subtitle {Organisation-Communication-Customer Relation
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

/* Replace this description with your own professional summary */
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
