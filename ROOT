# Simulasi-Bank
bank sederhana
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Dashboard Bank Simulasi</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f5f5f5;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #2b3d51;
      color: white;
      padding: 20px;
      text-align: center;
    }
    .container {
      max-width: 600px;
      margin: 30px auto;
      padding: 20px;
      background: white;
      border-radius: 8px;
      box-shadow: 0 0 12px rgba(0,0,0,0.1);
    }
    h2 {
      color: #2b3d51;
    }
    .saldo {
      font-size: 1.8rem;
      margin: 10px 0 20px;
      color: green;
    }
    label, input, button {
      display: block;
      width: 100%;
      margin-bottom: 15px;
    }
    input {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    button {
      background-color: #2b3d51;
      color: white;
      border: none;
      padding: 12px;
      border-radius: 6px;
      font-size: 1rem;
      cursor: pointer;
    }
    button:hover {
      background-color: #1e2e3d;
    }
    .riwayat {
      margin-top: 30px;
    }
    .riwayat ul {
      list-style: none;
      padding-left: 0;
    }
    .riwayat li {
      border-bottom: 1px solid #ddd;
      padding: 10px 0;
    }
    .error {
      color: red;
      font-size: 0.9rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Bank Simulasi</h1>
  </header>
  <div class="container">
    <h2>Halo, Budi</h2>
    <div class="saldo" id="saldo">Saldo Anda: Rp. 2.500.000</div>

    <h3>Transfer Dana</h3>
    <form id="formTransfer">
      <label for="tujuan">Rekening Tujuan</label>
      <input type="text" id="tujuan" placeholder="Masukkan No. Rekening" required>

      <label for="jumlah">Jumlah Transfer (Rp)</label>
      <input type="number" id="jumlah" placeholder="Masukkan jumlah" required min="1">

      <button type="submit">Kirim</button>
      <p class="error" id="errorMsg"></p>
    </form>

    <div class="riwayat">
      <h3>Riwayat Transaksi</h3>
      <ul id="daftarRiwayat"></ul>
    </div>
  </div>

  <script>
    let saldo = 2500000;
    const form = document.getElementById('formTransfer');
    const saldoEl = document.getElementById('saldo');
    const riwayatEl = document.getElementById('daftarRiwayat');
    const errorMsg = document.getElementById('errorMsg');

    function formatRupiah(angka) {
      return angka.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".");
    }

    function updateSaldo() {
      saldoEl.textContent = "Saldo Anda: Rp. " + formatRupiah(saldo);
    }

    form.addEventListener('submit', function(e) {
      e.preventDefault();
      const tujuan = document.getElementById('tujuan').value.trim();
      const jumlah = parseInt(document.getElementById('jumlah').value);

      if (!tujuan || isNaN(jumlah) || jumlah <= 0) {
        errorMsg.textContent = "Harap isi data yang benar.";
        return;
      }

      if (jumlah > saldo) {
        errorMsg.textContent = "Saldo tidak mencukupi.";
        return;
      }

      // Simulasi berhasil
      saldo -= jumlah;
      updateSaldo();
      errorMsg.textContent = "";

      // Tambahkan ke riwayat
      const li = document.createElement('li');
      li.textContent = `➜ Transfer ke ${tujuan} - Rp ${formatRupiah(jumlah)}`;
      riwayatEl.prepend(li);

      // Reset form
      form.reset();
    });

    // Inisialisasi tampilan awal
    updateSaldo();
  </script>
</body>
</html>
