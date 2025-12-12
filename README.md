<!doctype html>
<html lang="en" class="h-full">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hack Creator - Matrix Portal | AmirAli Bafti</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="/_sdk/element_sdk.js"></script>
    <script src="/_sdk/data_sdk.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&amp;family=VT323&amp;family=Source+Code+Pro:wght@400;700&amp;display=swap" rel="stylesheet">
    <style>
        body {
            box-sizing: border-box;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
         :root {
            --primary-color: #ff0033;
            --secondary-color: #00ff00;
            --bg-color: #0a0000;
            --glow-color: #ff3355;
        }
        
        body {
            font-family: 'Orbitron', monospace;
            background: var(--bg-color);
            overflow-x: hidden;
            color: var(--primary-color);
        }
        /* 3D Matrix Grid Background */
        
        .matrix-grid-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background: linear-gradient(0deg, transparent 24%, rgba(255, 0, 51, 0.05) 25%, rgba(255, 0, 51, 0.05) 26%, transparent 27%, transparent 74%, rgba(255, 0, 51, 0.05) 75%, rgba(255, 0, 51, 0.05) 76%, transparent 77%, transparent), linear-gradient(90deg, transparent 24%, rgba(255, 0, 51, 0.05) 25%, rgba(255, 0, 51, 0.05) 26%, transparent 27%, transparent 74%, rgba(255, 0, 51, 0.05) 75%, rgba(255, 0, 51, 0.05) 76%, transparent 77%, transparent);
            background-size: 50px 50px;
            animation: gridMove 20s linear infinite;
        }
        
        @keyframes gridMove {
            0% {
                transform: perspective(1000px) rotateX(60deg) translateY(0);
            }
            100% {
                transform: perspective(1000px) rotateX(60deg) translateY(50px);
            }
        }
        /* Particles */
        
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }
        
        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: var(--primary-color);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--glow-color);
            animation: particleFloat linear infinite;
        }
        
        @keyframes particleFloat {
            0% {
                transform: translateY(100%) translateX(0) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) translateX(100px) scale(1);
                opacity: 0;
            }
        }
        /* Digital Rain */
        
        .digital-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }
        
        .rain-column {
            position: absolute;
            top: -100%;
            font-family: 'VT323', monospace;
            font-size: 20px;
            color: var(--secondary-color);
            text-shadow: 0 0 5px var(--secondary-color);
            opacity: 0.6;
            animation: rainFall linear infinite;
            white-space: nowrap;
        }
        
        @keyframes rainFall {
            to {
                top: 100%;
            }
        }
        /* Scanline Effect */
        
        .scanline {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, transparent 0%, rgba(255, 0, 51, 0.05) 50%, transparent 100%);
            background-size: 100% 4px;
            z-index: 2;
            pointer-events: none;
            animation: scanlineMove 8s linear infinite;
        }
        
        @keyframes scanlineMove {
            0% {
                background-position: 0 0;
            }
            100% {
                background-position: 0 100%;
            }
        }
        /* 3D Card Effect */
        
        .card-3d {
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
            transform: translateZ(0);
            background: rgba(10, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            border: 2px solid var(--primary-color);
            box-shadow: 0 0 20px rgba(255, 0, 51, 0.3);
        }
        
        .card-3d:hover {
            transform: translateZ(30px) rotateY(5deg) rotateX(3deg);
            box-shadow: 0 0 40px var(--primary-color);
        }
        /* Glitch Text */
        
        .glitch-text {
            position: relative;
            font-weight: 900;
            text-shadow: 0 0 10px var(--glow-color), 0 0 20px var(--glow-color), 0 0 30px var(--primary-color);
            animation: glitchAnim 3s infinite;
        }
        
        @keyframes glitchAnim {
            0%,
            90%,
            100% {
                transform: translate(0);
            }
            92% {
                transform: translate(-2px, 2px);
            }
            94% {
                transform: translate(2px, -2px);
            }
            96% {
                transform: translate(-2px, -2px);
            }
        }
        /* Neon Button */
        
        .neon-btn {
            position: relative;
            padding: 16px 40px;
            background: linear-gradient(135deg, #660011, var(--bg-color));
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 2px;
            overflow: hidden;
            transform: translateZ(0);
            transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
            box-shadow: 0 0 20px rgba(255, 0, 51, 0.5), inset 0 0 20px rgba(255, 0, 51, 0.1);
            cursor: pointer;
        }
        
        .neon-btn:hover {
            transform: translateZ(20px) translateY(-3px);
            box-shadow: 0 0 40px var(--primary-color), inset 0 0 30px rgba(255, 0, 51, 0.3);
            border-color: var(--glow-color);
            color: white;
            background: linear-gradient(135deg, var(--primary-color), #cc0028);
        }
        
        .neon-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }
        /* Cyber Border */
        
        .cyber-border {
            position: relative;
            border: 2px solid var(--primary-color);
            background: rgba(10, 0, 0, 0.8);
            backdrop-filter: blur(10px);
        }
        
        .cyber-border::before,
        .cyber-border::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            border: 2px solid var(--glow-color);
            animation: cornerPulse 2s infinite;
        }
        
        .cyber-border::before {
            top: -2px;
            left: -2px;
            border-right: none;
            border-bottom: none;
        }
        
        .cyber-border::after {
            bottom: -2px;
            right: -2px;
            border-left: none;
            border-top: none;
        }
        
        @keyframes cornerPulse {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0.3;
            }
        }
        /* Input Fields */
        
        input,
        textarea {
            background: rgba(0, 0, 0, 0.9) !important;
            border: 2px solid #660011 !important;
            color: var(--primary-color) !important;
            font-family: 'Source Code Pro', monospace !important;
            transition: all 0.3s !important;
            padding: 12px 16px !important;
            border-radius: 8px !important;
        }
        
        input:focus,
        textarea:focus {
            outline: none !important;
            border-color: var(--primary-color) !important;
            box-shadow: 0 0 20px rgba(255, 0, 51, 0.5) !important;
            animation: inputGlow 1.5s infinite !important;
        }
        
        @keyframes inputGlow {
            0%,
            100% {
                box-shadow: 0 0 20px rgba(255, 0, 51, 0.5);
            }
            50% {
                box-shadow: 0 0 40px rgba(255, 0, 51, 0.8), inset 0 0 10px rgba(255, 0, 51, 0.2);
            }
        }
        /* Modal */
        
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        .modal-content {
            background: rgba(10, 0, 0, 0.95);
            border: 2px solid var(--primary-color);
            border-radius: 20px;
            max-width: 90%;
            max-height: 90%;
            overflow-y: auto;
            box-shadow: 0 0 60px var(--primary-color);
            animation: modalSlide 0.4s cubic-bezier(0.23, 1, 0.32, 1);
        }
        
        @keyframes modalSlide {
            from {
                transform: translateY(-50px) scale(0.9);
                opacity: 0;
            }
            to {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
        }
        /* Theme Grid */
        
        .theme-item {
            cursor: pointer;
            transition: all 0.4s;
            border: 2px solid transparent;
        }
        
        .theme-item:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: var(--primary-color);
            box-shadow: 0 0 30px var(--primary-color);
        }
        /* Course Card */
        
        .course-card {
            transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
        }
        
        .course-card:hover {
            transform: translateY(-15px) translateZ(30px) rotateX(3deg);
        }
        /* Code Block */
        
        .code-block {
            background: rgba(0, 0, 0, 0.95);
            border: 2px solid var(--primary-color);
            border-radius: 12px;
            padding: 20px;
            font-family: 'Source Code Pro', monospace;
            color: var(--secondary-color);
            box-shadow: 0 0 30px rgba(255, 0, 51, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 0, 51, 0.2), transparent);
            animation: codeShine 3s infinite;
        }
        
        @keyframes codeShine {
            0% {
                left: -100%;
            }
            100% {
                left: 200%;
            }
        }
        /* Terminal Animation */
        
        .terminal-text {
            font-family: 'VT323', monospace;
            color: var(--secondary-color);
            font-size: 18px;
            line-height: 1.5;
        }
        
        .terminal-cursor {
            animation: cursorBlink 1s infinite;
        }
        
        @keyframes cursorBlink {
            0%,
            49% {
                opacity: 1;
            }
            50%,
            100% {
                opacity: 0;
            }
        }
        /* Scrollbar */
        
         ::-webkit-scrollbar {
            width: 12px;
        }
        
         ::-webkit-scrollbar-track {
            background: var(--bg-color);
            border-left: 2px solid #660011;
        }
        
         ::-webkit-scrollbar-thumb {
            background: linear-gradient(180deg, var(--primary-color), #cc0028);
            border-radius: 6px;
            box-shadow: 0 0 10px var(--glow-color);
        }
        
         ::-webkit-scrollbar-thumb:hover {
            background: var(--glow-color);
            box-shadow: 0 0 20px var(--glow-color);
        }
        /* Hidden */
        
        .hidden {
            display: none !important;
        }
        /* Navigation */
        
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 100;
            background: rgba(10, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid var(--primary-color);
            box-shadow: 0 0 30px rgba(255, 0, 51, 0.5);
        }
        /* Toast */
        
        .toast {
            position: fixed;
            top: 100px;
            right: 20px;
            background: rgba(10, 0, 0, 0.95);
            border: 2px solid var(--primary-color);
            padding: 20px 30px;
            border-radius: 10px;
            box-shadow: 0 0 40px rgba(255, 0, 51, 0.7);
            z-index: 10000;
            animation: toastSlide 0.5s ease-out;
            font-family: 'Source Code Pro', monospace;
        }
        
        @keyframes toastSlide {
            from {
                transform: translateX(400px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        /* Loading Spinner */
        
        .loader {
            border: 4px solid #660011;
            border-top: 4px solid var(--primary-color);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            display: inline-block;
        }
        
        @keyframes spin {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        /* AI Character */
        
        .ai-character {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--primary-color), #660011);
            animation: aiPulse 3s infinite, aiFloat 4s ease-in-out infinite;
            box-shadow: 0 0 60px var(--primary-color), inset 0 0 40px rgba(255, 0, 51, 0.5);
            position: relative;
        }
        
        @keyframes aiPulse {
            0%,
            100% {
                box-shadow: 0 0 60px var(--primary-color), inset 0 0 40px rgba(255, 0, 51, 0.5);
            }
            50% {
                box-shadow: 0 0 100px var(--glow-color), inset 0 0 60px rgba(255, 0, 51, 0.7);
            }
        }
        
        @keyframes aiFloat {
            0%,
            100% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-20px) rotate(180deg);
            }
        }
        /* Footer */
        
        footer {
            border-top: 2px solid var(--primary-color);
            background: rgba(10, 0, 0, 0.95);
            backdrop-filter: blur(10px);
        }
        /* Responsive */
        
        @media (max-width: 768px) {
            .glitch-text {
                font-size: 2rem;
            }
            .modal-content {
                max-width: 95%;
            }
        }
    </style>
    <style>
        @view-transition {
            navigation: auto;
        }
    </style>
</head>

<body class="h-full">
    <!-- Background Effects -->
    <div class="matrix-grid-bg"></div>
    <div class="particles" id="particles"></div>
    <div class="digital-rain" id="digitalRain"></div>
    <div class="scanline"></div>
    <!-- Main Content Wrapper -->
    <div class="main-wrapper relative z-10 w-full h-full overflow-auto">
        <!-- Navigation -->
        <nav class="py-4">
            <div class="app-container mx-auto px-6 max-w-7xl">
                <div class="flex justify-between items-center flex-wrap gap-4">
                    <div class="flex items-center gap-4">
                        <div class="text-4xl">
                            🔴
                        </div>
                        <div>
                            <h1 class="text-2xl font-bold glitch-text" id="siteNameDisplay">HACK CREATOR</h1>
                            <p class="text-xs" style="color: var(--glow-color); font-family: 'VT323', monospace;">MATRIX INITIALIZED</p>
                        </div>
                    </div>
                    <div class="flex gap-4 flex-wrap items-center"><button onclick="showPage('home')" class="nav-link text-sm md:text-base hover:text-white transition-all" style="font-family: 'Source Code Pro', monospace;">HOME</button> <button onclick="showPage('courses')" class="nav-link text-sm md:text-base hover:text-white transition-all"
                            style="font-family: 'Source Code Pro', monospace;">COURSES</button> <button onclick="showPage('python')" class="nav-link text-sm md:text-base hover:text-white transition-all" style="font-family: 'Source Code Pro', monospace;">PYTHON</button>                        <button onclick="showPage('ai')" class="nav-link text-sm md:text-base hover:text-white transition-all" style="font-family: 'Source Code Pro', monospace;">AI</button> <button onclick="openThemeChanger()" class="neon-btn text-xs md:text-sm rounded-lg py-2 px-4">THEMES</button>                        <button id="loginBtn" onclick="showPage('login')" class="neon-btn text-xs md:text-sm rounded-lg py-2 px-4">LOGIN</button> <button id="logoutBtn" onclick="handleLogout()" class="neon-btn text-xs md:text-sm rounded-lg py-2 px-4 hidden">LOGOUT</button>
                    </div>
                </div>
            </div>
        </nav>
        <!-- Home Page -->
        <section id="home" class="min-h-screen flex items-center justify-center px-6 py-24">
            <div class="text-center max-w-6xl mx-auto">
                <div class="mb-8">
                    <div class="text-8xl mb-4">
                        💻
                    </div>
                    <h1 class="text-5xl md:text-8xl font-black mb-6 glitch-text" id="heroTitleDisplay">CYBER HACKER &amp; AI DEVELOPER</h1>
                </div>
                <div class="card-3d cyber-border rounded-2xl p-8 mb-12 max-w-4xl mx-auto">
                    <div class="terminal-text mb-6">
                        <div>
                            &gt; Initializing Matrix Protocol...
                        </div>
                        <div>
                            &gt; Loading Cyber Systems...
                        </div>
                        <div>
                            &gt; Connection Established <span class="terminal-cursor">_</span>
                        </div>
                    </div>
                    <h2 class="text-3xl font-bold mb-4" style="color: var(--primary-color);" id="creatorNameDisplay">AMIRALI BAFTI</h2>
                    <p class="text-xl leading-relaxed" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Welcome to the ultimate cybersecurity and AI development hub. Explore cutting-edge hacking courses, Python automation tools, and intelligent AI systems.</p>
                </div>
                <div class="flex gap-6 justify-center flex-wrap mb-16"><button onclick="showPage('courses')" class="neon-btn rounded-lg text-base md:text-lg"> EXPLORE COURSES </button> <button onclick="showPage('login')" class="neon-btn rounded-lg text-base md:text-lg"> GET STARTED </button>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
                    <div class="card-3d cyber-border rounded-xl p-6">
                        <div class="text-5xl mb-4">
                            🎓
                        </div>
                        <h3 class="text-2xl font-bold mb-2" style="color: var(--primary-color);">500+</h3>
                        <p class="text-sm" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Premium Courses</p>
                    </div>
                    <div class="card-3d cyber-border rounded-xl p-6">
                        <div class="text-5xl mb-4">
                            🐍
                        </div>
                        <h3 class="text-2xl font-bold mb-2" style="color: var(--primary-color);">1000+</h3>
                        <p class="text-sm" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Python Scripts</p>
                    </div>
                    <div class="card-3d cyber-border rounded-xl p-6">
                        <div class="text-5xl mb-4">
                            🤖
                        </div>
                        <h3 class="text-2xl font-bold mb-2" style="color: var(--primary-color);">AI-Powered</h3>
                        <p class="text-sm" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Smart Automation</p>
                    </div>
                </div>
            </div>
        </section>
        <!-- Login/Register Page -->
        <section id="login" class="min-h-screen hidden px-6 py-24">
            <div class="app-container mx-auto max-w-6xl">
                <h2 class="text-4xl md:text-6xl font-black text-center mb-12 glitch-text">ACCESS PORTAL</h2>
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- Login Form -->
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <h3 class="text-3xl font-bold mb-6" style="color: var(--primary-color);">🔓 LOGIN</h3>
                        <form onsubmit="handleLogin(event)" class="space-y-6">
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">USERNAME / EMAIL</label> <input type="text" id="loginUsername" required class="w-full" placeholder="Enter username or email...">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">PASSWORD</label> <input type="password" id="loginPassword" required class="w-full" placeholder="Enter password...">
                            </div><button type="submit" id="loginSubmitBtn" class="neon-btn rounded-lg w-full"> AUTHENTICATE </button>
                        </form>
                        <div class="mt-6">
                            <div class="text-center mb-4" style="color: var(--glow-color);">
                                - OR LOGIN WITH -
                            </div>
                            <div class="flex gap-4 justify-center"><button onclick="showToast('Google OAuth integration available in full version')" class="card-3d rounded-lg p-4 flex-1"> <span class="text-3xl">🔴</span>
          <div class="text-sm mt-2">
           Google
          </div></button> <button onclick="showToast('GitHub OAuth integration available in full version')" class="card-3d rounded-lg p-4 flex-1"> <span class="text-3xl">🐙</span>
          <div class="text-sm mt-2">
           GitHub
          </div></button>
                            </div>
                        </div>
                    </div>
                    <!-- Register Form -->
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <h3 class="text-3xl font-bold mb-6" style="color: var(--primary-color);">✨ REGISTER</h3>
                        <form onsubmit="handleRegister(event)" class="space-y-4">
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">FULL NAME</label> <input type="text" id="regFullname" required class="w-full" placeholder="Your full name...">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">USERNAME</label> <input type="text" id="regUsername" required class="w-full" placeholder="Choose username...">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">EMAIL</label> <input type="email" id="regEmail" required class="w-full" placeholder="your@email.com">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">PHONE NUMBER</label> <input type="tel" id="regPhone" required class="w-full" placeholder="+1234567890">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">PASSWORD</label> <input type="password" id="regPassword" required class="w-full" placeholder="Strong password...">
                            </div>
                            <div><label class="block mb-2 font-bold" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">CONFIRM PASSWORD</label> <input type="password" id="regConfirmPassword" required class="w-full" placeholder="Re-enter password...">
                            </div><button type="submit" id="registerSubmitBtn" class="neon-btn rounded-lg w-full"> CREATE ACCOUNT </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
        <!-- Courses Page -->
        <section id="courses" class="min-h-screen hidden px-6 py-24">
            <div class="app-container mx-auto max-w-7xl">
                <h2 class="text-4xl md:text-6xl font-black text-center mb-12 glitch-text">🎓 HACKING &amp; CYBERSECURITY COURSES</h2>
                <div id="coursesContainer" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Courses will be dynamically generated -->
                </div>
            </div>
        </section>
        <!-- Python Applications Page -->
        <section id="python" class="min-h-screen hidden px-6 py-24">
            <div class="app-container mx-auto max-w-7xl">
                <h2 class="text-4xl md:text-6xl font-black text-center mb-12 glitch-text">🐍 PYTHON CYBERSECURITY TOOLS</h2>
                <div class="space-y-8">
                    <!-- Python Tool 1 -->
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <div class="flex items-center gap-4 mb-6">
                            <div class="text-5xl">
                                🔐
                            </div>
                            <div>
                                <h3 class="text-2xl font-bold" style="color: var(--primary-color);">Password Strength Checker</h3>
                                <p class="text-sm" style="color: var(--glow-color);">Analyze password security with entropy calculation</p>
                            </div>
                        </div>
                        <div class="code-block">
                            <pre class="text-sm overflow-x-auto"><code>import re
import math

def check_password_strength(password):
    score = 0
    feedback = []
    
    # Length check
    if len(password) &gt;= 12:
        score += 2
    elif len(password) &gt;= 8:
        score += 1
    else:
        feedback.append("Use at least 8 characters")
    
    # Character variety
    if re.search(r'[a-z]', password):
        score += 1
    if re.search(r'[A-Z]', password):
        score += 1
    if re.search(r'\d', password):
        score += 1
    if re.search(r'[!@#$%^&amp;*(),.?":{}|&lt;&gt;]', password):
        score += 2
    
    # Calculate entropy
    charset = 0
    if re.search(r'[a-z]', password): charset += 26
    if re.search(r'[A-Z]', password): charset += 26
    if re.search(r'\d', password): charset += 10
    if re.search(r'[^a-zA-Z0-9]', password): charset += 32
    
    entropy = len(password) * math.log2(charset) if charset else 0
    
    # Strength evaluation
    if score &lt;= 3:
        strength = "WEAK 🔴"
    elif score &lt;= 5:
        strength = "MODERATE 🟡"
    else:
        strength = "STRONG 🟢"
    
    return f"Strength: {strength} | Entropy: {entropy:.1f} bits"

# Example usage
print(check_password_strength("MyP@ssw0rd123!"))</code></pre>
                        </div>
                        <div class="flex gap-4 mt-6"><button onclick="copyCode(this)" class="neon-btn rounded-lg flex-1">📋 COPY CODE</button> <button onclick="showToast('Demo executed in browser console')" class="neon-btn rounded-lg flex-1">▶️ RUN DEMO</button>
                        </div>
                    </div>
                    <!-- Python Tool 2 -->
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <div class="flex items-center gap-4 mb-6">
                            <div class="text-5xl">
                                🕸️
                            </div>
                            <div>
                                <h3 class="text-2xl font-bold" style="color: var(--primary-color);">Port Scanner</h3>
                                <p class="text-sm" style="color: var(--glow-color);">Network reconnaissance tool for open ports</p>
                            </div>
                        </div>
                        <div class="code-block">
                            <pre class="text-sm overflow-x-auto"><code>import socket
from concurrent.futures import ThreadPoolExecutor

def scan_port(host, port):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(1)
        result = sock.connect_ex((host, port))
        sock.close()
        if result == 0:
            return port
    except:
        pass
    return None

def port_scanner(host, ports):
    print(f"🔍 Scanning {host}...")
    open_ports = []
    
    with ThreadPoolExecutor(max_workers=100) as executor:
        results = executor.map(lambda p: scan_port(host, p), ports)
        open_ports = [p for p in results if p is not None]
    
    if open_ports:
        print(f"✅ Open ports: {open_ports}")
    else:
        print("❌ No open ports found")
    
    return open_ports

# Example: Scan common ports
common_ports = [21, 22, 23, 25, 80, 443, 3306, 3389, 8080]
# port_scanner("127.0.0.1", common_ports)</code></pre>
                        </div>
                        <div class="flex gap-4 mt-6"><button onclick="copyCode(this)" class="neon-btn rounded-lg flex-1">📋 COPY CODE</button> <button onclick="showToast('Demo executed in browser console')" class="neon-btn rounded-lg flex-1">▶️ RUN DEMO</button>
                        </div>
                    </div>
                    <!-- Python Tool 3 -->
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <div class="flex items-center gap-4 mb-6">
                            <div class="text-5xl">
                                🔒
                            </div>
                            <div>
                                <h3 class="text-2xl font-bold" style="color: var(--primary-color);">File Encryption Tool</h3>
                                <p class="text-sm" style="color: var(--glow-color);">AES-256 file encryption with Fernet</p>
                            </div>
                        </div>
                        <div class="code-block">
                            <pre class="text-sm overflow-x-auto"><code>from cryptography.fernet import Fernet
import os

class FileEncryptor:
    def __init__(self):
        self.key = None
    
    def generate_key(self):
        """Generate encryption key"""
        self.key = Fernet.generate_key()
        with open('secret.key', 'wb') as key_file:
            key_file.write(self.key)
        return self.key
    
    def load_key(self):
        """Load encryption key"""
        return open('secret.key', 'rb').read()
    
    def encrypt_file(self, filename):
        """Encrypt a file"""
        key = self.load_key()
        fernet = Fernet(key)
        
        with open(filename, 'rb') as file:
            original = file.read()
        
        encrypted = fernet.encrypt(original)
        
        with open(filename + '.encrypted', 'wb') as encrypted_file:
            encrypted_file.write(encrypted)
        
        print(f"✅ File encrypted: {filename}.encrypted")
    
    def decrypt_file(self, filename):
        """Decrypt a file"""
        key = self.load_key()
        fernet = Fernet(key)
        
        with open(filename, 'rb') as encrypted_file:
            encrypted = encrypted_file.read()
        
        decrypted = fernet.decrypt(encrypted)
        
        with open(filename.replace('.encrypted', ''), 'wb') as file:
            file.write(decrypted)
        
        print(f"✅ File decrypted successfully")

# Usage
# encryptor = FileEncryptor()
# encryptor.generate_key()
# encryptor.encrypt_file('secret.txt')</code></pre>
                        </div>
                        <div class="flex gap-4 mt-6"><button onclick="copyCode(this)" class="neon-btn rounded-lg flex-1">📋 COPY CODE</button> <button onclick="showToast('Demo executed in browser console')" class="neon-btn rounded-lg flex-1">▶️ RUN DEMO</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <!-- AI Intelligence Page -->
        <section id="ai" class="min-h-screen hidden px-6 py-24">
            <div class="app-container mx-auto max-w-7xl">
                <h2 class="text-4xl md:text-6xl font-black text-center mb-12 glitch-text">🤖 AI INTELLIGENCE CENTER</h2>
                <div class="grid md:grid-cols-2 gap-12 items-center mb-16">
                    <div>
                        <div class="ai-character mx-auto mb-8 flex items-center justify-center text-8xl">
                            🧠
                        </div>
                    </div>
                    <div class="card-3d cyber-border rounded-2xl p-8">
                        <h3 class="text-3xl font-bold mb-6" style="color: var(--primary-color);">Intelligent Code Designer</h3>
                        <div class="space-y-4 terminal-text">
                            <div>
                                &gt; AI System: ONLINE
                            </div>
                            <div>
                                &gt; Neural Network: ACTIVE
                            </div>
                            <div>
                                &gt; Learning Rate: 99.7%
                            </div>
                            <div>
                                &gt; Capabilities: UNLIMITED
                            </div>
                        </div>
                        <p class="text-lg mt-6 leading-relaxed" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Our advanced AI system assists in code generation, vulnerability detection, and automated pentesting. Leveraging deep learning algorithms to predict security threats before they happen.</p>
                    </div>
                </div>
                <div class="grid md:grid-cols-3 gap-8 mb-16">
                    <div class="card-3d cyber-border rounded-xl p-6 text-center">
                        <div class="text-5xl mb-4">
                            ⚡
                        </div>
                        <h3 class="text-xl font-bold mb-3" style="color: var(--primary-color);">Auto Code Generation</h3>
                        <p class="text-sm" style="color: var(--glow-color);">AI generates optimized exploit code in seconds</p>
                    </div>
                    <div class="card-3d cyber-border rounded-xl p-6 text-center">
                        <div class="text-5xl mb-4">
                            🛡️
                        </div>
                        <h3 class="text-xl font-bold mb-3" style="color: var(--primary-color);">Vulnerability Analysis</h3>
                        <p class="text-sm" style="color: var(--glow-color);">Deep learning models detect zero-day exploits</p>
                    </div>
                    <div class="card-3d cyber-border rounded-xl p-6 text-center">
                        <div class="text-5xl mb-4">
                            🎯
                        </div>
                        <h3 class="text-xl font-bold mb-3" style="color: var(--primary-color);">Smart Automation</h3>
                        <p class="text-sm" style="color: var(--glow-color);">Automated pentesting with AI decision-making</p>
                    </div>
                </div>
                <div class="card-3d cyber-border rounded-2xl p-8">
                    <h3 class="text-2xl font-bold mb-6" style="color: var(--primary-color);">🗨️ AI Chat Interface</h3>
                    <div class="space-y-4 mb-6">
                        <div class="flex gap-4">
                            <div class="text-3xl">
                                👤
                            </div>
                            <div class="flex-1 card-3d rounded-lg p-4">
                                <p style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Can you help me write a SQL injection test script?</p>
                            </div>
                        </div>
                        <div class="flex gap-4">
                            <div class="text-3xl">
                                🤖
                            </div>
                            <div class="flex-1 card-3d rounded-lg p-4">
                                <p style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Certainly! I'll create a secure SQL injection testing script for authorized penetration testing. This script includes payload generation, injection detection, and result parsing...</p>
                                <div class="code-block mt-4 text-xs">
                                    <pre><code>import requests

payloads = ["' OR '1'='1", "' OR '1'='1' --", "admin'--"]
target_url = "http://example.com/login"

for payload in payloads:
    data = {"username": payload, "password": "test"}
    response = requests.post(target_url, data=data)
    if "Welcome" in response.text:
        print(f"✅ Vulnerable to: {payload}")</code></pre>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="flex gap-4"><input type="text" placeholder="Ask AI anything about cybersecurity..." class="flex-1" id="aiInput"> <button onclick="handleAIChat()" class="neon-btn rounded-lg px-8">SEND</button>
                    </div>
                </div>
            </div>
        </section>
        <!-- Footer -->
        <footer class="py-12 px-6 relative z-10">
            <div class="app-container mx-auto max-w-7xl">
                <div class="grid md:grid-cols-4 gap-8 mb-8">
                    <div>
                        <h3 class="text-2xl font-bold mb-4 glitch-text">HACK CREATOR</h3>
                        <p class="text-sm" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Elite cybersecurity training platform powered by AI</p>
                    </div>
                    <div>
                        <h4 class="text-lg font-bold mb-4" style="color: var(--primary-color);">QUICK LINKS</h4>
                        <div class="space-y-2">
                            <div>
                                <button onclick="showPage('home')" class="text-sm hover:text-white transition-all" style="color: var(--glow-color);">Home</button>
                            </div>
                            <div>
                                <button onclick="showPage('courses')" class="text-sm hover:text-white transition-all" style="color: var(--glow-color);">Courses</button>
                            </div>
                            <div>
                                <button onclick="showPage('python')" class="text-sm hover:text-white transition-all" style="color: var(--glow-color);">Python Tools</button>
                            </div>
                            <div>
                                <button onclick="showPage('ai')" class="text-sm hover:text-white transition-all" style="color: var(--glow-color);">AI Systems</button>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h4 class="text-lg font-bold mb-4" style="color: var(--primary-color);">CONTACT</h4>
                        <div class="space-y-2 text-sm" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">
                            <div>
                                📧 <span id="contactEmailDisplay">contact@hackcreator.com</span>
                            </div>
                            <div>
                                📍 Cyberspace, Digital Realm
                            </div>
                            <div>
                                ⏰ 24/7 Available
                            </div>
                        </div>
                    </div>
                    <div>
                        <h4 class="text-lg font-bold mb-4" style="color: var(--primary-color);">SOCIAL</h4>
                        <div class="flex gap-3"><button class="card-3d rounded-lg p-3 hover:scale-110 transition-all">💼</button> <button class="card-3d rounded-lg p-3 hover:scale-110 transition-all">🐙</button> <button class="card-3d rounded-lg p-3 hover:scale-110 transition-all">🐦</button>                            <button class="card-3d rounded-lg p-3 hover:scale-110 transition-all">📸</button>
                        </div>
                    </div>
                </div>
                <div class="border-t-2 pt-8" style="border-color: var(--primary-color);">
                    <div class="flex flex-col md:flex-row justify-between items-center gap-4">
                        <p style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">© 2025 <span id="footerCreatorName">AmirAli Bafti</span>. All Rights Reserved.</p>
                        <div class="flex gap-6 text-sm"><button onclick="showToast('Privacy Policy page')" class="hover:text-white transition-all" style="color: var(--glow-color);">Privacy Policy</button> <button onclick="showToast('Terms of Service page')" class="hover:text-white transition-all"
                                style="color: var(--glow-color);">Terms of Service</button>
                        </div>
                    </div>
                </div>
            </div>
        </footer>
    </div>
    <!-- Theme Changer Modal -->
    <div id="themeModal" class="modal-overlay hidden">
        <div class="modal-content p-8" style="width: 90%; max-width: 1200px;">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-4xl font-black glitch-text">🎨 THEME SELECTOR</h2><button onclick="closeThemeChanger()" class="text-4xl hover:scale-125 transition-all" style="color: var(--primary-color);">✕</button>
            </div>
            <p class="text-center mb-8" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">Choose from over 500 cyberpunk Matrix themes</p>
            <div id="themesGrid" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4 max-h-[60vh] overflow-y-auto">
                <!-- Themes will be generated dynamically -->
            </div>
        </div>
    </div>
    <script>
        // Configuration
        const defaultConfig = {
            site_name: "HACK CREATOR",
            creator_name: "AmirAli Bafti",
            hero_title: "CYBER HACKER & AI DEVELOPER",
            contact_email: "contact@hackcreator.com"
        };

        let currentUser = null;
        let allUsers = [];

        // Initialize Data SDK
        const dataHandler = {
            onDataChanged(data) {
                allUsers = data;
                checkLoginStatus();
            }
        };

        async function initDataSdk() {
            if (window.dataSdk) {
                const result = await window.dataSdk.init(dataHandler);
                if (!result.isOk) {
                    console.error("Failed to initialize Data SDK");
                }
            }
        }

        // Check Login Status
        function checkLoginStatus() {
            const loggedInUser = allUsers.find(user => user.is_logged_in);
            if (loggedInUser) {
                currentUser = loggedInUser;
                document.getElementById('loginBtn').classList.add('hidden');
                document.getElementById('logoutBtn').classList.remove('hidden');
            } else {
                currentUser = null;
                document.getElementById('loginBtn').classList.remove('hidden');
                document.getElementById('logoutBtn').classList.add('hidden');
            }
        }

        // Handle Login
        async function handleLogin(e) {
            e.preventDefault();

            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            const submitBtn = document.getElementById('loginSubmitBtn');

            submitBtn.disabled = true;
            submitBtn.innerHTML = '<div class="loader"></div>';

            const user = allUsers.find(u =>
                (u.username === username || u.email === username) && u.password === password
            );

            if (user) {
                const updatedUser = {...user,
                    is_logged_in: true
                };
                const result = await window.dataSdk.update(updatedUser);

                if (result.isOk) {
                    showToast('✅ LOGIN SUCCESSFUL');
                    showPage('home');
                    e.target.reset();
                } else {
                    showToast('❌ Login failed. Please try again.');
                }
            } else {
                showToast('❌ Invalid credentials');
            }

            submitBtn.disabled = false;
            submitBtn.textContent = 'AUTHENTICATE';
        }

        // Handle Register
        async function handleRegister(e) {
            e.preventDefault();

            const fullname = document.getElementById('regFullname').value;
            const username = document.getElementById('regUsername').value;
            const email = document.getElementById('regEmail').value;
            const phone = document.getElementById('regPhone').value;
            const password = document.getElementById('regPassword').value;
            const confirmPassword = document.getElementById('regConfirmPassword').value;
            const submitBtn = document.getElementById('registerSubmitBtn');

            if (password !== confirmPassword) {
                showToast('❌ Passwords do not match');
                return;
            }

            if (password.length < 8) {
                showToast('❌ Password must be at least 8 characters');
                return;
            }

            const existingUser = allUsers.find(u => u.username === username || u.email === email);
            if (existingUser) {
                showToast('❌ Username or email already exists');
                return;
            }

            if (allUsers.length >= 999) {
                showToast('❌ Maximum user limit reached (999 users)');
                return;
            }

            submitBtn.disabled = true;
            submitBtn.innerHTML = '<div class="loader"></div>';

            const newUser = {
                username,
                email,
                fullname,
                phone,
                password,
                registered_at: new Date().toISOString(),
                is_logged_in: false
            };

            const result = await window.dataSdk.create(newUser);

            if (result.isOk) {
                showToast('✅ ACCOUNT CREATED SUCCESSFULLY');
                e.target.reset();
                setTimeout(() => {
                    document.getElementById('loginUsername').value = username;
                }, 500);
            } else {
                showToast('❌ Registration failed. Please try again.');
            }

            submitBtn.disabled = false;
            submitBtn.textContent = 'CREATE ACCOUNT';
        }

        // Handle Logout
        async function handleLogout() {
            if (!currentUser) return;

            const updatedUser = {...currentUser,
                is_logged_in: false
            };
            const result = await window.dataSdk.update(updatedUser);

            if (result.isOk) {
                showToast('✅ LOGGED OUT SUCCESSFULLY');
                showPage('home');
            }
        }

        // Show Page
        function showPage(pageId) {
            const pages = ['home', 'login', 'courses', 'python', 'ai'];
            pages.forEach(id => {
                const page = document.getElementById(id);
                if (id === pageId) {
                    page.classList.remove('hidden');
                } else {
                    page.classList.add('hidden');
                }
            });
            window.scrollTo(0, 0);
        }

        // Generate Courses
        function generateCourses() {
            const container = document.getElementById('coursesContainer');
            const courses = [{
                title: "Ethical Hacking Masterclass",
                desc: "Complete A-Z ethical hacking course with hands-on labs",
                price: "$199",
                emoji: "🎯"
            }, {
                title: "Python for Hackers",
                desc: "Advanced Python scripting for penetration testing",
                price: "$149",
                emoji: "🐍"
            }, {
                title: "Network Security & Defense",
                desc: "Master network security protocols and defense strategies",
                price: "$179",
                emoji: "🛡️"
            }, {
                title: "Web Application Pentesting",
                desc: "OWASP Top 10 vulnerabilities and exploitation techniques",
                price: "$169",
                emoji: "🌐"
            }, {
                title: "Malware Analysis & Reverse Engineering",
                desc: "Deep dive into malware behavior and reverse engineering",
                price: "$249",
                emoji: "🔬"
            }, {
                title: "Cryptography & Encryption",
                desc: "Modern cryptographic algorithms and implementation",
                price: "$159",
                emoji: "🔐"
            }, {
                title: "Cloud Security (AWS/Azure)",
                desc: "Secure cloud infrastructure and penetration testing",
                price: "$189",
                emoji: "☁️"
            }, {
                title: "Mobile App Security",
                desc: "iOS and Android application security testing",
                price: "$169",
                emoji: "📱"
            }, {
                title: "Social Engineering",
                desc: "Psychological manipulation techniques for security testing",
                price: "$139",
                emoji: "🎭"
            }, {
                title: "Wireless Network Hacking",
                desc: "WiFi security auditing and exploitation",
                price: "$149",
                emoji: "📡"
            }, {
                title: "Advanced SQL Injection",
                desc: "Master database exploitation techniques",
                price: "$159",
                emoji: "💉"
            }, {
                title: "Zero-Day Exploit Development",
                desc: "Discover and develop zero-day vulnerabilities",
                price: "$299",
                emoji: "⚡"
            }];

            container.innerHTML = courses.map(course => `
        <div class="card-3d course-card cyber-border rounded-2xl p-6">
          <div class="text-6xl mb-4 text-center">${course.emoji}</div>
          <h3 class="text-xl font-bold mb-3" style="color: var(--primary-color);">${course.title}</h3>
          <p class="text-sm mb-6" style="color: var(--glow-color); font-family: 'Source Code Pro', monospace;">
            ${course.desc}
          </p>
          <div class="flex justify-between items-center mb-6">
            <span class="text-2xl font-bold" style="color: var(--primary-color);">${course.price}</span>
            <span class="text-sm" style="color: var(--glow-color);">⭐ 4.9/5</span>
          </div>
          <button onclick="handleBuyCourse('${course.title}')" class="neon-btn rounded-lg w-full">
            BUY COURSE
          </button>
        </div>
      `).join('');
        }

        // Handle Buy Course
        function handleBuyCourse(courseTitle) {
            if (!currentUser) {
                showToast('⚠️ Please login to purchase courses');
                showPage('login');
            } else {
                showToast(`🎓 Course "${courseTitle}" added to cart!`);
            }
        }

        // Generate Theme Palette
        function generateThemes() {
            const container = document.getElementById('themesGrid');
            const themes = [];

            const baseColors = [
                '#ff0033', '#00ff00', '#0099ff', '#ff00ff', '#ffff00', '#00ffff',
                '#ff6600', '#9900ff', '#00ff99', '#ff0099', '#99ff00', '#0066ff'
            ];

            for (let i = 0; i < 500; i++) {
                const primary = baseColors[Math.floor(Math.random() * baseColors.length)];
                const secondary = baseColors[Math.floor(Math.random() * baseColors.length)];
                const bg = `#${Math.floor(Math.random()*16777215).toString(16).padStart(6, '0')}`;

                themes.push({
                    primary,
                    secondary,
                    bg
                });
            }

            container.innerHTML = themes.map((theme, index) => `
        <div class="theme-item card-3d rounded-lg p-4 cursor-pointer" onclick="applyTheme('${theme.primary}', '${theme.secondary}', '${theme.bg}')">
          <div class="h-20 rounded-lg mb-2" style="background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary});"></div>
          <div class="text-center text-xs" style="color: var(--glow-color);">Theme ${index + 1}</div>
        </div>
      `).join('');
        }

        // Apply Theme
        function applyTheme(primary, secondary, bg) {
            document.documentElement.style.setProperty('--primary-color', primary);
            document.documentElement.style.setProperty('--secondary-color', secondary);
            document.documentElement.style.setProperty('--bg-color', bg);
            document.documentElement.style.setProperty('--glow-color', primary + 'aa');

            showToast('✅ THEME APPLIED');
            closeThemeChanger();
        }

        // Open Theme Changer
        function openThemeChanger() {
            document.getElementById('themeModal').classList.remove('hidden');
            generateThemes();
        }

        // Close Theme Changer
        function closeThemeChanger() {
            document.getElementById('themeModal').classList.add('hidden');
        }

        // Create Particles
        function createParticles() {
            const container = document.getElementById('particles');
            container.innerHTML = '';
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDuration = (Math.random() * 3 + 2) + 's';
                particle.style.animationDelay = Math.random() * 2 + 's';
                container.appendChild(particle);
            }
        }

        // Create Digital Rain
        function createDigitalRain() {
            const container = document.getElementById('digitalRain');
            container.innerHTML = '';
            const columns = Math.floor(window.innerWidth / 30);

            for (let i = 0; i < columns; i++) {
                const column = document.createElement('div');
                column.className = 'rain-column';
                column.style.left = (i * 30) + 'px';
                column.style.animationDuration = (Math.random() * 2 + 3) + 's';
                column.style.animationDelay = Math.random() * 2 + 's';

                const chars = '01ハミヒフヘホマミムメモヤユヨラリルレロワヲン';
                let text = '';
                for (let j = 0; j < 20; j++) {
                    text += chars[Math.floor(Math.random() * chars.length)] + '<br>';
                }
                column.innerHTML = text;
                container.appendChild(column);
            }
        }

        // Toast Notification
        function showToast(message) {
            const toast = document.createElement('div');
            toast.className = 'toast';
            toast.innerHTML = `<div style="color: var(--primary-color); font-weight: bold;">${message}</div>`;
            document.body.appendChild(toast);
            setTimeout(() => toast.remove(), 3000);
        }

        // Copy Code
        function copyCode(button) {
            const codeBlock = button.parentElement.previousElementSibling;
            const code = codeBlock.querySelector('code').textContent;

            navigator.clipboard.writeText(code).then(() => {
                showToast('✅ CODE COPIED TO CLIPBOARD');
            });
        }

        // Handle AI Chat
        function handleAIChat() {
            const input = document.getElementById('aiInput');
            const message = input.value.trim();

            if (message) {
                showToast('🤖 AI processing your request...');
                input.value = '';
            }
        }

        // Element SDK Integration
        async function onConfigChange(config) {
            document.getElementById('siteNameDisplay').textContent = (config.site_name || defaultConfig.site_name).toUpperCase();
            document.getElementById('creatorNameDisplay').textContent = (config.creator_name || defaultConfig.creator_name).toUpperCase();
            document.getElementById('heroTitleDisplay').textContent = (config.hero_title || defaultConfig.hero_title).toUpperCase();
            document.getElementById('contactEmailDisplay').textContent = config.contact_email || defaultConfig.contact_email;
            document.getElementById('footerCreatorName').textContent = config.creator_name || defaultConfig.creator_name;
        }

        // Initialize
        async function init() {
            createParticles();
            createDigitalRain();
            generateCourses();

            window.addEventListener('resize', () => {
                createDigitalRain();
            });

            await initDataSdk();

            if (window.elementSdk) {
                window.elementSdk.init({
                    defaultConfig,
                    onConfigChange,
                    mapToCapabilities: (config) => ({
                        recolorables: [],
                        borderables: [],
                        fontEditable: undefined,
                        fontSizeable: undefined
                    }),
                    mapToEditPanelValues: (config) => new Map([
                        ['site_name', config.site_name || defaultConfig.site_name],
                        ['creator_name', config.creator_name || defaultConfig.creator_name],
                        ['hero_title', config.hero_title || defaultConfig.hero_title],
                        ['contact_email', config.contact_email || defaultConfig.contact_email]
                    ])
                });
            }
        }

        init();
    </script>
    <script>
        (function() {
            function c() {
                var b = a.contentDocument || a.contentWindow.document;
                if (b) {
                    var d = b.createElement('script');
                    d.innerHTML = "window.__CF$cv$params={r:'9abf1c36c39968ec',t:'MTc2NTM5NDUzOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";
                    b.getElementsByTagName('head')[0].appendChild(d)
                }
            }
            if (document.body) {
                var a = document.createElement('iframe');
                a.height = 1;
                a.width = 1;
                a.style.position = 'absolute';
                a.style.top = 0;
                a.style.left = 0;
                a.style.border = 'none';
                a.style.visibility = 'hidden';
                document.body.appendChild(a);
                if ('loading' !== document.readyState) c();
                else if (window.addEventListener) document.addEventListener('DOMContentLoaded', c);
                else {
                    var e = document.onreadystatechange || function() {};
                    document.onreadystatechange = function(b) {
                        e(b);
                        'loading' !== document.readyState && (document.onreadystatechange = e, c())
                    }
                }
            }
        })();
    </script>
</body>

</html>
