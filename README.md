<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Tijeras Locas</title>
    <link rel="icon" type="image/png" href="cdc715c6-6b30-40d4-93ed-cfbd5efb1716.jfif">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

    <style>
        html {
            scroll-behavior: smooth;
            font-size: 16px;
        }

        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff4b5c, #0d6efd);
            color: #333;
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: rgba(0, 0, 0, 0.6);
            color: white;
            text-align: center;
            padding: 80px 20px;
            position: relative;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }

        header h1 {
            font-size: 4.5em;
            margin: 0;
            animation: fadeIn 2s ease-in-out;
        }

        header p {
            font-size: 1.5em;
            margin-top: 10px;
            animation: fadeIn 2s ease-in-out 0.5s;
        }

        /* Navigation */
        nav {
            background-color: #0d6efd;
            text-align: center;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 10;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        nav a {
            color: white;
            text-decoration: none;
            padding: 15px 20px;
            margin: 0 15px;
            font-size: 1.2em;
            transition: background 0.3s, color 0.3s;
        }

        nav a:hover {
            background-color: white;
            color: #0d6efd;
            border-radius: 5px;
        }

        /* Parallax Section */
        .parallax {
            background-image: url('background-image.jpg');
            height: 500px;
            background-attachment: fixed;
            background-position: center;
            background-size: cover;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            font-size: 2em;
        }

        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        /* Services Section */
        section h2 {
            text-align: center;
            font-size: 3.5em;
            margin-bottom: 30px;
            color: #ffffff;
            text-transform: uppercase;
            animation: fadeIn 2s ease-in-out;
        }

        .service-list {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
            animation: slideIn 1s ease-in-out;
        }

        .service {
            background-color: #fff;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
            margin: 15px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            width: 300px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            opacity: 0;
            animation: fadeInUp 1s ease-in-out forwards;
        }

        .service:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.15);
        }

        .service img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            margin-bottom: 15px;
            transition: transform 0.3s ease;
        }

        .service img:hover {
            transform: scale(1.1);
        }

        .service .title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 10px;
            color: #0d6efd;
        }

        .service p {
            font-size: 1.1em;
            line-height: 1.6;
            color: #777;
        }

        /* Gallery Section */
        .gallery-section {
            text-align: center;
            margin-bottom: 60px;
        }

        .gallery-section h2 {
            font-size: 3.5em;
            margin-bottom: 40px;
            text-transform: uppercase;
            animation: fadeIn 2s ease-in-out;
            color: #ffffff;
        }

        .gallery-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); /* Cambiado a 300px para crear un formato cuadrado */
            gap: 20px;
            animation: fadeInUp 1.5s ease-in-out;
        }

        .gallery-item {
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            position: relative;
            transition: transform 0.3s ease;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Esto hace que las imágenes sean cuadradas */
            transition: transform 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-item:hover::after {
            content: 'Ver más';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 1.2em;
            color: white;
            background-color: rgba(0, 0, 0, 0.5);
            padding: 10px 20px;
            border-radius: 5px;
            opacity: 0;
            animation: fadeIn 0.5s ease-in-out forwards;
        }

        /* Contact Section */
        .contact form {
            display: flex;
            flex-direction: column;
            align-items: center;
            max-width: 600px;
            margin: auto;
            animation: fadeInUp 2s ease-in-out;
        }

        .contact input,
        .contact textarea {
            margin: 10px;
            padding: 15px;
            width: 100%;
            max-width: 500px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 1.2em;
            transition: border 0.3s ease;
        }

        .contact input:focus,
        .contact textarea:focus {
            border-color: #0d6efd;
        }

        .contact button {
            background-color: #0d6efd;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2em;
            border-radius: 6px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .contact button:hover {
            background-color: #ff4b5c;
        }

        /* Footer */
        footer {
            background-color: #222;
            color: white;
            text-align: center;
            padding: 20px 0;
            font-size: 1.1em;
        }

        footer p {
            margin: 0;
        }

        /* Animations */
        @keyframes fadeIn {
            0% {
                opacity: 0;
            }
            100% {
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideIn {
            0% {
                opacity: 0;
                transform: translateX(-50px);
            }
            100% {
                opacity: 1;
                transform: translateX(0);
            }
        }

    </style>
</head>

<body>

    <header>
        <h1>Tijeras Locas</h1>
        <p>Transformá tu look con nuestro servicio personalizado de cortes de cabello</p>
    </header>

    <nav>
        <a href="#quien-soy">¿Quién soy?</a>
        <a href="#services">Servicios</a>
        <a href="#gallery">Galería</a>
        <a href="#contact">Contacto</a>
    </nav>

    <main class="container">

        <section class="parallax">
            <h2>¡Bienvenidos a Tijeras Locas!</h2>
        </section>

        <section id="services">
            <h2>Servicios</h2>
            <div class="service-list">
                <div class="service">
                    <div class="title">Corte de Pelo</div>
                </div>
                <div class="service">
                    <div class="title">Corte con Diseño</div>
                </div>
                <div class="service">
                    <div class="title">Corte y Cejas</div>
                </div>
            </div>
        </section>

        <section id="gallery" class="gallery-section">
            <h2>Galería</h2>
            <div class="gallery-list">
                <div class="gallery-item">
                    <img src="cortedepelo.jfif" alt="Corte de Pelo">
                </div>
                <div class="gallery-item">
                    <img src="cortedepelo+diseño.jfif" alt="Corte con Diseño">
                </div>
                <div class="gallery-item">
                    <img src="cpelo.jfif" alt="Corte y Cejas">
                </div>
            </div>
        </section>

        <section class="contact" id="contact">
            <h2>Contacto</h2>
            <form action="https://formspree.io/f/mkgrnevv" method="POST">
                <input type="text" name="_honey" style="display:none">
                <input type="hidden" name="_next" value="https://tijeraslocas.com/gracias.html">
                <input type="text" name="nombre" placeholder="Tu nombre" required>
                <input type="email" name="email" placeholder="Tu correo" required>
                <textarea name="mensaje" placeholder="Escribí tu mensaje" rows="5" required></textarea>
                <button type="submit">Enviar mensaje</button>
            </form>
        </section>

        <section id="quien-soy">
            <h2>¿Quién soy?</h2>
            <p>¡Hola! Soy Jerónimo Galván, tengo 17 años. Comencé a cortar el pelo en mayo de 2024 en La Pelu Of The City, donde me formé durante dos meses. Luego, en septiembre, realicé un curso de corte avanzado para perfeccionar mis habilidades.</p>
        </section>

    </main>

    <footer>
        <p>&copy; 2025 Tijeras Locas | Todos los derechos reservados</p>
        <p>Visítanos en GitHub: <a href="https://github.com/jeroogalvan/Tijeras-Locas" target="_blank" style="color: #0d6efd;">Tijeras-Locas en GitHub</a></p>
    </footer>

</body>

</html>
