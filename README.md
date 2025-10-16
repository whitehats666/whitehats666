<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Krishna Anilkumar - Data Analyst Portfolio</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --neon-teal: #00f5d4;
            --neon-purple: #9d4edd;
            --neon-pink: #ff006e;
            --neon-blue: #4361ee;
            --dark-bg: #0a0a12;
            --darker-bg: #050509;
            --card-bg: #121225;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: var(--dark-bg);
            color: #fff;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Particle Background */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }
        
        /* Navigation */
        .navbar {
            background-color: rgba(10, 10, 18, 0.8);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            transition: all 0.3s ease;
            z-index: 1000;
        }
        
        .navbar-brand {
            font-weight: 700;
            font-size: 1.5rem;
            background: linear-gradient(90deg, var(--neon-teal), var(--neon-blue));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .nav-link {
            color: #fff !important;
            font-weight: 500;
            margin: 0 0.5rem;
            position: relative;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background: linear-gradient(90deg, var(--neon-teal), var(--neon-purple));
            transition: width 0.3s ease;
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(90deg, var(--neon-teal), var(--neon-blue), var(--neon-pink));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .hero h2 {
            font-size: 1.8rem;
            font-weight: 500;
            margin-bottom: 1.5rem;
            color: #e0e0e0;
        }
        
        .typing-text {
            font-size: 1.8rem;
            font-weight: 600;
            margin-bottom: 2rem;
            height: 2.5rem;
        }
        
        .typing-text span {
            color: var(--neon-teal);
            border-right: 2px solid var(--neon-teal);
            animation: blink 0.7s infinite;
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        .hero-btns .btn {
            padding: 0.8rem 2rem;
            border-radius: 30px;
            font-weight: 500;
            margin-right: 1rem;
            margin-bottom: 1rem;
            transition: all 0.3s ease;
            border: none;
        }
        
        .btn-primary {
            background: linear-gradient(45deg, var(--neon-blue), var(--neon-purple));
            box-shadow: 0 0 15px rgba(67, 97, 238, 0.5);
        }
        
        .btn-outline-primary {
            background: transparent;
            border: 2px solid var(--neon-teal);
            color: var(--neon-teal);
            box-shadow: 0 0 10px rgba(0, 245, 212, 0.3);
        }
        
        .btn-primary:hover, .btn-outline-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.7);
        }
        
        .profile-img {
            width: 100%;
            max-width: 400px;
            border-radius: 20px;
            box-shadow: 0 0 30px rgba(0, 245, 212, 0.4);
            animation: float 6s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        /* Social Icons */
        .social-icons {
            position: fixed;
            top: 50%;
            right: 30px;
            transform: translateY(-50%);
            z-index: 100;
            display: flex;
            flex-direction: column;
        }
        
        .social-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 10px 0;
            color: white;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .social-icon::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: inherit;
            filter: blur(8px);
            opacity: 0.6;
            z-index: -1;
        }
        
        .social-icon.email {
            background: linear-gradient(45deg, #ea4335, #fbbc05);
        }
        
        .social-icon.whatsapp {
            background: linear-gradient(45deg, #25d366, #128c7e);
        }
        
        .social-icon.instagram {
            background: linear-gradient(45deg, #833ab4, #fd1d1d, #fcb045);
        }
        
        .social-icon.github {
            background: linear-gradient(45deg, #333, #6e5494);
        }
        
        .social-icon.linkedin {
            background: linear-gradient(45deg, #0077b5, #00a0dc);
        }
        
        .social-icon:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        /* Section Headers */
        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            position: relative;
            display: inline-block;
        }
        
        .section-header h2::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--neon-teal), var(--neon-purple));
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }
        
        /* Projects Section */
        .projects {
            padding: 100px 0;
            background-color: var(--darker-bg);
            position: relative;
        }
        
        .project-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            margin-bottom: 30px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 245, 212, 0.2);
            border-color: var(--neon-teal);
        }
        
        .project-img {
            height: 200px;
            background: linear-gradient(45deg, var(--neon-blue), var(--neon-purple));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 1rem;
        }
        
        .project-tag {
            background: rgba(157, 78, 221, 0.2);
            color: var(--neon-purple);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-right: 0.5rem;
            margin-bottom: 0.5rem;
        }
        
        .project-btn {
            background: linear-gradient(45deg, var(--neon-teal), var(--neon-blue));
            color: white;
            border: none;
            padding: 0.5rem 1.5rem;
            border-radius: 30px;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .project-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 245, 212, 0.4);
        }
        
        /* About Section */
        .about {
            padding: 100px 0;
            position: relative;
        }
        
        .about-content {
            margin-bottom: 3rem;
        }
        
        .skill-item {
            margin-bottom: 1.5rem;
        }
        
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }
        
        .skill-bar {
            height: 10px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            border-radius: 5px;
            position: relative;
            overflow: hidden;
        }
        
        .skill-progress::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, var(--neon-teal), var(--neon-purple));
            animation: glowing 2s ease-in-out infinite alternate;
        }
        
        @keyframes glowing {
            0% { opacity: 0.7; }
            100% { opacity: 1; }
        }
        
        .certifications {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-top: 2rem;
        }
        
        .cert-logo {
            width: 100px;
            height: 100px;
            background: var(--card-bg);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: var(--neon-teal);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
        }
        
        .cert-logo:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 245, 212, 0.3);
        }
        
        /* Experience Section */
        .experience {
            padding: 100px 0;
            background-color: var(--darker-bg);
            position: relative;
        }
        
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .timeline::after {
            content: '';
            position: absolute;
            width: 6px;
            background: linear-gradient(to bottom, var(--neon-teal), var(--neon-purple));
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
        }
        
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            box-sizing: border-box;
        }
        
        .timeline-item::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: var(--neon-teal);
            border: 4px solid var(--neon-purple);
            border-radius: 50%;
            top: 15px;
            right: -10px;
            z-index: 1;
        }
        
        .left {
            left: 0;
        }
        
        .right {
            left: 50%;
        }
        
        .right::after {
            left: -10px;
        }
        
        .timeline-content {
            padding: 20px 30px;
            background-color: var(--card-bg);
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        /* Education Section */
        .education {
            padding: 100px 0;
            position: relative;
        }
        
        .education-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .education-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 245, 212, 0.2);
            border-color: var(--neon-teal);
        }
        
        /* Footer */
        .footer {
            background-color: var(--darker-bg);
            padding: 2rem 0;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Modal */
        .modal-content {
            background-color: var(--card-bg);
            color: white;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .modal-header {
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .modal-footer {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .btn-close {
            filter: invert(1);
        }
        
        /* Project Display Area */
        .project-display {
            height: 500px;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .project-display iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .project-display .github-embed {
            background-color: var(--darker-bg);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            height: 100%;
            padding: 20px;
            text-align: center;
        }
        
        .github-embed i {
            font-size: 5rem;
            margin-bottom: 20px;
            color: var(--neon-teal);
        }
        
        .project-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .project-tab {
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }
        
        .project-tab.active {
            border-bottom: 3px solid var(--neon-teal);
            color: var(--neon-teal);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .social-icons {
                position: static;
                flex-direction: row;
                justify-content: center;
                margin: 2rem 0;
                transform: none;
            }
            
            .social-icon {
                margin: 0 10px;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero h2 {
                font-size: 1.5rem;
            }
            
            .typing-text {
                font-size: 1.5rem;
            }
            
            .timeline::after {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item::after {
                left: 21px;
            }
            
            .right {
                left: 0%;
            }
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero h2 {
                font-size: 1.2rem;
            }
            
            .typing-text {
                font-size: 1.2rem;
            }
            
            .section-header h2 {
                font-size: 2rem;
            }
            
            .project-display {
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <!-- Particle Background -->
    <div id="particles-js"></div>
    
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#">Krishna Anilkumar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#projects">Projects</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#experience">Experience</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#about">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#education">Education</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
    
    <!-- Social Icons -->
    <div class="social-icons">
        <a href="mailto:krishna06ak@gmail.com" class="social-icon email">
            <i class="fas fa-envelope"></i>
        </a>
        <a href="https://wa.me/916282430019" class="social-icon whatsapp">
            <i class="fab fa-whatsapp"></i>
        </a>
        <a href="https://linkedin.com/in/krishna-anilkumar" class="social-icon linkedin">
            <i class="fab fa-linkedin"></i>
        </a>
        <a href="https://github.com/krishna06ak" class="social-icon github">
            <i class="fab fa-github"></i>
        </a>
    </div>
    
    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6 hero-content">
                    <h1>Hi, I'm Krishna Anilkumar</h1>
                    <h2>Turning raw data into smart business insights.</h2>
                    <div class="typing-text">
                        I'm a <span id="typed-text"></span>
                    </div>
                    <div class="hero-btns">
                        <button class="btn btn-primary" onclick="scrollToSection('projects')">View My Projects</button>
                        <a href="Deedy_Resume_Reversed__1_.pdf" class="btn btn-outline-primary" download>Download Resume</a>
                    </div>
                </div>
                <div class="col-lg-6 text-center">
                    <img src="C:\Users\Dell\Desktop\1000089229.jpg" alt="Krishna Anilkumar" class="profile-img">
                </div>
            </div>
        </div>
    </section>
    
    <!-- Projects Section -->
    <section class="projects" id="projects">
        <div class="container">
            <div class="section-header">
                <h2>My Projects</h2>
                <p>Explore my data analysis and web development projects</p>
            </div>
            <div class="row">
                <!-- Project 1 -->
                <div class="col-lg-4 col-md-6">
                    <div class="project-card">
                        <div class="project-img">
                            <i class="fas fa-tshirt"></i>
                        </div>
                        <div class="project-content">
                            <h4>GLAMGENIE AI Fashion Helper</h4>
                            <p>AI-driven fashion recommender using Python, Machine Learning, and a responsive React frontend.</p>
                            <div class="project-tags">
                                <span class="project-tag">Python</span>
                                <span class="project-tag">ML</span>
                                <span class="project-tag">React</span>
                                <span class="project-tag">AI</span>
                            </div>
                            <button class="project-btn" data-bs-toggle="modal" data-bs-target="#projectModal1">View Project</button>
                        </div>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="col-lg-4 col-md-6">
                    <div class="project-card">
                        <div class="project-img">
                            <i class="fas fa-recycle"></i>
                        </div>
                        <div class="project-content">
                            <h4>ECOVAULT Waste Management System</h4>
                            <p>Comprehensive waste management system using Python Flask and MySQL for efficient tracking.</p>
                            <div class="project-tags">
                                <span class="project-tag">Python</span>
                                <span class="project-tag">Flask</span>
                                <span class="project-tag">MySQL</span>
                                <span class="project-tag">Web App</span>
                            </div>
                            <button class="project-btn" data-bs-toggle="modal" data-bs-target="#projectModal2">View Project</button>
                        </div>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="col-lg-4 col-md-6">
                    <div class="project-card">
                        <div class="project-img">
                            <i class="fas fa-spa"></i>
                        </div>
                        <div class="project-content">
                            <h4>Alloura Beauty Salon Website</h4>
                            <p>Business website with booking system, maps integration, and payment gateway functionality.</p>
                            <div class="project-tags">
                                <span class="project-tag">Web Dev</span>
                                <span class="project-tag">Booking</span>
                                <span class="project-tag">Payment</span>
                                <span class="project-tag">Maps API</span>
                            </div>
                            <button class="project-btn" data-bs-toggle="modal" data-bs-target="#projectModal3">View Project</button>
                        </div>
                    </div>
                </div>
                
                <!-- Project 4 - HR Analytics Dashboard -->
                <div class="col-lg-4 col-md-6">
                    <div class="project-card">
                        <div class="project-img">
                            <i class="fas fa-chart-bar"></i>
                        </div>
                        <div class="project-content">
                            <h4>HR Analytics Dashboard</h4>
                            <p>Interactive Power BI dashboard analyzing HR metrics, employee performance, and attrition patterns.</p>
                            <div class="project-tags">
                                <span class="project-tag">Power BI</span>
                                <span class="project-tag">Data Analysis</span>
                                <span class="project-tag">HR Analytics</span>
                                <span class="project-tag">Dashboard</span>
                            </div>
                            <button class="project-btn" data-bs-toggle="modal" data-bs-target="#projectModal4">View Project</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Experience Section -->
    <section class="experience" id="experience">
        <div class="container">
            <div class="section-header">
                <h2>Professional Experience</h2>
                <p>My journey in tech and data analysis</p>
            </div>
            <div class="timeline">
                <!-- Experience 1 -->
                <div class="timeline-item left">
                    <div class="timeline-content">
                        <h4>Python Full Stack Developer</h4>
                        <h5>QSpiders</h5>
                        <p class="text-muted">2025 | Ernakulam, Kerala</p>
                        <p>Develop end-to-end web applications using Python, Django, Flask, and React. Build responsive user interfaces with HTML5, CSS3, JavaScript, and Bootstrap.</p>
                    </div>
                </div>
                
                <!-- Experience 2 -->
                <div class="timeline-item right">
                    <div class="timeline-content">
                        <h4>Intern</h4>
                        <h5>Jayakalyan Multipurpose Education Society</h5>
                        <p class="text-muted">2023</p>
                        <p>Fundraised for students' education, developing communication and project management skills.</p>
                    </div>
                </div>
                
                <!-- Leadership Experience -->
                <div class="timeline-item left">
                    <div class="timeline-content">
                        <h4>College President</h4>
                        <h5>Student Leadership Role</h5>
                        <p class="text-muted">2023–2024</p>
                        <p>Organized annual program for 400+ students, managed events and student initiatives.</p>
                    </div>
                </div>
                
                <!-- Leadership Experience 2 -->
                <div class="timeline-item right">
                    <div class="timeline-content">
                        <h4>Editor, MLA Project Magazine</h4>
                        <h5>Editorial Management</h5>
                        <p class="text-muted">2023–2024</p>
                        <p>Managed content creation and publication process for college magazine.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="section-header">
                <h2>About Me</h2>
                <p>My skills and expertise in data analysis and development</p>
            </div>
            <div class="row">
                <div class="col-lg-6 about-content">
                    <h3>Data Analyst & Full Stack Developer</h3>
                    <p>I'm a passionate data analyst and developer with expertise in transforming complex data into actionable insights. My technical skills span across data visualization, statistical analysis, and full-stack web development.</p>
                    <p>I hold a Master's degree in Computer Science and have experience working with various technologies including Python, JavaScript, SQL, and Power BI. My goal is to help businesses make data-driven decisions through compelling visualizations and robust applications.</p>
                    
                    <h4 class="mt-4">Core Competencies</h4>
                    <div class="row mt-3">
                        <div class="col-md-6">
                            <ul>
                                <li>Full Stack Development</li>
                                <li>Problem Solving</li>
                                <li>Team Collaboration</li>
                            </ul>
                        </div>
                        <div class="col-md-6">
                            <ul>
                                <li>Project Management</li>
                                <li>Agile Development</li>
                                <li>Database Design</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-lg-6">
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Python</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>SQL</span>
                            <span>88%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 88%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Power BI</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    
                    <h4 class="mt-4">Languages</h4>
                    <div class="project-tags mt-2">
                        <span class="project-tag">English (Fluent)</span>
                        <span class="project-tag">Malayalam (Native)</span>
                        <span class="project-tag">Tamil (Intermediate)</span>
                        <span class="project-tag">Spanish (Beginner)</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Education Section -->
    <section class="education" id="education">
        <div class="container">
            <div class="section-header">
                <h2>Education</h2>
                <p>My academic background</p>
            </div>
            <div class="row">
                <div class="col-lg-4 col-md-6">
                    <div class="education-card">
                        <h4>Master of Computer Science</h4>
                        <h5>Sree Narayana Gurukulam Engineering College</h5>
                        <p class="text-muted">2023–2025 | Ernakulam, Kerala</p>
                    </div>
                </div>
                <div class="col-lg-4 col-md-6">
                    <div class="education-card">
                        <h4>Bachelor of Mathematics and Statistics</h4>
                        <h5>St. Teresa's College</h5>
                        <p class="text-muted">2020–2023 | Ernakulam, Kerala</p>
                    </div>
                </div>
                <div class="col-lg-4 col-md-6">
                    <div class="education-card">
                        <h4>AI-DQA Diploma</h4>
                        <h5>Don Bosco</h5>
                        <p class="text-muted">2024 | Ernakulam, Kerala</p>
                    </div>
                </div>
            </div>
            
            <div class="section-header mt-5">
                <h2>Certifications</h2>
            </div>
            <div class="row">
                <div class="col-md-6">
                    <div class="education-card">
                        <h4>FreeCodeCamp: Responsive Web Design</h4>
                        <p class="text-muted">300 hours training program | 2024</p>
                    </div>
                </div>
                <div class="col-md-6">
                    <div class="education-card">
                        <h4>Infosys Springboard Training Program</h4>
                        <p class="text-muted">Industry-focused development training | 2024</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2025 Krishna Anilkumar. All Rights Reserved.</p>
        </div>
    </footer>
    
    <!-- Project Modals -->
    <!-- Modal 1 - GLAMGENIE AI Fashion Helper -->
    <div class="modal fade" id="projectModal1" tabindex="-1">
        <div class="modal-dialog modal-xl">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">GLAMGENIE AI Fashion Helper</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <div class="project-tabs">
                        <div class="project-tab active" data-tab="description">Description</div>
                        <div class="project-tab" data-tab="demo">Live Demo</div>
                        <div class="project-tab" data-tab="code">Source Code</div>
                    </div>
                    
                    <div class="tab-content active" id="description-tab">
                        <p>This AI-driven fashion recommender system helps users find clothing items that match their style preferences and body type.</p>
                        <ul>
                            <li>Machine learning algorithms for style recommendation</li>
                            <li>Responsive React frontend for seamless user experience</li>
                            <li>Python backend for data processing and ML model serving</li>
                            <li>Integration with fashion databases and APIs</li>
                        </ul>
                        <p><strong>Tools Used:</strong> Python, Machine Learning, React, Node.js, REST APIs</p>
                    </div>
                    
                    <div class="tab-content" id="demo-tab">
                        <div class="project-display">
                            <div class="github-embed">
                                <i class="fab fa-react"></i>
                                <h4>Live Demo Coming Soon</h4>
                                <p>The live demo for this project is currently under development.</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="tab-content" id="code-tab">
                        <div class="project-display">
                            <div class="github-embed">
                                <i class="fab fa-github"></i>
                                <h4>GitHub Repository</h4>
                                <p>You can view the source code for this project on GitHub:</p>
                                <a href="https://github.com/krishna06ak/glamgenie-ai-fashion" target="_blank" class="btn btn-primary mt-3">View on GitHub</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Modal 2 - ECOVAULT Waste Management System -->
    <div class="modal fade" id="projectModal2" tabindex="-1">
        <div class="modal-dialog modal-xl">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">ECOVAULT Waste Management System</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <div class="project-tabs">
                        <div class="project-tab active" data-tab="description">Description</div>
                        <div class="project-tab" data-tab="demo">Live Demo</div>
                        <div class="project-tab" data-tab="code">Source Code</div>
                    </div>
                    
                    <div class="tab-content active" id="description-tab">
                        <p>Comprehensive waste management system designed to track, manage, and optimize waste collection and recycling processes.</p>
                        <ul>
                            <li>User-friendly interface for waste tracking and reporting</li>
                            <li>Database management for waste collection records</li>
                            <li>Reporting and analytics for waste management efficiency</li>
                            <li>Admin dashboard for system management</li>
                        </ul>
                        <p><strong>Tools Used:</strong> Python, Flask, MySQL, HTML5, CSS3, JavaScript</p>
                    </div>
                    
                    <div class="tab-content" id="demo-tab">
                        <div class="project-display">
                            <div class="github-embed">
                                <i class="fab fa-python"></i>
                                <h4>Live Demo Coming Soon</h4>
                                <p>The live demo for this project is currently under development.</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="tab-content" id="code-tab">
                        <div class="project-display">
                            <div class="github-embed">
                                <i class="fab fa-github"></i>
                                <h4>GitHub Repository</h4>
                                <p>You can view the source code for this project on GitHub:</p>
                                <a href="https://github.com/krishna06ak/ecovault-waste-management" target="_blank" class="btn btn-primary mt-3">View on GitHub</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Modal 3 - Alloura Beauty Salon Website -->
    <div class="modal fade" id="projectModal3" tabindex="-1">
        <div class="modal-dialog modal-xl">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Alloura Beauty Salon Website</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <div class="project-tabs">
                        <div class="project-tab active" data-tab="description">Description</div>
                        <div class="project-tab" data-tab="demo">Live Demo</div>
                        <div class="project-tab" data-tab="code">Source Code</div>
                    </div>
                    
                    <div class="tab-content active" id="description-tab">
                        <p>Business website for a beauty salon with integrated booking system, location services, and payment processing.</p>
                        <ul>
                            <li>Online appointment booking system</li>
                            <li>Google Maps integration for location services</li>
                            <li>Secure payment gateway integration</li>
                            <li>Responsive design for all devices</li>
                            <li>Service catalog and pricing information</li>
                        </ul>
                        <p><strong>Tools Used:</strong> HTML5, CSS3, JavaScript, Bootstrap, Payment Gateway APIs, Google Maps API</p>
                    </div>
                    
                    <div class="tab-content" id="demo-tab">
                        <div class="project-display">
                            <iframe src="https://alloura-beauty-salon-demo.netlify.app" title="Alloura Beauty Salon Demo"></iframe>
                        </div>
                    </div>
                    
                    <div class="tab-content" id="code-tab">
                        <div class="project-display">
                            <div class="github-embed">
                                <i class="fab fa-github"></i>
                                <h4>GitHub Repository</h4>
                                <p>You can view the source code for this project on GitHub:</p>
                                <a href="https://github.com/krishna06ak/alloura-beauty-salon" target="_blank" class="btn btn-primary mt-3">View on GitHub</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Modal 4 - HR Analytics Dashboard -->
    <div class="modal fade" id="projectModal4" tabindex="-1">
        <div class="modal-dialog modal-xl">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">HR Analytics Dashboard</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <div class="project-tabs">
                        <div class="project-tab active" data-tab="hr-description">Description</div>
                        <div class="project-tab" data-tab="hr-dashboard">Dashboard</div>
                    </div>
                    
                    <div class="tab-content active" id="hr-description-tab">
                        <p>Interactive Power BI dashboard analyzing HR metrics, employee performance, and attrition patterns.</p>
                        <ul>
                            <li>Comprehensive HR metrics visualization</li>
                            <li>Employee attrition analysis and predictive insights</li>
                            <li>Performance tracking and KPI monitoring</li>
                            <li>Interactive filters for customized data exploration</li>
                        </ul>
                        <p><strong>Tools Used:</strong> Power BI, DAX, Data Modeling, Data Visualization</p>
                    </div>
                    
                    <div class="tab-content" id="hr-dashboard-tab">
                        <div class="project-display">
                            <iframe title="HR Analytics Dashboard" width="100%" height="100%" src="https://app.powerbi.com/view?r=eyJrIjoiM2Q3Y2YxZjctMTI1ZS00OTFmLWJlOTktYjFhNTM5NjJiZjJhIiwidCI6IjU2NTM4NTAxLWFiMzYtNDE4NC1hM2IxLThlZTAyYTc1MTRlMCJ9" frameborder="0" allowFullScreen="true"></iframe>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        // Typing Animation
        const typedTextSpan = document.getElementById("typed-text");
        const textArray = ["Data Analyst", "Business Analyst", "Full Stack Developer", "Problem Solver", "AI Enthusiast"];
        const typingDelay = 100;
        const erasingDelay = 50;
        const newTextDelay = 1500;
        let textArrayIndex = 0;
        let charIndex = 0;

        function type() {
            if (charIndex < textArray[textArrayIndex].length) {
                typedTextSpan.textContent += textArray[textArrayIndex].charAt(charIndex);
                charIndex++;
                setTimeout(type, typingDelay);
            } else {
                setTimeout(erase, newTextDelay);
            }
        }

        function erase() {
            if (charIndex > 0) {
                typedTextSpan.textContent = textArray[textArrayIndex].substring(0, charIndex - 1);
                charIndex--;
                setTimeout(erase, erasingDelay);
            } else {
                textArrayIndex++;
                if (textArrayIndex >= textArray.length) textArrayIndex = 0;
                setTimeout(type, typingDelay + 500);
            }
        }

        document.addEventListener("DOMContentLoaded", function() {
            setTimeout(type, newTextDelay + 250);
            
            // Initialize project tabs
            initProjectTabs();
        });

        // Particles.js Configuration
        particlesJS("particles-js", {
            particles: {
                number: { value: 80, density: { enable: true, value_area: 800 } },
                color: { value: "#00f5d4" },
                shape: { type: "circle" },
                opacity: { value: 0.5, random: true },
                size: { value: 3, random: true },
                line_linked: {
                    enable: true,
                    distance: 150,
                    color: "#9d4edd",
                    opacity: 0.4,
                    width: 1
                },
                move: {
                    enable: true,
                    speed: 2,
                    direction: "none",
                    random: true,
                    straight: false,
                    out_mode: "out",
                    bounce: false
                }
            },
            interactivity: {
                detect_on: "canvas",
                events: {
                    onhover: { enable: true, mode: "repulse" },
                    onclick: { enable: true, mode: "push" },
                    resize: true
                }
            },
            retina_detect: true
        });

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            if (window.scrollY > 50) {
                document.querySelector('.navbar').style.padding = '0.5rem 0';
                document.querySelector('.navbar').style.boxShadow = '0 5px 15px rgba(0, 0, 0, 0.2)';
            } else {
                document.querySelector('.navbar').style.padding = '1rem 0';
                document.querySelector('.navbar').style.boxShadow = 'none';
            }
        });

        // Smooth scrolling function
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }

        // Project tabs functionality
        function initProjectTabs() {
            const projectTabs = document.querySelectorAll('.project-tab');
            
            projectTabs.forEach(tab => {
                tab.addEventListener('click', function() {
                    const modal = this.closest('.modal');
                    const tabId = this.getAttribute('data-tab');
                    
                    // Remove active class from all tabs in this modal
                    const allTabs = modal.querySelectorAll('.project-tab');
                    allTabs.forEach(t => t.classList.remove('active'));
                    
                    // Add active class to clicked tab
                    this.classList.add('active');
                    
                    // Hide all tab content in this modal
                    const allTabContent = modal.querySelectorAll('.tab-content');
                    allTabContent.forEach(content => content.classList.remove('active'));
                    
                    // Show the selected tab content
                    const targetTab = modal.querySelector(`#${tabId}-tab`);
                    if (targetTab) {
                        targetTab.classList.add('active');
                    }
                });
            });
        }
    </script>
</body>
</html>
