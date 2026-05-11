<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Time Dilation | Special Relativity Explained</title>
    <style>
        :root {
            --space-dark: #0b0d17;
            --star-white: #f1f1f1;
            --accent-blue: #4cc9f0;
            --accent-purple: #7209b7;
        }
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.7;
            color: var(--star-white);
            background-color: var(--space-dark);
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
            background: #000;
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
