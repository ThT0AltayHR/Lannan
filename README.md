<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="referrer" content="no-referrer">

    <title>Hacked By TurkHackTeam | Saldırı Timleri</title>
    <link rel="icon" type="image/png" href="https://i.hizliresim.com/9x1hxd2.png">

    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet">

    <style>
        /* ==========================================================================
           1. TEMEL VE SIFIRLAMA STİLLERİ
           ========================================================================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            height: 100%;
            background-color: #050505;
            color: #ffffff;
            font-family: 'Rajdhani', sans-serif;
            overflow: hidden;
            user-select: none;
            cursor: crosshair;
        }

        /* ==========================================================================
           2. ARKA PLAN KATMANLARI VE PARALAKS
           ========================================================================== */
        .bg-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            z-index: 1;
            opacity: 0;
            transform: scale(1.1);
            transition: transform 0.1s linear;
        }

        /* Orijinal Resim 1 */
        .bg-1 {
            background-image: url('https://i.hizliresim.com/hzquks5.png');
            animation: fadeBg1 32s infinite;
        }

        /* Orijinal Resim 2 */
        .bg-2 {
            background-image: url('https://i.imgur.com/GeIWsSg.png');
            animation: fadeBg2 32s infinite;
        }

        /* Yeni Eklenen Resim 1 */
        .bg-3 {
            background-image: url('https://i.hizliresim.com/segn1lt.png');
            animation: fadeBg3 32s infinite;
        }

        /* Yeni Eklenen Resim 2 */
        .bg-4 {
            background-image: url('https://i.hizliresim.com/32f7w9r.png');
            animation: fadeBg4 32s infinite;
        }

        #networkCanvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 2;
        }

        .vignette-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, transparent 15%, #000000 100%);
            z-index: 3;
            pointer-events: none;
        }

        /* ==========================================================================
           3. ANA DÜZEN
           ========================================================================== */
        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            text-align: center;
            position: relative;
            padding: 20px;
            pointer-events: none;
            z-index: 4;
            transition: transform 0.1s linear;
        }

        /* ==========================================================================
           4. LOGO & LINKS
           ========================================================================== */
        .logos-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 30px;
            margin-bottom: 40px;
            pointer-events: auto;
            text-decoration: none;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .logos-container:hover {
            transform: scale(1.05);
        }

        .logos-container img {
            width: 200px;
            height: auto;
            max-height: 200px;
            object-fit: contain;
            border-radius: 8px;
            filter: drop-shadow(0 0 15px rgba(255, 0, 0, 0.6));
            animation: breathe 4s ease-in-out infinite alternate;
        }

        /* ==========================================================================
           5. TEXT SLIDER
           ========================================================================== */
        .slider-container {
            position: relative;
            width: 100%;
            max-width: 1000px;
            height: 150px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .slide {
            position: absolute;
            opacity: 0;
            transform: scale(0.95) translateY(10px);
            transition: opacity 1.2s ease, transform 1.2s ease, filter 1.2s ease;
            filter: blur(5px);
            font-family: 'Orbitron', sans-serif;
            font-size: 2.2rem;
            color: #e0e0e0;
            text-shadow: 0 0 15px rgba(255, 0, 0, 0.4);
            width: 100%;
            pointer-events: none;
        }

        .slide.active {
            opacity: 1;
            transform: scale(1) translateY(0);
            filter: blur(0);
        }

        .slide span {
            color: #ff0000;
            font-weight: 900;
            text-shadow: 0 0 25px rgba(255, 0, 0, 0.9);
            letter-spacing: 2px;
        }

        /* ==========================================================================
           6. CSS KEYFRAMES
           ========================================================================== */
        @keyframes fadeBg1 {
            0%, 20% { opacity: 0.45; }
            25%, 95% { opacity: 0; }
            100% { opacity: 0.45; }
        }

        @keyframes fadeBg2 {
            0%, 20% { opacity: 0; }
            25%, 45% { opacity: 0.45; }
            50%, 100% { opacity: 0; }
        }

        @keyframes fadeBg3 {
            0%, 45% { opacity: 0; }
            50%, 70% { opacity: 0.45; }
            75%, 100% { opacity: 0; }
        }

        @keyframes fadeBg4 {
            0%, 70% { opacity: 0; }
            75%, 95% { opacity: 0.45; }
            100% { opacity: 0; }
        }

        @keyframes breathe {
            0% { transform: scale(0.97); opacity: 0.8; }
            100% { transform: scale(1.03); opacity: 1; filter: drop-shadow(0 0 35px rgba(255,0,0,1)); }
        }

        @media (max-width: 768px) {
            .slide { font-size: 1.4rem; }
            .logos-container img { width: 100px; }
        }
    </style>
</head>
<body>

    <div class="bg-layer bg-1"></div>
    <div class="bg-layer bg-2"></div>
    <div class="bg-layer bg-3"></div>
    <div class="bg-layer bg-4"></div>

    <canvas id="networkCanvas"></canvas>
    <div class="vignette-overlay"></div>

    <div class="container">

        <a href="https://www.turkhackteam.org/" target="_blank" class="logos-container" title="TurkHackTeam Forumuna Git">
            <img src="https://i.hizliresim.com/9x1hxd2.png" alt="TurkHackTeam Logo 1">
        </a>

        <div class="slider-container">
            <div class="slide active">HELLO ADMIN SYSTEM HACKED!<br><span>TURKHACKTEAM</span></div>
            <div class="slide">VETERAN7 - ZORROKİN - B0YNER<br><span>HACKED!</span></div>
            <div class="slide">İSTEDİĞİMİZ ZAMAN<br><span>İSTEDİĞİMİZ YERDE!</span></div>
        </div>

    </div>

    <script>
        /**
         * --------------------------------------------------------------------------
         * 1. PARALLAX EFFECT (Mouse Movement Interaction)
         * --------------------------------------------------------------------------
         */
        let mouse = { x: null, y: null, radius: 180 };

        window.addEventListener('mousemove', function(event) {
            mouse.x = event.clientX;
            mouse.y = event.clientY;

            let xAxis = (window.innerWidth / 2 - event.clientX) / 25;
            let yAxis = (window.innerHeight / 2 - event.clientY) / 25;

            // Shift background layers opposite to mouse
            document.querySelectorAll('.bg-layer').forEach(bg => {
                bg.style.transform = `scale(1.1) translate(${xAxis}px, ${yAxis}px)`;
            });

            // Shift main container towards mouse (creates 3D depth)
            document.querySelector('.container').style.transform = `translate(${-xAxis * 0.6}px, ${-yAxis * 0.6}px)`;
        });

        window.addEventListener('mouseout', function() {
            mouse.x = undefined;
            mouse.y = undefined;

            document.querySelectorAll('.bg-layer').forEach(bg => {
                bg.style.transform = `scale(1.1) translate(0px, 0px)`;
            });
            document.querySelector('.container').style.transform = `translate(0px, 0px)`;
        });

        /**
         * --------------------------------------------------------------------------
         * 2. CANVAS NETWORK ANIMATION
         * --------------------------------------------------------------------------
         */
        const canvas = document.getElementById('networkCanvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let particlesArray = [];

        class Particle {
            constructor(x, y, directionX, directionY, size) {
                this.x = x;
                this.y = y;
                this.directionX = directionX;
                this.directionY = directionY;
                this.size = size;
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);

                let dx = mouse.x - this.x;
                let dy = mouse.y - this.y;
                let distance = Math.sqrt(dx * dx + dy * dy);

                if (distance < mouse.radius) {
                    ctx.fillStyle = '#ff1111';
                    ctx.shadowBlur = 15;
                    ctx.shadowColor = '#ff0000';
                } else {
                    ctx.fillStyle = 'rgba(100, 0, 0, 0.4)';
                    ctx.shadowBlur = 0;
                }
                ctx.fill();
            }

            update() {
                if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;

                this.x += this.directionX;
                this.y += this.directionY;
                this.draw();
            }
        }

        function initCanvas() {
            particlesArray = [];
            let numberOfParticles = Math.floor((canvas.height * canvas.width) / 12000);

            // Limit particles to prevent browser freeze on ultra-wide screens                                                      if (numberOfParticles > 150) numberOfParticles = 150;

            for (let i = 0; i < numberOfParticles; i++) {
                let size = (Math.random() * 1.5) + 0.5;
                let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                let directionX = (Math.random() * 0.4) - 0.2;
                let directionY = (Math.random() * 0.4) - 0.2;
                                                                                                                                        particlesArray.push(new Particle(x, y, directionX, directionY, size));                                              }
        }

        function connectParticles() {
            for (let a = 0; a < particlesArray.length; a++) {
                for (let b = a; b < particlesArray.length; b++) {
                    let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b].x))
                                 + ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));

                    if (distance < (canvas.width / 9) * (canvas.height / 9)) {
                        let opacityValue = 1 - (distance / 16000);
                        let dx = mouse.x - particlesArray[a].x;
                        let dy = mouse.y - particlesArray[a].y;
                        let mouseDistance = Math.sqrt(dx * dx + dy * dy);

                        if (mouseDistance < mouse.radius) {
                            ctx.strokeStyle = 'rgba(255, 0, 0,' + opacityValue + ')';
                            ctx.lineWidth = 1.8;
                        } else {
                            ctx.strokeStyle = 'rgba(100, 0, 0,' + (opacityValue * 0.15) + ')';
                            ctx.lineWidth = 0.5;
                        }
                        ctx.beginPath();
                        ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                        ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                        ctx.stroke();
                    }
                }
            }
        }

        function animateCanvas() {
            requestAnimationFrame(animateCanvas);
            ctx.clearRect(0, 0, innerWidth, innerHeight);

            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
            }
            connectParticles();
        }

        window.addEventListener('resize', () => {
            canvas.width = innerWidth;
            canvas.height = innerHeight;
            initCanvas();
        });

        // Initialize Canvas                                                                                                    initCanvas();
        animateCanvas();                                                                                                
        /**                                                                                                                      * --------------------------------------------------------------------------
         * 3. TEXT SLIDER LOGIC                                                                                                  * --------------------------------------------------------------------------
         */                                                                                                                     const slides = document.querySelectorAll('.slide');
        let currentSlide = 0;
                                                                                                                                function nextSlide() {
            if(slides.length > 0) {
                slides[currentSlide].classList.remove('active');
                currentSlide = (currentSlide + 1) % slides.length;
                slides[currentSlide].classList.add('active');
            }
        }
        setInterval(nextSlide, 4500);

        /**
         * --------------------------------------------------------------------------
         * 4. SECURITY (Disable Right-Click & Dev Tools)
         * --------------------------------------------------------------------------
         */
        document.addEventListener('contextmenu', event => {
            event.preventDefault();
            alert('TURKHACKTEAM | İndexi kopyalamak yasaktır.');
        });

        document.addEventListener('keydown', event => {
            // Disable F12, Ctrl+Shift+I, Ctrl+Shift+J, Ctrl+U
            if (event.keyCode === 123 ||
               (event.ctrlKey && event.shiftKey && (event.keyCode === 73 || event.keyCode === 74)) ||
               (event.ctrlKey && event.keyCode === 85)) {
                event.preventDefault();
                return false;
            }
        });

        document.addEventListener('dragstart', event => event.preventDefault());

    </script>
</body>
