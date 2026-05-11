
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Understanding Time Dilation</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f4f7f6;
        }
        header {
            text-align: center;
            padding: 40px 0;
            background: #2c3e50;
            color: white;
            border-radius: 8px;
            margin-bottom: 30px;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h2 { color: #2c3e50; border-bottom: 2px solid #3498db; padding-bottom: 10px; }
        
        /* Experiment Visuals */
        .experiment-box {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin: 30px 0;
            background: #eee;
            padding: 20px;
            border-radius: 10px;
        }
        .clock-canvas {
            text-align: center;
            background: #fff;
            padding: 15px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .math-box {
            background: #e8f4fd;
            padding: 20px;
            border-left: 5px solid #3498db;
            margin: 20px 0;
            font-family: serif;
            font-size: 1.2rem;
        }
        footer {
            text-align: center;
            margin-top: 50px;
            font-size: 0.9rem;
            color: #7f8c8d;
        }
    </style>
</head>
<body>

<header>
    <h1>Time is Relative</h1>
    <p>A Student's Guide to the Light Clock Experiment</p>
</header>

<div class="container">
    <h2>1. The Concept</h2>
    <p>
        According to Einstein's Special Relativity, time isn't a constant "tick-tock" for everyone in the universe. Instead, <strong>the faster you move through space, the slower you move through time.</strong> This isn't just a trick of the mind; it's a fundamental property of the universe.
    </p>

    

    <h2>2. The Light Clock Experiment</h2>
    <p>
        Imagine a clock made of two mirrors and a single photon (a particle of light) bouncing between them. One "tick" is the time it takes for the light to go up and back down.
    </p>

    <div class="experiment-box">
        <div class="clock-canvas">
            <h3>Stationary Observer</h3>
            <p>The photon moves straight up and down.</p>
            <svg width="100" height="200">
                <rect x="10" y="10" width="80" height="5" fill="#333"/>
                <rect x="10" y="185" width="80" height="5" fill="#333"/>
                <line x1="50" y1="15" x2="50" y2="185" stroke="#3498db" stroke-width="2" stroke-dasharray="5,5" />
                <circle cx="50" cy="100" r="5" fill="gold">
                    <animate attributeName="cy" values="20;180;20" dur="2s" repeatCount="indefinite" />
                </circle>
            </svg>
        </div>

        <div class="clock-canvas">
            <h3>Moving Observer</h3>
            <p>The photon must travel a longer, diagonal path.</p>
            <svg width="200" height="200">
                <rect x="10" y="10" width="180" height="5" fill="#333"/>
                <rect x="10" y="185" width="180" height="5" fill="#333"/>
                <path d="M 20 180 L 100 20 L 180 180" fill="transparent" stroke="#e74c3c" stroke-width="2" stroke-dasharray="5,5" />
                <circle r="5" fill="gold">
                    <animateMotion path="M 20 180 L 100 20 L 180 180" dur="2s" repeatCount="indefinite" />
                </circle>
            </svg>
        </div>
    </div>

    <p>
        Because the speed of light ($c$) is <strong>always the same</strong> for everyone, the photon in the moving clock has to travel a <em>longer distance</em> to complete one tick. If it's traveling a longer distance at the same speed, it must take <strong>more time</strong>. 
    </p>

    <h2>3. The Math</h2>
    <p>We calculate this "stretching" of time using the Lorentz Factor. If an observer on Earth watches a spaceship fly by at velocity $v$, the time on the ship ($\Delta t'$) relates to Earth time ($\Delta t$) like this:</p>
    
    <div class="math-box">
        $$\Delta t' = \frac{\Delta t}{\sqrt{1 - \frac{v^2}{c^2}}}$$
    </div>

    

    <h3>Key Takeaways:</h3>
    <ul>
        <li><strong>Speed of Light is Constant:</strong> $c \approx 300,000$ km/s.</li>
        <li><strong>Length Contraction:</strong> As time slows down, the object also appears shorter in the direction of motion.</li>
        <li><strong>Real World Use:</strong> GPS satellites move so fast that their internal clocks must be adjusted for time dilation, otherwise your phone's map would be off by kilometers!</li>
    </ul>
</div>

<footer>
    <p>Built for Physics Students | 2026 Educational Series</p>
</footer>

<!-- MathJax for rendering LaTeX formulas -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

</body>
</html>a charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Time Dilation | Special Relativity Explained</title>
    <style>
        :root {
            --space-dark: #ffffff;
            --star-white: #000000;
            --accent-blue: #0077b6;
            --accent-purple: #7209b7;
        }
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.7;
            color: var(--star-white);
            background-color: var(--star-white);
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 850px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        header {
            text-align: center;
            padding: 60px 0;
            background: linear-gradient(135deg, #0b0d17 0%, #1a1c2c 100%);
        }
        h1 {
            font-size: 3rem;
            margin: 0;
            color: var(--accent-blue);
            text-transform: uppercase;
            letter-spacing: 4px;
        }
        .card {
            background: transparent; 
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
        }
        h2 {
            color: var(--accent-blue);
            border-left: 4px solid var(--accent-purple);
            padding-left: 15px;
        }
        .formula-box {
            background: var(--star-white);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            font-size: 1.4rem;
            border: 1px solid var(--accent-purple);
            margin: 20px 0;
        }
        .highlight {
            color: var(--accent-blue);
            font-weight: bold;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background-color: transparent;
        }
        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        th { color: var(--accent-blue); }
        
        /* Animation Styling */
        #animation-container button {
            padding: 10px 20px; 
            background: var(--accent-blue); 
            border: none; 
            cursor: pointer; 
            font-weight: bold;
            border-radius: 5px;
            transition: 0.3s;
        }
        #animation-container button:hover {
            background: var(--accent-purple);
            color: white;
        }
        input[type=range] {
            cursor: pointer;
            accent-color: var(--accent-blue);
        }

        footer {
            text-align: center;
            padding: 40px;
            font-size: 0.8rem;
            opacity: 0.6;
        }
    </style>
</head>
<body>

<header>
    <h1>Time Dilation</h1>
    <p>Moving through space changes your journey through time.</p>
</header>

<div class="container">
    <section class="card">
        <h2>What is Time Dilation?</h2>
        <p>In simple terms, <strong>Time Dilation</strong> is the difference in the elapsed time measured by two observers. According to Einstein, time slows down for an object the faster it moves through space.</p>
    </section>

    <section class="card" id="animation-container" style="text-align: center;">
        <h2>The Light Clock Experiment</h2>
        <p>Observe how light travels a longer, diagonal path when the clock is in motion. Because the speed of light cannot change, the clock must "tick" more slowly to cover that extra distance.</p>
        
        <canvas id="lightClockCanvas" width="800" height="300" style="background: #000; border: 1px solid var(--accent-blue); width: 100%; max-width: 800px; border-radius: 10px;"></canvas>
        
        <div style="margin-top: 20px;">
            <button onclick="toggleAnimation()" id="startBtn">Pause / Resume</button>
            <span style="margin-left: 20px; font-weight: bold;">
                Velocity (v): <input type="range" id="speedRange" min="0" max="0.9" step="0.01" value="0.5"> 
                <span id="speedVal" style="color: var(--accent-blue);">0.5</span>c
            </span>
        </div>

        <script>
            const canvas = document.getElementById('lightClockCanvas');
            const ctx = canvas.getContext('2d');
            const speedRange = document.getElementById('speedRange');
            const speedVal = document.getElementById('speedVal');
            
            let isRunning = true;
            let time = 0;
            const L = 80; 
            const c = 3;  
            
            function toggleAnimation() {
                isRunning = !isRunning;
            }

            function draw() {
                if (isRunning) {
                    time += 0.5;
                }

                const v = parseFloat(speedRange.value);
                speedVal.innerText = v;

                ctx.clearRect(0, 0, canvas.width, canvas.height);

                ctx.fillStyle = "#4cc9f0";
                ctx.font = "bold 16px Inter";
                ctx.fillText("Stationary Observer (Frame A)", 50, 40);
                ctx.fillText("Moving Observer (Frame B)", 450, 40);

                const x1 = 150;
                const y_top = 100;
                const y_bot = 100 + (2 * L);
                
                ctx.strokeStyle = "#7209b7";
                ctx.lineWidth = 3;
                ctx.strokeRect(x1-30, y_top-5, 60, 5); 
                ctx.strokeRect(x1-30, y_bot, 60, 5);  

                let photonY = y_bot - (Math.abs((time * c) % (2 * L) - L));
                if (((time * c) % (4 * L)) > 2 * L) { 
                    photonY = y_top + (Math.abs((time * c) % (2 * L) - L));
                }
                
                ctx.beginPath();
                ctx.arc(x1, photonY, 6, 0, Math.PI * 2);
                ctx.fillStyle = "yellow";
                ctx.shadowBlur = 15;
                ctx.shadowColor = "yellow";
                ctx.fill();
                ctx.shadowBlur = 0;

                const x2_base = 500;
                const horizontalShift = (time * v * 2) % 250; 
                const x2 = x2_base + horizontalShift;

                ctx.strokeStyle = "#7209b7";
                ctx.strokeRect(x2-30, y_top-5, 60, 5); 
                ctx.strokeRect(x2-30, y_bot, 60, 5);

                const period = (2 * L) / Math.sqrt(c*c - v*v);
                let movingPhotonY;
                const phase = (time) % (2 * period);
                
                if (phase < period) {
                    movingPhotonY = y_bot - (phase / period) * (2 * L);
                } else {
                    movingPhotonY = y_top + ((phase - period) / period) * (2 * L);
                }

                ctx.beginPath();
                ctx.arc(x2, movingPhotonY, 6, 0, Math.PI * 2);
                ctx.fillStyle = "yellow";
                ctx.shadowBlur = 15;
                ctx.shadowColor = "yellow";
                ctx.fill();
                ctx.shadowBlur = 0;

                requestAnimationFrame(draw);
            }
            draw();
        </script>
    </section>

    <section class="card">
        <h2>The Math</h2>
        <div class="formula-box">
            $$t = \frac{t_0}{\sqrt{1 - \frac{v^2}{c^2}}}$$
        </div>
    </section>

    <section class="card">
    <ul>
            <li><strong>$t$:</strong> Time measured by the stationary observer (dilated time).</li>
            <li><strong>$t_0$:</strong> Proper time (measured by the person moving).</li>
            <li><strong>$v$:</strong> Velocity of the moving object.</li>
            <li><strong>$c$:</strong> The speed of light.</li>
        </ul>
        
        <h2>Velocity vs. Time Flow</h2>
        <table>
            <tr>
                <th>Speed (% of Light)</th>
                <th>Time for Moving Person</th>
                <th>Time for Earth Observer</th>
            </tr>
            <tr>
                <td>10%</td>
                <td>1 Year</td>
                <td>1.005 Years</td>
            </tr>
            <tr>
                <td>50%</td>
                <td>1 Year</td>
                <td>1.15 Years</td>
            </tr>
            <tr>
                <td>90%</td>
                <td>1 Year</td>
                <td>2.29 Years</td>
            </tr>
            <tr>
                <td>99.9%</td>
                <td>1 Year</td>
                <td>22.37 Years</td>
            </tr>
        </table>
    </section>
</div>

<footer>
    <p>Physics Lab &copy; 2026 | Built for Future Physicists</p>
</footer>

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

</body>
</html>
