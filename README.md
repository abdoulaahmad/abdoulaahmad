
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abdullahi Abba Ahmad - Interactive GitHub Profile</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        @keyframes glow {
            0%, 100% { box-shadow: 0 0 20px rgba(59, 130, 246, 0.3); }
            50% { box-shadow: 0 0 30px rgba(59, 130, 246, 0.6); }
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        .float-animation { animation: float 3s ease-in-out infinite; }
        .glow-animation { animation: glow 2s ease-in-out infinite; }
        .slide-in { animation: slideIn 0.8s ease-out forwards; }
        
        .tech-badge {
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .tech-badge:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }
        
        .project-card {
            transition: all 0.3s ease;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        .stats-counter {
            font-family: 'Courier New', monospace;
        }
    </style>
</head>
<body class="min-h-full gradient-bg text-white">
    <main class="container mx-auto px-6 py-8">
        <!-- Header Section -->
        <header class="text-center mb-12">
            <div class="float-animation mb-6">
                <div class="w-32 h-32 mx-auto bg-gradient-to-r from-blue-400 to-purple-500 rounded-full flex items-center justify-center text-4xl font-bold glow-animation">
                    AA
                </div>
            </div>
            <h1 class="text-5xl font-bold mb-4 slide-in">Abdullahi Abba Ahmad</h1>
            <p class="text-xl text-blue-200 mb-2 slide-in">Software Engineer Student at Federal University Dutse</p>
            <p class="text-lg text-purple-200 slide-in">Working at Virtual Connekt</p>
            
            <!-- Live Stats Counter -->
            <div class="mt-8 flex justify-center space-x-8">
                <div class="text-center">
                    <div class="stats-counter text-3xl font-bold text-yellow-300" id="repoCounter">0</div>
                    <div class="text-sm text-gray-300">Public Repos</div>
                </div>
                <div class="text-center">
                    <div class="stats-counter text-3xl font-bold text-green-300" id="starCounter">0</div>
                    <div class="text-sm text-gray-300">Stars</div>
                </div>
                <div class="text-center">
                    <div class="stats-counter text-3xl font-bold text-pink-300" id="projectCounter">0</div>
                    <div class="text-sm text-gray-300">Featured Projects</div>
                </div>
            </div>
        </header>

        <!-- Tech Stack Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-8">🚀 Tech Stack & Expertise</h2>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4" id="techStack">
                <!-- Tech badges will be populated by JavaScript -->
            </div>
        </section>

        <!-- Featured Projects Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-8">⭐ Featured Projects</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6" id="projectsGrid">
                <!-- Projects will be populated by JavaScript -->
            </div>
        </section>

        <!-- Areas of Expertise -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-8">💡 Areas of Expertise</h2>
            <div class="grid md:grid-cols-3 gap-6">
                <div class="project-card rounded-lg p-6 text-center">
                    <div class="text-4xl mb-4">⛓️</div>
                    <h3 class="text-xl font-bold mb-3">Blockchain & Web3</h3>
                    <p class="text-gray-300">Polygon, Ethereum, Sui ecosystem, token distribution, wallet generation</p>
                </div>
                <div class="project-card rounded-lg p-6 text-center">
                    <div class="text-4xl mb-4">🌐</div>
                    <h3 class="text-xl font-bold mb-3">Full-Stack Development</h3>
                    <p class="text-gray-300">Vue.js, TypeScript, JavaScript, PHP, modern web frameworks</p>
                </div>
                <div class="project-card rounded-lg p-6 text-center">
                    <div class="text-4xl mb-4">⚙️</div>
                    <h3 class="text-xl font-bold mb-3">Automation & Scale</h3>
                    <p class="text-gray-300">Infrastructure thinking, bulk operations, testnet tooling</p>
                </div>
            </div>
        </section>

        <!-- Interactive Contact Section -->
        <section class="text-center">
            <h2 class="text-3xl font-bold mb-6">🤝 Let's Connect</h2>
            <div class="flex justify-center space-x-4">
                <button class="tech-badge bg-gray-800 text-white px-6 py-3 rounded-lg font-semibold hover:bg-gray-700" onclick="openGitHub()">
                    📱 GitHub Profile
                </button>
                <button class="tech-badge bg-blue-600 text-white px-6 py-3 rounded-lg font-semibold hover:bg-blue-700" onclick="showContact()">
                    💼 Virtual Connekt
                </button>
            </div>
            <div id="contactInfo" class="mt-4 p-4 bg-black bg-opacity-30 rounded-lg hidden">
                <p class="text-green-300">🎓 Currently studying at Federal University Dutse</p>
                <p class="text-blue-300">💻 Building the future with Web3 & modern web technologies</p>
            </div>
        </section>
    </main>

    <script>
        // Tech stack data
        const techStack = [
            { name: 'TypeScript', color: 'bg-blue-500', icon: '📘' },
            { name: 'JavaScript', color: 'bg-yellow-500', icon: '⚡' },
            { name: 'Vue.js', color: 'bg-green-500', icon: '💚' },
            { name: 'PHP', color: 'bg-purple-500', icon: '🐘' },
            { name: 'Blockchain', color: 'bg-orange-500', icon: '⛓️' },
            { name: 'Web3', color: 'bg-indigo-500', icon: '🌐' },
            { name: 'Polygon', color: 'bg-purple-600', icon: '🔷' },
            { name: 'Ethereum', color: 'bg-gray-600', icon: '💎' }
        ];

        // Projects data
        const projects = [
            {
                name: 'Aptick',
                tech: 'TypeScript',
                description: 'Advanced TypeScript application with modern architecture',
                color: 'from-blue-500 to-blue-700'
            },
            {
                name: 'MerkPoll',
                tech: 'Vue.js',
                description: 'Interactive voting system built with Vue.js',
                color: 'from-green-500 to-green-700'
            },
            {
                name: 'sui_flow',
                tech: 'JavaScript',
                description: 'Sui ecosystem integration and flow management',
                color: 'from-yellow-500 to-yellow-700'
            },
            {
                name: 'polygon-faucet',
                tech: 'TypeScript',
                description: 'Futuristic glassmorphic Web3 faucet for MATIC tokens',
                color: 'from-purple-500 to-purple-700'
            },
            {
                name: 'Bulk-ETH-Wallet-Generator',
                tech: 'PHP',
                description: 'Scalable Ethereum wallet generation system',
                color: 'from-indigo-500 to-indigo-700'
            }
        ];

        // Animate counters
        function animateCounter(elementId, targetValue, duration = 2000) {
            const element = document.getElementById(elementId);
            const startValue = 0;
            const increment = targetValue / (duration / 16);
            let currentValue = startValue;

            const timer = setInterval(() => {
                currentValue += increment;
                if (currentValue >= targetValue) {
                    currentValue = targetValue;
                    clearInterval(timer);
                }
                element.textContent = Math.floor(currentValue);
            }, 16);
        }

        // Populate tech stack
        function populateTechStack() {
            const container = document.getElementById('techStack');
            techStack.forEach((tech, index) => {
                const badge = document.createElement('div');
                badge.className = `tech-badge ${tech.color} rounded-lg p-4 text-center text-white font-semibold`;
                badge.style.animationDelay = `${index * 0.1}s`;
                badge.innerHTML = `
                    <div class="text-2xl mb-2">${tech.icon}</div>
                    <div>${tech.name}</div>
                `;
                badge.addEventListener('click', () => {
                    badge.style.transform = 'scale(1.2) rotate(360deg)';
                    setTimeout(() => {
                        badge.style.transform = '';
                    }, 500);
                });
                container.appendChild(badge);
            });
        }

        // Populate projects
        function populateProjects() {
            const container = document.getElementById('projectsGrid');
            projects.forEach((project, index) => {
                const card = document.createElement('div');
                card.className = 'project-card rounded-lg p-6';
                card.style.animationDelay = `${index * 0.2}s`;
                card.innerHTML = `
                    <div class="bg-gradient-to-r ${project.color} w-full h-32 rounded-lg mb-4 flex items-center justify-center">
                        <div class="text-3xl font-bold text-white">${project.name.charAt(0)}</div>
                    </div>
                    <h3 class="text-xl font-bold mb-2">${project.name}</h3>
                    <p class="text-sm text-blue-300 mb-3">${project.tech}</p>
                    <p class="text-gray-300 text-sm">${project.description}</p>
                `;
                card.addEventListener('click', () => {
                    card.style.transform = 'scale(1.05)';
                    setTimeout(() => {
                        card.style.transform = '';
                    }, 200);
                });
                container.appendChild(card);
            });
        }

        // Interactive functions
        function openGitHub() {
            window.open('https://github.com', '_blank', 'noopener,noreferrer');
        }

        function showContact() {
            const contactInfo = document.getElementById('contactInfo');
            contactInfo.classList.toggle('hidden');
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', () => {
            // Start counter animations
            setTimeout(() => animateCounter('repoCounter', 31), 500);
            setTimeout(() => animateCounter('starCounter', 5), 800);
            setTimeout(() => animateCounter('projectCounter', 5), 1100);

            // Populate sections
            populateTechStack();
            populateProjects();

            // Add slide-in animation to sections
            const sections = document.querySelectorAll('section');
            sections.forEach((section, index) => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(50px)';
                setTimeout(() => {
                    section.style.transition = 'all 0.8s ease';
                    section.style.opacity = '1';
                    section.style.transform = 'translateY(0)';
                }, index * 200);
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'99417ff987badc8d',t:'MTc2MTM5MzA2NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
