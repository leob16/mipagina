<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cuadrado 3x3 con Modal</title>
    <style>
        /* Fondo con GIF */
        body {
            background-image: url('img/mariposas.gif'); /* Cambia la imagen de fondo */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Contenedor del Grid */
        .contenedor {
            display: grid;
            grid-template-columns: repeat(3, 150px);
            grid-template-rows: repeat(3, 150px);
            gap: 10px;
            background: rgba(0, 0, 0, 0.5);
            padding: 15px;
            border-radius: 10px;
        }

        /* Cada celda con imagen */
        .celda {
            width: 150px;
            height: 150px;
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer; /* Hace que se vea clickeable */
        }

        /* Ajuste de las imágenes */
        .celda img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        /* Efecto hover */
        .celda img:hover {
            transform: scale(1.1);
        }

        /* 🔹 Modal para mostrar la imagen ampliada */
        .modal {
            display: none; /* Oculto por defecto */
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
        }

        /* Imagen dentro del modal */
        .modal img {
            max-width: 90%;
            max-height: 90%;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
        }

        /* Botón para cerrar */
        .cerrar {
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 30px;
            color: white;
            cursor: pointer;
        }

    </style>
</head>
<body>

    <!-- Grid de imágenes -->
    <div class="contenedor">
        <div class="celda"><img src="img/1.jfif" alt="Imagen 1" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/2.jfif" alt="Imagen 2" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/3.jfif" alt="Imagen 3" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/4.jfif" alt="Imagen 4" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/carta.png" alt="Imagen 5" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/5.jfif" alt="Imagen 6" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/6.jfif" alt="Imagen 7" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/7.jfif" alt="Imagen 8" onclick="mostrarImagen(this)"></div>
        <div class="celda"><img src="img/8.jfif" alt="Imagen 9" onclick="mostrarImagen(this)"></div>
    </div>

    <!-- Modal para imagen ampliada -->
    <div class="modal" id="modal">
        <span class="cerrar" onclick="cerrarModal()">&times;</span>
        <img id="imagenModal">
    </div>

    <script>
        // Función para mostrar la imagen en el modal
        function mostrarImagen(imagen) {
            document.getElementById("imagenModal").src = imagen.src;
            document.getElementById("modal").style.display = "flex";
        }

        // Función para cerrar el modal
        function cerrarModal() {
            document.getElementById("modal").style.display = "none";
        }
    </script>


</body>
</html>
