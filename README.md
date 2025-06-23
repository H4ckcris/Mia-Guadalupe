<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Mi hermosa Guadalupe!</title>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;700&family=Kalam:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #fce4ec 0%, #e0f2f7 100%);
            font-family: 'Kalam', cursive; /* Fuente infantil */
            overflow: hidden;
            color: #333;
            position: relative;
        }

        .top-text {
            font-size: clamp(1.5em, 4vw, 3em);
            color: #FF69B4; /* Rosa para niña */
            margin-bottom: 20px;
            animation: fadeIn 1.5s ease-out forwards;
            opacity: 0;
            animation-delay: 0.2s;
            text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #FF1493; /* Neón rosa */
        }

        .container {
            text-align: center;
            background-color: #ffffff;
            padding: 40px 60px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-out;
            cursor: pointer;
            position: relative;
            z-index: 1;
        }
        .container:hover {
            transform: translateY(-5px);
        }
        h1 {
            font-size: clamp(3em, 8vw, 6em);
            margin-bottom: 15px;
            color: #FF69B4; /* Rosa para niña */
            animation: fadeInScale 1.5s ease-out forwards, pulse 2s infinite alternate;
            position: relative;
            z-index: 1;
            transition: color 0.8s ease-in-out;
            text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #00ffff; /* Neón */
        }
        p {
            font-size: clamp(1.2em, 3vw, 2em);
            color: #555;
            animation: fadeIn 2s ease-out forwards;
            animation-delay: 0.5s;
            opacity: 0;
            position: relative;
            z-index: 1;
        }
        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        @keyframes pulse {
            from {
                transform: scale(1);
            }
            to {
                transform: scale(1.05);
            }
        }
        .bubble {
            position: absolute;
            border-radius: 50%;
            background-color: rgba(255, 105, 180, 0.3); /* Rosa claro para niña */
            animation: floatBubble 10s infinite linear, colorChange 5s infinite alternate;
            z-index: 0;
        }
        @keyframes floatBubble {
            0% {
                transform: translateY(100vh) scale(0);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) scale(1);
                opacity: 0;
            }
        }

        @keyframes colorChange {
            0% { background-color: rgba(255, 105, 180, 0.3); } /* Rosa claro */
            100% { background-color: rgba(255, 192, 203, 0.3); } /* Rosa pastel */
        }

        .heart {
            position: absolute;
            font-size: 2em;
            color: #FFC0CB; /* Rosa pastel */
            top: -20px;
            animation: heartRain 5s linear infinite;
            opacity: 0;
            pointer-events: none;
        }

        @keyframes heartRain {
            0% {
                transform: translateY(0);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            100% {
                transform: translateY(100vh);
                opacity: 0;
            }
        }

        .matrix-transition {
            animation: matrixFadeOut 0.5s forwards;
        }

        @keyframes matrixFadeOut {
            0% { opacity: 1; }
            100% { opacity: 0; }
        }

        /* Estilos para el botón */
        .more-options-button {
            background-color: #FFB6C1; /* Rosa claro para el botón */
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 20px;
            font-family: 'Kalam', cursive;
            font-size: 1.2em;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }

        .more-options-button:hover {
            background-color: #FF69B4; /* Rosa más fuerte al pasar el ratón */
        }

        /* Estilos para el contenedor de opciones adicionales */
        .additional-options {
            display: none;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
            animation: fadeIn 1s ease-out forwards;
        }

        /* Estilos para la imagen */
        .girl-image {
            max-width: 100%;
            height: auto;
            border-radius: 15px;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
    </style>
</head>
<body>
    <div class="top-text">Mia Guadalupe</div>
    <div class="container" onclick="changeContent()">
        <h1 class="color-change-text" id="mainMessage">¡Mi hermosa Guadalupe!</h1>
        <p id="subMessage">¡Eres un sol!</p>
    </div>

    <button class="more-options-button" onclick="toggleOptions()">Más opciones</button>

    <div class="additional-options" id="additionalOptions">
        <p id="option1">¡Eres mi princesa!</p>
        <p id="option2">¡Te adoro, mi reina!</p>
        <p id="option3">¡Eres la más bella!</p>
    </div>

    <img src="https://i.ibb.co/pjsbT5hd/IMG-0424.jpg" alt="Una niña adorable" class="girl-image">

    <script>
        const messages = [
            { main: "¡Mi hermosa Guadalupe!", sub: "¡Eres un sol!" },
            { main: "¡Qué linda eres!", sub: "¡Mi pequeña maravilla!" },
            { main: "¡Mira, mira!", sub: "¡Te quiero mucho!" },
            { main: "¡Eres mi alegría!", sub: "¡Un regalo del cielo!" },
            { main: "¡Sonríe, mi amor!", sub: "¡Tu sonrisa ilumina el día!" }
        ];
        const colors = ['#ff6f91', '#a2d2ff', '#baffc9', '#ffffba', '#ffadad', '#cddafd', '#ffdbed', '#d3e0ea'];
        let currentMessageIndex = 0;
        let currentColorIndex = 0;

        function changeContent() {
            const mainMessageElement = document.getElementById('mainMessage');
            const subMessageElement = document.getElementById('subMessage');

            mainMessageElement.classList.add('matrix-transition');
            subMessageElement.classList.add('matrix-transition');

            setTimeout(() => {
                currentMessageIndex = (currentMessageIndex + 1) % messages.length;
                mainMessageElement.textContent = messages[currentMessageIndex].main;
                subMessageElement.textContent = messages[currentMessageIndex].sub;

                currentColorIndex = (currentColorIndex + 1) % colors.length;
                mainMessageElement.style.color = colors[currentColorIndex];

                mainMessageElement.classList.remove('matrix-transition');
                subMessageElement.classList.remove('matrix-transition');
                mainMessageElement.style.animation = 'none';
                subMessageElement.style.animation = 'none';
                void mainMessageElement.offsetWidth;
                mainMessageElement.style.animation = 'fadeInScale 0.8s ease-out forwards, pulse 2s infinite alternate';
                subMessageElement.style.animation = 'fadeIn 1s ease-out forwards';
            }, 500);
        }

        function createBubble() {
            const bubble = document.createElement('div');
            bubble.classList.add('bubble');
            document.body.appendChild(bubble);

            const size = Math.random() * 80 + 20;
            bubble.style.width = `${size}px`;
            bubble.style.height = `${size}px`;
            bubble.style.left = `${Math.random() * 100}vw`;

            const duration = Math.random() * 10 + 5;
            const delay = Math.random() * 5;
            bubble.style.animationDuration = `${duration}s`;
            bubble.style.animationDelay = `${delay}s`;

            bubble.addEventListener('animationend', () => {
                bubble.remove();
            });
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.textContent = '❤️';
            document.body.appendChild(heart);

            heart.style.left = `${Math.random() * 100}vw`;
            heart.style.animationDuration = `${Math.random() * 3 + 2}s`;
            heart.style.animationDelay = `${Math.random() * 5}s`;
            heart.style.fontSize = `${Math.random() * 1.5 + 1}em`;

            heart.addEventListener('animationend', () => {
                heart.remove();
            });
        }

        // Función para mostrar/ocultar las opciones adicionales
        function toggleOptions() {
            const optionsContainer = document.getElementById('additionalOptions');
            optionsContainer.style.display = optionsContainer.style.display === 'none' ? 'flex' : 'none';
        }

        setInterval(createBubble, 1000);
        setInterval(createHeart, 300);
    </script>
</body>
</html>
