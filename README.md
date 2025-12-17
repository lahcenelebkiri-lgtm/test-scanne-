# test-scanne-
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Test Scan Carte Embarquement</title>
  <script src="https://unpkg.com/html5-qrcode"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 20px;
    }
    #reader {
      width: 100%;
      max-width: 400px;
      margin: auto;
    }
    .card {
      background: white;
      padding: 15px;
      margin-top: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

<h2>📷 Scan carte d’embarquement (TEST)</h2>

<div id="reader"></div>

<div id="result" class="card" style="display:none;">
  <h3>✈️ Informations passager</h3>
  <p><strong>Données scannées :</strong></p>
  <pre id="data"></pre>
</div>

<script>
  function onScanSuccess(decodedText) {
    document.getElementById("result").style.display = "block";
    document.getElementById("data").textContent = decodedText;
  }

  new Html5Qrcode("reader").start(
    { facingMode: "environment" },
    { fps: 10, qrbox: 250 },
    onScanSuccess
  );
</script>

</body>
</html>
