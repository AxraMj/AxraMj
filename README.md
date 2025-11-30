<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Axra Manoj | Full Stack Developer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;600&family=Orbitron:wght@400;500;700;900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --color-primary: #667eea;
            --color-secondary: #764ba2;
            --color-accent: #f093fb;
            --bg-dark: #0d1117;
        }

        body {
            background-color: var(--bg-dark);
            color: #e6edf3;
            font-family: 'Fira Code', monospace;
            overflow-x: hidden;
        }

        /* Font Overrides */
        .font-orbitron { font-family: 'Orbitron', sans-serif; }
        .font-fira { font-family: 'Fira Code', monospace; }

        /* CRT Effect Overlay */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0,0,0,0.1) 50%,
                rgba(0,0,0,0.1)
            );
            background-size: 100% 4px;
            pointer-events: none;
            z-index: 50;
            animation: fadeIn 1s ease-out;
        }

        /* Glowing Text */
        .neon-text {
            text-shadow: 0 0 5px var(--color-primary), 0 0 10px var(--color-secondary);
        }

        .neon-box {
            box-shadow: 0 0 10px var(--color-primary), inset 0 0 5px var(--color-secondary);
            border: 1px solid var(--color-primary);
        }

        /* Gradient Text */
        .text-gradient {
            background: linear-gradient(to right, #667eea, #764ba2, #f093fb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Code Block Styling */
        .code-window {
            background: rgba(13, 17, 23, 0.9);
            border: 1px solid #30363d;
            border-radius: 8px;
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .code-window:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(118, 75, 162, 0.3);
        }

        /* Canvas Background */
        #starfield {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #0d1117;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(var(--color-primary), var(--color-accent));
            border-radius: 5px;
        }

        /* Keyframes */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        .animate-float { animation: float 4s ease-in-out infinite; }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        .cursor-blink { animation: blink 1s step-end infinite; }
    </style>
</head>
<body class="antialiased min-h-screen relative selection:bg-purple-500 selection:text-white">

    <!-- Background Animation -->
    <canvas id="starfield"></canvas>
    
    <!-- CRT Effect -->
    <div class="scanlines"></div>

    <!-- Navigation -->
    <nav class="fixed w-full z-40 top-0 left-0 border-b border-white/10 bg-gray-900/80 backdrop-blur-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center gap-2">
                    <i class="fas fa-terminal text-[#f093fb]"></i>
                    <span class="font-orbitron font-bold text-xl tracking-wider">AXRA<span class="text-[#667eea]">.DEV</span></span>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-8">
                        <a href="#about" class="hover:text-[#f093fb] transition-colors duration-300 px-3 py-2 rounded-md text-sm font-medium">/_About</a>
                        <a href="#stack" class="hover:text-[#f093fb] transition-colors duration-300 px-3 py-2 rounded-md text-sm font-medium">/_Stack</a>
                        <a href="#projects" class="hover:text-[#f093fb] transition-colors duration-300 px-3 py-2 rounded-md text-sm font-medium">/_Projects</a>
                        <a href="#contact" class="hover:text-[#f093fb] transition-colors duration-300 px-3 py-2 rounded-md text-sm font-medium">/_Contact</a>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <main class="pt-24 pb-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="text-center py-20 relative">
            <div class="inline-block p-1 rounded-full bg-gradient-to-r from-[#667eea] via-[#764ba2] to-[#f093fb] mb-6 animate-float">
                <img src="https://github.com/AxraMj.png" alt="Axra Profile" class="w-32 h-32 rounded-full border-4 border-[#0d1117] object-cover">
            </div>
            
            <h1 class="text-5xl md:text-7xl font-orbitron font-black mb-4 tracking-tight">
                <span class="text-white">AXRA</span> <span class="text-gradient">MANOJ</span>
            </h1>
            
            <div class="h-8 mb-8 text-xl md:text-2xl text-gray-400 font-fira">
                <span id="typing-text"></span><span class="cursor-blink">_</span>
            </div>

            <div class="flex justify-center gap-4 mt-8">
                <a href="https://github.com/AxraMj" target="_blank" class="bg-[#24292e] hover:bg-[#2f363d] text-white px-6 py-3 rounded-lg border border-white/10 transition-all flex items-center gap-2 hover:scale-105">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="#projects" class="bg-gradient-to-r from-[#667eea] to-[#764ba2] text-white px-6 py-3 rounded-lg shadow-lg hover:shadow-[#667eea]/50 transition-all flex items-center gap-2 hover:scale-105">
                    <i class="fas fa-rocket"></i> View Projects
                </a>
            </div>
        </div>

        <!-- About / JSON Section -->
        <section id="about" class="py-12 grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div class="code-window p-6 text-sm md:text-base overflow-hidden relative group">
                <div class="flex gap-2 mb-4 border-b border-white/10 pb-4">
                    <div class="w-3 h-3 rounded-full bg-red-500"></div>
                    <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                    <div class="w-3 h-3 rounded-full bg-green-500"></div>
                    <span class="ml-2 text-xs text-gray-500 font-sans">profile.js</span>
                </div>
                <pre><code class="language-javascript text-gray-300">
<span class="text-[#f093fb]">const</span> <span class="text-[#667eea]">AxraManoj</span> = {
    <span class="text-[#764ba2]">identity</span>: <span class="text-green-400">"🧙‍♀️ Full Stack Developer"</span>,
    <span class="text-[#764ba2]">location</span>: <span class="text-green-400">"🌍 Kerala, India"</span>,
    <span class="text-[#764ba2]">passion</span>: <span class="text-green-400">"Creating digital magic ✨"</span>,
    
    <span class="text-[#764ba2]">expertise</span>: {
        frontend: [<span class="text-green-400">"React"</span>, <span class="text-green-400">"Next.js"</span>, <span class="text-green-400">"TS"</span>],
        backend: [<span class="text-green-400">"Node"</span>, <span class="text-green-400">"Python"</span>, <span class="text-green-400">"Firebase"</span>],
        mobile: [<span class="text-green-400">"React Native"</span>]
    },

    <span class="text-[#764ba2]">funFact</span>: <span class="text-green-400">"Rubik's cube < 2 mins! 🧩"</span>
};
                </code></pre>
            </div>

            <div class="space-y-6">
                <h2 class="text-3xl font-orbitron font-bold text-transparent bg-clip-text bg-gradient-to-r from-white to-gray-400">
                    <i class="fas fa-terminal mr-2 text-[#667eea]"></i>Mission Control
                </h2>
                <p class="text-gray-400 leading-relaxed">
                    I don't just write code; I craft experiences. From the front-end gloss to the back-end logic, I love turning complex ideas into sleek, scalable, and user-friendly applications.
                </p>
                
                <!-- Stats Row -->
                <div class="grid grid-cols-2 gap-4 mt-6">
                    <div class="bg-white/5 p-4 rounded-lg border border-white/10 text-center hover:bg-white/10 transition">
                        <i class="fas fa-fire text-[#f093fb] text-2xl mb-2"></i>
                        <div class="text-2xl font-bold">Always</div>
                        <div class="text-xs text-gray-500 uppercase tracking-wider">Learning</div>
                    </div>
                    <div class="bg-white/5 p-4 rounded-lg border border-white/10 text-center hover:bg-white/10 transition">
                        <i class="fas fa-code-branch text-[#667eea] text-2xl mb-2"></i>
                        <div class="text-2xl font-bold">Open</div>
                        <div class="text-xs text-gray-500 uppercase tracking-wider">Source</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tech Stack -->
        <section id="stack" class="py-12">
            <h2 class="text-3xl font-orbitron font-bold mb-8 text-center">
                <span class="border-b-4 border-[#764ba2]">Tech Stack</span>
            </h2>
            
            <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                <!-- Stack Items generated by JS to keep it clean -->
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fab fa-react text-3xl text-blue-400 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">React</span>
                </div>
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fab fa-js text-3xl text-yellow-400 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">JavaScript</span>
                </div>
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fab fa-node text-3xl text-green-500 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">Node.js</span>
                </div>
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fab fa-python text-3xl text-blue-300 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">Python</span>
                </div>
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fas fa-database text-3xl text-orange-400 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">Firebase</span>
                </div>
                <div class="stack-item p-4 bg-[#161b22] border border-white/5 rounded-xl flex flex-col items-center justify-center gap-2 hover:border-[#667eea] transition-all group">
                    <i class="fab fa-docker text-3xl text-blue-600 group-hover:scale-110 transition-transform"></i>
                    <span class="text-sm font-medium">Docker</span>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="py-12">
            <h2 class="text-3xl font-orbitron font-bold mb-10 text-center">Featured <span class="text-[#f093fb]">Deployments</span></h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Project 1 -->
                <div class="group relative bg-[#161b22] rounded-xl overflow-hidden border border-white/10 hover:border-[#667eea] transition-all duration-300 hover:shadow-xl hover:shadow-[#667eea]/20">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0d1117] to-transparent opacity-90 z-10"></div>
                    <div class="h-48 bg-gradient-to-r from-[#667eea] to-[#764ba2] opacity-50 group-hover:opacity-70 transition-opacity"></div>
                    
                    <div class="absolute bottom-0 left-0 w-full p-6 z-20">
                        <div class="flex justify-between items-end mb-2">
                            <h3 class="text-2xl font-bold font-orbitron">ColorPal</h3>
                            <span class="text-[#f093fb] text-2xl"><i class="fas fa-palette"></i></span>
                        </div>
                        <p class="text-gray-300 text-sm mb-4">Advanced Color Palette Generator with real-time harmony and export features.</p>
                        
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">React</span>
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">CSS3</span>
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">Design</span>
                        </div>

                        <div class="flex gap-4">
                            <a href="https://github.com/AxraMj/colorpal" class="text-white hover:text-[#f093fb] text-sm flex items-center gap-1 transition-colors">
                                <i class="fab fa-github"></i> Source
                            </a>
                            <a href="#" class="text-white hover:text-[#f093fb] text-sm flex items-center gap-1 transition-colors">
                                <i class="fas fa-external-link-alt"></i> Demo
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="group relative bg-[#161b22] rounded-xl overflow-hidden border border-white/10 hover:border-[#764ba2] transition-all duration-300 hover:shadow-xl hover:shadow-[#764ba2]/20">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0d1117] to-transparent opacity-90 z-10"></div>
                    <div class="h-48 bg-gradient-to-r from-[#764ba2] to-[#f093fb] opacity-50 group-hover:opacity-70 transition-opacity"></div>
                    
                    <div class="absolute bottom-0 left-0 w-full p-6 z-20">
                        <div class="flex justify-between items-end mb-2">
                            <h3 class="text-2xl font-bold font-orbitron">Travel Explorer</h3>
                            <span class="text-[#f093fb] text-2xl"><i class="fas fa-map-marked-alt"></i></span>
                        </div>
                        <p class="text-gray-300 text-sm mb-4">Complete Travel Companion mobile app with location services and social features.</p>
                        
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">React Native</span>
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">Firebase</span>
                            <span class="px-2 py-1 text-xs rounded bg-white/10 text-white">Mobile</span>
                        </div>

                        <div class="flex gap-4">
                            <a href="https://github.com/AxraMj/TRAVEL-AND-EXPLORATION-MOBILE-APP" class="text-white hover:text-[#f093fb] text-sm flex items-center gap-1 transition-colors">
                                <i class="fab fa-github"></i> Source
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer / Contact -->
        <footer id="contact" class="mt-20 border-t border-white/10 pt-10 text-center">
            <h2 class="text-2xl font-orbitron mb-6">Let's <span class="text-[#667eea]">Connect</span></h2>
            
            <div class="flex justify-center gap-6 mb-8">
                <a href="mailto:offxaxra@gmail.com" class="w-12 h-12 rounded-full bg-[#161b22] flex items-center justify-center hover:bg-[#667eea] transition-all hover:-translate-y-1">
                    <i class="fas fa-envelope text-xl"></i>
                </a>
                <a href="https://www.linkedin.com/in/akshara-manoj/" class="w-12 h-12 rounded-full bg-[#161b22] flex items-center justify-center hover:bg-[#0077b5] transition-all hover:-translate-y-1">
                    <i class="fab fa-linkedin-in text-xl"></i>
                </a>
                <a href="https://twitter.com" class="w-12 h-12 rounded-full bg-[#161b22] flex items-center justify-center hover:bg-[#1DA1F2] transition-all hover:-translate-y-1">
                    <i class="fab fa-twitter text-xl"></i>
                </a>
            </div>
            
            <p class="text-gray-500 text-sm font-fira pb-8">
                &copy; 2025 Axra Manoj. Crafted with <i class="fas fa-heart text-[#f093fb]"></i> and Code.
            </p>
        </footer>

    </main>

    <script>
        // --- Starfield Animation ---
        const canvas = document.getElementById('starfield');
        const ctx = canvas.getContext('2d');
        
        let width, height;
        let stars = [];
        const numStars = 200;
        const speed = 2; // Warp speed factor

        function resize() {
            width = window.innerWidth;
            height = window.innerHeight;
            canvas.width = width;
            canvas.height = height;
        }

        class Star {
            constructor() {
                this.reset();
            }
            
            reset() {
                this.x = (Math.random() - 0.5) * width;
                this.y = (Math.random() - 0.5) * height;
                this.z = Math.random() * width;
                this.color = Math.random() > 0.8 ? '#f093fb' : (Math.random() > 0.5 ? '#667eea' : '#ffffff');
            }

            update() {
                this.z = this.z - speed;
                if (this.z <= 0) {
                    this.reset();
                    this.z = width;
                }
            }

            draw() {
                let x = (this.x / this.z) * width + width / 2;
                let y = (this.y / this.z) * height + height / 2;
                let radius = (1 - this.z / width) * 2; // Size based on depth

                if (x < 0 || x > width || y < 0 || y > height) return;

                ctx.beginPath();
                ctx.arc(x, y, radius > 0 ? radius : 0, 0, Math.PI * 2);
                ctx.fillStyle = this.color;
                ctx.fill();
            }
        }

        function initStars() {
            stars = [];
            for (let i = 0; i < numStars; i++) {
                stars.push(new Star());
            }
        }

        function animateStars() {
            ctx.fillStyle = '#0d1117'; // Background color clear
            ctx.fillRect(0, 0, width, height);
            
            stars.forEach(star => {
                star.update();
                star.draw();
            });
            requestAnimationFrame(animateStars);
        }

        window.addEventListener('resize', () => { resize(); initStars(); });
        resize();
        initStars();
        animateStars();

        // --- Typing Effect ---
        const texts = [
            "Building AMAZING applications!",
            "Creating BEAUTIFUL user experiences",
            "Turning IDEAS into REALITY",
            "Always LEARNING new technologies"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typeSpeed = 80;
        const deleteSpeed = 40;
        const pauseTime = 2000;
        
        const typeTarget = document.getElementById('typing-text');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typeTarget.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typeTarget.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            let nextSpeed = isDeleting ? deleteSpeed : typeSpeed;

            if (!isDeleting && charIndex === currentText.length) {
                isDeleting = true;
                nextSpeed = pauseTime;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                nextSpeed = 500;
            }

            setTimeout(type, nextSpeed);
        }

        // Start typing after a brief delay
        setTimeout(type, 1000);

        // --- Smooth Scroll ---
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
