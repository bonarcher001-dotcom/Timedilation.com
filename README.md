
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
    <p>
            Before Albert Einstein, the world believed time was "absolute"—a universal clock that ticked at the exact same rate for everyone, everywhere. 
            Einstein’s breakthrough was the realization that time is not a separate background; it is the <strong>fourth dimension</strong>, 
            intimately woven together with space to form a single fabric called <span class="highlight">spacetime</span>.
        </p>
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
        Because the speed of light (c) is <strong>always the same</strong> for everyone, the photon in the moving clock has to travel a <em>longer distance</em> to complete one tick. If it's traveling a longer distance at the same speed, it must take <strong>more time</strong>. 
    </p>

    <h2>3. The Math</h2>
    <p>We calculate this "stretching" of time using the Lorentz Factor. If an observer on Earth watches a spaceship fly by at velocity v, the time on the ship relates to Earth time like this:</p>
    
    <div class="math-box">
        $$\Delta t' = \frac{\Delta t}{\sqrt{1 - \frac{v^2}{c^2}}}$$
    </div>

    

    <h3>Key Takeaways:</h3>
    <ul>
        <li><strong>Speed of Light is Constant:</strong> c \approx 300,000 km/s.</li>
        <li><strong>Length Contraction:</strong> As time slows down, the object also appears shorter in the direction of motion.</li>
        <li><strong>Real World Use:</strong> GPS satellites move so fast that their internal clocks must be adjusted for time dilation, otherwise your phone's map would be off by kilometers!</li>
    </ul>
</div>

<footer>
    <p>Created by CHMSU TALISAY BSED SCIENCE - 3A | 2026 Educational Series</p>
</footer>

<!-- MathJax for rendering LaTeX formulas -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

</body>
</html>
