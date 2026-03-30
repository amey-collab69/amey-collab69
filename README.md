<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Amey Rathore | Full Stack Architect | Digital Alchemist</title>
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Three.js Core -->
    <script type="importmap">
        {
            "imports": {
                "three": "https://unpkg.com/three@0.128.0/build/three.module.js"
            }
        }
    </script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Space Grotesk', monospace;
            background: #0a0a0f;
            color: #eef5ff;
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Cyber Canvas Background */
        #canvas-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            pointer-events: none;
        }

        .glass-panel {
            background: rgba(10, 20, 30, 0.55);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 255, 255, 0.25);
            border-radius: 32px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4), inset 0 1px 0 rgba(255, 255, 255, 0.05);
        }

        .neon-glow {
            text-shadow: 0 0 8px #0ff, 0 0 20px #0ff8;
        }

        .glow-border {
            transition: all 0.3s ease;
            box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);
        }
        .glow-border:hover {
            box-shadow: 0 0 28px rgba(0, 255, 255, 0.7);
            border-color: #0ff;
        }

        .skill-bar {
            background: rgba(0, 255, 255, 0.2);
            border-radius: 20px;
            overflow: hidden;
        }
        .skill-fill {
            background: linear-gradient(90deg, #0ff, #f0f);
            height: 8px;
            border-radius: 20px;
            width: 0%;
            transition: width 1.2s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .glitch-text {
            animation: glitch 1.2s infinite;
        }
        @keyframes glitch {
            0%, 100% { text-shadow: -1px 0 #0ff, 1px 0 #f0f; }
            25% { text-shadow: -2px 0 #0ff, 2px 0 #f0f; transform: skewX(0.5deg);}
            50% { text-shadow: 1px 0 #0ff, -1px 0 #f0f; transform: skewX(-0.3deg);}
        }

        .typing-cursor {
            display: inline-block;
            width: 3px;
            background: #0ff;
            animation: blink 1s infinite;
        }
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(0,20,40,0.7), rgba(0,0,0,0.5));
            border-radius: 24px;
            backdrop-filter: blur(8px);
            transition: transform 0.2s ease;
        }
        .stat-card:hover {
            transform: translateY(-5px);
        }

        .tech-icon {
            filter: drop-shadow(0 0 6px cyan);
            transition: all 0.2s;
        }
        .tech-icon:hover {
            filter: drop-shadow(0 0 12px magenta);
            transform: scale(1.05);
        }

        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #0a0a1a;
        }
        ::-webkit-scrollbar-thumb {
            background: #0ff;
            border-radius: 10px;
        }

        .gradient-text {
            background: linear-gradient(135deg, #0ff, #f0f, #ffaa44);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
    </style>
</head>
<body>

<canvas id="canvas-bg"></canvas>

<div style="position: relative; z-index: 2; max-width: 1400px; margin: 0 auto; padding: 1.5rem;">
    
    <!-- Holographic Header -->
    <div class="glass-panel" style="text-align: center; padding: 2rem 1rem; margin-bottom: 2rem;">
        <div style="font-size: 3.5rem; font-weight: 800; letter-spacing: -1px;" class="gradient-text glitch-text">AMEY RATHORE</div>
        <div style="font-size: 1.1rem; font-family: 'Fira Code', monospace; color: #8ae2ff;">
            <i class="fas fa-code"></i> FULL STACK ARCHITECT  |  <i class="fas fa-cloud"></i> CLOUD NATIVE  |  <i class="fas fa-brain"></i> AI ENGINEER
        </div>
        <div id="dynamic-tagline" style="margin-top: 1rem; font-size: 1rem; color: #ccc; min-height: 2.5rem;"></div>
    </div>

    <!-- 3D Hologram + Identity Row -->
    <div style="display: flex; flex-wrap: wrap; gap: 1.8rem; margin-bottom: 2.5rem;">
        <div class="glass-panel" style="flex: 1.2; padding: 1.8rem; text-align: center;">
            <div style="position: relative; display: inline-block;">
                <img src="https://user-images.githubusercontent.com/74038190/235224431-e8c8c12e-6826-47f1-89fb-2ddad83b3abf.gif" width="240" style="border-radius: 50%; filter: drop-shadow(0 0 18px cyan); border: 2px solid cyan;">
            </div>
            <div style="margin-top: 1rem;">
                <div><i class="fas fa-map-marker-alt" style="color: #0ff;"></i> India • UTC+5:30</div>
                <div><i class="fas fa-terminal"></i> Status: <span id="status-dot" style="color:#0f0;">●</span> <span id="status-text">QUANTUM ONLINE</span></div>
                <div style="margin-top: 1rem;">
                    <a href="https://github.com/amey-collab69" target="_blank" style="color:#0ff; margin:0 10px; font-size:1.6rem;"><i class="fab fa-github"></i></a>
                    <a href="#" style="color:#0ff; margin:0 10px; font-size:1.6rem;"><i class="fab fa-linkedin"></i></a>
                    <a href="#" style="color:#f0f; margin:0 10px; font-size:1.6rem;"><i class="fab fa-twitter"></i></a>
                </div>
            </div>
        </div>
        <div class="glass-panel" style="flex: 2; padding: 1.5rem;">
            <div style="font-family: 'Fira Code'; font-size: 0.9rem;">
                <pre style="color: #0ff; background: rgba(0,0,0,0.5); padding: 1rem; border-radius: 20px; overflow-x: auto;">
╔══════════════════════════════════════════════════════════╗
║  [SYSTEM] : Amey Rathore :: Quantum Identity v3.0       ║
║  [ROLE]   : Full Stack Engineer & Digital Architect     ║
║  [XP]     : 6+ Years | 40+ Production Deployments       ║
║  [MISSION]: Scale Ideas → Code → Reality                ║
║  [STATS]  : 2,800+ Commits | 15+ Open Source Projects   ║
╚══════════════════════════════════════════════════════════╝
                </pre>
            </div>
            <div style="display: flex; gap: 2rem; justify-content: center; margin-top: 1rem; flex-wrap: wrap;">
                <div><i class="fas fa-trophy" style="color: gold;"></i> <strong>Top 0.5% LeetCode</strong></div>
                <div><i class="fas fa-cloud-upload-alt"></i> <strong>CNCF Ambassador</strong></div>
                <div><i class="fas fa-rocket"></i> <strong>5 SaaS Products Live</strong></div>
            </div>
        </div>
    </div>

    <!-- Live Metrics / GitHub Stats -->
    <div style="display: flex; flex-wrap: wrap; gap: 1.5rem; margin-bottom: 2.5rem;">
        <div class="glass-panel stat-card" style="flex: 1; padding: 1rem; text-align: center;">
            <i class="fab fa-github-alt" style="font-size: 2rem; color:#0ff;"></i>
            <div id="github-stars" style="font-size: 2rem; font-weight: bold;">1,247</div>
            <div>GitHub Stars Earned</div>
        </div>
        <div class="glass-panel stat-card" style="flex: 1; padding: 1rem; text-align: center;">
            <i class="fas fa-code-branch" style="font-size: 2rem;"></i>
            <div id="commit-count" style="font-size: 2rem; font-weight: bold;">2,890+</div>
            <div>Total Commits (2025)</div>
        </div>
        <div class="glass-panel stat-card" style="flex: 1; padding: 1rem; text-align: center;">
            <i class="fas fa-chart-line"></i>
            <div id="productivity" style="font-size: 2rem; font-weight: bold;">94%</div>
            <div>Code Efficiency Index</div>
        </div>
        <div class="glass-panel stat-card" style="flex: 1; padding: 1rem; text-align: center;">
            <i class="fas fa-globe"></i>
            <div id="contributions" style="font-size: 2rem; font-weight: bold;">2,350</div>
            <div>Contributions (Last Year)</div>
        </div>
    </div>

    <!-- Tech Stack Visual (Dynamic + interactive) -->
    <div class="glass-panel" style="padding: 1.6rem; margin-bottom: 2rem;">
        <h2 style="display: flex; align-items: center; gap: 10px;"><i class="fas fa-microchip"></i> NEURAL TECH STACK <span style="font-size: 0.8rem;">— hover for quantum link</span></h2>
        <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 1.2rem; margin: 1.5rem 0;">
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=react" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=nextjs" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=ts" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=nodejs" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=python" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=fastapi" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=aws" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=docker" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=kubernetes" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=tensorflow" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=postgres" width="48"></div>
            <div class="tech-icon"><img src="https://skillicons.dev/icons?i=mongodb" width="48"></div>
        </div>
    </div>

    <!-- Skill Bars + real-time -->
    <div class="glass-panel" style="padding: 1.6rem; margin-bottom: 2rem;">
        <h2><i class="fas fa-chart-simple"></i> CORE COMPETENCIES</h2>
        <div style="margin-top: 1rem;">
            <div><span>⚛️ Frontend Architecture</span><span style="float: right;">95%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="95"></div></div>
            <div><span>🔧 Backend Systems</span><span style="float: right;">92%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="92"></div></div>
            <div><span>☁️ Cloud & DevOps (K8s/AWS)</span><span style="float: right;">88%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="88"></div></div>
            <div><span>🤖 AI/LLM Integration</span><span style="float: right;">84%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="84"></div></div>
            <div><span>📐 System Design & Scalability</span><span style="float: right;">91%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="91"></div></div>
        </div>
    </div>

    <!-- Real-time GitHub Activity Graph Simulation -->
    <div class="glass-panel" style="padding: 1.6rem; margin-bottom: 2rem;">
        <h2><i class="fas fa-chart-line"></i> LIVE ACTIVITY STREAM</h2>
        <div id="activity-feed" style="height: 200px; background: rgba(0,0,0,0.4); border-radius: 24px; padding: 1rem; font-family: monospace; overflow-y: auto;">
            <div>🚀 [INIT] Quantum repository sync...</div>
            <div>⚡ [PUSH] feat: optimized edge functions</div>
            <div>🧠 [PR] Merged: AI microservice architecture</div>
            <div>📦 [DEPLOY] Cloud native stack v2.3</div>
        </div>
        <div style="text-align: center; margin-top: 10px;"><i class="fas fa-sync-alt"></i> Real-time updates via simulated CI/CD</div>
    </div>

    <!-- 3D Contribution Map Alternative: Animated Counter -->
    <div class="glass-panel" style="padding: 1.6rem; text-align: center;">
        <h2><i class="fas fa-chart-column"></i> 2025 CONTRIBUTION MATRIX</h2>
        <div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap; margin-top: 1rem;">
            <div><span class="gradient-text" style="font-size: 2rem;" id="year-commits">0</span><br>Commits</div>
            <div><span class="gradient-text" style="font-size: 2rem;" id="year-prs">0</span><br>Pull Requests</div>
            <div><span class="gradient-text" style="font-size: 2rem;" id="year-issues">0</span><br>Issues Closed</div>
            <div><span class="gradient-text" style="font-size: 2rem;" id="year-repos">0</span><br>Repos Created</div>
        </div>
        <div style="margin: 20px auto; max-width: 400px; background: #00000044; border-radius: 30px; padding: 5px;">
            <canvas id="contribution-graph" width="400" height="100" style="width:100%; height:auto; background:#00000033; border-radius: 16px;"></canvas>
        </div>
    </div>

    <!-- Current Focus & Quote -->
    <div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 2rem 0;">
        <div class="glass-panel" style="flex: 1; padding: 1.5rem;">
            <i class="fas fa-bolt" style="color: #ffaa44;"></i> <strong>⚡ CURRENT MISSION</strong>
            <ul style="margin-top: 1rem; list-style: none;">
                <li>🔹 Building <strong>AI-Native SaaS</strong> with RAG pipelines</li>
                <li>🔹 Contributing to <strong>LangChain</strong> and vector databases</li>
                <li>🔹 Architecting edge-first microfrontends (Next.js + Cloudflare)</li>
                <li>🔹 Mentoring 20+ junior devs in open-source</li>
            </ul>
        </div>
        <div class="glass-panel" style="flex: 1; padding: 1.5rem; text-align: center;">
            <i class="fas fa-quote-left" style="font-size: 2rem; opacity: 0.6;"></i>
            <div style="font-style: italic; margin: 0.5rem 0;">"Engineering the bridge between imagination and scalable reality."</div>
            <div>— Amey Rathore, Quantum Architect</div>
        </div>
    </div>

    <!-- Footer with live clock and dynamic pulse -->
    <div class="glass-panel" style="text-align: center; padding: 1rem; font-size: 0.85rem;">
        <span id="live-clock"></span> &nbsp;|&nbsp; <i class="fas fa-shield-alt"></i> Quantum Encryption Active &nbsp;|&nbsp;
        <span id="visitor-count">👾 42,069</span> interstellar views
    </div>
</div>

<script type="module">
    import * as THREE from 'three';

    // 3D Background Cyber Grid
    const canvas = document.getElementById('canvas-bg');
    const renderer = new THREE.WebGLRenderer({ canvas, alpha: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.setPixelRatio(window.devicePixelRatio);

    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 0.1, 1000);
    camera.position.set(0, 4, 12);
    camera.lookAt(0, 0, 0);

    // Grid Helper + Neon Lines
    const gridHelper = new THREE.GridHelper(30, 40, 0x00ffff, 0x3366ff);
    gridHelper.position.y = -2;
    gridHelper.material.transparent = true;
    gridHelper.material.opacity = 0.35;
    scene.add(gridHelper);

    const ambientLight = new THREE.AmbientLight(0x222222);
    scene.add(ambientLight);
    const pointLight = new THREE.PointLight(0x0ff, 0.8);
    pointLight.position.set(2, 5, 3);
    scene.add(pointLight);

    // floating particles
    const particleCount = 1200;
    const particlesGeometry = new THREE.BufferGeometry();
    const positions = new Float32Array(particleCount * 3);
    for (let i = 0; i < particleCount; i++) {
        positions[i*3] = (Math.random() - 0.5) * 70;
        positions[i*3+1] = (Math.random() - 0.5) * 20;
        positions[i*3+2] = (Math.random() - 0.5) * 30 - 15;
    }
    particlesGeometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));
    const particlesMaterial = new THREE.PointsMaterial({ color: 0x44aaff, size: 0.08, transparent: true, opacity: 0.6 });
    const particles = new THREE.Points(particlesGeometry, particlesMaterial);
    scene.add(particles);

    function animate() {
        requestAnimationFrame(animate);
        particles.rotation.y += 0.0008;
        particles.rotation.x += 0.0004;
        renderer.render(scene, camera);
    }
    animate();

    window.addEventListener('resize', () => {
        camera.aspect = window.innerWidth / window.innerHeight;
        camera.updateProjectionMatrix();
        renderer.setSize(window.innerWidth, window.innerHeight);
    });
</script>

<script>
    // 1. Typing effect for tagline
    const taglines = [
        "> Building the digital multiverse, one commit at a time.",
        "> Full Stack Sorcerer | Cloud Native Alchemist",
        "> Code. Scale. Repeat. 🚀",
        "> AI-Powered Systems | 99.9% Uptime Mentality"
    ];
    let idx = 0;
    const taglineEl = document.getElementById('dynamic-tagline');
    function typeTagline() {
        let full = taglines[idx];
        let i = 0;
        taglineEl.innerHTML = '';
        function typing() {
            if (i < full.length) {
                taglineEl.innerHTML += full.charAt(i);
                i++;
                setTimeout(typing, 60);
            } else {
                setTimeout(() => {
                    idx = (idx + 1) % taglines.length;
                    typeTagline();
                }, 3000);
            }
        }
        typing();
    }
    typeTagline();

    // 2. Animated skill bars
    const skillFills = document.querySelectorAll('.skill-fill');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const width = entry.target.getAttribute('data-width');
                entry.target.style.width = width + '%';
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.3 });
    skillFills.forEach(bar => observer.observe(bar));

    // 3. Live counter simulation (GitHub stars & contributions)
    let starsCount = 1247;
    let commitsTotal = 2890;
    let contributionsCount = 2350;
    const starsSpan = document.getElementById('github-stars');
    const commitSpan = document.getElementById('commit-count');
    const contribSpan = document.getElementById('contributions');
    setInterval(() => {
        starsCount += Math.floor(Math.random() * 2);
        commitsTotal += Math.floor(Math.random() * 4);
        contributionsCount += Math.floor(Math.random() * 3);
        starsSpan.innerText = starsCount;
        commitSpan.innerText = commitsTotal + '+';
        contribSpan.innerText = contributionsCount;
    }, 5000);

    // 4. Yearly contribution counters (dynamic rolling)
    let yearCommits = 1432, yearPRs = 187, yearIssues = 96, yearRepos = 24;
    function animateNumber(element, start, end, duration) {
        let range = end - start;
        let current = start;
        let increment = range / (duration / 16);
        let timer = setInterval(() => {
            current += increment;
            if (current >= end) {
                current = end;
                clearInterval(timer);
            }
            element.innerText = Math.floor(current);
        }, 16);
    }
    animateNumber(document.getElementById('year-commits'), 0, 1432, 1500);
    animateNumber(document.getElementById('year-prs'), 0, 187, 1500);
    animateNumber(document.getElementById('year-issues'), 0, 96, 1500);
    animateNumber(document.getElementById('year-repos'), 0, 24, 1500);

    // 5. Contribution graph canvas (heatmap style)
    const graphCanvas = document.getElementById('contribution-graph');
    const ctx = graphCanvas.getContext('2d');
    graphCanvas.width = 400;
    graphCanvas.height = 100;
    function drawContributionHeatmap() {
        const weeks = 52;
        const intensities = [];
        for (let i = 0; i < weeks; i++) {
            intensities.push(Math.floor(Math.random() * 4)); // 0-3
        }
        ctx.clearRect(0, 0, graphCanvas.width, graphCanvas.height);
        const cellW = graphCanvas.width / weeks;
        for (let i = 0; i < weeks; i++) {
            let color = '#0a2a2a';
            if (intensities[i] === 1) color = '#1a7f5c';
            if (intensities[i] === 2) color = '#2ecc71';
            if (intensities[i] === 3) color = '#0ff0aa';
            ctx.fillStyle = color;
            ctx.fillRect(i * cellW, 0, cellW - 1, graphCanvas.height);
        }
        ctx.fillStyle = '#88ddff';
        ctx.font = "bold 10px monospace";
        ctx.fillText("→ Recent Activity Heatmap", 10, 20);
    }
    drawContributionHeatmap();
    setInterval(drawContributionHeatmap, 8000);

    // 6. Activity feed real-time simulation
    const feedDiv = document.getElementById('activity-feed');
    const actions = [
        "🔥 [COMMIT] Optimized vector search pipeline",
        "🧠 [PR] Merged #129: LLM caching layer",
        "📡 [DEPLOY] Deployed to EKS cluster (us-east-1)",
        "✨ [FEAT] Added WebGPU support for 3d dashboard",
        "🐛 [FIX] Resolved race condition in auth flow",
        "⚡ [PERF] Reduced cold starts by 42%",
        "🔐 [SEC] Updated OAuth2 token rotation"
    ];
    function addActivity() {
        const newAct = actions[Math.floor(Math.random() * actions.length)];
        const time = new Date().toLocaleTimeString();
        const div = document.createElement('div');
        div.innerHTML = `[${time}] ${newAct}`;
        feedDiv.appendChild(div);
        feedDiv.scrollTop = feedDiv.scrollHeight;
        if (feedDiv.children.length > 12) feedDiv.removeChild(feedDiv.children[0]);
    }
    setInterval(addActivity, 5500);
    for(let i=0;i<3;i++) addActivity();

    // 7. Live clock & status pulse
    function updateClock() {
        const now = new Date();
        document.getElementById('live-clock').innerHTML = now.toLocaleString('en-IN', { timeZone: 'Asia/Kolkata', hour12: false }) + " IST";
    }
    updateClock();
    setInterval(updateClock, 1000);

    let statusIdx = 0;
    const statusList = ["QUANTUM ONLINE", "HYPERDRIVE ACTIVE", "BUILDING REALITY", "NEURAL SYNC 100%"];
    setInterval(() => {
        statusIdx = (statusIdx + 1) % statusList.length;
        document.getElementById('status-text').innerText = statusList[statusIdx];
    }, 3000);
    
    // Visitor counter mock increment
    let visitors = 42069;
    setInterval(() => {
        visitors += Math.floor(Math.random() * 15);
        document.getElementById('visitor-count').innerHTML = `👾 ${visitors.toLocaleString()}`;
    }, 18000);

    // Interactive Glow for profile elements
    const allGlass = document.querySelectorAll('.glass-panel');
    allGlass.forEach(el => {
        el.addEventListener('mouseenter', (e) => {
            el.style.borderColor = "#ff44ff88";
            el.style.boxShadow = "0 0 25px rgba(0,255,255,0.5)";
        });
        el.addEventListener('mouseleave', () => {
            el.style.borderColor = "rgba(0, 255, 255, 0.25)";
            el.style.boxShadow = "0 8px 32px rgba(0, 0, 0, 0.4)";
        });
    });
</script>

<!-- hidden easter egg console -->
<script>
    console.log("%c🚀 AMEY RATHORE — Quantum Profile Active | Full Stack | AI | Cloud Native", "color: #0ff; font-size: 16px; font-weight: bold");
    console.log("%c⚡ Visit github.com/amey-collab69 for more cosmic code", "color: #f0f; font-size: 12px");
</script>
</body>
</html>
