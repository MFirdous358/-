<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muhammad Firdous | Business Development & AI Automation</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- GSAP for High-Performance Animations -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Space Grotesk', 'sans-serif'],
                    },
                    colors: {
                        primary: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0ea5e9',
                            600: '#0284c7',
                            900: '#0c4a6e',
                        },
                        accent: {
                            cyan: '#06b6d4',
                            purple: '#8b5cf6',
                            pink: '#ec4899',
                        }
                    },
                    animation: {
                        'blob': 'blob 7s infinite',
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    },
                    keyframes: {
                        blob: {
                            '0%': { transform: 'translate(0px, 0px) scale(1)' },
                            '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
                            '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
                            '100%': { transform: 'translate(0px, 0px) scale(1)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-20px)' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom CSS Variables for Theming */
        :root {
            --bg-primary: #f8fafc;
            --bg-secondary: #f1f5f9;
            --text-primary: #0f172a;
            --text-secondary: #475569;
            --glass-bg: rgba(255, 255, 255, 0.7);
            --glass-border: rgba(255, 255, 255, 0.5);
            --neu-shadow-light: #ffffff;
            --neu-shadow-dark: #cbd5e1;
            --accent-glow: rgba(14, 165, 233, 0.5);
        }

        .dark {
            --bg-primary: #0f172a;
            --bg-secondary: #1e293b;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --glass-bg: rgba(30, 41, 59, 0.7);
            --glass-border: rgba(255, 255, 255, 0.1);
            --neu-shadow-light: #334155;
            --neu-shadow-dark: #0f172a;
            --accent-glow: rgba(6, 182, 212, 0.5);
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-primary);
            transition: background-color 0.5s ease, color 0.5s ease;
            overflow-x: hidden;
        }

        /* Grain Texture Overlay */
        .grain-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 9999;
            opacity: 0.03;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
        }

        /* Glassmorphism Utility */
        .glass {
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid var(--glass-border);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.07);
        }

        /* Neumorphism Utility */
        .neu-flat {
            background: var(--bg-primary);
            box-shadow: 8px 8px 16px var(--neu-shadow-dark), 
                       -8px -8px 16px var(--neu-shadow-light);
            border-radius: 20px;
            border: 1px solid var(--glass-border);
        }

        .neu-pressed {
            background: var(--bg-primary);
            box-shadow: inset 6px 6px 12px var(--neu-shadow-dark), 
                       inset -6px -6px 12px var(--neu-shadow-light);
            border-radius: 20px;
        }

        .neu-icon {
            background: var(--bg-primary);
            box-shadow: 5px 5px 10px var(--neu-shadow-dark), 
                       -5px -5px 10px var(--neu-shadow-light);
            transition: all 0.3s ease;
        }

        .neu-icon:hover {
            box-shadow: 8px 8px 16px var(--neu-shadow-dark), 
                       -8px -8px 16px var(--neu-shadow-light);
            transform: translateY(-2px);
        }

        .neu-icon:active {
            box-shadow: inset 4px 4px 8px var(--neu-shadow-dark), 
                       inset -4px -4px 8px var(--neu-shadow-light);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, #0ea5e9, #8b5cf6);
            border-radius: 5px;
        }

        /* Scroll Progress Bar */
        .scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            height: 3px;
            background: linear-gradient(90deg, #06b6d4, #8b5cf6, #ec4899);
            z-index: 10000;
            width: 0%;
            transition: width 0.1s;
        }

        /* Magnetic Button Effect */
        .magnetic-btn {
            position: relative;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s cubic-bezier(0.23, 1, 0.32, 1);
        }

        /* Text Gradient */
        .text-gradient {
            background: linear-gradient(135deg, #06b6d4 0%, #8b5cf6 50%, #ec4899 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Animated Border Gradient */
        .gradient-border {
            position: relative;
            background: var(--bg-primary);
            border-radius: 16px;
            z-index: 1;
        }
        .gradient-border::before {
            content: "";
            position: absolute;
            inset: -2px;
            border-radius: 18px;
            background: linear-gradient(45deg, #06b6d4, #8b5cf6, #ec4899, #06b6d4);
            background-size: 400%;
            z-index: -1;
            animation: glow 20s linear infinite;
        }
        .gradient-border::after {
            content: "";
            position: absolute;
            inset: 0;
            border-radius: 16px;
            background: var(--bg-primary);
            z-index: -1;
        }

        @keyframes glow {
            0% { background-position: 0 0; }
            50% { background-position: 400% 0; }
            100% { background-position: 0 0; }
        }

        /* Loader */
        .loader-container {
            position: fixed;
            inset: 0;
            background: var(--bg-primary);
            z-index: 99999;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .loader-text {
            font-family: 'Space Grotesk', sans-serif;
            font-size: 2rem;
            font-weight: 700;
            overflow: hidden;
            white-space: nowrap;
            border-right: 3px solid var(--text-primary);
            animation: typing 2s steps(20) forwards, blink 0.7s infinite;
            width: 0;
        }

        @keyframes typing {
            to { width: 100%; }
        }
        @keyframes blink {
            50% { border-color: transparent; }
        }

        /* 3D Tilt Card */
        .tilt-card {
            transform-style: preserve-3d;
            transform: perspective(1000px);
        }
        .tilt-content {
            transform: translateZ(20px);
        }

        /* Particle Canvas */
        #particle-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        /* Hide elements for scroll reveal */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Timeline */
        .timeline-line {
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, #06b6d4, #8b5cf6, #ec4899);
            transform: translateX(-50%);
        }
        
        @media (max-width: 768px) {
            .timeline-line { left: 20px; }
        }

        /* Skill Bar Animation */
        .skill-fill {
            width: 0%;
            transition: width 1.5s cubic-bezier(0.22, 1, 0.36, 1);
        }

        /* Custom Cursor */
        .custom-cursor {
            width: 20px;
            height: 20px;
            border: 2px solid #06b6d4;
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 99998;
            transition: transform 0.2s, opacity 0.2s;
            mix-blend-mode: difference;
        }
        .custom-cursor.hovered {
            transform: scale(2.5);
            background: rgba(6, 182, 212, 0.1);
            border-color: #8b5cf6;
        }
    </style>
</head>
<body class="antialiased selection:bg-cyan-500 selection:text-white">

    <!-- Grain Overlay -->
    <div class="grain-overlay"></div>
    
    <!-- Scroll Progress -->
    <div class="scroll-progress" id="scrollProgress"></div>
    
    <!-- Custom Cursor -->
    <div class="custom-cursor hidden md:block" id="cursor"></div>

    <!-- Loader -->
    <div class="loader-container" id="loader">
        <div class="text-gradient text-4xl font-bold mb-4 font-display">MF</div>
        <div class="loader-text text-primary">Initializing Portfolio...</div>
    </div>

    <!-- Particle Background -->
    <canvas id="particle-canvas"></canvas>

    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-50 px-4 py-4 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto glass rounded-2xl px-6 py-4 flex justify-between items-center">
            <a href="#" class="text-2xl font-bold font-display text-gradient tracking-tighter">FIRDOUS.</a>
            
            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center gap-8">
                <a href="#about" class="text-sm font-medium hover:text-cyan-500 transition-colors magnetic-btn">About</a>
                <a href="#skills" class="text-sm font-medium hover:text-cyan-500 transition-colors magnetic-btn">Skills</a>
                <a href="#experience" class="text-sm font-medium hover:text-cyan-500 transition-colors magnetic-btn">Experience</a>
                <a href="#contact" class="text-sm font-medium hover:text-cyan-500 transition-colors magnetic-btn">Contact</a>
                
                <!-- Theme Toggle -->
                <button id="themeToggle" class="neu-icon w-10 h-10 rounded-full flex items-center justify-center text-primary">
                    <i data-lucide="sun" class="w-5 h-5 hidden dark:block"></i>
                    <i data-lucide="moon" class="w-5 h-5 block dark:hidden"></i>
                </button>
            </div>

            <!-- Mobile Menu Button -->
            <button class="md:hidden neu-icon w-10 h-10 rounded-full flex items-center justify-center" id="mobileMenuBtn">
                <i data-lucide="menu" class="w-5 h-5"></i>
            </button>
        </div>

        <!-- Mobile Menu -->
        <div class="md:hidden hidden mt-4 glass rounded-2xl p-6 mx-auto max-w-7xl" id="mobileMenu">
            <div class="flex flex-col gap-4">
                <a href="#about" class="text-lg font-medium py-2 border-b border-gray-200 dark:border-gray-700">About</a>
                <a href="#skills" class="text-lg font-medium py-2 border-b border-gray-200 dark:border-gray-700">Skills</a>
                <a href="#experience" class="text-lg font-medium py-2 border-b border-gray-200 dark:border-gray-700">Experience</a>
                <a href="#contact" class="text-lg font-medium py-2">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="min-h-screen flex items-center justify-center relative pt-20 px-4 overflow-hidden">
        <!-- Animated Background Blobs -->
        <div class="absolute top-20 left-10 w-72 h-72 bg-cyan-400 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob dark:opacity-20"></div>
        <div class="absolute top-20 right-10 w-72 h-72 bg-purple-400 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob animation-delay-2000 dark:opacity-20"></div>
        <div class="absolute -bottom-8 left-1/2 w-72 h-72 bg-pink-400 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob animation-delay-4000 dark:opacity-20"></div>

        <div class="max-w-7xl mx-auto grid md:grid-cols-2 gap-12 items-center relative z-10">
            <div class="space-y-8">
                <div class="inline-flex items-center gap-2 glass px-4 py-2 rounded-full text-sm font-medium text-cyan-600 dark:text-cyan-400 reveal">
                    <span class="w-2 h-2 bg-cyan-500 rounded-full animate-pulse"></span>
                    Available for Opportunities
                </div>
                
                <h1 class="text-5xl md:text-7xl font-bold font-display leading-tight reveal" style="transition-delay: 100ms;">
                    Turning <span class="text-gradient">Cold Outreach</span> into Warm Handshakes
                </h1>
                
                <p class="text-lg md:text-xl text-secondary-600 dark:text-secondary-400 max-w-lg reveal" style="transition-delay: 200ms;" id="typewriter-text">
                    Business Development Executive & AI Automation Specialist. I bridge the gap between complex business needs and cutting-edge freelance talent solutions.
                </p>
                
                <div class="flex flex-wrap gap-4 reveal" style="transition-delay: 300ms;">
                    <a href="#contact" class="magnetic-btn gradient-border px-8 py-4 rounded-full font-semibold text-primary hover:scale-105 transition-transform flex items-center gap-2 group">
                        Start a Project
                        <i data-lucide="arrow-right" class="w-5 h-5 group-hover:translate-x-1 transition-transform"></i>
                    </a>
                    <a href="#experience" class="neu-flat px-8 py-4 rounded-full font-semibold hover:scale-105 transition-transform flex items-center gap-2">
                        View Experience
                    </a>
                </div>

                <div class="flex items-center gap-6 pt-4 reveal" style="transition-delay: 400ms;">
                    <a href="https://linkedin.com" target="_blank" class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-primary hover:text-cyan-500">
                        <i data-lucide="linkedin" class="w-5 h-5"></i>
                    </a>
                    <a href="mailto:muhammadfirdous@protonmail.com" class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-primary hover:text-cyan-500">
                        <i data-lucide="mail" class="w-5 h-5"></i>
                    </a>
                    <a href="tel:+923345149503" class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-primary hover:text-cyan-500">
                        <i data-lucide="phone" class="w-5 h-5"></i>
                    </a>
                </div>
            </div>

            <div class="relative reveal" style="transition-delay: 500ms;">
                <div class="neu-flat p-8 relative z-10 tilt-card" id="heroCard">
                    <div class="tilt-content space-y-6">
                        <div class="flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-16 h-16 rounded-full bg-gradient-to-br from-cyan-400 to-purple-600 flex items-center justify-center text-white text-2xl font-bold font-display">
                                    MF
                                </div>
                                <div>
                                    <h3 class="font-bold text-lg">Muhammad Firdous</h3>
                                    <p class="text-sm text-secondary-500">Business Development</p>
                                </div>
                            </div>
                            <div class="neu-pressed px-3 py-1 rounded-lg text-xs font-mono text-cyan-600 dark:text-cyan-400">
                                ONLINE
                            </div>
                        </div>
                        
                        <div class="space-y-3">
                            <div class="flex justify-between text-sm">
                                <span class="text-secondary-500">Sales Conversion</span>
                                <span class="font-semibold">95%</span>
                            </div>
                            <div class="h-2 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden">
                                <div class="h-full bg-gradient-to-r from-cyan-500 to-purple-500 w-[95%]"></div>
                            </div>
                        </div>

                        <div class="space-y-3">
                            <div class="flex justify-between text-sm">
                                <span class="text-secondary-500">Client Retention</span>
                                <span class="font-semibold">92%</span>
                            </div>
                            <div class="h-2 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden">
                                <div class="h-full bg-gradient-to-r from-purple-500 to-pink-500 w-[92%]"></div>
                            </div>
                        </div>

                        <div class="grid grid-cols-2 gap-4 pt-4">
                            <div class="neu-pressed p-4 rounded-xl text-center">
                                <div class="text-2xl font-bold text-gradient">3+</div>
                                <div class="text-xs text-secondary-500 mt-1">Years Exp.</div>
                            </div>
                            <div class="neu-pressed p-4 rounded-xl text-center">
                                <div class="text-2xl font-bold text-gradient">1000+</div>
                                <div class="text-xs text-secondary-500 mt-1">Leads Gen</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Decorative Elements -->
                <div class="absolute -top-6 -right-6 w-24 h-24 bg-cyan-400 rounded-full opacity-20 blur-xl animate-float"></div>
                <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-purple-400 rounded-full opacity-20 blur-xl animate-float" style="animation-delay: 1s;"></div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 px-4 relative">
        <div class="max-w-7xl mx-auto">
            <div class="grid md:grid-cols-2 gap-16 items-center">
                <div class="reveal">
                    <h2 class="text-4xl md:text-5xl font-bold font-display mb-6">
                        Digital <span class="text-gradient">Architect</span> of Business Growth
                    </h2>
                    <div class="space-y-4 text-secondary-600 dark:text-secondary-400 leading-relaxed">
                        <p>
                            I am the person who turns complex problems into simple solutions. Over the past 3+ years, I have navigated the full spectrum of sales and business development—from qualifying leads to closing high-ticket deals.
                        </p>
                        <p>
                            Currently, I specialize in matching global companies with elite freelance talent on Upwork. Whether translating technical specs for business owners or deciphering what a startup actually needs versus what they think they need, my approach remains consistent: <strong class="text-primary">listen first, recommend second, build relationships that last.</strong>
                        </p>
                        <p>
                            I get restless if I'm not learning something new. Currently obsessed with AI automation (n8n), prompt engineering, and optimizing workflows to eliminate redundancy.
                        </p>
                    </div>
                    
                    <div class="mt-8 flex flex-wrap gap-3">
                        <span class="glass px-4 py-2 rounded-full text-sm font-medium">B2B Sales</span>
                        <span class="glass px-4 py-2 rounded-full text-sm font-medium">AI Automation</span>
                        <span class="glass px-4 py-2 rounded-full text-sm font-medium">Lead Generation</span>
                        <span class="glass px-4 py-2 rounded-full text-sm font-medium">CRM Management</span>
                    </div>
                </div>
                
                <div class="relative reveal">
                    <div class="glass rounded-3xl p-8 relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-64 h-64 bg-gradient-to-br from-cyan-400 to-purple-600 opacity-10 rounded-full blur-3xl -mr-20 -mt-20"></div>
                        
                        <h3 class="text-2xl font-bold mb-6 font-display">Quick Facts</h3>
                        
                        <div class="space-y-6">
                            <div class="flex items-start gap-4">
                                <div class="neu-icon w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-cyan-600">
                                    <i data-lucide="map-pin" class="w-6 h-6"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Location</h4>
                                    <p class="text-sm text-secondary-500">Rawalpindi, Pakistan (Remote Ready)</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start gap-4">
                                <div class="neu-icon w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-purple-600">
                                    <i data-lucide="languages" class="w-6 h-6"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Languages</h4>
                                    <p class="text-sm text-secondary-500">English (Fluent), Urdu (Native)</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start gap-4">
                                <div class="neu-icon w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-pink-600">
                                    <i data-lucide="zap" class="w-6 h-6"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Superpower</h4>
                                    <p class="text-sm text-secondary-500">Translating tech jargon into business value</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-24 px-4 relative bg-secondary-50/50 dark:bg-secondary-900/20">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16 reveal">
                <h2 class="text-4xl md:text-5xl font-bold font-display mb-4">Technical <span class="text-gradient">Arsenal</span></h2>
                <p class="text-secondary-600 dark:text-secondary-400 max-w-2xl mx-auto">Modern tools for modern business challenges. I leverage technology to automate, optimize, and scale.</p>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <!-- Category 1: Automation & AI -->
                <div class="neu-flat p-8 rounded-3xl reveal group hover:scale-[1.02] transition-transform duration-300">
                    <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-cyan-400 to-blue-600 flex items-center justify-center text-white mb-6 group-hover:rotate-6 transition-transform">
                        <i data-lucide="bot" class="w-7 h-7"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 font-display">Automation & AI</h3>
                    <ul class="space-y-3">
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-cyan-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">n8n Workflow Automation</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-cyan-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Prompt Engineering</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-cyan-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">GoHighLevel (Power User)</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-cyan-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">AI Tool Optimization</span>
                        </li>
                    </ul>
                </div>

                <!-- Category 2: Sales & CRM -->
                <div class="neu-flat p-8 rounded-3xl reveal group hover:scale-[1.02] transition-transform duration-300" style="transition-delay: 100ms;">
                    <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-purple-400 to-pink-600 flex items-center justify-center text-white mb-6 group-hover:rotate-6 transition-transform">
                        <i data-lucide="trending-up" class="w-7 h-7"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 font-display">Sales & CRM</h3>
                    <ul class="space-y-3">
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-purple-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Cold Calling & Outreach</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-purple-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Lead Qualification</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-purple-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">CRM Management</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-purple-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Negotiation & Closing</span>
                        </li>
                    </ul>
                </div>

                <!-- Category 3: Data & Marketing -->
                <div class="neu-flat p-8 rounded-3xl reveal group hover:scale-[1.02] transition-transform duration-300" style="transition-delay: 200ms;">
                    <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-orange-400 to-red-600 flex items-center justify-center text-white mb-6 group-hover:rotate-6 transition-transform">
                        <i data-lucide="bar-chart-3" class="w-7 h-7"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4 font-display">Data & Marketing</h3>
                    <ul class="space-y-3">
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-orange-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Email Campaign Management</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-orange-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Lead Scraping</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-orange-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Google Analytics</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <div class="w-2 h-2 rounded-full bg-orange-500"></div>
                            <span class="text-secondary-600 dark:text-secondary-400">Canva Design</span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Skill Bars -->
            <div class="mt-16 grid md:grid-cols-2 gap-8 reveal">
                <div class="space-y-6">
                    <div>
                        <div class="flex justify-between mb-2">
                            <span class="font-semibold">B2B Sales</span>
                            <span class="text-cyan-600">95%</span>
                        </div>
                        <div class="h-3 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden neu-pressed">
                            <div class="skill-fill h-full bg-gradient-to-r from-cyan-500 to-blue-500 rounded-full" data-width="95%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-2">
                            <span class="font-semibold">CRM & Automation</span>
                            <span class="text-purple-600">90%</span>
                        </div>
                        <div class="h-3 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden neu-pressed">
                            <div class="skill-fill h-full bg-gradient-to-r from-purple-500 to-pink-500 rounded-full" data-width="90%"></div>
                        </div>
                    </div>
                </div>
                <div class="space-y-6">
                    <div>
                        <div class="flex justify-between mb-2">
                            <span class="font-semibold">Lead Generation</span>
                            <span class="text-orange-600">92%</span>
                        </div>
                        <div class="h-3 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden neu-pressed">
                            <div class="skill-fill h-full bg-gradient-to-r from-orange-500 to-red-500 rounded-full" data-width="92%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-2">
                            <span class="font-semibold">Client Communication</span>
                            <span class="text-green-600">98%</span>
                        </div>
                        <div class="h-3 w-full bg-gray-200 dark:bg-gray-700 rounded-full overflow-hidden neu-pressed">
                            <div class="skill-fill h-full bg-gradient-to-r from-green-500 to-emerald-500 rounded-full" data-width="98%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Timeline -->
    <section id="experience" class="py-24 px-4 relative overflow-hidden">
        <div class="max-w-5xl mx-auto">
            <div class="text-center mb-16 reveal">
                <h2 class="text-4xl md:text-5xl font-bold font-display mb-4">Career <span class="text-gradient">Trajectory</span></h2>
                <p class="text-secondary-600 dark:text-secondary-400">My professional journey through sales and business development.</p>
            </div>

            <div class="relative">
                <div class="timeline-line"></div>

                <!-- Timeline Item 1 -->
                <div class="relative mb-12 md:mb-24 reveal">
                    <div class="md:flex items-center justify-between">
                        <div class="md:w-5/12 md:text-right mb-4 md:mb-0">
                            <div class="glass inline-block p-6 rounded-2xl">
                                <span class="text-cyan-500 font-bold text-sm">Aug 2025 - Present</span>
                                <h3 class="text-xl font-bold mt-2 font-display">Business Development Executive</h3>
                                <p class="text-secondary-500 font-medium">Work Generations Pvt Ltd</p>
                                <ul class="mt-3 text-sm text-secondary-600 dark:text-secondary-400 space-y-1">
                                    <li>• Matching global companies with elite freelance talent</li>
                                    <li>• Full-cycle business development on Upwork</li>
                                    <li>• Long-term relationship management</li>
                                </ul>
                            </div>
                        </div>
                        <div class="absolute left-0 md:left-1/2 transform md:-translate-x-1/2 w-8 h-8 rounded-full bg-gradient-to-r from-cyan-400 to-blue-600 border-4 border-white dark:border-gray-900 z-10"></div>
                        <div class="md:w-5/12 md:pl-12 hidden md:block"></div>
                    </div>
                </div>

                <!-- Timeline Item 2 -->
                <div class="relative mb-12 md:mb-24 reveal">
                    <div class="md:flex items-center justify-between flex-row-reverse">
                        <div class="md:w-5/12 md:text-left mb-4 md:mb-0">
                            <div class="glass inline-block p-6 rounded-2xl">
                                <span class="text-purple-500 font-bold text-sm">Dec 2024 - July 2025</span>
                                <h3 class="text-xl font-bold mt-2 font-display">Customer Sales Associate</h3>
                                <p class="text-secondary-500 font-medium">Touchstone Communications</p>
                                <ul class="mt-3 text-sm text-secondary-600 dark:text-secondary-400 space-y-1">
                                    <li>• Solar Live Transfer (B2C)</li>
                                    <li>• Outbound cold calling & lead prequalification</li>
                                    <li>• Real-time warm transfers to closers</li>
                                </ul>
                            </div>
                        </div>
                        <div class="absolute left-0 md:left-1/2 transform md:-translate-x-1/2 w-8 h-8 rounded-full bg-gradient-to-r from-purple-400 to-pink-600 border-4 border-white dark:border-gray-900 z-10"></div>
                        <div class="md:w-5/12 md:pr-12 hidden md:block"></div>
                    </div>
                </div>

                <!-- Timeline Item 3 -->
                <div class="relative mb-12 md:mb-24 reveal">
                    <div class="md:flex items-center justify-between">
                        <div class="md:w-5/12 md:text-right mb-4 md:mb-0">
                            <div class="glass inline-block p-6 rounded-2xl">
                                <span class="text-orange-500 font-bold text-sm">April 2024 - Dec 2024</span>
                                <h3 class="text-xl font-bold mt-2 font-display">Account Executive</h3>
                                <p class="text-secondary-500 font-medium">Advantix Solutions</p>
                                <ul class="mt-3 text-sm text-secondary-600 dark:text-secondary-400 space-y-1">
                                    <li>• Real Estate leads network (B2B)</li>
                                    <li>• Cold-texted 1000+ USA realtors daily</li>
                                    <li>• GoHighLevel automation expert</li>
                                </ul>
                            </div>
                        </div>
                        <div class="absolute left-0 md:left-1/2 transform md:-translate-x-1/2 w-8 h-8 rounded-full bg-gradient-to-r from-orange-400 to-red-600 border-4 border-white dark:border-gray-900 z-10"></div>
                        <div class="md:w-5/12 md:pl-12 hidden md:block"></div>
                    </div>
                </div>

                <!-- Timeline Item 4 -->
                <div class="relative reveal">
                    <div class="md:flex items-center justify-between flex-row-reverse">
                        <div class="md:w-5/12 md:text-left mb-4 md:mb-0">
                            <div class="glass inline-block p-6 rounded-2xl">
                                <span class="text-green-500 font-bold text-sm">March 2023 - April 2024</span>
                                <h3 class="text-xl font-bold mt-2 font-display">Customer Sales Associate</h3>
                                <p class="text-secondary-500 font-medium">Global Hire Placement</p>
                                <ul class="mt-3 text-sm text-secondary-600 dark:text-secondary-400 space-y-1">
                                    <li>• Telecom Sales (B2B)</li>
                                    <li>• Cold calls & email marketing campaigns</li>
                                    <li>• End-to-end deal closing</li>
                                </ul>
                            </div>
                        </div>
                        <div class="absolute left-0 md:left-1/2 transform md:-translate-x-1/2 w-8 h-8 rounded-full bg-gradient-to-r from-green-400 to-emerald-600 border-4 border-white dark:border-gray-900 z-10"></div>
                        <div class="md:w-5/12 md:pr-12 hidden md:block"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="py-24 px-4 bg-secondary-50/50 dark:bg-secondary-900/20">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16 reveal">
                <h2 class="text-4xl md:text-5xl font-bold font-display mb-4">Value <span class="text-gradient">Proposition</span></h2>
                <p class="text-secondary-600 dark:text-secondary-400">What I bring to your organization</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="neu-flat p-6 rounded-2xl text-center group hover:-translate-y-2 transition-transform duration-300 reveal">
                    <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-gradient-to-br from-cyan-400 to-blue-600 flex items-center justify-center text-white group-hover:scale-110 transition-transform">
                        <i data-lucide="users" class="w-8 h-8"></i>
                    </div>
                    <h3 class="font-bold text-lg mb-2">Talent Matching</h3>
                    <p class="text-sm text-secondary-500">Connecting business needs with world-class freelance talent</p>
                </div>

                <div class="neu-flat p-6 rounded-2xl text-center group hover:-translate-y-2 transition-transform duration-300 reveal" style="transition-delay: 100ms;">
                    <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-gradient-to-br from-purple-400 to-pink-600 flex items-center justify-center text-white group-hover:scale-110 transition-transform">
                        <i data-lucide="workflow" class="w-8 h-8"></i>
                    </div>
                    <h3 class="font-bold text-lg mb-2">Automation</h3>
                    <p class="text-sm text-secondary-500">Building n8n workflows to eliminate repetitive tasks</p>
                </div>

                <div class="neu-flat p-6 rounded-2xl text-center group hover:-translate-y-2 transition-transform duration-300 reveal" style="transition-delay: 200ms;">
                    <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-gradient-to-br from-orange-400 to-red-600 flex items-center justify-center text-white group-hover:scale-110 transition-transform">
                        <i data-lucide="phone-call" class="w-8 h-8"></i>
                    </div>
                    <h3 class="font-bold text-lg mb-2">Cold Outreach</h3>
                    <p class="text-sm text-secondary-500">Transforming cold leads into warm opportunities</p>
                </div>

                <div class="neu-flat p-6 rounded-2xl text-center group hover:-translate-y-2 transition-transform duration-300 reveal" style="transition-delay: 300ms;">
                    <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-gradient-to-br from-green-400 to-emerald-600 flex items-center justify-center text-white group-hover:scale-110 transition-transform">
                        <i data-lucide="handshake" class="w-8 h-8"></i>
                    </div>
                    <h3 class="font-bold text-lg mb-2">Deal Closing</h3>
                    <p class="text-sm text-secondary-500">Negotiation and persuasive communication expert</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 px-4 relative">
        <div class="max-w-4xl mx-auto">
            <div class="glass rounded-3xl p-8 md:p-12 reveal">
                <div class="text-center mb-12">
                    <h2 class="text-4xl md:text-5xl font-bold font-display mb-4">Let's <span class="text-gradient">Connect</span></h2>
                    <p class="text-secondary-600 dark:text-secondary-400">Ready to scale your business? Let's talk.</p>
                </div>

                <form class="space-y-6" id="contactForm">
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="relative">
                            <input type="text" id="name" required class="peer w-full bg-transparent border-2 border-gray-200 dark:border-gray-700 rounded-xl px-4 py-4 outline-none focus:border-cyan-500 transition-colors placeholder-transparent" placeholder="Name">
                            <label for="name" class="absolute left-4 top-4 text-secondary-500 transition-all peer-focus:-top-2 peer-focus:left-2 peer-focus:bg-white dark:peer-focus:bg-gray-900 peer-focus:px-2 peer-focus:text-sm peer-focus:text-cyan-500 peer-not-placeholder-shown:-top-2 peer-not-placeholder-shown:left-2 peer-not-placeholder-shown:bg-white dark:peer-not-placeholder-shown:bg-gray-900 peer-not-placeholder-shown:px-2 peer-not-placeholder-shown:text-sm">Your Name</label>
                        </div>
                        <div class="relative">
                            <input type="email" id="email" required class="peer w-full bg-transparent border-2 border-gray-200 dark:border-gray-700 rounded-xl px-4 py-4 outline-none focus:border-cyan-500 transition-colors placeholder-transparent" placeholder="Email">
                            <label for="email" class="absolute left-4 top-4 text-secondary-500 transition-all peer-focus:-top-2 peer-focus:left-2 peer-focus:bg-white dark:peer-focus:bg-gray-900 peer-focus:px-2 peer-focus:text-sm peer-focus:text-cyan-500 peer-not-placeholder-shown:-top-2 peer-not-placeholder-shown:left-2 peer-not-placeholder-shown:bg-white dark:peer-not-placeholder-shown:bg-gray-900 peer-not-placeholder-shown:px-2 peer-not-placeholder-shown:text-sm">Email Address</label>
                        </div>
                    </div>
                    
                    <div class="relative">
                        <textarea id="message" rows="4" required class="peer w-full bg-transparent border-2 border-gray-200 dark:border-gray-700 rounded-xl px-4 py-4 outline-none focus:border-cyan-500 transition-colors placeholder-transparent resize-none" placeholder="Message"></textarea>
                        <label for="message" class="absolute left-4 top-4 text-secondary-500 transition-all peer-focus:-top-2 peer-focus:left-2 peer-focus:bg-white dark:peer-focus:bg-gray-900 peer-focus:px-2 peer-focus:text-sm peer-focus:text-cyan-500 peer-not-placeholder-shown:-top-2 peer-not-placeholder-shown:left-2 peer-not-placeholder-shown:bg-white dark:peer-not-placeholder-shown:bg-gray-900 peer-not-placeholder-shown:px-2 peer-not-placeholder-shown:text-sm">Your Message</label>
                    </div>

                    <button type="submit" class="w-full gradient-border py-4 rounded-xl font-bold text-lg hover:scale-[1.02] transition-transform flex items-center justify-center gap-2 group">
                        <span>Send Message</span>
                        <i data-lucide="send" class="w-5 h-5 group-hover:translate-x-1 group-hover:-translate-y-1 transition-transform"></i>
                    </button>
                </form>

                <div class="mt-12 pt-8 border-t border-gray-200 dark:border-gray-700 flex flex-col md:flex-row justify-between items-center gap-6">
                    <div class="flex items-center gap-4">
                        <div class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-cyan-600">
                            <i data-lucide="mail" class="w-5 h-5"></i>
                        </div>
                        <div>
                            <p class="text-sm text-secondary-500">Email</p>
                            <a href="mailto:muhammadfirdous@protonmail.com" class="font-semibold hover:text-cyan-500 transition-colors">muhammadfirdous@protonmail.com</a>
                        </div>
                    </div>
                    
                    <div class="flex items-center gap-4">
                        <div class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-purple-600">
                            <i data-lucide="phone" class="w-5 h-5"></i>
                        </div>
                        <div>
                            <p class="text-sm text-secondary-500">Phone</p>
                            <a href="tel:+923345149503" class="font-semibold hover:text-purple-500 transition-colors">+92 334 5149503</a>
                        </div>
                    </div>

                    <div class="flex items-center gap-4">
                        <div class="neu-icon w-12 h-12 rounded-full flex items-center justify-center text-pink-600">
                            <i data-lucide="map-pin" class="w-5 h-5"></i>
                        </div>
                        <div>
                            <p class="text-sm text-secondary-500">Location</p>
                            <span class="font-semibold">Rawalpindi, Pakistan</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 px-4 border-t border-gray-200 dark:border-gray-800">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
            <div class="text-2xl font-bold font-display text-gradient">FIRDOUS.</div>
            <p class="text-secondary-500 text-sm">© 2025 Muhammad Firdous. All rights reserved.</p>
            <div class="flex gap-4">
                <a href="#" class="neu-icon w-10 h-10 rounded-full flex items-center justify-center text-secondary-600 hover:text-cyan-500 transition-colors">
                    <i data-lucide="linkedin" class="w-5 h-5"></i>
                </a>
                <a href="#" class="neu-icon w-10 h-10 rounded-full flex items-center justify-center text-secondary-600 hover:text-cyan-500 transition-colors">
                    <i data-lucide="twitter" class="w-5 h-5"></i>
                </a>
                <a href="#" class="neu-icon w-10 h-10 rounded-full flex items-center justify-center text-secondary-600 hover:text-cyan-500 transition-colors">
                    <i data-lucide="github" class="w-5 h-5"></i>
                </a>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Loader
        window.addEventListener('load', () => {
            setTimeout(() => {
                const loader = document.getElementById('loader');
                loader.style.opacity = '0';
                setTimeout(() => {
                    loader.style.display = 'none';
                    // Trigger reveal animations after loader
                    document.querySelectorAll('.reveal').forEach(el => el.classList.add('active'));
                }, 500);
            }, 2000);
        });

        // Dark Mode Toggle
        const themeToggle = document.getElementById('themeToggle');
        const html = document.documentElement;
        
        // Check local storage or system preference
        if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            html.classList.add('dark');
        } else {
            html.classList.remove('dark');
        }

        themeToggle.addEventListener('click', () => {
            html.classList.toggle('dark');
            if (html.classList.contains('dark')) {
                localStorage.theme = 'dark';
            } else {
                localStorage.theme = 'light';
            }
        });

        // Mobile Menu
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        
        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Custom Cursor
        const cursor = document.getElementById('cursor');
        let mouseX = 0, mouseY = 0;
        let cursorX = 0, cursorY = 0;

        document.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });

        function animateCursor() {
            cursorX += (mouseX - cursorX) * 0.1;
            cursorY += (mouseY - cursorY) * 0.1;
            cursor.style.left = cursorX - 10 + 'px';
            cursor.style.top = cursorY - 10 + 'px';
            requestAnimationFrame(animateCursor);
        }
        animateCursor();

        // Magnetic Effect
        document.querySelectorAll('.magnetic-btn').forEach(btn => {
            btn.addEventListener('mousemove', (e) => {
                const rect = btn.getBoundingClientRect();
                const x = e.clientX - rect.left - rect.width / 2;
                const y = e.clientY - rect.top - rect.height / 2;
                btn.style.transform = `translate(${x * 0.3}px, ${y * 0.3}px)`;
            });
            
            btn.addEventListener('mouseleave', () => {
                btn.style.transform = 'translate(0, 0)';
            });
        });

        // 3D Tilt Effect
        const heroCard = document.getElementById('heroCard');
        if (heroCard) {
            heroCard.addEventListener('mousemove', (e) => {
                const rect = heroCard.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateX = (y - centerY) / 20;
                const rotateY = (centerX - x) / 20;
                
                heroCard.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
            });
            
            heroCard.addEventListener('mouseleave', () => {
                heroCard.style.transform = 'perspective(1000px) rotateX(0) rotateY(0)';
            });
        }

        // Scroll Progress
        window.addEventListener('scroll', () => {
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            document.getElementById('scrollProgress').style.width = scrolled + '%';
            
            // Navbar background on scroll
            const navbar = document.getElementById('navbar');
            if (winScroll > 50) {
                navbar.classList.add('py-2');
                navbar.classList.remove('py-4');
            } else {
                navbar.classList.add('py-4');
                navbar.classList.remove('py-2');
            }
        });

        // Intersection Observer for Reveal Animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    
                    // Animate skill bars if present
                    const skillFills = entry.target.querySelectorAll('.skill-fill');
                    skillFills.forEach(fill => {
                        const width = fill.getAttribute('data-width');
                        fill.style.width = width;
                    });
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

        // Particle Background
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.speedY = Math.random() * 0.5 - 0.25;
                this.opacity = Math.random() * 0.5 + 0.1;
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
            }

            draw() {
                ctx.fillStyle = document.documentElement.classList.contains('dark') 
                    ? `rgba(6, 182, 212, ${this.opacity})` 
                    : `rgba(14, 165, 233, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particles = [];
            const particleCount = Math.min(window.innerWidth / 10, 100);
            for (let i = 0; i < particleCount; i++) {
                particles.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            
            // Draw connections
            particles.forEach((a, index) => {
                particles.slice(index + 1).forEach(b => {
                    const dx = a.x - b.x;
                    const dy = a.y - b.y;
                    const distance = Math.sqrt(dx * dx + dy * dy);
                    
                    if (distance < 150) {
                        ctx.strokeStyle = document.documentElement.classList.contains('dark')
                            ? `rgba(6, 182, 212, ${0.1 * (1 - distance / 150)})`
                            : `rgba(14, 165, 233, ${0.1 * (1 - distance / 150)})`;
                        ctx.lineWidth = 0.5;
                        ctx.beginPath();
                        ctx.moveTo(a.x, a.y);
                        ctx.lineTo(b.x, b.y);
                        ctx.stroke();
                    }
                });
            });
            
            requestAnimationFrame(animateParticles);
        }

        initParticles();
        animateParticles();

        // Form Handling
        document.getElementById('contactForm').addEventListener('submit', (e) => {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const originalContent = btn.innerHTML;
            
            btn.innerHTML = '<span class="animate-pulse">Sending...</span>';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.innerHTML = '<span class="flex items-center gap-2"><i data-lucide="check" class="w-5 h-5"></i> Message Sent!</span>';
                btn.classList.remove('gradient-border');
                btn.classList.add('bg-green-500', 'text-white');
                lucide.createIcons();
                
                setTimeout(() => {
                    btn.innerHTML = originalContent;
                    btn.disabled = false;
                    btn.classList.add('gradient-border');
                    btn.classList.remove('bg-green-500', 'text-white');
                    e.target.reset();
                    lucide.createIcons();
                }, 3000);
            }, 1500);
        });

        // Smooth Scroll for Anchor Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                    // Close mobile menu if open
                    mobileMenu.classList.add('hidden');
                }
            });
        });

        // Hover cursor effect
        document.querySelectorAll('a, button, .neu-icon').forEach(el => {
            el.addEventListener('mouseenter', () => cursor.classList.add('hovered'));
            el.addEventListener('mouseleave', () => cursor.classList.remove('hovered'));
        });

        // Parallax effect on scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallaxElements = document.querySelectorAll('.animate-blob');
            parallaxElements.forEach((el, index) => {
                const speed = 0.5 + (index * 0.1);
                el.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });

        // Typewriter effect for hero section
        const typewriterElement = document.getElementById('typewriter-text');
        if (typewriterElement) {
            const text = typewriterElement.textContent;
            typewriterElement.textContent = '';
            typewriterElement.style.borderRight = '2px solid var(--text-primary)';
            typewriterElement.style.animation = 'blink 0.7s infinite';
            
            let i = 0;
            const typeInterval = setInterval(() => {
                if (i < text.length) {
                    typewriterElement.textContent += text.charAt(i);
                    i++;
                } else {
                    clearInterval(typeInterval);
                    typewriterElement.style.borderRight = 'none';
                    typewriterElement.style.animation = 'none';
                }
            }, 30);
        }

        // Easter egg: Konami code
        let konamiCode = ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'b', 'a'];
        let konamiIndex = 0;
        
        document.addEventListener('keydown', (e) => {
            if (e.key === konamiCode[konamiIndex]) {
                konamiIndex++;
                if (konamiIndex === konamiCode.length) {
                    activateEasterEgg();
                    konamiIndex = 0;
                }
            } else {
                konamiIndex = 0;
            }
        });

        function activateEasterEgg() {
            document.body.style.animation = 'rainbow 2s linear infinite';
            const style = document.createElement('style');
            style.textContent = `
                @keyframes rainbow {
                    0% { filter: hue-rotate(0deg); }
                    100% { filter: hue-rotate(360deg); }
                }
            `;
            document.head.appendChild(style);
            
            setTimeout(() => {
                document.body.style.animation = '';
                style.remove();
            }, 5000);
            
            // Show toast notification
            const toast = document.createElement('div');
            toast.className = 'fixed top-24 right-4 glass px-6 py-4 rounded-xl z-50 transform translate-x-full transition-transform duration-500';
            toast.innerHTML = `
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-full bg-gradient-to-br from-yellow-400 to-orange-500 flex items-center justify-center text-white">
                        <i data-lucide="sparkles" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h4 class="font-bold">Easter Egg Found!</h4>
                        <p class="text-sm text-secondary-500">You discovered the Konami code!</p>
                    </div>
                </div>
            `;
            document.body.appendChild(toast);
            lucide.createIcons();
            
            setTimeout(() => toast.classList.remove('translate-x-full'), 100);
            setTimeout(() => {
                toast.classList.add('translate-x-full');
                setTimeout(() => toast.remove(), 500);
            }, 3000);
        }

        // Floating action button
        const fab = document.createElement('button');
        fab.className = 'fixed bottom-8 right-8 w-14 h-14 rounded-full bg-gradient-to-r from-cyan-500 to-purple-600 text-white shadow-lg hover:scale-110 transition-transform z-40 flex items-center justify-center';
        fab.innerHTML = '<i data-lucide="arrow-up" class="w-6 h-6"></i>';
        fab.onclick = () => window.scrollTo({ top: 0, behavior: 'smooth' });
        document.body.appendChild(fab);
        lucide.createIcons();

        // Show/hide FAB based on scroll
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 500) {
                fab.style.opacity = '1';
                fab.style.pointerEvents = 'auto';
            } else {
                fab.style.opacity = '0';
                fab.style.pointerEvents = 'none';
            }
        });

        // Sound toggle (visual only - no actual sound for autoplay policy compliance)
        const soundToggle = document.createElement('button');
        soundToggle.className = 'neu-icon fixed bottom-8 left-8 w-12 h-12 rounded-full flex items-center justify-center z-40 text-secondary-600';
        soundToggle.innerHTML = '<i data-lucide="volume-x" class="w-5 h-5"></i>';
        soundToggle.title = 'Sound effects (visual toggle)';
        let soundEnabled = false;
        
        soundToggle.addEventListener('click', () => {
            soundEnabled = !soundEnabled;
            soundToggle.innerHTML = soundEnabled ? 
                '<i data-lucide="volume-2" class="w-5 h-5 text-cyan-500"></i>' : 
                '<i data-lucide="volume-x" class="w-5 h-5"></i>';
            lucide.createIcons();
            
            // Visual feedback
            const indicator = document.createElement('div');
            indicator.className = 'fixed bottom-24 left-8 glass px-3 py-2 rounded-lg text-xs font-medium z-40';
            indicator.textContent = soundEnabled ? 'Sound ON' : 'Sound OFF';
            document.body.appendChild(indicator);
            setTimeout(() => indicator.remove(), 2000);
        });
        document.body.appendChild(soundToggle);
        lucide.createIcons();

        // Intersection Observer for timeline animations
        const timelineObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.2 });

        document.querySelectorAll('#experience .reveal').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.8s cubic-bezier(0.5, 0, 0, 1)';
            timelineObserver.observe(el);
        });

        // Skill cards stagger animation
        const skillCards = document.querySelectorAll('#skills .neu-flat');
        skillCards.forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            setTimeout(() => {
                card.style.transition = 'all 0.6s cubic-bezier(0.5, 0, 0, 1)';
                card.style.opacity = '1';
                card.style.transform = 'translateY(0)';
            }, index * 150);
        });

        // Counter animation for stats
        function animateCounter(element, target, duration = 2000) {
            let start = 0;
            const increment = target / (duration / 16);
            
            function updateCounter() {
                start += increment;
                if (start < target) {
                    element.textContent = Math.floor(start) + (element.textContent.includes('+') ? '+' : '');
                    requestAnimationFrame(updateCounter);
                } else {
                    element.textContent = target + (element.textContent.includes('+') ? '+' : '');
                }
            }
            updateCounter();
        }

        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting && !entry.target.classList.contains('counted')) {
                    entry.target.classList.add('counted');
                    const value = parseInt(entry.target.textContent);
                    animateCounter(entry.target, value);
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.text-gradient.text-2xl.font-bold').forEach(stat => {
            statsObserver.observe(stat);
        });

        // Project modal functionality (if projects are added later)
        function openProjectModal(projectData) {
            const modal = document.createElement('div');
            modal.className = 'fixed inset-0 z-50 flex items-center justify-center p-4';
            modal.innerHTML = `
                <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" onclick="this.parentElement.remove()"></div>
                <div class="glass rounded-3xl p-8 max-w-2xl w-full relative transform scale-95 opacity-0 transition-all duration-300">
                    <button onclick="this.closest('.fixed').remove()" class="absolute top-4 right-4 neu-icon w-10 h-10 rounded-full flex items-center justify-center">
                        <i data-lucide="x" class="w-5 h-5"></i>
                    </button>
                    <h3 class="text-2xl font-bold mb-4 font-display">${projectData.title}</h3>
                    <p class="text-secondary-600 dark:text-secondary-400 mb-6">${projectData.description}</p>
                    <div class="flex flex-wrap gap-2 mb-6">
                        ${projectData.tags.map(tag => `<span class="glass px-3 py-1 rounded-full text-sm">${tag}</span>`).join('')}
                    </div>
                    <a href="${projectData.link}" target="_blank" class="gradient-border px-6 py-3 rounded-xl font-semibold inline-flex items-center gap-2">
                        View Project <i data-lucide="external-link" class="w-4 h-4"></i>
                    </a>
                </div>
            `;
            document.body.appendChild(modal);
            lucide.createIcons();
            
            setTimeout(() => {
                modal.querySelector('.glass').classList.remove('scale-95', 'opacity-0');
            }, 10);
        }

        // Initialize all icons after dynamic content
        setTimeout(() => lucide.createIcons(), 100);

        // Performance optimization: Pause particles when tab is hidden
        document.addEventListener('visibilitychange', () => {
            if (document.hidden) {
                cancelAnimationFrame(animateParticles);
            } else {
                animateParticles();
            }
        });

        // Reduce motion for accessibility
        if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
            document.querySelectorAll('.animate-blob, .animate-float').forEach(el => {
                el.style.animation = 'none';
            });
        }

        console.log('%c🚀 Portfolio Loaded', 'color: #06b6d4; font-size: 20px; font-weight: bold;');
        console.log('%cWelcome to Muhammad Firdous\'s digital space.', 'color: #8b5cf6; font-size: 14px;');
        console.log('%cTry the Konami code: ↑↑↓↓←→←→BA', 'color: #ec4899; font-size: 12px;');
    </script>
</body>
</html>
