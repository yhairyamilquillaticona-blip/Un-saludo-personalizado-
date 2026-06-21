# Saludo-personalizado-
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Saludo Personalizado</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .container {
            background: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            text-align: center;
            max-width: 400px;
            width: 90%;
        }

        h1 {
            color: #333;
            margin-bottom: 30px;
            font-size: 28px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            color: #555;
            margin-bottom: 8px;
            font-weight: 500;
        }

        input {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        input:focus {
            outline: none;
            border-color: #667eea;
        }

        button {
            width: 100%;
            padding: 12px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s;
        }

        button:hover {
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
        }

        .resultado {
            margin-top: 30px;
            padding: 20px;
            background: #f0f4ff;
            border-radius: 5px;
            display: none;
            animation: slideIn 0.3s ease;
        }

        .resultado.mostrar {
            display: block;
        }

        .resultado i {
            font-size: 40px;
            color: #667eea;
            margin-bottom: 10px;
        }

        .saludo-texto {
            font-size: 24px;
            color: #333;
            font-weight: 600;
        }

        .mensaje {
            font-size: 14px;
            color: #666;
            margin-top: 10px;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>👋 Saludo Personalizado</h1>
        
        <div class="form-group">
            <label for="nombre">Ingresa tu nombre</label>
            <input 
                type="text" 
                id="nombre" 
                placeholder="Ej: Arya Camila"
                autocomplete="off"
            >
        </div>

        <button onclick="generarSaludo()">Saludar</button>

        <div class="resultado" id="resultado">
            <div style="font-size: 40px; margin-bottom: 10px;">ℹ️</div>
            <div class="saludo-texto" id="saludoTexto"></div>
            <div class="mensaje">¡Bienvenido!</div>
        </div>
    </div>

    <script>
        const inputNombre = document.getElementById('nombre');
        const divResultado = document.getElementById('resultado');
        const saludoTexto = document.getElementById('saludoTexto');

        function generarSaludo() {
            const nombre = inputNombre.value.trim();

            if (nombre === '') {
                alert('Por favor, ingresa tu nombre');
                inputNombre.focus();
                return;
            }

            saludoTexto.textContent = `¡Hola ${nombre}, bienvenido!`;
            divResultado.classList.add('mostrar');
        }

        // Permitir envío con Enter
        inputNombre.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                generarSaludo();
            }
        });

        // Limpiar resultado cuando se escribe nuevo nombre
        inputNombre.addEventListener('input', () => {
            divResultado.classList.remove('mostrar');
        });
    </script>
</body>
</html>
