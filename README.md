# WiFi-ESP32
<!DOCTYPE html>
<html>
<head>
  <title>Controle de Lâmpada</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }

    .button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }

    .button-label {
      font-size: 20px;
    }

    #ligar-button {
      background-color: green;
      color: white;
    }

    #subir-button {
      background-color: blue;
      color: white;
    }

    #descer-button {
      background-color: orange;
      color: white;
    }
  </style>
</head>
<body>
  <h1>Controle de Lâmpada</h1>

  <button class="button" id="ligar-button"><span class="button-label">Ligar</span></button>
  <button class="button" id="subir-button"><span class="button-label">Subir</span></button>
  <button class="button" id="descer-button"><span class="button-label">Descer</span></button>

  <script>
    // Função para ligar a lâmpada
    document.getElementById("ligar-button").addEventListener("click", function() {
      // Adicione a lógica para ligar ou desligar aqui
      var ligado = !document.getElementById("ligar-button").classList.contains("ligado");
      document.getElementById("ligar-button").classList.toggle("ligado", ligado);
      document.getElementById("ligar-button").innerText = ligado ? "Ligado" : "Ligar";
    });

    // Função para ligar a lâmpada por 14 segundos (Subir e Descer)
    function ligarPor14Segundos() {
      // Adicione a lógica para ligar a lâmpada por 14 segundos aqui
      document.getElementById("ligar-button").classList.add("ligado");
      document.getElementById("ligar-button").innerText = "Ligado";
      setTimeout(function() {
        document.getElementById("ligar-button").classList.remove("ligado");
        document.getElementById("ligar-button").innerText = "Ligar";
      }, 14000);
    }

    document.getElementById("subir-button").addEventListener("mousedown", ligarPor14Segundos);
    document.getElementById("descer-button").addEventListener("mousedown", ligarPor14Segundos);
  </script>
</body>
</html>
