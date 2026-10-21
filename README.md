Praktikum 5 — JavaScript Dasar dan Manipulasi HTML
Repository ini berisi pengerjaan Praktikum 5: JavaScript Dasar dan Manipulasi HTML untuk mata kuliah Pemrograman Web (Pertemuan 6).

Identitas Praktikum
Mata kuliah: Pemrograman Web
Pertemuan: 6
Topik: JavaScript dasar dan manipulasi elemen HTML
Cakupan: Variabel, tipe data, operator, output, percabangan, perulangan, function, DOM, form, dan validasi
Nama repository: Lab5Web
Lengkapi nama, NIM, kelas, dan identitas lain sesuai data mahasiswa sebelum dikumpulkan.

Tujuan Praktikum
Memahami sintaks dasar JavaScript dan cara menyisipkan JavaScript pada HTML.
Menggunakan variabel, tipe data, operator, percabangan, perulangan, dan function.
Menampilkan informasi melalui Console, alert(), prompt(), dan elemen HTML.
Memanipulasi konten serta gaya elemen HTML menggunakan JavaScript.
Membuat interaksi sederhana pada form dan melakukan validasi input.
Mendokumentasikan pekerjaan praktikum beserta hasil pengujiannya.
Perangkat yang Dibutuhkan
Laptop atau PC.
Browser modern, misalnya Google Chrome, Microsoft Edge, atau Firefox.
Editor kode, misalnya Visual Studio Code.
Git dan akun GitHub (untuk membuat repository dan mengirim hasil).
Validator HTML (opsional).
Struktur Folder yang Disarankan
Lab5Web/
├── index.html
├── script.js
├── README.md
└── screenshots/
    ├── latihan-1-output.png
    ├── latihan-2-alert-prompt.png
    ├── latihan-3-operasi-aritmetika.png
    ├── latihan-4-if-else.png
    ├── latihan-5-switch.png
    ├── latihan-6-genap-ganjil.png
    ├── latihan-7-ubah-warna.png
    ├── latihan-8-total-menu.png
    └── mini-project-kalkulator-nilai.png
Jika setiap latihan dibuat sebagai file terpisah, susun folder dan nama file dengan jelas, misalnya latihan-1/, latihan-2/, dan seterusnya. Sesuaikan nama file dengan implementasi yang benar-benar dibuat.

Persiapan dan Cara Menjalankan
Buat folder bernama Lab5Web.

Buat file index.html dan script.js di dalam folder tersebut.

Pastikan index.html memuat JavaScript eksternal sebelum penutup </body>:

<script src="script.js"></script>
Simpan kedua file di folder yang sama, kecuali jika lokasi script.js disesuaikan pada atribut src.

Buka index.html di browser.

Untuk melihat output console.log(), buka Developer Tools dengan Inspect/Periksa → Console.

Uji setiap latihan sesuai skenario yang ditulis di bawah.

Ambil screenshot hasil pada browser; sertakan Console jika diperlukan.

Simpan screenshot ke folder screenshots/ dan cantumkan gambar tersebut di bagian hasil.

Commit semua file ke repository Git dan kirim URL repository melalui e-learning/ecampus sesuai arahan dosen.

Daftar Latihan dan Hasil yang Diharapkan
Latihan 1 — Menampilkan Output
Tujuan: Memahami perbedaan output pada halaman web dan Console.

Kode JavaScript:

document.getElementById("pesan").textContent = "Hello World";
console.log("Hello World");
Prasyarat HTML:

<p id="pesan">Konten awal.</p>
Langkah pengujian:

Jalankan index.html.
Periksa teks pada halaman.
Buka Console dan periksa pesan.
Hasil yang diharapkan: Teks paragraf berubah menjadi Hello World, dan pesan yang sama muncul di Console.

Screenshot: screenshots/latihan-1-output.png

Catatan: textContent mengubah teks elemen HTML, sedangkan console.log() menampilkan informasi di Console browser.

Latihan 2 — Alert dan Prompt
Tujuan: Meminta nama pengguna dan menampilkan sapaan serta menangani input kosong atau pembatalan.

Kode JavaScript:

const namaPengguna = prompt("Masukkan nama Anda:", "");

if (namaPengguna && namaPengguna.trim() !== "") {
  alert("Halo, " + namaPengguna + "!");
  document.getElementById("pesan").textContent =
    "Selamat datang, " + namaPengguna + ".";
} else {
  alert("Nama belum diisi.");
}
Prasyarat HTML:

<p id="pesan">Konten awal.</p>
Langkah pengujian:

Jalankan halaman dan masukkan nama.
Ulangi dengan menekan Cancel.
Ulangi dengan membiarkan input kosong.
Amati dialog dan teks pada halaman.
Hasil yang diharapkan: Jika nama diisi, muncul sapaan dan teks selamat datang. Jika input dibatalkan atau kosong, muncul pesan Nama belum diisi.

Screenshot: screenshots/latihan-2-alert-prompt.png

Latihan 3 — Function dan Operasi Aritmetika
Tujuan: Menggunakan function untuk melakukan operasi aritmetika pada dua bilangan.

Kode JavaScript:

function operasiDasar(a, b) {
  console.log("Penjumlahan:", a + b);
  console.log("Pengurangan:", a - b);
  console.log("Perkalian:", a * b);
  console.log(
    "Pembagian:",
    b !== 0 ? a / b : "Tidak dapat dibagi nol"
  );
  console.log("Modulus:", a % b);
}

operasiDasar(9, 4);
Langkah pengujian:

Jalankan halaman.
Buka Console browser.
Periksa hasil setiap operasi.
Ubah argumen function untuk mencoba bilangan lain, termasuk pembagi nol.
Hasil yang diharapkan untuk operasiDasar(9, 4):

Penjumlahan: 13
Pengurangan: 5
Perkalian: 36
Pembagian: 2.25
Modulus/sisa bagi: 1
Screenshot: screenshots/latihan-3-operasi-aritmetika.png

Latihan 4 — Seleksi Kondisi if–else
Tujuan: Memeriksa nilai mahasiswa, memvalidasi input 0–100, lalu menentukan status lulus.

Kode JavaScript:

const inputNilai = prompt("Masukkan nilai (0–100):");
const nilaiMahasiswa = Number(inputNilai);

if (
  inputNilai === null ||
  inputNilai.trim() === "" ||
  Number.isNaN(nilaiMahasiswa) ||
  nilaiMahasiswa < 0 ||
  nilaiMahasiswa > 100
) {
  alert("Input nilai tidak valid.");
} else if (nilaiMahasiswa >= 60) {
  alert("Lulus");
} else {
  alert("Belum lulus");
}
Langkah pengujian:

Masukkan nilai 80.
Masukkan nilai 50.
Masukkan nilai di luar rentang, misalnya 120 atau -1.
Coba input kosong dan tombol Cancel.
Hasil yang diharapkan: Nilai 60–100 menghasilkan Lulus; nilai 0 sampai kurang dari 60 menghasilkan Belum lulus; input kosong, dibatalkan, bukan angka, atau di luar rentang menghasilkan Input nilai tidak valid.

Screenshot: screenshots/latihan-4-if-else.png

Latihan 5 — Seleksi Kondisi switch
Tujuan: Mengubah input angka 1–5 menjadi nama bilangan.

Kode JavaScript:

const inputPilihan = prompt("Masukkan angka 1–5:");

switch (inputPilihan) {
  case "1":
    alert("Bilangan satu");
    break;
  case "2":
    alert("Bilangan dua");
    break;
  case "3":
    alert("Bilangan tiga");
    break;
  case "4":
    alert("Bilangan empat");
    break;
  case "5":
    alert("Bilangan lima");
    break;
  default:
    alert("Pilihan tidak tersedia");
}
Langkah pengujian:

Masukkan angka dari 1 sampai 5.
Masukkan angka di luar rentang, huruf, atau input kosong.
Periksa pesan yang muncul.
Hasil yang diharapkan: Input 1–5 menampilkan nama bilangan yang sesuai; input lainnya menampilkan Pilihan tidak tersedia.

Screenshot: screenshots/latihan-5-switch.png

Catatan: prompt() menghasilkan string. Karena itu, case menggunakan "1", "2", dan seterusnya.

Latihan 6 — Form Bilangan Genap atau Ganjil
Tujuan: Memeriksa input bilangan bulat dari form HTML dan menentukan apakah genap atau ganjil.

HTML:

<label for="bilangan">Masukkan bilangan bulat:</label>
<input type="number" id="bilangan" step="1">
<button type="button" onclick="cekBilangan()">Periksa</button>
<p id="hasilBilangan"></p>
JavaScript:

function cekBilangan() {
  const input = document.getElementById("bilangan").value;
  const angka = Number(input);
  const hasil = document.getElementById("hasilBilangan");

  if (input.trim() === "" || !Number.isInteger(angka)) {
    hasil.textContent = "Masukkan bilangan bulat yang valid.";
  } else if (angka % 2 === 0) {
    hasil.textContent = "Bilangan genap";
  } else {
    hasil.textContent = "Bilangan ganjil";
  }
}
Langkah pengujian:

Masukkan bilangan positif, misalnya 8.
Masukkan bilangan negatif, misalnya -3.
Masukkan 0.
Coba bilangan desimal dan input kosong.
Hasil yang diharapkan: Angka genap menghasilkan Bilangan genap, angka ganjil menghasilkan Bilangan ganjil, sedangkan input kosong atau bukan bilangan bulat menghasilkan pesan validasi.

Screenshot: screenshots/latihan-6-genap-ganjil.png

Latihan 7 — Mengubah Warna Halaman
Tujuan: Mengubah warna latar halaman melalui tombol dan function berparameter.

HTML:

<button type="button" onclick="ubahWarnaLatar('lightgreen')">
  Latar Hijau
</button>
<button type="button" onclick="ubahWarnaLatar('white')">
  Latar Putih
</button>
<button type="button" onclick="ubahWarnaLatar('lightyellow')">
  Latar Kuning
</button>
JavaScript:

function ubahWarnaLatar(warna) {
  document.body.style.backgroundColor = warna;
}
Langkah pengujian:

Jalankan halaman.
Klik tombol Latar Hijau.
Klik tombol Latar Putih.
Klik tombol Latar Kuning.
Hasil yang diharapkan: Warna latar halaman berubah sesuai tombol yang ditekan.

Screenshot: screenshots/latihan-7-ubah-warna.png

Latihan 8 — DOM dan Checkbox Menu Makanan
Tujuan: Menghitung total harga menu secara otomatis berdasarkan checkbox yang dipilih.

HTML:

<h3>Daftar Menu Makanan</h3>
<label>
  <input type="checkbox" class="menu" value="5000">
  Ayam Goreng — Rp5.000
</label><br>

<label>
  <input type="checkbox" class="menu" value="500">
  Tempe — Rp500
</label><br>

<label>
  <input type="checkbox" class="menu" value="2500">
  Telur Dadar — Rp2.500
</label><br>

<p>Total: Rp<span id="total">0</span></p>
JavaScript:

const daftarMenu = document.querySelectorAll(".menu");

daftarMenu.forEach((item) => {
  item.addEventListener("change", hitungTotal);
});

function hitungTotal() {
  let total = 0;

  daftarMenu.forEach((item) => {
    if (item.checked) {
      total += Number(item.value);
    }
  });

  document.getElementById("total").textContent =
    total.toLocaleString("id-ID");
}
Langkah pengujian:

Pastikan total awal menunjukkan 0.
Centang satu menu dan periksa total.
Centang beberapa menu sekaligus.
Lepas centang dan pastikan total diperbarui.
Hasil yang diharapkan:

Ayam Goreng: Rp5.000
Tempe: Rp500
Telur Dadar: Rp2.500
Semua menu dipilih: Rp8.000
Total berubah otomatis ketika checkbox dicentang atau dilepas.
Screenshot: screenshots/latihan-8-total-menu.png

Catatan: Letakkan <script src="script.js"></script> menjelang akhir elemen <body> agar elemen menu sudah tersedia ketika JavaScript dijalankan.

Mini Project — Kalkulator Nilai Mahasiswa
Tujuan: Menghitung nilai akhir dari nilai tugas, UTS, dan UAS, menentukan predikat, serta menampilkan status kelulusan.

Rumus
Nilai akhir dihitung dengan bobot:

Tugas: 30%
UTS: 30%
UAS: 40%
Nilai Akhir = (Tugas × 0,30) + (UTS × 0,30) + (UAS × 0,40)
Ketentuan Predikat
Rentang nilai akhir	Predikat
85–100	A
75–kurang dari 85	B
60–kurang dari 75	C
50–kurang dari 60	D
Di bawah 50	E
Status Lulus jika nilai akhir minimal 60; selain itu Belum lulus.

Kode dasar dari modul
function hitungNilaiAkhir(tugas, uts, uas) {
  return tugas * 0.30 + uts * 0.30 + uas * 0.40;
}

function tentukanPredikat(nilai) {
  if (nilai >= 85) return "A";
  if (nilai >= 75) return "B";
  if (nilai >= 60) return "C";
  if (nilai >= 50) return "D";
  return "E";
}

const tugas = 85;
const uts = 78;
const uas = 88;
const akhir = hitungNilaiAkhir(tugas, uts, uas);

console.log("Nilai akhir:", akhir.toFixed(2));
console.log("Predikat:", tentukanPredikat(akhir));
console.log("Status:", akhir >= 60 ? "Lulus" : "Belum lulus");
Pengembangan yang diminta
Tambahkan form input untuk nilai tugas, UTS, dan UAS.
Validasi agar setiap nilai berada pada rentang 0–100.
Tampilkan nilai akhir, predikat, dan status pada halaman HTML, bukan hanya Console.
Pisahkan proses perhitungan dan tampilan hasil menggunakan function.
Uji sekurang-kurangnya tiga skenario nilai berbeda.
Hasil contoh dari nilai pada modul
Dengan tugas 85, UTS 78, dan UAS 88:

Nilai akhir = (85 × 0,30) + (78 × 0,30) + (88 × 0,40) = 84,10
Predikat = B
Status = Lulus
Screenshot: screenshots/mini-project-kalkulator-nilai.png

Eksperimen Mandiri
Kerjakan eksperimen berikut sebagai latihan tambahan sesuai modul:

Ubah Latihan 3 agar menerima dua nilai dari prompt() dan mengonversinya menjadi number.
Buat perulangan untuk menampilkan tabel perkalian angka 7 dari 1 sampai 10.
Buat function cekGenap(angka) yang mengembalikan true jika angka genap.
Tambahkan validasi form agar kolom tidak boleh kosong.
Ubah Latihan 8 dengan menambah minimal dua pilihan menu dan harga.
Gunakan tombol untuk menyembunyikan atau menampilkan elemen HTML.
Penomoran eksperimen mengikuti urutan topik yang tercantum pada modul; modul menuliskan nomor 1, lalu 7–11.

Pertanyaan dan Tugas
Dokumentasikan jawaban untuk pertanyaan berikut bila diminta dalam laporan:

Jelaskan perbedaan console.log(), alert(), prompt(), dan textContent/innerHTML.
Apa perbedaan let dan const? Berikan contoh.
Apa perbedaan operator == dan ===?
Jelaskan fungsi if–else dan switch. Kapan masing-masing dapat digunakan?
Apa fungsi parameter dan return dalam function?
Bagaimana JavaScript memilih elemen HTML menggunakan document.getElementById()?
Buat script untuk memvalidasi form agar nama tidak kosong dan nilai berada pada rentang 0–100.
Dokumentasi Screenshot
Masukkan screenshot hasil pengerjaan ke folder screenshots/. Setelah gambar tersedia, gunakan format Markdown berikut untuk menampilkannya di README:

![Latihan 1 - Menampilkan Output](screenshots/latihan-1-output.png)
Ulangi untuk setiap latihan dan mini project. Screenshot belum disertakan otomatis; ganti nama file pada dokumentasi sesuai gambar yang benar-benar diambil.

Checklist Sebelum Dikumpulkan
[ ] Repository bernama Lab5Web.
[ ] Semua file HTML dan JavaScript sudah disimpan.
[ ] Delapan latihan dikerjakan dan diuji.
[ ] Mini project kalkulator nilai dikembangkan sesuai ketentuan.
[ ] Eksperimen mandiri dikerjakan sesuai instruksi dosen.
[ ] Screenshot setiap latihan dan mini project sudah dimasukkan.
[ ] README sudah disesuaikan dengan implementasi dan hasil aktual.
[ ] Nama, NIM, dan kelas sudah dilengkapi bila diperlukan.
[ ] Semua perubahan sudah di-commit.
[ ] URL repository dikirim melalui e-learning/ecampus.
Referensi
Flanagan, D. (2020). JavaScript: The Definitive Guide (7th ed.). O’Reilly Media.
MDN Web Docs, JavaScript Guide.
Rencana Pembelajaran Semester (RPS) Mata Kuliah Pemrograman Web, Pertemuan 6: JavaScript dasar — variabel, tipe data, operator, percabangan, perulangan, dan function.

