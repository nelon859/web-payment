<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Metode Pembayaran</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Inter', sans-serif;
      background: linear-gradient(to right, #1f2937, #4b5563);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 30px 15px;
    }

    .container {
      background: #111827;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
      max-width: 400px;
      width: 100%;
      text-align: center;
    }

    h1 {
      margin-bottom: 25px;
      font-size: 2rem;
      color: #60a5fa;
    }

    .payment-method {
      background-color: #1f2937;
      border: 1px solid #374151;
      border-radius: 10px;
      padding: 15px 20px;
      margin-bottom: 15px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .method-info {
      text-align: left;
    }

    .method-name {
      font-weight: bold;
      font-size: 1.1rem;
      color: #93c5fd;
    }

    .method-number {
      font-size: 1rem;
      color: #e5e7eb;
    }

    .copy-btn {
      background-color: #3b82f6;
      border: none;
      color: white;
      padding: 8px 12px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: background-color 0.3s ease;
    }

    .copy-btn:hover {
      background-color: #2563eb;
    }

    .qris-section {
      margin-top: 25px;
    }

    .qris-section img {
      width: 100%;
      max-width: 250px;
      border-radius: 12px;
      border: 2px solid #374151;
    }

    .zoom-btn {
      margin-top: 10px;
      background-color: #10b981;
      border: none;
      padding: 8px 14px;
      border-radius: 8px;
      color: #fff;
      cursor: pointer;
      font-size: 0.9rem;
    }

    .zoom-btn:hover {
      background-color: #059669;
    }

    /* Modal styles */
    .modal {
      display: none;
      position: fixed;
      z-index: 999;
      padding-top: 60px;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0,0,0,0.8);
    }

    .modal-content {
      margin: auto;
      display: block;
      max-width: 90%;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 35px;
      color: #fff;
      font-size: 35px;
      font-weight: bold;
      cursor: pointer;
    }

    .close:hover {
      color: #f87171;
    }
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="soun/1.mp3" type="soun/mp3">
    </audio>
  <div class="container">
    <h1>Payment Kyo Store</h1>

    <div class="payment-method">
      <div class="method-info">
        <div class="method-name">DANA</div>
        <div class="method-number" id="dana">085714353387</div>
      </div>
      <button class="copy-btn" onclick="copyToClipboard('dana')">Copy</button>
    </div>

    <div class="payment-method">
      <div class="method-info">
        <div class="method-name">Gopay</div>
        <div class="method-number" id="gopay">TIDAK PUNYA</div>
      </div>
      <button class="copy-btn" onclick="copyToClipboard('gopay')">Copy</button>
    </div>

    <div class="payment-method">
      <div class="method-info">
        <div class="method-name">OVO</div>
        <div class="method-number" id="ovo">TIDAK PUNYA</div>
      </div>
      <button class="copy-btn" onclick="copyToClipboard('ovo')">Copy</button>
    </div>

    <div class="qris-section">
      <img src="https://img1.pixhost.to/images/7732/629155974_uploaded_image.jpg" alt="QRIS" id="qrisImage">
      <button class="zoom-btn" onclick="openModal()">Perbesar QRIS</button>
    </div>
  </div>

  <!-- Modal QRIS -->
  <div id="qrisModal" class="modal">
    <span class="close" onclick="closeModal()">&times;</span>
    <img class="modal-content" id="qrisFullImage" src="https://files.catbox.moe/7yokm2.jpg alt="QRIS Full">
  </div>

  <script>
    function copyToClipboard(id) {
      const text = document.getElementById(id).innerText;
      navigator.clipboard.writeText(text).then(() => {
        alert(id.toUpperCase() + ' berhasil disalin: ' + text);
      });
    }

    function openModal() {
      document.getElementById("qrisModal").style.display = "block";
    }

    function closeModal() {
      document.getElementById("qrisModal").style.display = "none";
    }

    // Tutup modal jika klik di luar gambar
    window.onclick = function(event) {
      const modal = document.getElementById("qrisModal");
      if (event.target === modal) {
        modal.style.display = "none";
      }
    }
  </script>
</body>
</html>
