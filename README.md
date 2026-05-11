
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
        /* UPDATED: Removed the white tint to make it transparent */
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
        /* UPDATED: Table is now fully transparent */
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
        <p>In simple terms, <strong>Time Dilation</strong> is the difference in the elapsed time measured by two observers. According to Einstein, time is not a "universal clock" that ticks the same for everyone. Instead, time <span class="highlight">slows down</span> for an object the faster it moves through space.</p>
    </section>

    <section class="card">
        <h2>The Light Clock Experiment</h2>
        <p>Imagine a clock that works by bouncing a beam of light between two mirrors. One "tick" is the time it takes for light to go up and down.</p>
        <ul>
            <li><strong>At Rest:</strong> The light travels a straight vertical path.</li>
            <li><strong>In Motion:</strong> To an outside observer, the light must travel a <span class="highlight">diagonal path</span> to catch up with the moving mirrors.</li>
        </ul>
        <p>Since the speed of light ($c$) is constant and the diagonal path is longer, the clock <em>must</em> take more time to complete one tick. Thus, time stretches!</p>
    </section>

    <section class="card">
        <h2>The Math</h2>
        <p>We use the Lorentz Factor ($\gamma$) to calculate exactly how much time dilates:</p>
        <div class="formula-box">
            $$t = \frac{t_0}{\sqrt{1 - \frac{v^2}{c^2}}}$$
        </div>
        <p>Where:</p>
        <ul>
            <li><strong>$t$:</strong> Time measured by the stationary observer (dilated time).</li>
            <li><strong>$t_0$:</strong> Proper time (measured by the person moving).</li>
            <li><strong>$v$:</strong> Velocity of the moving object.</li>
            <li><strong>$c$:</strong> The speed of light.</li>
        </ul>
    </section>
    
<section id="animation-container" style="text-align: center;">
    <h2>The Light Clock Experiment</h2>
    <p>Observe how light travels a longer, diagonal path when the clock is in motion. Because the speed of light cannot change, the clock must "tick" more slowly to cover that extra distance.</p>
    
    <canvas id="lightClockCanvas" width="800" height="300" style="background: #000; border: 1px solid #00d4ff; width: 100%; max-width: 800px;"></canvas>
    
    <div style="margin-top: 15px;">
        <button onclick="toggleAnimation()" id="startBtn" style="padding: 10px 20px; background: #00d4ff; border: none; cursor: pointer; font-weight: bold;">Pause/Resume</button>
        <span style="margin-left: 20px;">Velocity (v): <input type="range" id="speedRange" min="0" max="0.9" step="0.01" value="0.5"> <span id="speedVal">0.5</span>c</span>
    </div>

    <script>
        const canvas = document.getElementById('lightClockCanvas');
        const ctx = canvas.getContext('2d');
        const speedRange = document.getElementById('speedRange');
        const speedVal = document.getElementById('speedVal');
        
        let isRunning = true;
        let time = 0;
        const L = 80; // Distance between mirrors
        const c = 3;  // Constant speed of light
        
        function toggleAnimation() {
            isRunning = !isRunning;
        }

        function draw() {
            if (isRunning) {
                time += 0.5;
            }

            const v = parseFloat(speedRange.value);
            speedVal.innerText = v;

            // Clear Canvas
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Labels
            ctx.fillStyle = "#00d4ff";
            ctx.font = "16px Arial";
            ctx.fillText("Stationary Observer (Frame A)", 50, 40);
            ctx.fillText("Moving Observer (Frame B)", 450, 40);

            // Draw Stationary Clock
            const x1 = 150;
            const y_top = 100;
            const y_bot = 100 + (2 * L);
            
            ctx.strokeStyle = "#444";
            ctx.strokeRect(x1-30, y_top-5, 60, 5); // Top mirror
            ctx.strokeRect(x1-30, y_bot, 60, 5);   // Bottom mirror

            // Stationary Photon Logic
            let photonY = y_bot - (Math.abs((time * c) % (2 * L) - L));
            if (((time * c) % (4 * L)) > 2 * L) { // Moving up/down logic
                photonY = y_top + (Math.abs((time * c) % (2 * L) - L));
            }
            
            // Draw Photon A
            ctx.beginPath();
            ctx.arc(x1, photonY, 5, 0, Math.PI * 2);
            ctx.fillStyle = "yellow";
            ctx.shadowBlur = 15;
            ctx.shadowColor = "yellow";
            ctx.fill();
            ctx.shadowBlur = 0;

            // Draw Moving Clock
            const x2_base = 500;
            const horizontalShift = (time * v * 2) % 250; 
            const x2 = x2_base + horizontalShift;

            ctx.strokeStyle = "#444";
            ctx.strokeRect(x2-30, y_top-5, 60, 5); 
            ctx.strokeRect(x2-30, y_bot, 60, 5);

            // Moving Photon Path (The Zig-Zag)
            // In the moving frame, light still moves at c, but covers a diagonal
            const period = (2 * L) / Math.sqrt(c*c - v*v);
            let movingPhotonY;
            const phase = (time) % (2 * period);
            
            if (phase < period) {
                movingPhotonY = y_bot - (phase / period) * (2 * L);
            } else {
                movingPhotonY = y_top + ((phase - period) / period) * (2 * L);
            }

            // Draw Photon B
            ctx.beginPath();
            ctx.arc(x2, movingPhotonY, 5, 0, Math.PI * 2);
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
</html>

    <section class="card">
        <h2>The Light Clock Experiment</h2>
        <p>Imagine a clock that works by bouncing a beam of light between two mirrors. One "tick" is the time it takes for light to go up and down.</p>
        <ul>
            <li><strong>At Rest:</strong> The light travels a straight vertical path.</li>
            <li><strong>In Motion:</strong> To an outside observer, the light must travel a diagonal path to catch up with the moving mirrors.</li>

            <footer>
    <p>Created by CHMSU TALISAY BSED SCIENCE - 3A &copy; 2026 | Built for Future Physicists</p>
</footer>
