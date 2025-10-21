<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mielsita Vapes | Tu nube, tu estilo</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #000;
            color: #fff;
            margin: 0;
            padding: 0;
        }

        header {
            background: linear-gradient(90deg, #0a0a0a, #1e1e1e);
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 10;
        }

        header h1 {
            color: #ffb7d5;
            font-size: 1.8em;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            margin: 0 15px;
            font-weight: 500;
        }

        nav a:hover {
            color: #ffb7d5;
        }

        .hero {
            background-image: url('https://images.unsplash.com/photo-1600959907703-9e66e4bdfd1b');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .hero h2 {
            font-size: 3em;
            text-shadow: 0 0 10px #ffb7d5;
        }

        .hero p {
            font-size: 1.2em;
            max-width: 600px;
        }

        .btn {
            background-color: #ffb7d5;
            color: #000;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 20px;
            text-decoration: none;
            transition: 0.3s;
        }

        .btn:hover {
            background-color: #ff8dbd;
        }

        .productos {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 40px;
            background-color: #111;
        }

        .producto {
            background-color: #1b1b1b;
            border-radius: 10px;
            margin: 15px;
            padding: 20px;
            width: 280px;
            text-align: center;
            box-shadow: 0 0 10px #ffb7d540;
        }

        .producto img {
            width: 100%;
            border-radius: 10px;
        }

        .producto h3 {
            color: #ffb7d5;
        }

        footer {
            background-color: #0a0a0a;
            text-align: center;
            padding: 20px;
            font-size: 0.9em;
        }

        footer a {
            color: #ffb7d5;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }

        /* Carrito */
        #carrito {
            position: fixed;
            top: 100px;
            right: 20px;
            background-color: #1b1b1b;
            border: 1px solid #ffb7d540;
            border-radius: 10px;
            padding: 20px;
            width: 250px;
            display: none;
        }

        #carrito h3 {
            color: #ffb7d5;
            margin-top: 0;
        }

        #lista-carrito p {
            font-size: 0.9em;
        }

        #btn-whatsapp {
            display: inline-block;
            background-color: #25D366;
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 15px;
        }

        #btn-whatsapp:hover {
            background-color: #1ebc5d;
        }
    </style>
</head>
<body>

<header>
    <h1>Mielsita Vapes</h1>
    <nav>
        <a href="#inicio">Inicio</a>
        <a href="#productos">Productos</a>
        <a href="#contacto">Contacto</a>
        <a href="#" onclick="mostrarCarrito()">🛒 Carrito</a>
    </nav>
</header>

<section class="hero" id="inicio">
    <h2>Tu nube, tu estilo 💨</h2>
    <p>Explora la mejor colección de vapes, waxs y sabores únicos. Envíos a todo México 🇲🇽.</p>
    <a href="#productos" class="btn">Ver catálogo</a>
</section>

<section class="productos" id="productos">
    <div class="producto">
        <img src="https://images.unsplash.com/photo-1600959907703-9e66e4bdfd1b" alt="Vape 1">
        <h3>Ice Blueberry</h3>
        <p>Sabores fríos y frutales con 5000 puffs.</p>
        <p><strong>$249 MXN</strong></p>
        <button class="btn" onclick="agregarCarrito('Ice Blueberry', 249)">Agregar al carrito</button>
    </div>

    <div class="producto">
        <img src="https://images.unsplash.com/photo-1622653903906-5f0e6b15d79f" alt="Vape 2">
        <h3>Mango Blast</h3>
        <p>Toque tropical en cada puff.</p>
        <p><strong>$249 MXN</strong></p>
        <button class="btn" onclick="agregarCarrito('Mango Blast', 249)">Agregar al carrito</button>
    </div>

    <div class="producto">
        <img src="https://images.unsplash.com/photo-1610917039356-9ecdd17c8e8c" alt="Vape 3">
        <h3>Cotton Candy</h3>
        <p>Dulce, suave y con un sabor inolvidable.</p>
        <p><strong>$249 MXN</strong></p>
        <button class="btn" onclick="agregarCarrito('Cotton Candy', 249)">Agregar al carrito</button>
    </div>

    <div class="producto">
        <img src="https://images.unsplash.com/photo-1622445273998-0a5a63b89d44" alt="Waxs">
        <h3>Waxs Premium</h3>
        <p>Concentrado intenso, máxima potencia y pureza garantizada.</p>
        <p><strong>$499 MXN</strong></p>
        <button class="btn" onclick="agregarCarrito('Waxs Premium', 499)">Agregar al carrito</button>
    </div>
</section>

<!-- Carrito -->
<div id="carrito">
    <h3>🛒 Tu Carrito</h3>
    <div id="lista-carrito"></div>
    <p><strong>Total: $<span id="total">0</span> MXN</strong></p>
    <a id="btn-whatsapp" href="#" target="_blank">Pedir por WhatsApp</a>
</div>

<footer id="contacto">
    <p>📍 Envíos a todo México | 💬 WhatsApp: 
        <a href="https://wa.me/528133796301?text=Hola%20Mielsita!%20Quiero%20más%20información%20sobre%20los%20vapes.">
            +52 81 3379 6301
        </a>
    </p>
    <p>© 2025 Mielsita Vapes - Todos los derechos reservados.</p>
</footer>

<script>
    let carrito = [];
    let total = 0;

    function agregarCarrito(nombre, precio) {
        carrito.push({ nombre, precio });
        total += precio;
        actualizarCarrito();
        mostrarCarrito();
    }

    function mostrarCarrito() {
        const contenedor = document.getElementById('carrito');
        contenedor.style.display = 'block';
        actualizarCarrito();
    }

    function actualizarCarrito() {
        const lista = document.getElementById('lista-carrito');
        lista.innerHTML = carrito.map(p => `<p>${p.nombre} - $${p.precio} MXN</p>`).join('');
        document.getElementById('total').innerText = total;

        const mensaje = carrito.map(p => `${p.nombre} - $${p.precio} MXN`).join('%0A');
        const numero = "528133796301"; // Tu número real
        document.getElementById('btn-whatsapp').href = `https://wa.me/${numero}?text=Hola%20Mielsita!%20Quiero%20hacer%20un%20pedido:%0A${mensaje}%0A%0ATotal:%20$${total}%20MXN`;
    }
</script>

</body>
</html>
