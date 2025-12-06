[deepseek_html_20251206_55d7c6.html](https://github.com/user-attachments/files/24003876/deepseek_html_20251206_55d7c6.html)
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ujian Metabolisme Zat Gizi Pangan (PANG 4223)</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            padding: 30px;
        }
        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 3px solid #4a6fa5;
        }
        h1 {
            color: #2c3e50;
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        .subtitle {
            color: #7f8c8d;
            font-size: 1.1rem;
        }
        .timer {
            background: #2c3e50;
            color: white;
            padding: 15px;
            border-radius: 10px;
            font-size: 1.5rem;
            text-align: center;
            margin-bottom: 20px;
            font-weight: bold;
        }
        .question-container {
            margin-bottom: 25px;
            padding: 20px;
            border-radius: 15px;
            background: #f8f9fa;
            border-left: 5px solid #4a6fa5;
            display: none;
        }
        .question-container.active {
            display: block;
            animation: fadeIn 0.5s;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .question-number {
            font-size: 1.1rem;
            color: #4a6fa5;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .question-text {
            font-size: 1.2rem;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        .options {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        .option {
            padding: 15px;
            background: white;
            border: 2px solid #ddd;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1rem;
        }
        .option:hover {
            background: #eef2f7;
            border-color: #a3b1cc;
        }
        .option.selected {
            background: #d4edda;
            border-color: #28a745;
            color: #155724;
        }
        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }
        button {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: background 0.3s;
            font-weight: bold;
        }
        .prev-btn {
            background: #6c757d;
            color: white;
        }
        .prev-btn:hover {
            background: #545b62;
        }
        .next-btn {
            background: #4a6fa5;
            color: white;
        }
        .next-btn:hover {
            background: #3a577d;
        }
        .submit-btn {
            background: #28a745;
            color: white;
            margin-left: auto;
        }
        .submit-btn:hover {
            background: #218838;
        }
        .result-container {
            display: none;
            padding: 30px;
            background: #f8f9fa;
            border-radius: 15px;
            margin-top: 30px;
        }
        .result-title {
            font-size: 1.8rem;
            color: #2c3e50;
            margin-bottom: 20px;
            text-align: center;
        }
        .score {
            font-size: 2.5rem;
            color: #28a745;
            text-align: center;
            margin: 20px 0;
            font-weight: bold;
        }
        .score-detail {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 30px;
        }
        .wrong-answers {
            margin-top: 30px;
        }
        .wrong-title {
            font-size: 1.4rem;
            color: #dc3545;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #dc3545;
        }
        .wrong-item {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border-left: 5px solid #dc3545;
        }
        .wrong-question {
            font-weight: bold;
            margin-bottom: 10px;
            color: #2c3e50;
        }
        .your-answer {
            color: #dc3545;
            margin-bottom: 5px;
        }
        .correct-answer {
            color: #28a745;
            margin-bottom: 10px;
        }
        .explanation {
            background: #f8d7da;
            padding: 15px;
            border-radius: 8px;
            color: #721c24;
            line-height: 1.5;
        }
        .progress-bar {
            height: 10px;
            background: #e9ecef;
            border-radius: 5px;
            margin-bottom: 20px;
            overflow: hidden;
        }
        .progress {
            height: 100%;
            background: #4a6fa5;
            width: 0%;
            transition: width 0.5s;
        }
        footer {
            text-align: center;
            margin-top: 30px;
            color: #7f8c8d;
            font-size: 0.9rem;
            padding-top: 20px;
            border-top: 1px solid #ddd;
        }
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            h1 {
                font-size: 1.8rem;
            }
            .question-text {
                font-size: 1.1rem;
            }
            .nav-buttons {
                flex-direction: column;
                gap: 10px;
            }
            button {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Ujian Metabolisme Zat Gizi Pangan (PANG 4223)</h1>
            <p class="subtitle">Tes Formatif Modul 1 & 2 - 50 Soal Pilihan Ganda</p>
        </header>

        <div class="timer" id="timer">Waktu: 60:00</div>
        
        <div class="progress-bar">
            <div class="progress" id="progress"></div>
        </div>

        <div id="question-wrapper">
            <!-- Soal akan di-generate oleh JavaScript -->
        </div>

        <div class="nav-buttons">
            <button class="prev-btn" id="prev-btn">← Sebelumnya</button>
            <button class="next-btn" id="next-btn">Selanjutnya →</button>
            <button class="submit-btn" id="submit-btn">Selesai & Lihat Nilai</button>
        </div>

        <div class="result-container" id="result-container">
            <h2 class="result-title">Hasil Ujian Anda</h2>
            <div class="score" id="score">0</div>
            <p class="score-detail" id="score-detail">Benar: 0 | Salah: 0</p>
            
            <div class="wrong-answers" id="wrong-answers-container">
                <h3 class="wrong-title">Pembahasan Jawaban Salah</h3>
                <!-- Daftar jawaban salah akan dimasukkan di sini -->
            </div>
        </div>
    </div>

    <footer>
        &copy; 2025 Ujian Online PANG 4223 - Metabolisme Zat Gizi Pangan
    </footer>

    <script>
        // Data soal dari Tes Formatif Modul 1 & 2
        const questions = [
            // Modul 1 - Tes Formatif 1 (10 soal pertama)
            {
                question: "Zat gizi sumber energi adalah sebagai berikut, kecuali ...",
                options: ["Vitamin", "Karbohidrat (pati, gula)", "Lemak", "Protein"],
                correct: 0,
                explanation: "Vitamin bukan sumber energi. Sumber energi adalah karbohidrat, lemak, dan protein. Vitamin berfungsi sebagai ko-enzim dalam reaksi metabolisme."
            },
            {
                question: "Energi yang terkandung dalam makanan/minuman disebut sebagai ...",
                options: ["Energi pembakaran", "Energi kalorimeter", "Energi basal", "SDA makanan"],
                correct: 0,
                explanation: "Energi pembakaran adalah energi yang dihasilkan dari pembakaran sempurna makanan dalam bomb calorimeter."
            },
            {
                question: "Energi fisiologis adalah energi yang terkandung dalam makanan dikoreksi dengan ...",
                options: ["Daya cerna dan kehilangan dalam urine", "Panas dan daya cerna", "Metabolisme dan kehilangan dalam urine", "Kehilangan dalam urine dan panas"],
                correct: 0,
                explanation: "Energi fisiologis = energi pembakaran dikoreksi daya cerna dan kehilangan energi dalam urine (khusus protein menjadi urea)."
            },
            {
                question: "Energi yang terbuang dalam urine bersal dari zat gizi ...",
                options: ["Karbohidrat", "Lemak", "Protein", "Air"],
                correct: 2,
                explanation: "Protein menghasilkan urea yang diekskresikan lewat urine, membawa energi sekitar 1.2 kkal/g protein."
            },
            {
                question: "Metabolisme basal harus diukur pada kondisi seseorang ...",
                options: ["Istirahat total, fisik, dan mental", "Post absorptive (12 jam setelah makan)", "Suhu tubuh normal", "Semuanya benar"],
                correct: 3,
                explanation: "Metabolisme basal diukur saat istirahat fisik & mental, post absorptive (12 jam setelah makan), dan suhu tubuh normal."
            },
            {
                question: "Berat badan biologis adalah berat badan ...",
                options: ["Seseorang yang normal", "Seseorang sewaktu istirahat total", "Normal pangkat 0,75", "Seseorang tanpa pakaian"],
                correct: 2,
                explanation: "Berat badan biologis = berat badan (kg)^0.75, disebut juga metabolic body size."
            },
            {
                question: "SDA makanan adalah ...",
                options: ["Energi yang diperlukan untuk mengunyah makanan", "Energi yang diperlukan untuk mencerna makanan", "Energi yang diperlukan untuk mencerna dan metabolisme makanan", "Semuanya benar"],
                correct: 2,
                explanation: "Specific Dynamic Action (SDA) adalah energi tambahan yang diperlukan untuk mencerna, menyerap, dan memetabolisme makanan."
            },
            {
                question: "Energi aktivitas adalah ...",
                options: ["Energi yang diperlukan untuk bekerja", "Energi yang diperlukan selama 24 jam", "Energi yang diperlukan untuk semua aktivitas tubuh", "Semuanya benar"],
                correct: 2,
                explanation: "Energi aktivitas adalah energi untuk semua aktivitas fisik otot, ditambah peningkatan denyut jantung dan pernapasan."
            },
            {
                question: "Energi yang dibutuhkan seseorang dalam sehari adalah ...",
                options: ["Penjumlahan basal metabolisme dan energi aktivitas", "Penjumlahan SDA makanan dan energi aktivitas", "Basal metabolisme + SDA makanan + energi aktivitas", "Tidak ada yang benar"],
                correct: 2,
                explanation: "Kebutuhan energi total = metabolisme basal + energi aktivitas + SDA (thermic effect) makanan."
            },
            {
                question: "Energi yang diperlukan oleh wanita hamil ...",
                options: ["Sama dengan wanita dewasa", "Sama dengan ibu menyusui", "Lebih besar dari wanita dewasa", "Tidak ada yang benar"],
                correct: 2,
                explanation: "Wanita hamil butuh tambahan energi sekitar 250–300 kkal/hari untuk pertumbuhan janin dan akumulasi lemak."
            },
            // Modul 1 - Tes Formatif 2 (soal 11–20)
            {
                question: "Kecukupan konsumsi karbohidrat (pati, gula) tidak dapat ditetapkan karena ...",
                options: ["Tidak ada peralatan yang sesuai untuk itu", "Adanya proses glukoneogenesis", "Angka kecukupannya sangat rendah", "Semuanya benar"],
                correct: 1,
                explanation: "Tubuh dapat membuat glukosa dari protein/lemak via glukoneogenesis, sehingga kebutuhan minimum karbohidrat sulit ditetapkan."
            },
            {
                question: "Seseorang menderita 'ketosis' karena ...",
                options: ["Kurang mengonsumsi sumber energi", "Oksidasi pati/gula yang tidak sempurna", "Oksidasi lemak yang tidak sempurna", "Oksidasi protein yang tidak sempurna"],
                correct: 2,
                explanation: "Ketosis terjadi akibat oksidasi lemak yang tidak sempurna, menghasilkan senyawa keton (aseton, asam asetoasetat, asam β-hidroksibutirat)."
            },
            {
                question: "Seseorang akan menderita oedema bila kekurangan konsumsi protein karena protein berfungsi untuk ...",
                options: ["Menjaga netralitas tubuh", "Regulasi keseimbangan air", "Pembentukan antibodi", "Alat transport zat gizi"],
                correct: 1,
                explanation: "Protein plasma menciptakan tekanan onkotik yang menjaga keseimbangan cairan. Defisiensi protein menyebabkan edema."
            },
            {
                question: "Yang menentukan jumlah protein (asam amino) makanan yang dapat diserap oleh usus dan masuk ke dalam tubuh adalah ...",
                options: ["Nilai cernanya (daya cernanya)", "Nilai PER-nya", "Komposisi asam aminonya", "Jumlah dan komposisi asam amino esensialnya"],
                correct: 0,
                explanation: "Daya cerna (digestibility) menentukan berapa % protein yang bisa diserap usus."
            },
            {
                question: "Yang menentukan bahwa protein (asam amino) yang telah diserap oleh usus dapat digunakan untuk sintesis protein tubuh adalah ...",
                options: ["Jumlah energi yang dikonsumsi", "Jenis protein yang dikonsumsi", "Jenis lemak yang dikonsumsi", "Jenis karbohidrat yang dikonsumsi"],
                correct: 0,
                explanation: "Kecukupan energi menentukan apakah asam amino digunakan untuk sintesis protein atau dioksidasi untuk energi."
            },
            {
                question: "Fungsi lemak dalam makanan adalah sebagai berikut, kecuali ...",
                options: ["Sebagai sumber energi", "Sebagai pelarut/pembawa vitamin ADEK", "Meningkatkan palatabilitas", "Sebagai insulator tubuh"],
                correct: 3,
                explanation: "Insulator tubuh adalah fungsi lemak dalam tubuh, bukan dalam makanan."
            },
            {
                question: "Fungsi lemak dalam tubuh adalah sebagai berikut, kecuali ...",
                options: ["Sebagai cadangan energi", "Menahan/menjaga organ tubuh yang vital", "Meningkatkan palatabilitas", "Sebagai insulator tubuh"],
                correct: 2,
                explanation: "Meningkatkan palatabilitas adalah fungsi lemak dalam makanan, bukan dalam tubuh."
            },
            {
                question: "Manusia tidak memerlukan konsumsi lemak, tetapi memerlukan asam lemak ...",
                options: ["Linoleat", "Palmitat", "Arakhidonat", "Stearat"],
                correct: 0,
                explanation: "Asam linoleat (omega-6) adalah asam lemak esensial yang harus didapat dari makanan."
            },
            {
                question: "Orang gemuk (menderita obesitas) disebabkan karena terlalu banyak mengonsumsi ...",
                options: ["Lemak", "Pati dan gula", "Protein", "Semuanya benar"],
                correct: 3,
                explanation: "Obesitas disebabkan kelebihan energi dari lemak, karbohidrat, atau protein."
            },
            {
                question: "Konsumsi protein secara berlebihan tidak menguntungkan karena ...",
                options: ["Makanan sumber protein harganya mahal", "Tidak efisien sebagai bahan untuk sintesis protein tubuh", "Mengakibatkan kerja ginjal berlebihan untuk membuang urea", "Semuanya benar"],
                correct: 3,
                explanation: "Kelebihan protein meningkatkan beban ginjal (urea), mahal, dan tidak efisien untuk sintesis protein."
            },
            // Modul 1 - Tes Formatif 3 (soal 21–30)
            {
                question: "Defisiensi vitamin ini dapat menimbulkan beri-beri adalah ...",
                options: ["Vitamin B2", "Vitamin B12", "Vitamin B1", "Asam folat"],
                correct: 2,
                explanation: "Beri-beri disebabkan defisiensi tiamin (vitamin B1)."
            },
            {
                question: "Defisiensi vitamin ini dapat menimbulkan anemia megaloblastik adalah ...",
                options: ["Vitamin B2", "Vitamin B12", "Vitamin B1", "Asam folat"],
                correct: 1,
                explanation: "Anemia megaloblastik disebabkan defisiensi vitamin B12 atau asam folat."
            },
            {
                question: "Vitamin ini dapat meningkatkan penyerapan zat besi dalam usus adalah ...",
                options: ["Vitamin A", "Vitamin B2", "Vitamin C", "Vitamin D"],
                correct: 2,
                explanation: "Vitamin C mereduksi Fe³⁺ menjadi Fe²⁺ yang lebih mudah diserap."
            },
            {
                question: "Rabun senja disebabkan karena kekurangan ...",
                options: ["Vitamin A", "Vitamin B2", "Vitamin C", "Vitamin D"],
                correct: 0,
                explanation: "Rabun senja (night blindness) adalah gejala awal defisiensi vitamin A."
            },
            {
                question: "Vitamin ini berfungsi pada pembentukan tulang dan gigi adalah ...",
                options: ["Vitamin A", "Vitamin B2", "Vitamin C", "Vitamin D"],
                correct: 3,
                explanation: "Vitamin D meningkatkan absorpsi kalsium dan fosfor untuk mineralisasi tulang dan gigi."
            },
            {
                question: "Konsumsi protein yang berlebihan akan meningkatkan ekskresi mineral ini dalam urine adalah ...",
                options: ["Kalium (K)", "Kalsium (Ca)", "Natrium (Na)", "Magnesium (Mg)"],
                correct: 1,
                explanation: "Protein meningkatkan ekskresi kalsium urine karena metabolisme asam amino menghasilkan ion H⁺."
            },
            {
                question: "Mineral ini antara lain berfungsi untuk membentuk sel darah merah adalah ...",
                options: ["Seng (Zn)", "Selenium (Se)", "Besi (Fe)", "Fosfor (P)"],
                correct: 2,
                explanation: "Besi adalah komponen hemoglobin dalam sel darah merah."
            },
            {
                question: "Mineral ini antara lain berfungsi dalam sintesis RNA, DNA dan protein adalah ...",
                options: ["Seng (Zn)", "Selenium (Se)", "Besi (Fe)", "Fosfor (P)"],
                correct: 0,
                explanation: "Seng (Zn) adalah kofaktor >70 enzim, termasuk enzim sintesis DNA, RNA, dan protein."
            },
            {
                question: "Konsumsi mineral ini secara berlebihan dapat menimbulkan hipertensi adalah ...",
                options: ["Kalium (K)", "Kalsium (Ca)", "Natrium (Na)", "Magnesium (Mg)"],
                correct: 2,
                explanation: "Kelebihan natrium (garam) meningkatkan retensi air dan tekanan darah."
            },
            {
                question: "Kekurangan mineral ini dapat menimbulkan kekerdilan dan keterbelakangan mental adalah ...",
                options: ["Tembaga (Cu)", "Iodium (I)", "Chromium (Cr)", "Mangan (Mn)"],
                correct: 1,
                explanation: "Defisiensi iodium menyebabkan gondok, kretinisme (kekerdilan), dan retardasi mental."
            },
            // Modul 2 - Tes Formatif 1 (soal 31–40)
            {
                question: "Sel-sel epitel permukaan dalam lambung yang memproduksi enzim pepsin adalah ...",
                options: ["Mucous cells", "Parietal cells", "G cells", "Chief cells"],
                correct: 3,
                explanation: "Chief cells mensekresikan pepsinogen (prekursor pepsin)."
            },
            {
                question: "Sel-sel epitel permukaan dalam lambung yang memproduksi hormon gastrin adalah ...",
                options: ["Mucous cells", "Parietal cells", "G cells", "Chief cells"],
                correct: 2,
                explanation: "G cells mensekresikan hormon gastrin yang merangsang sekresi asam lambung."
            },
            {
                question: "Lapisan terluar dinding saluran pencernaan adalah Tunika ...",
                options: ["Serosa", "Muskularis", "Submukosa", "Mukosa"],
                correct: 0,
                explanation: "Tunika serosa adalah lapisan terluar saluran pencernaan."
            },
            {
                question: "Mikroflora usus besar yang dikatakan sebagai 'bakteri baik' adalah ...",
                options: ["Lactobacillus sp.", "Streptococcus sp.", "Clostridium sp.", "Tidak ada yang benar"],
                correct: 0,
                explanation: "Lactobacillus sp. adalah bakteri asam laktat yang menguntungkan (probiotik)."
            },
            {
                question: "Mikroflora usus besar yang dikatakan sebagai 'bakteri jahat' adalah ...",
                options: ["Lactobacillus sp.", "Streptococcus sp.", "Clostridium sp.", "Tidak ada yang benar"],
                correct: 2,
                explanation: "Clostridium sp. dapat menghasilkan toksin dan gas berlebihan."
            },
            {
                question: "Sel-sel pankreas yang memproduksi hormon insulin adalah ...",
                options: ["Sel-sel A", "Sel-sel B", "Sel-sel C", "Sel-sel D"],
                correct: 1,
                explanation: "Sel beta (B) pulau Langerhans mensekresikan insulin."
            },
            {
                question: "Sel-sel pankreas yang memproduksi enzim-enzim pencernaan adalah ...",
                options: ["Sel-sel A", "Sel-sel B", "Sel-sel C", "Sel-sel D"],
                correct: 3,
                explanation: "Sel asinar (D) mensekresikan enzim pencernaan seperti amilase, lipase, protease."
            },
            {
                question: "Fungsi hati dalam metabolisme zat gizi adalah sebagai berikut, kecuali ...",
                options: ["Sintesis asam amino esensial", "Sintesis protein plasma", "Pembentukan glikogen dari gula darah", "Sintesis urea"],
                correct: 0,
                explanation: "Hati tidak dapat mensintesis asam amino esensial; harus diperoleh dari makanan."
            },
            {
                question: "Fungsi cairan empedu adalah ...",
                options: ["Emulsifikasi lemak", "Eliminasi kolesterol", "Menetralkan asam (chyme)", "Semuanya benar"],
                correct: 3,
                explanation: "Cairan empedu berfungsi emulsifikasi lemak, ekskresi kolesterol, dan menetralkan asam lambung."
            },
            {
                question: "Secara garis besar, bagian usus yang paling banyak mengandung bakteri adalah ...",
                options: ["Duodenum", "Jejunum", "Ileum", "Colon"],
                correct: 3,
                explanation: "Kolon (usus besar) mengandung populasi bakteri tertinggi (10¹⁰–10¹² per gram)."
            },
            // Modul 2 - Tes Formatif 2 (soal 41–50)
            {
                question: "Sekresi cairan lambung diprakarsai oleh ...",
                options: ["Mekanisme nervous atau refleks", "Hormon gastrin (gastric secretin)", "Histamin, yang diproduksi dari asam amino histidin", "Semua jawaban benar"],
                correct: 3,
                explanation: "Sekresi cairan lambung dirangsang oleh saraf, hormon gastrin, dan histamin."
            },
            {
                question: "Enzim pepsin dalam lambung berfungsi untuk ...",
                options: ["Mengubah kasein menjadi para-kasein", "Menghidrolisis protein menjadi asam-asam amino", "Mengubah protein menjadi proteosa dan pepton", "Tidak ada yang benar"],
                correct: 2,
                explanation: "Pepsin memecah protein menjadi proteosa dan pepton (belum menjadi asam amino)."
            },
            {
                question: "Enzim rennin (rennet) dalam lambung berfungsi untuk ...",
                options: ["Mengubah kasein menjadi para-kasein", "Menghidrolisis protein menjadi asam-asam amino", "Mengubah protein menjadi proteosa dan pepton", "Tidak ada yang benar"],
                correct: 0,
                explanation: "Rennin mengkoagulasi kasein susu menjadi para-kasein (penting pada bayi)."
            },
            {
                question: "Enzim-enzim berikut ini diproduksi oleh pankreas, kecuali ...",
                options: ["Karboksipeptidase", "Aminopeptidase", "Lipase", "Amilase"],
                correct: 1,
                explanation: "Aminopeptidase diproduksi oleh usus halus, bukan pankreas."
            },
            {
                question: "Enzim-enzim berikut ini diproduksi oleh usus kecil, kecuali ...",
                options: ["Disakaridase", "Aminopeptidase", "Dipeptidase", "Amilase"],
                correct: 3,
                explanation: "Amilase terutama dari saliva dan pankreas, usus kecil menghasilkan disakaridase dan peptidase."
            },
            {
                question: "Penyerapan monosakarida (glukosa, fruktosa, galaktosa) dilakukan melalui mekanisme berikut ini, kecuali difusi ...",
                options: ["Pasif", "Fasilitas", "Aktif menggunakan ATP", "Aktif menggunakan Na-pump"],
                correct: 1,
                explanation: "Monosakarida diserap via difusi pasif, fasilitas, atau aktif dengan Na-pump, tapi tidak menggunakan ATP langsung."
            },
            {
                question: "Mineral seperti zat besi dan kalsium diserap dalam ...",
                options: ["Lambung", "Duodenum", "Jejunum", "Ileum"],
                correct: 1,
                explanation: "Zat besi dan kalsium diserap di duodenum karena memerlukan suasana asam."
            },
            {
                question: "Sebagian kecil alkohol dari minuman diserap dalam ...",
                options: ["Lambung", "Duodenum", "Jejunum", "Ileum"],
                correct: 0,
                explanation: "Sekitar 20% alkohol diserap di lambung, sisanya di usus halus."
            },
            {
                question: "Sebagian besar vitamin B diserap oleh usus melalui mekanisme difusi pasif atau dengan bantuan Na-pump, kecuali ...",
                options: ["Tiamin", "Riboflavin", "Cobalamin", "Niasin"],
                correct: 2,
                explanation: "Vitamin B12 (cobalamin) memerlukan faktor intrinsik dari lambung untuk penyerapan."
            },
            {
                question: "Umumnya penyerapan mineral dilakukan secara ...",
                options: ["Difusi pasif", "Transport aktif", "Difusi fasilitas", "Semuanya benar"],
                correct: 1,
                explanation: "Kebanyakan mineral (Ca, Fe, Zn) diserap via transport aktif menggunakan carrier protein dan energi."
            }
        ];

        // Variabel state
        let currentQuestion = 0;
        let userAnswers = new Array(questions.length).fill(null);
        let timeLeft = 60 * 60; // 60 menit dalam detik
        let timerInterval;
        const totalQuestions = questions.length;

        // Inisialisasi tampilan soal
        function initExam() {
            const wrapper = document.getElementById('question-wrapper');
            wrapper.innerHTML = '';
            questions.forEach((q, index) => {
                const questionDiv = document.createElement('div');
                questionDiv.className = 'question-container';
                questionDiv.id = `question-${index}`;
                questionDiv.innerHTML = `
                    <div class="question-number">Soal ${index + 1} dari ${totalQuestions}</div>
                    <div class="question-text">${q.question}</div>
                    <div class="options">
                        ${q.options.map((opt, optIndex) => `
                            <div class="option" data-index="${optIndex}">${String.fromCharCode(65 + optIndex)}. ${opt}</div>
                        `).join('')}
                    </div>
                `;
                wrapper.appendChild(questionDiv);
            });
            showQuestion(currentQuestion);
            startTimer();
            updateProgress();
        }

        // Tampilkan soal tertentu
        function showQuestion(index) {
            document.querySelectorAll('.question-container').forEach(q => q.classList.remove('active'));
            document.getElementById(`question-${index}`).classList.add('active');
            
            // Restore pilihan sebelumnya
            const selectedOption = userAnswers[index];
            if (selectedOption !== null) {
                const options = document.querySelectorAll(`#question-${index} .option`);
                options[selectedOption].classList.add('selected');
            }
            
            // Update tombol navigasi
            document.getElementById('prev-btn').style.display = index === 0 ? 'none' : 'block';
            document.getElementById('next-btn').style.display = index === totalQuestions - 1 ? 'none' : 'block';
            document.getElementById('submit-btn').style.display = index === totalQuestions - 1 ? 'block' : 'none';
        }

        // Pilih jawaban
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('option')) {
                const questionContainer = e.target.closest('.question-container');
                const questionId = questionContainer.id;
                const questionIndex = parseInt(questionId.split('-')[1]);
                
                // Hapus pilihan sebelumnya di soal ini
                questionContainer.querySelectorAll('.option').forEach(opt => opt.classList.remove('selected'));
                
                // Tandai pilihan baru
                e.target.classList.add('selected');
                const selectedOption = parseInt(e.target.getAttribute('data-index'));
                userAnswers[questionIndex] = selectedOption;
            }
        });

        // Navigasi soal
        document.getElementById('prev-btn').addEventListener('click', function() {
            if (currentQuestion > 0) {
                currentQuestion--;
                showQuestion(currentQuestion);
                updateProgress();
            }
        });

        document.getElementById('next-btn').addEventListener('click', function() {
            if (currentQuestion < totalQuestions - 1) {
                currentQuestion++;
                showQuestion(currentQuestion);
                updateProgress();
            }
        });

        // Timer
        function startTimer() {
            clearInterval(timerInterval);
            timerInterval = setInterval(() => {
                timeLeft--;
                updateTimerDisplay();
                if (timeLeft <= 0) {
                    clearInterval(timerInterval);
                    submitExam();
                }
            }, 1000);
        }

        function updateTimerDisplay() {
            const minutes = Math.floor(timeLeft / 60);
            const seconds = timeLeft % 60;
            document.getElementById('timer').textContent = `Waktu: ${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        // Progress bar
        function updateProgress() {
            const progress = ((currentQuestion + 1) / totalQuestions) * 100;
            document.getElementById('progress').style.width = `${progress}%`;
        }

        // Submit ujian
        document.getElementById('submit-btn').addEventListener('click', submitExam);

        function submitExam() {
            clearInterval(timerInterval);
            
            // Hitung skor
            let correctCount = 0;
            let wrongCount = 0;
            const wrongAnswers = [];
            
            questions.forEach((q, index) => {
                if (userAnswers[index] === q.correct) {
                    correctCount++;
                } else {
                    wrongCount++;
                    wrongAnswers.push({
                        question: q.question,
                        userAnswer: q.options[userAnswers[index]] || "Tidak dijawab",
                        correctAnswer: q.options[q.correct],
                        explanation: q.explanation
                    });
                }
            });
            
            const score = Math.round((correctCount / totalQuestions) * 100);
            
            // Tampilkan hasil
            document.getElementById('score').textContent = `${score}`;
            document.getElementById('score-detail').textContent = `Benar: ${correctCount} | Salah: ${wrongCount}`;
            
            const wrongContainer = document.getElementById('wrong-answers-container');
            if (wrongAnswers.length === 0) {
                wrongContainer.innerHTML = '<p style="text-align:center; color:#28a745;">Selamat! Semua jawaban Anda benar.</p>';
            } else {
                wrongContainer.innerHTML = `
                    <h3 class="wrong-title">Pembahasan Jawaban Salah (${wrongAnswers.length} soal)</h3>
                    ${wrongAnswers.map((item, idx) => `
                        <div class="wrong-item">
                            <div class="wrong-question">Soal ${idx + 1}: ${item.question}</div>
                            <div class="your-answer"><strong>Jawaban Anda:</strong> ${item.userAnswer}</div>
                            <div class="correct-answer"><strong>Jawaban Benar:</strong> ${item.correctAnswer}</div>
                            <div class="explanation"><strong>Penjelasan:</strong> ${item.explanation}</div>
                        </div>
                    `).join('')}
                `;
            }
            
            document.getElementById('question-wrapper').style.display = 'none';
            document.querySelector('.nav-buttons').style.display = 'none';
            document.getElementById('result-container').style.display = 'block';
            document.getElementById('timer').style.display = 'none';
        }

        // Inisialisasi saat halaman dimuat
        window.onload = initExam;
    </script>
</body>
</html>
