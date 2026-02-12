Simplifikasi penjelasan Elliptic Curve Cryptography secp256k1 dengan Bahasa Manusia
--

Pernah nggak kepikiran, gimana cara Bitcoin jagain duit triliunan orang cuma pakai matematika? Nah, rahasianya ada di sebuah gembok digital yang namanya ECC secp256k1.Nama 'secp256k1' mungkin terdengar kayak kode rahasia agen intelijen, tapi aslinya ini cuma aturan main matematika untuk memutar tuas gembok raksasa kita. Logikanya simpel banget dan bisa dirangkum dalam satu rumus maut:

$$P = k \times G$$

Ini bukan perkalian matematika SD ya, ini perkalian titik di kurva eliptik, tapi biar gampang kita bayangin kayak gembok sandi scroll aja. Aku punya tiga gambar gembok di sini yang bakal jelasin kenapa rumus ini bikin hacker paling jago sekalipun bakal angkat tangan. Yuk, kita bedah satu-satu mulai dari titik nolnya...

--

**1. Titik Awal: Generator Point ($G$) — [Gambar 1]**


<img width="1920" height="1080" alt="1" src="https://github.com/user-attachments/assets/38ec3bf0-5cc6-478f-838a-f540490298ab" />

Semua dimulai dari Gambar 1, yaitu kondisi gembok dengan 78 roda angka yang semuanya disetel di angka 000...0.
- Dalam rumus, ini adalah $G$.
- Ini adalah standar global yang diketahui semua orang. Semua gembok "diproduksi" dari titik nol yang sama ini.

--

**2. Rahasia Pemilik: Private Key ($k$)**

Inilah kunci yang kamu simpan rapat-rapat.
- Dalam rumus, ini adalah $k$.
- Ini adalah sebuah kombinasi angka acak antara 1 sampai $2^{256}$ (angka 78 digit dalam gembok itu.).
- Bayangkan $k$ adalah jumlah putaran yang kamu lakukan. Kamu memerintahkan mesin untuk memutar gembok dari Gambar 1 (Nol) sebanyak $k$ kali. Karena kamu punya angkanya, kamu bisa sampai ke tujuan secara instan.


--


**3. Alamat Publik: Public Key ($P$) — [Gambar 2]**

<img width="1920" height="1080" alt="2" src="https://github.com/user-attachments/assets/f9130092-b422-418e-9939-15d5a6ca7b80" />

Setelah diputar sebanyak $k$ kali, gembok berhenti di posisi tertentu.
- Dalam rumus, ini adalah $P$.
- Gambar 2 menunjukkan hasilnya: roda angka berhenti di kombinasi unik (misalnya yang ada angka ...42...). Inilah yang kamu berikan ke orang lain sebagai alamat terima transferan.


--

4. Benteng Pertahanan: Kenapa Hacker Gagal? — [Gambar 3]
Di sinilah keajaiban matematikanya. Dalam sistem gembok ini, perkalian itu gampang, tapi pembagian itu mustahil.
- Pemilik (Maju): Kamu punya $k$ dan $G$, maka mendapatkan $P$ itu sangat cepat ($P = k \times G$).
- Hacker (Mundur): Hacker punya $P$ (Gambar 2) dan tahu $G$ (Gambar 1), tapi dia tidak bisa menghitung mundur ($k = P / G$) untuk mendapatkan jumlah putaranmu.

Satu-satunya cara hacker adalah mencoba menyusul dengan memutar gemboknya sendiri dari nol. Namun, seperti di Gambar 3, jika hacker salah menebak jumlah putaran walau cuma selisih satu angka saja ($k+1$), posisi gemboknya akan acak total dan tidak mirip sama sekali dengan angka "42" milikmu.

Karena ada $2^{256}$ kemungkinan posisi dan tidak ada pola yang bisa diikuti, hacker butuh waktu lebih lama dari usia alam semesta untuk menemukan jumlah putaran yang tepat.

--

Kesimpulan Akhir:

Kamu mulai dari G (Gambar 1), memutar sebanyak k (PrivKey), dan menghasilkan P (Gambar 2). Hacker terjebak di Gambar 3 selamanya karena dia tidak akan pernah bisa menebak berapa kali kamu memutar tuasnya di antara $2^{256}$ kemungkinan yang ada. Karena cuma kamu yang tahu kombinasi berapa kali kamu putar sandinya (private key) untuk menemukan angka kuncinya (public key).
