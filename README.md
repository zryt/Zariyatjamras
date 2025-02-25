# Kalkulator Sederhana

Ini adalah kalkulator sederhana yang dibuat menggunakan HTML, CSS, dan JavaScript. Kalkulator ini memiliki fungsi dasar seperti penjumlahan, pengurangan, perkalian, pembagian, dan menghitung hasil dari ekspresi matematika.

## Fitur

- Menjumlahkan angka
- Mengurangi angka
- Mengalikan angka
- Membagi angka
- Menampilkan hasil perhitungan secara real-time
- Tombol "C" untuk menghapus input

## Teknologi yang Digunakan

- **HTML**: Untuk struktur halaman
- **CSS**: Untuk desain dan tata letak
- **JavaScript**: Untuk logika perhitungan dan interaktivitas

## Cara Menggunakan

1. **Clone Repository** atau **Download** file ini ke komputer Anda.
2. Buka file `index.html` di browser pilihan Anda untuk mulai menggunakan kalkulator.
3. Masukkan angka dan operasi matematika di input, kemudian tekan tombol "=" untuk melihat hasilnya.

## codenya

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Sederhana</title>
    <style>
    body {
            font-family    : Arial, sans-serif; 
            display        : flex;
            justify-content: center; 
            align-items    : center; 
            height         : 100vh; 
            background-color: blue
        }
        .calculator {
            width: 300px;
            background-color: black;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
        }
        .calculator input {
            width: 100%;
            box-sizing: border-box;
            height: 40px;
            font-size: 20px;
            text-align: right;
            margin-bottom: 20px;
            padding: 10px;
            border-radius: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 8px;
        }
        .buttons button {
            background-color: white;
            font-size: 18px;
            padding: 20px;
            border-radius: 5px;
        }
        .buttons .hasil{
            grid-column: span 4;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display">

        <div class="buttons">
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>

            <button onclick="appendToDisplay('+')">+</button>

            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>

            <button onclick="appendToDisplay('*')">x</button>

            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>

            <button onclick="appendToDisplay('-')">-</button>

            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="clearDisplay   (   )">C</button>
            <button onclick="appendToDisplay('/')">/</button>
            
            <button class="hasil" onclick="calculateResult(   )">=</button>
        </div>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculateResult() {
            let display = document.getElementById('display').value;
            try {
                let result = eval(display);
                document.getElementById('display').value = result;
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>
</body>
</html>

