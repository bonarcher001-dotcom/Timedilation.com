
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


<footer>
    <p>Physics Lab &copy; 2026 | Built for Future Physicists</p>
</footer>

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

</body>
</html>

    <section class="card">
        <h2>The Light Clock Experiment</h2>
        <p>Imagine a clock that works by bouncing a beam of light between two mirrors. One "tick" is the time it takes for light to go up and down.</p>
        <ul>
            <li><strong>At Rest:</strong> The light travels a straight vertical path.</li>
            <li><strong>In Motion:</strong> To an outside observer, the light must travel a
