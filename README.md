<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MingMing - GitHub Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0d1117 0%, #1a1f2e 50%, #0d1117 100%);
            color: #e6edf3;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .stars {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }
        
        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 3s infinite alternate;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.3; }
            100% { opacity: 1; }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .profile-header {
            text-align: center;
            margin-bottom: 50px;
            animation: fadeInDown 1s ease-out;
        }
        
        .profile-avatar {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: linear-gradient(45deg, #7c3aed, #2563eb, #06b6d4);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 30px;
            position: relative;
            animation: float 3s ease-in-out infinite;
        }
        
        .profile-avatar::before {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(45deg, #7c3aed, #2563eb, #06b6d4, #7c3aed);
            border-radius: 50%;
            z-index: -1;
            animation: rotate 4s linear infinite;
        }
        
        .avatar-text {
            font-size: 4rem;
            font-weight: 700;
            color: white;
            text-shadow: 0 0 20px rgba(255,255,255,0.5);
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .profile-name {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #7c3aed, #2563eb, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shimmer 2s ease-in-out infinite;
        }
        
        @keyframes shimmer {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .profile-title {
            font-size: 1.5rem;
            color: #8b949e;
            margin-bottom: 20px;
        }
        
        .typing-text {
            font-size: 1.2rem;
            color: #7c3aed;
            border-right: 2px solid #7c3aed;
            white-space: nowrap;
            overflow: hidden;
            animation: typing 4s steps(40, end) infinite, blink 1s infinite;
        }
        
        @keyframes typing {
            0% { width: 0; }
            50% { width: 100%; }
            100% { width: 0; }
        }
        
        @keyframes blink {
            50% { border-color: transparent; }
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
            animation: fadeInUp 1s ease-out 0.3s both;
        }
        
        .stat-card {
            background: rgba(22, 27, 34, 0.8);
            border: 1px solid #30363d;
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            border-color: #7c3aed;
            box-shadow: 0 20px 40px rgba(124, 58, 237, 0.3);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #7c3aed;
            margin-bottom: 10px;
            animation: countUp 2s ease-out;
        }
        
        @keyframes countUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .stat-label {
            color: #8b949e;
            font-weight: 500;
        }
        
        .skills-section {
            animation: fadeInUp 1s ease-out 0.6s both;
        }
        
        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 40px;
            color: #e6edf3;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .skill-category {
            background: rgba(22, 27, 34, 0.8);
            border: 1px solid #30363d;
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .skill-category:hover {
            border-color: #7c3aed;
            box-shadow: 0 10px 30px rgba(124, 58, 237, 0.2);
        }
        
        .category-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: #7c3aed;
            display: flex;
            align-items: center;
        }
        
        .category-icon {
            margin-right: 10px;
            font-size: 1.8rem;
        }
        
        .skills-list {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }
        
        .skill-tag {
            background: linear-gradient(45deg, #7c3aed, #2563eb);
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-weight: 500;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            cursor: pointer;
            animation: slideInRight 0.5s ease-out;
        }
        
        .skill-tag:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(124, 58, 237, 0.4);
        }
        
        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        .activity-graph {
            margin: 50px 0;
            background: rgba(22, 27, 34, 0.8);
            border: 1px solid #30363d;
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            animation: fadeInUp 1s ease-out 0.9s both;
        }
        
        .graph-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .graph-container {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 3px;
            margin: 20px 0;
        }
        
        .graph-cell {
            width: 12px;
            height: 12px;
            border-radius: 2px;
            background: #161b22;
            transition: all 0.3s ease;
        }
        
        .graph-cell.active-1 { background: #0e4429; }
        .graph-cell.active-2 { background: #006d32; }
        .graph-cell.active-3 { background: #26a641; }
        .graph-cell.active-4 { background: #39d353; }
        
        .footer {
            text-align: center;
            margin-top: 50px;
            padding: 30px;
            color: #8b949e;
            animation: fadeIn 1s ease-out 1.2s both;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #7c3aed, #2563eb);
            border-radius: 50%;
            color: white;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            transform: scale(1.2) rotate(360deg);
            box-shadow: 0 10px 20px rgba(124, 58, 237, 0.4);
        }
        
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: #7c3aed;
            border-radius: 50%;
            pointer-events: none;
            animation: particleFloat 3s ease-out forwards;
        }
        
        @keyframes particleFloat {
            0% {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
            100% {
                opacity: 0;
                transform: scale(0.5) translateY(-100px);
            }
        }
        
        @media (max-width: 768px) {
            .profile-name {
                font-size: 2rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .graph-container {
                grid-template-columns: repeat(26, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    
    <div class="container">
        <div class="profile-header">
            <div class="profile-avatar">
                <div class="avatar-text">MM</div>
            </div>
            <h1 class="profile-name">MingMing</h1>
            <p class="profile-title">Full-Stack Developer & AI Enthusiast</p>
            <p class="typing-text">Building the future with code and intelligence...</p>
        </div>
        
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number">500+</div>
                <div class="stat-label">Repositories</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">2.5K</div>
                <div class="stat-label">Contributions</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">15+</div>
                <div class="stat-label">Languages</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">50+</div>
                <div class="stat-label">Projects</div>
            </div>
        </div>
        
        <div class="skills-section">
            <h2 class="section-title">💻 Technical Arsenal</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">🌐</span>
                        Frontend
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">HTML</span>
                        <span class="skill-tag">CSS</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">jQuery</span>
                        <span class="skill-tag">Flutter</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">⚙️</span>
                        Backend
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">PHP</span>
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">Java</span>
                        <span class="skill-tag">C#</span>
                        <span class="skill-tag">Kotlin</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">💾</span>
                        Databases
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">SQLite</span>
                        <span class="skill-tag">SQL Server</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">⚡</span>
                        Systems
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">C++</span>
                        <span class="skill-tag">C</span>
                        <span class="skill-tag">C#</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">🤖</span>
                        AI & ML
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">Machine Learning</span>
                        <span class="skill-tag">CNN</span>
                        <span class="skill-tag">YOLO</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="category-title">
                        <span class="category-icon">🛠️</span>
                        Tools
                    </h3>
                    <div class="skills-list">
                        <span class="skill-tag">VS Code</span>
                        <span class="skill-tag">XAMPP</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="activity-graph">
            <h3 class="graph-title">📈 Contribution Activity</h3>
            <div class="graph-container" id="contribution-graph">
                <!-- Contribution squares will be generated by JavaScript -->
            </div>
        </div>
        
        <div class="footer">
            <div class="social-links">
                <a href="#" class="social-link" title="GitHub">🐱</a>
                <a href="#" class="social-link" title="LinkedIn">💼</a>
                <a href="#" class="social-link" title="Twitter">🐦</a>
                <a href="#" class="social-link" title="Email">📧</a>
            </div>
            <p>⭐ "Code is poetry, and I'm writing verses that change the world" ⭐</p>
        </div>
    </div>
    
    <script>
        // Create animated stars background
        function createStars() {
            const starsContainer = document.querySelector('.stars');
            const starCount = 100;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }
        
        // Generate contribution graph
        function createContributionGraph() {
            const graphContainer = document.getElementById('contribution-graph');
            const totalCells = 365;
            
            for (let i = 0; i < totalCells; i++) {
                const cell = document.createElement('div');
                cell.className = 'graph-cell';
                
                // Randomly assign activity levels
                const random = Math.random();
                if (random > 0.8) cell.classList.add('active-4');
                else if (random > 0.6) cell.classList.add('active-3');
                else if (random > 0.4) cell.classList.add('active-2');
                else if (random > 0.2) cell.classList.add('active-1');
                
                // Add hover effect
                cell.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.5)';
                });
                
                cell.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1)';
                });
                
                graphContainer.appendChild(cell);
            }
        }
        
        // Create particle effects on skill tag hover
        function createParticle(x, y) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = x + 'px';
            particle.style.top = y + 'px';
            document.body.appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 3000);
        }
        
        // Add particle effects to skill tags
        document.addEventListener('DOMContentLoaded', function() {
            const skillTags = document.querySelectorAll('.skill-tag');
            
            skillTags.forEach(tag => {
                tag.addEventListener('mouseenter', function(e) {
                    const rect = this.getBoundingClientRect();
                    const x = rect.left + rect.width / 2;
                    const y = rect.top + rect.height / 2;
                    
                    // Create multiple particles
                    for (let i = 0; i < 3; i++) {
                        setTimeout(() => {
                            createParticle(x + (Math.random() - 0.5) * 20, y + (Math.random() - 0.5) * 20);
                        }, i * 100);
                    }
                });
            });
            
            // Animate stat numbers counting up
            const statNumbers = document.querySelectorAll('.stat-number');
            statNumbers.forEach(stat => {
                const target = parseInt(stat.textContent.replace(/\D/g, ''));
                const suffix = stat.textContent.replace(/[0-9]/g, '');
                let current = 0;
                const increment = target / 50;
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                    }
                    stat.textContent = Math.floor(current) + suffix;
                }, 40);
            });
        });
        
        // Initialize everything
        createStars();
        createContributionGraph();
        
        // Add floating animation to skill categories
        const skillCategories = document.querySelectorAll('.skill-category');
        skillCategories.forEach((category, index) => {
            category.style.animationDelay = (index * 0.2) + 's';
            category.style.animation = 'fadeInUp 1s ease-out ' + (0.6 + index * 0.1) + 's both';
        });
        
        // Typing animation cycling through different texts
        const typingTexts = [
            'Building the future with code and intelligence...',
            'Crafting elegant solutions to complex problems...',
            'Exploring the frontiers of AI and machine learning...',
            'Creating digital experiences that inspire...'
        ];
        
        let currentTextIndex = 0;
        const typingElement = document.querySelector('.typing-text');
        
        function cycleTypingText() {
            currentTextIndex = (currentTextIndex + 1) % typingTexts.length;
            typingElement.textContent = typingTexts[currentTextIndex];
        }
        
        setInterval(cycleTypingText, 4000);
    </script>
</body>
</html>
