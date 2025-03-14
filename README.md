# website-hasilkan-uang
hasilkan uang
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toko Buah Segar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 15px;
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin: 20px;
        }
        .buah {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 15px;
            margin: 10px;
            width: 200px;
            text-align: center;
            box-shadow: 2px 2px 12px rgba(0,0,0,0.1);
        }
        .buah img {
            width: 100%;
            border-radius: 5px;
        }
        .button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Selamat Datang di Toko Buah Segar</h1>
    </header>
    <div class="container">
        <div class="buah">
            <img src="apple.jpg" alt="Apel">
            <h2>Apel</h2>
            <p>Harga: Rp 10.000/kg</p>
            <button class="button">Beli</button>
        </div>
        <div class="buah">
            <img src="banana.jpg" alt="Pisang">
            <h2>Pisang</h2>
            <p>Harga: Rp 8.000/kg</p>
            <button class="button">Beli</button>
        </div>
        <div class="buah">
            <img src="orange.jpg" alt="Jeruk">
            <h2>Jeruk</h2>
            <p>Harga: Rp 12.000/kg</p>
            <button class="button">Beli</button>
        </div>
    </div>
</body>
</html>
