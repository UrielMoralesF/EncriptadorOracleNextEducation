<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background: linear-gradient(to bottom right, #4CAF50, #00BCD4);
        }

        h1 {
            text-align: center;
            color: white;
        }

        .container {
            max-width: 400px;
            margin: 0 auto;
            background-color: white;
            padding: 20px;
            border-radius: 8px;
        }

        label {
            display: block;
            margin-top: 10px;
        }

        textarea {
            width: 100%;
            height: 150px;
            margin-top: 5px;
        }

        button {
            margin-top: 10px;
            padding: 8px 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }

        .button-clear {
            background-color: #f44336;
        }
    </style>
</head>

<body>
    <div class="container">
        <h1 style="color: rgb(1, 107, 45)">Encriptador de Texto de Uriel Morales</h1>
        <label for=" original-text">Texto Original:</label>
        <textarea id="original-text" placeholder="Ingresa tu texto a encriptar"></textarea>
        <label for="encrypted-text">Texto Encriptado:</label>
        <textarea id="encrypted-text" readonly></textarea>
        <label for="decrypted-text">Texto Desencriptado:</label>
        <textarea id="decrypted-text" readonly></textarea>
        <button onclick="encryptText()">Encriptar</button>
        <button onclick="decryptText()">Desencriptar</button>
        <button class="button-clear" onclick="clearText()">Limpiar</button>
    </div>

    <script>
        function encryptText() {
            var originalText = document.getElementById('original-text').value;
            var encryptedText = '';

            // Lógica de encriptación (puedes usar cualquier algoritmo aquí)
            for (var i = 0; i < originalText.length; i++) {
                var charCode = originalText.charCodeAt(i);
                encryptedText += String.fromCharCode(charCode + 1);
            }

            document.getElementById('encrypted-text').value = encryptedText;
            document.getElementById('decrypted-text').value = ''; // Limpiar el campo de texto desencriptado
        }

        function decryptText() {
            var encryptedText = document.getElementById('encrypted-text').value;
            var decryptedText = '';

            // Lógica de desencriptación (debe ser el inverso del algoritmo de encriptación)
            for (var i = 0; i < encryptedText.length; i++) {
                var charCode = encryptedText.charCodeAt(i);
                decryptedText += String.fromCharCode(charCode - 1);
            }

            document.getElementById('original-text').value = ''; // Limpiar el campo de texto original
            document.getElementById('decrypted-text').value = decryptedText;
        }

        function clearText() {
            document.getElementById('original-text').value = '';
            document.getElementById('encrypted-text').value = '';
            document.getElementById('decrypted-text').value = '';
        }
    </script>
</body>

</html>
