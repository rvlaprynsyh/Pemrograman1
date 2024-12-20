<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TUGAS PERTEMUAN 18</title>
</head>
<body>
    <h2>Menghitung Indeks Prestasi</h2>
    <form id="form">
        <label>Quis (10%): </label>
        <input type="number" id="quis" min="0" max="100" required><br><br>
        <label>Tugas (20%): </label>
        <input type="number" id="tugas" min="0" max="100" required><br><br>
        <label>UTS (30%): </label>
        <input type="number" id="uts" min="0" max="100" required><br><br>
        <label>UAS (40%): </label>
        <input type="number" id="uas" min="0" max="100" required><br><br>
        <button type="button" onclick="hitung()">Hitung</button>
        <button type="reset">Ulang</button>
    </form>
    <p>Indeks Prestasi: <span id="indeks">-</span></p>
    <p>Keterangan: <span id="keterangan">-</span></p>

    <script>
        function hitung() {
            const quis = parseFloat(document.getElementById("quis").value) || 0;
            const tugas = parseFloat(document.getElementById("tugas").value) || 0;
            const uts = parseFloat(document.getElementById("uts").value) || 0;
            const uas = parseFloat(document.getElementById("uas").value) || 0;

            const nilaiAkhir = (quis * 0.1) + (tugas * 0.2) + (uts * 0.3) + (uas * 0.4);

            let indeks = "";
            let keterangan = "";

            if (nilaiAkhir >= 80) {
                indeks = "A";
                keterangan = "Lulus dengan Sangat Baik";
            } else if (nilaiAkhir >= 68) {
                indeks = "B";
                keterangan = "Lulus dengan Baik";
            } else if (nilaiAkhir >= 55) {
                indeks = "C";
                keterangan = "Lulus dengan Cukup";
            } else if (nilaiAkhir >= 38) {
                indeks = "D";
                keterangan = "Lulus dengan Kurang";
            } else {
                indeks = "E";
                keterangan = "Tidak Lulus";
            }

            document.getElementById("indeks").textContent = indeks;
            document.getElementById("keterangan").textContent = keterangan;
        }
    </script>
</body>
</html>
