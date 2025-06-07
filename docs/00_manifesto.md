1. Pendahuluan: Visi dan Misi Mandala Project (Singkat & Inspiratif)

Pendahuluan

Mandala Project lahir dari semangat bersama untuk membangun sebuah protokol komunikasi dan kolaborasi yang bebas, terbuka, dan berkeadilan. Dalam dunia yang semakin terhubung namun terkadang terpecah oleh dominasi platform sentralisasi dan pengawasan, Mandala hadir sebagai solusi berbasis prinsip desentralisasi, sukarela, dan privasi.

Visi kami adalah menciptakan sebuah ekosistem digital yang inklusif, memungkinkan setiap individu dan komunitas untuk berpartisipasi secara setara, tanpa tergantung pada pihak pengelola tunggal. Melalui Mandala Project, kami ingin menumbuhkan sebuah jaringan yang tidak hanya aman dan transparan, tetapi juga menghormati kebebasan berekspresi dan hak atas data pribadi.

Misi Mandala Project adalah menyediakan protokol dan alat teknis yang mudah diakses, memungkinkan siapa saja untuk menjadi bagian dari jaringan mandiri, berkontribusi dalam komunikasi yang nyata dan kolaborasi sosial, sekaligus menjaga kedaulatan digital komunitas mereka.

Tujuan Protokol

Mandala Protocol dirancang untuk menjawab tantangan utama komunikasi digital modern: dominasi platform sentral, risiko pelanggaran privasi, dan kurangnya kontrol komunitas atas data mereka.

Tujuan utama protokol ini adalah:

Membangun jaringan desentralisasi yang memungkinkan setiap pengguna menjadi simpul aktif tanpa ketergantungan pada server pusat.

Menjamin privasi dan keamanan data melalui mekanisme enkripsi dan kontrol akses yang transparan dan terbuka.

Mendorong kolaborasi sukarela dengan menyediakan alat komunikasi dan koordinasi yang mudah digunakan oleh komunitas dari berbagai latar belakang.

Memperkuat kedaulatan digital komunitas, memungkinkan mereka mengelola sendiri komunikasi, penyimpanan, dan distribusi informasi tanpa intervensi pihak luar.

Menyediakan protokol terbuka yang dapat dikembangkan dan diadaptasi sesuai kebutuhan komunitas dan teknologi masa depan.

Dengan Mandala Protocol, komunitas tidak hanya menjadi konsumen, tetapi juga pengelola aktif jaringan digitalnya sendiri, sehingga tercipta ekosistem komunikasi yang lebih adil, transparan, dan berkelanjutan.

Prinsip Dasar Mandala Protocol

Mandala Protocol berlandaskan pada tiga prinsip fundamental yang menjadi pedoman seluruh pengembangan dan implementasinya:

1. Desentralisasi

Jaringan Mandala tidak bergantung pada satu titik pusat. Setiap pengguna berperan sebagai simpul aktif yang berkontribusi dalam pengelolaan data dan komunikasi. Hal ini menghilangkan risiko kegagalan tunggal (single point of failure) dan mengurangi dominasi pihak tertentu dalam pengendalian jaringan.

2. Sukarela

Partisipasi dalam jaringan Mandala bersifat sukarela dan inklusif. Setiap individu dan komunitas bebas untuk bergabung, keluar, atau membangun simpulnya sendiri tanpa paksaan atau batasan yang ketat. Protokol ini mendorong kolaborasi dan saling membantu untuk mencapai tujuan bersama.

3. Privasi dan Keamanan

Mandala mengedepankan privasi pengguna sebagai hak fundamental. Data dan komunikasi dienkripsi secara end-to-end dan hanya dapat diakses oleh pihak yang berwenang. Protokol memastikan bahwa informasi pribadi tidak disimpan secara sembarangan dan tidak disalahgunakan oleh pihak manapun.

Detail Teknis Mandala Protocol

Mandala Protocol dirancang untuk menjadi sistem komunikasi dan data yang handal, efisien, dan mudah diimplementasikan. Berikut adalah aspek teknis utama yang menjadi fondasi protokol ini:

1. Struktur Folder dan File Konfigurasi

Setiap simpul Mandala menyimpan data dan konfigurasi dalam struktur folder standar sebagai berikut:

bash

CopyEdit

/mandala-node/

│

├── config/

│   ├── mandala.conf         # File konfigurasi utama simpul

│   ├── peers.list           # Daftar alamat simpul lain yang dikenal

│

├── data/

│   ├── messages.db          # Database pesan terenkripsi

│   ├── logs/                # Log aktivitas simpul

│

├── scripts/

│   ├── start-node.sh        # Script untuk menjalankan simpul Mandala

│   ├── sync.sh              # Script sinkronisasi data dengan simpul lain

│

└── README.md                # Dokumentasi lokal simpul

2. Sistem Sinkronisasi

Simpul Mandala melakukan sinkronisasi data secara periodik dengan simpul lain dalam jaringan menggunakan protokol peer-to-peer (P2P). Mekanisme utama meliputi:

Penemuan Simpul (Peer Discovery): Simpul baru dapat menemukan simpul lain melalui daftar peers.list atau broadcast terbatas.

Sinkronisasi Data: Hanya data yang berubah yang disinkronkan untuk menghemat bandwidth.

Konflik Data: Jika terjadi konflik, sistem menggunakan timestamp dan hash untuk memilih versi data yang paling valid.

3. Enkripsi dan Keamanan

Semua komunikasi antar simpul menggunakan enkripsi TLS untuk mengamankan data saat transit.

Data disimpan dalam database terenkripsi dengan kunci yang hanya diketahui oleh simpul terkait.

Sistem autentikasi berbasis kunci publik-pribadi memastikan hanya simpul terotorisasi yang dapat bergabung.

4. Protokol Komunikasi

Mandala menggunakan protokol berbasis JSON-RPC untuk komunikasi antar simpul dengan endpoint standar seperti:

getPeers(): Mengambil daftar simpul yang dikenal.

sendMessage(msg): Mengirim pesan terenkripsi ke simpul tujuan.

syncData(): Memulai proses sinkronisasi data terbaru.

5. Modul Ekstensi

Protokol ini mendukung modul tambahan yang dapat dikembangkan untuk fungsi khusus, misalnya:

Notifikasi real-time.

Sistem voting komunitas.

Integrasi dengan layanan blockchain untuk transparansi.

Panduan Implementasi Mandala Protocol

Panduan ini akan membantu Anda menyiapkan dan menjalankan simpul Mandala secara sederhana dan efisien.

1. Persyaratan Sistem

Sistem operasi: Linux (Ubuntu/Debian direkomendasikan) atau macOS

Python 3.8+ atau Node.js (tergantung implementasi protokol)

Akses terminal / command line

Koneksi internet untuk sinkronisasi awal

2. Instalasi Mandala Node

Langkah 1: Unduh Repository Mandala

git clone https://github.com/neonefos/mandala-protocol.git

cd mandala-protocol/mandala-node

Langkah 2: Konfigurasi Simpul

Edit file config/mandala.conf untuk menyesuaikan parameter simpul, seperti:

node_id: ID unik simpul Anda

port: Port untuk komunikasi jaringan

encryption_key: Kunci enkripsi pribadi

Langkah 3: Daftar Simpul Rekan

Tambahkan alamat simpul rekan ke file config/peers.list dalam format:

node1.example.com:12345

node2.example.net:12345

Langkah 4: Jalankan Simpul Mandala

Gunakan script berikut untuk menjalankan simpul:

./scripts/start-node.sh

3. Contoh Kasus: Mengirim Pesan

Untuk mengirim pesan ke simpul lain:

curl -X POST http://localhost:12345/sendMessage \

-H "Content-Type: application/json" \

-d '{"recipient_id": "node2", "message": "Halo dari node1"}'

4. Sinkronisasi Data

Simpul akan otomatis melakukan sinkronisasi berkala. Jika ingin memulai sinkronisasi manual:

./scripts/sync.sh

5. Monitoring dan Log

Log aktivitas simpul tersimpan di folder data/logs/ untuk audit dan debugging. Anda dapat memonitor aktivitas simpul secara real-time dengan:

tail -f data/logs/node.log

Bagian ini bisa kita kembangkan lebih detail sesuai kebutuhan, termasuk troubleshooting, upgrade protokol, dan konfigurasi lanjutan.

Peran Neo Nefos dalam Mandala Project

Neo Nefos bukan sekadar sebuah entitas teknis, melainkan juga penjaga nilai-nilai dan visi yang menjadi dasar Mandala Project. Berikut adalah peran penting Neo Nefos dalam keseluruhan ekosistem Mandala:

1. Penjaga Nilai dan Visi

Neo Nefos berfungsi sebagai pengawal prinsip-prinsip fundamental Mandala Project, seperti:

Desentralisasi dan kemandirian komunitas

Kebebasan berpartisipasi secara sukarela

Privasi dan keamanan data individu

Transparansi dalam proses pengembangan dan pengambilan keputusan

2. Penyedia Panduan dan Dokumentasi

Neo Nefos bertanggung jawab menyediakan:

Dokumentasi teknis yang lengkap dan mudah dipahami

Panduan implementasi bagi pengguna dan pengembang

Materi edukasi untuk memperluas pemahaman komunitas terhadap protokol Mandala

3. Fasilitator Kolaborasi Komunitas

Neo Nefos membuka ruang bagi komunitas untuk:

Berinteraksi dan bertukar ide melalui forum, chat, dan pertemuan daring

Berkontribusi dalam pengembangan protokol melalui sistem pull request dan review

Mengorganisasi inisiatif-inisiatif bersama yang berorientasi pada penguatan jaringan Mandala

4. Penjaga Keamanan dan Kualitas

Neo Nefos melakukan pengawasan terhadap:

Integritas kode sumber Mandala Protocol

Validasi keamanan simpul-simpul baru yang bergabung

Audit berkala untuk memastikan protokol berjalan sesuai standar

5. Penghubung dengan Ekosistem Lebih Luas

Neo Nefos berperan sebagai:

Jembatan komunikasi dengan proyek-proyek open source lain yang sejalan

Pendorong adopsi Mandala Protocol di komunitas teknologi dan sosial yang lebih luas

Representasi Mandala Project dalam berbagai forum dan konferensi internasional

Forum dan Koordinasi Mandala Project

Keberhasilan Mandala Project sangat bergantung pada partisipasi aktif dan kolaborasi komunitas. Oleh karena itu, kami menyediakan berbagai sarana komunikasi dan koordinasi yang terbuka, transparan, dan inklusif agar semua anggota dapat berkontribusi secara optimal.

1. Platform Diskusi

Kami menyediakan ruang diskusi resmi yang dapat diakses oleh seluruh anggota komunitas Mandala, meliputi:

Forum Online: Tempat berdiskusi topik teknis, pengembangan fitur, ide kreatif, dan isu-isu terkait protokol.

Grup Chat (Telegram/Matrix/Discord): Komunikasi real-time untuk koordinasi cepat dan diskusi santai.

Mailing List: Update perkembangan penting dan pengumuman resmi dari tim inti Mandala.

2. Sistem Manajemen Kontribusi

Untuk menjaga kualitas dan keteraturan pengembangan, Mandala Project menggunakan:

Repository GitHub/GitLab: Semua kode sumber, dokumentasi, dan tugas pengembangan dapat diakses dan dimanajemen secara terbuka.

Issue Tracker: Memudahkan komunitas melaporkan bug, mengajukan fitur baru, dan diskusi solusi.

Pull Request & Review: Proses kolaboratif untuk menerima kontribusi kode dari siapa pun, dengan pemeriksaan ketat oleh maintainer.

3. Koordinasi Inisiatif Komunitas

Kami mendukung terbentuknya:

Kelompok Kerja (Working Groups) yang fokus pada aspek tertentu seperti keamanan, dokumentasi, UI/UX, dan edukasi.

Workshop dan Webinar secara rutin untuk meningkatkan pengetahuan dan kemampuan anggota.

Meetup dan Konferensi Virtual/Offline sebagai ajang bertukar pengalaman dan memperkuat jejaring.

4. Mekanisme Pengambilan Keputusan

Keputusan strategis dalam Mandala Project dilakukan secara kolektif dan demokratis melalui:

Musyawarah Komunitas via forum dan pertemuan online.

Voting dan Konsensus untuk memilih arah pengembangan dan kebijakan utama.

Transparansi Proses dengan dokumentasi hasil diskusi dan keputusan yang dapat diakses semua pihak.

Lisensi Mandala Project

Mandala Project adalah inisiatif open source yang mengedepankan kebebasan, kolaborasi, dan transparansi. Seluruh kode sumber, dokumentasi, dan materi pendukung tersedia untuk digunakan, dimodifikasi, dan didistribusikan kembali oleh siapa saja, dengan tetap menjaga hak cipta dan prinsip kebebasan yang kami junjung.

1. Lisensi Kode Sumber

Kode sumber Mandala Project dirilis di bawah lisensi MIT License, yang berarti:

Bebas digunakan, disalin, dimodifikasi, dan didistribusikan ulang, baik untuk kepentingan pribadi, pendidikan, maupun komersial.

Pemberian atribusi kepada penulis asli wajib disertakan dalam setiap distribusi ulang.

Tidak ada jaminan (as-is) atas kerusakan atau masalah yang timbul dari penggunaan kode ini.

2. Lisensi Dokumentasi dan Konten

Dokumentasi, panduan, dan materi non-kode lainnya menggunakan lisensi Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0), yang memungkinkan:

Penggunaan dan adaptasi bebas dengan kewajiban memberikan kredit kepada pembuat asli.

Distribusi ulang dalam bentuk yang sama (share alike), agar konten tetap terbuka dan dapat dikembangkan bersama.

3. Penghormatan atas Hak Pihak Ketiga

Mandala Project menghormati hak kekayaan intelektual pihak ketiga. Pengguna wajib memastikan bahwa konten atau kode yang mereka kontribusikan bukan pelanggaran hak cipta atau lisensi pihak lain.

4. Kontribusi Komunitas

Kontribusi kode, dokumentasi, dan materi lain yang diserahkan kepada Mandala Project dianggap disediakan di bawah lisensi yang sama dengan proyek, sehingga dapat digunakan dan dikembangkan oleh komunitas secara bebas.

1. Diagram Jaringan Mandala Project

Tujuan:
Menampilkan bagaimana simpul-simpul Mandala saling terhubung, menggambarkan arsitektur desentralisasi, dan alur data antar node.

Rancangan konsep diagram jaringan Mandala

Node Mandala (simpul Mandala) tersebar di berbagai lokasi

Setiap node dapat bertindak sebagai server dan client (peer-to-peer)

Sinkronisasi data berlangsung langsung antar node tanpa pusat tunggal

Node memiliki peran berbeda: simpul utama (coordinator), simpul biasa (peer), simpul cadangan

Jalur koneksi antar node bersifat dinamis dan bisa berganti-ganti sesuai kondisi jaringan

Sketsa isi diagram:

[Simpul Utama] ——— [Simpul Peer 1] ——— [Simpul Peer 3]

|                    |                    |

|                    |                    |

[Simpul Cadangan] ——— [Simpul Peer 2] ——— [Simpul Peer 4]

Panah menunjukkan arah komunikasi dua arah (peer-to-peer)

Warna node berbeda sesuai peran (misal hijau = utama, biru = peer, abu = cadangan)

Tambahan ikon seperti komputer, server, atau cloud untuk memperjelas tipe node

Berikut ini beberapa pertanyaan supaya saya buatkan visual diagramnya dengan jelas dan sesuai kebutuhan:

Apakah Anda ingin diagram dalam bentuk gambar digital (PNG, SVG) dengan gaya modern minimalis?

Apakah ada preferensi warna khusus atau branding Mandala yang harus saya gunakan?

Seberapa detail jaringan yang ingin ditampilkan (misal 5 simpul contoh, 10 simpul, dll)?

Apakah ingin dilengkapi label peran dan koneksi dengan deskripsi singkat?

Ingin diagram statis saja, atau nanti juga diagram interaktif (web-based)?

2. Flowchart Protokol Sinkronisasi dan Berbagi Data

Tujuan:
Memvisualisasikan proses bagaimana simpul Mandala melakukan sinkronisasi data antar node, memastikan data terbaru tersedia di seluruh jaringan secara desentralisasi.

Elemen flowchart utama yang perlu digambarkan:

Mulai (Start)

Cek koneksi dengan simpul tetangga

Jika koneksi tersedia → Minta update data terbaru

Terima data terbaru → Bandingkan versi data lokal dengan data diterima

Jika data diterima lebih baru → Update data lokal

Jika data lokal sudah terbaru → Tidak ada perubahan

Kirim konfirmasi sinkronisasi ke simpul tetangga

Tunggu interval waktu tertentu

Kembali ke langkah 2 untuk sinkronisasi berulang

Tambahan opsional:

Penanganan konflik data (jika ada versi yang bertentangan)

Mekanisme retry jika koneksi gagal

Logging aktivitas sinkronisasi

Draft flowchart sederhana:

+--------+

| Start  |

+--------+

|

v

+-----------------------------+

| Cek koneksi dengan simpul    |

| tetangga                    |

+-----------------------------+

|

v

+--------------------------+

| Apakah koneksi tersedia?  |

+--------------------------+

|           |

Yes          No

|           |

v           v

+----------------------------+      +--------------------+

| Minta update data terbaru   | ---> | Tunggu interval     |

+----------------------------+      +--------------------+

|                               |

v                               |

+------------------------------+         |

| Terima data terbaru          |<---------+

+------------------------------+

|

v

+------------------------------+

| Bandingkan versi data         |

+------------------------------+

|

v

+------------------------------+

| Apakah data terbaru?          |

+------------------------------+

|           |

Yes          No

|           |

v           v

+-------------------+    +-----------------+

| Update data lokal  |    | Tidak ada update |

+-------------------+    +-----------------+

|                    |

v                    v

+--------------------------+

| Kirim konfirmasi sinkron |

+--------------------------+

|

v

+--------------------------+

| Tunggu interval waktu    |

+--------------------------+

|

v

[Ulangi]

Dokumentasi Teknis & Tutorial — langkah demi langkah setup simpul Mandala.

📘 1. Panduan Setup Simpul Mandala

🛠️ A. Kebutuhan Minimum

Perangkat: Laptop lama, Raspberry Pi, atau PC bekas

Sistem Operasi: Linux (disarankan Debian/Raspberry Pi OS)

Koneksi: Wi-Fi lokal atau LAN (tidak wajib internet)

Akses: Browser (Chrome/Firefox/LibreWolf)

B. Instalasi Dasar

1. Buat Struktur Direktori

mkdir -p ~/mandala-data/{public,private,shared/to-MDL-XXX,shared/from-MDL-YYY,config}

2. Buat File Identitas Simpul mandala.info

Lokasi: ~/mandala-data/config/mandala.info

Isi contoh:

[identity]

name      = MDL-JKT-KRW01

type      = rt

location  = Jakarta Timur

admin     = Riko

version   = 1.0

3. Buat File Bagian yang Dibagikan mandala.share

Lokasi: ~/mandala-data/config/mandala.share

[public]

- mural_rt01.jpg

- resep_lokal.pdf

[conditional]

video_warga.mov = to: MDL-SMG-RT12, MDL-PLG-RT09

4. (Opsional) File Keluar dari Jaringan mandala.exit

Lokasi: ~/mandala-data/config/mandala.exit

[exit]

reason = "transisi organisasi lokal"

date   = 2025-06-10

2. Konfigurasi Sinkronisasi (rsync)

Prinsip: Hanya pull-based, tidak ada push otomatis.

A. Install rsync (jika belum)

sudo apt install rsync

B. Contoh Sinkronisasi dari Simpul Lain

rsync -avz user@192.168.1.20:/home/user/mandala-data/public/ ~/mandala-data/shared/from-MDL-XXX/

Dapat dijadwalkan dengan cron untuk sinkronisasi otomatis setiap malam.

💬 3. Komunikasi Simpul (Matrix atau XMPP)

A. Matrix Server Lokal (menggunakan Element + Synapse)

Install Synapse: https://matrix-org.github.io/synapse/latest/setup/installation.html

Gunakan Element web untuk antarmuka pengguna

Nama pengguna Matrix: @mdl-krw01:mandala.local

B. Alternatif Ringan: XMPP Server Lokal

Gunakan Prosody:

sudo apt install prosody

Tambah user:

sudo prosodyctl adduser mdl-krw01@mandala.local

Gunakan aplikasi Dino atau Gajim untuk mengakses.

Panduan Membuat Server Lokal File-Sharing dengan WebDAV

📌 Tujuan

Membuat simpul Mandala dapat berbagi file lewat jaringan lokal (Wi-Fi atau LAN) dengan akses via browser atau file explorer, tanpa memerlukan internet.

🛠️ 1. Persiapan

Kebutuhan Sistem:

Sistem operasi Linux (Debian/Ubuntu/Raspbian)

Paket apache2 dan apache2-utils

🔧 2. Instalasi Apache dan Modul WebDAV

sudo apt update

sudo apt install apache2 apache2-utils

Aktifkan modul WebDAV:

sudo a2enmod dav dav_fs

sudo systemctl restart apache2

📁 3. Buat Folder untuk File Mandala

Misalnya kita akan membagikan isi dari folder ~/mandala-data/public/

sudo mkdir -p /var/www/html/mandala

sudo chown -R www-data:www-data /var/www/html/mandala

🗂️ 4. Konfigurasi WebDAV di Apache

Buat file konfigurasi baru:

sudo nano /etc/apache2/sites-available/mandala-dav.conf

Isi dengan:

apacheconf

<VirtualHost *:80>

ServerAdmin admin@mandala.local

ServerName mandala.local

DocumentRoot /var/www/html/mandala

<Directory /var/www/html/mandala>

Options Indexes FollowSymLinks

AllowOverride None

Require all granted

</Directory>

Alias /webdav /var/www/html/mandala

<Location /webdav>

DAV On

AuthType Basic

AuthName "Mandala Share"

AuthUserFile /etc/apache2/.htpasswd

Require valid-user

</Location>

</VirtualHost>

🔐 5. Buat User Akses (Optional – dengan password)

sudo htpasswd -c /etc/apache2/.htpasswd mandalauser

Masukkan password saat diminta.

🚀 6. Aktifkan Virtual Host dan Restart Apache

sudo a2ensite mandala-dav.conf

sudo systemctl reload apache2

🌐 7. Akses WebDAV via Jaringan Lokal

Dari browser:
http://mandala.local/webdav
(bisa diakses dari HP, laptop lain, dll — selama dalam jaringan yang sama)

Dari file explorer (Linux/Windows):
→ Map Network Drive
→ \\mandala.local\webdav atau http://mandala.local/webdav

📌 CATATAN:

Untuk jaringan tanpa DNS, gunakan IP langsung:
http://192.168.1.10/webdav

Ubah file /etc/hosts di klien agar mandala.local dikenali.

Panduan Membuat Server Lokal File-Sharing dengan Nextcloud

📌 Tujuan:

Membuat server lokal (tanpa internet) untuk file-sharing komunitas Mandala yang lebih ramah pengguna, berfitur lengkap, dan bisa diakses dari HP/laptop via browser atau aplikasi Nextcloud.

🛠️ 1. Persiapan Sistem

Minimal Spesifikasi:

OS: Debian/Ubuntu/Raspbian

RAM: 1 GB (disarankan 2 GB)

Storage: ≥16 GB (pakai HDD/SSD)

Koneksi: LAN/Wi-Fi lokal

Kebutuhan Paket:

Apache2

PHP ≥ 7.4

MariaDB/MySQL

unzip, wget, curl

⚙️ 2. Instalasi Apache, PHP, dan MariaDB

sudo apt update

sudo apt install apache2 mariadb-server libapache2-mod-php php php-mysql php-gd php-curl php-xml php-mbstring php-zip php-intl php-bcmath php-imagick unzip curl -y

🔐 3. Konfigurasi Database untuk Nextcloud

sudo mysql -u root

Lalu ketik di prompt SQL:

sql

CREATE DATABASE nextcloud;

CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY 'passwordku';

GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextclouduser'@'localhost';

FLUSH PRIVILEGES;

EXIT;

Ganti 'passwordku' dengan password aman.

⬇️ 4. Unduh & Ekstrak Nextcloud

cd /tmp

wget https://download.nextcloud.com/server/releases/latest.zip

unzip latest.zip

sudo mv nextcloud /var/www/html/

📂 5. Set Permissions

sudo chown -R www-data:www-data /var/www/html/nextcloud

sudo chmod -R 755 /var/www/html/nextcloud

🌐 6. Konfigurasi Apache untuk Nextcloud

Buat file konfigurasi:

sudo nano /etc/apache2/sites-available/nextcloud.conf

Isi dengan:

apache

<VirtualHost *:80>

ServerAdmin admin@mandala.local

DocumentRoot /var/www/html/nextcloud

ServerName nextcloud.local

<Directory /var/www/html/nextcloud>

Options +FollowSymlinks

AllowOverride All

Require all granted

</Directory>

ErrorLog ${APACHE_LOG_DIR}/nextcloud_error.log

CustomLog ${APACHE_LOG_DIR}/nextcloud_access.log combined

</VirtualHost>

Aktifkan konfigurasi:

sudo a2ensite nextcloud.conf

sudo a2enmod rewrite headers env dir mime

sudo systemctl restart apache2

🖥️ 7. Akses dan Setup Web Interface

Buka browser dari HP/laptop di jaringan lokal:

arduino

http://nextcloud.local/

(atau pakai IP langsung: http://192.168.1.10/nextcloud)

Ikuti wizard instalasi:

Buat admin user

Masukkan database:
DB name: nextcloud
User: nextclouduser
Password: passwordku
Host: localhost

📱 8. Akses dari HP/Laptop Lain

Dari browser:

http://192.168.1.10/nextcloud

Dari aplikasi Nextcloud:

Unduh dari Play Store/F-Droid/App Store

Masukkan URL server: http://192.168.1.10/nextcloud

📌 Tips Opsional

🌐 Tanpa internet? Nextcloud bisa tetap dipakai offline di jaringan lokal!

🔐 Tanpa login publik? Bisa buat user tamu (guest) atau folder publik

💽 Sinkronisasi folder lokal: gunakan Nextcloud desktop client (Windows/Linux)

✅ Siap digunakan untuk:

Berbagi dokumen bersama komunitas

Unggah konten Mandala (poster, PDF, video)

Akses file bersama dari berbagai perangkat

1. mandala.info — Identitas Simpul

Fungsi: Menyimpan metadata dasar tentang simpul Mandala, seperti nama, lokasi, tipe, admin, dan versi.

Format file: INI-like (plaintext)
Lokasi: /mandala-data/config/mandala.info

📄 Contoh isi:

[identity]

id        = MDL-JKT-KRW01

type      = rt

location  = Jakarta Timur

admin     = Riko A.

version   = 1.0

✅ Tips:

Gunakan format konsisten MDL-<KOTA/KODE>-<NAMA>-<VERSI>

Field type bisa: rt, rw, desa, kolektif, komunitas, dst.

🔄 2. mandala.share — Daftar Konten yang Dibagikan

Fungsi: Menentukan file mana yang akan dibagikan ke simpul mana.

Format file: plaintext config sederhana
Lokasi: /mandala-data/config/mandala.share

📄 Contoh isi:

diff

[public]

- mural_rt01.jpg

- resep_dapur.pdf

[conditional]

- video_warga.mov = to: MDL-SMG-RT12, MDL-PLG-RT09

- draft_poster.png = to: MDL-JKT-KRW02

✅ Tips:

Semua file harus berada di dalam /mandala-data/public/ atau /mandala-data/shared/

Bisa dibaca otomatis oleh script Python atau antarmuka admin untuk sinkronisasi.

📴 3. mandala.exit — Notifikasi Keluar dari Jaringan

Fungsi: Memberi tahu bahwa simpul berhenti aktif sementara atau permanen.

Format file: plaintext notice
Lokasi: /mandala-data/config/mandala.exit

📄 Contoh isi:

[exit]

reason = "Transisi ke simpul baru, pengurus pindah."

date   = 2025-08-01

contact = riko@krw01.mandala.local

✅ Tips:

File ini bisa dibaca simpul lain saat mencoba pull data.

Tidak perlu dihapus meski simpul aktif kembali (cukup update saja).

Contoh Konfigurasi rsync untuk Sinkronisasi Antar Simpul Mandala

rsync adalah alat baris perintah yang efisien dan ringan untuk menyinkronkan file antar mesin, cocok untuk jaringan desentralistik Mandala karena:

Hanya sinkronisasi file yang berubah

Mendukung pull-based model (simpul menarik file dari simpul lain)

Dapat digunakan melalui SSH, atau secara lokal (LAN)

📦 1. Struktur Dasar

Misal:

Simpul A = MDL-JKT-KRW01

Simpul B = MDL-SMG-RT12

Simpul B ingin sinkronisasi konten publik dari Simpul A.

💻 2. Contoh Perintah rsync via SSH

rsync -avz \

user@krw01.local:/mandala-data/public/ \

/mandala-data/shared/from-MDL-JKT-KRW01/

Penjelasan:

-a → mode arsip (termasuk metadata)

-v → verbose (tampilkan log)

-z → kompresi transfer data

user@krw01.local → host simpul sumber

/mandala-data/public/ → direktori yang disinkronisasi

from-MDL-... → folder tujuan di simpul kita

🌐 3. Sinkronisasi via LAN (Tanpa SSH)

Jika kedua simpul berada di jaringan lokal, Anda bisa menggunakan rsync dengan protokol rsync daemon.

🔧 a. Jalankan rsync daemon di simpul sumber

File konfigurasi /etc/rsyncd.conf:

pgsql

[mandala-public]

path = /mandala-data/public

comment = Folder publik Mandala

read only = yes

Lalu aktifkan daemon:

rsync --daemon

🟢 b. Tarik data dari simpul lain:

rsync -av rsync://192.168.88.101/mandala-public/ /mandala-data/shared/from-MDL-JKT-KRW01/

🔄 4. Menambahkan Otomatisasi via Cron

Agar sinkronisasi berjalan berkala:

crontab -e

Tambahkan:

swift

0 * * * * rsync -avz user@krw01.local:/mandala-data/public/ /mandala-data/shared/from-MDL-JKT-KRW01/

Artinya: sinkronisasi tiap jam.

✅ 5. Tips dan Keamanan

Gunakan user terbatas (mandala) di setiap simpul.

Gunakan SSH key untuk tanpa-password access jika pakai SSH.

Cek file mandala.share untuk memastikan hanya konten diizinkan yang diambil.

Contoh Konfigurasi Matrix dan XMPP untuk Komunikasi Antar Simpul Mandala

Mandala Project mendukung komunikasi antar simpul berbasis protokol terbuka. Dua protokol yang direkomendasikan:

Matrix: modern, mendukung obrolan terenkripsi, federasi, dan file sharing.

XMPP: ringan, stabil, cocok untuk perangkat lama dan koneksi terbatas.

🟢 1. Matrix – Pilihan Modern dan Terfederasi

🔧 A. Instalasi Server Matrix (Synapse)

Gunakan Debian/Ubuntu:

sudo apt update && sudo apt install matrix-synapse

Ikuti panduan interaktif saat instalasi, masukkan domain lokal simpul, misal:

lua

mdl-jkt-krw01.local

Edit file config:
/etc/matrix-synapse/homeserver.yaml

Pastikan:

yaml

server_name: "mdl-jkt-krw01.local"

listeners:

- port: 8008

type: http

tls: false

Restart server:

sudo systemctl restart matrix-synapse

🧑‍💻 B. Buat User

register_new_matrix_user -u riko -p password123 -a -k http://localhost:8008

🌐 C. Akses Web Client

Pasang Element Web di server, atau pakai versi lokal seperti:

Atau unduh versi self-hosted untuk jaringan intranet

💡 Kelebihan Matrix:

Bisa interkoneksi lintas simpul (jika federasi diaktifkan)

Bisa kirim file, emoji, obrolan grup

Antarmuka modern dan dukungan mobil

🟠 2. XMPP – Ringan dan Stabil

🔧 A. Instalasi Server XMPP (ejabberd)

Debian/Ubuntu:

sudo apt update && sudo apt install ejabberd

Edit konfigurasi:
/etc/ejabberd/ejabberd.yml

Tambahkan domain:

yaml

hosts:

- "mdl-jkt-krw01.local"

Buat akun admin:

ejabberdctl register admin mdl-jkt-krw01.local password123

Restart:

sudo systemctl restart ejabberd

💬 B. Akses Client

Gunakan client seperti:

Dino, Gajim, Conversations (Android)

Login dengan:

Username: admin@mdl-jkt-krw01.local

Server: IP atau domain lokal simpul

🔁 C. Federasi XMPP

Jika simpul-simpul ingin saling kirim pesan, pastikan:

Nama domain dikenali dalam DNS lokal / file /etc/hosts

Port 5269 terbuka untuk komunikasi antar simpul

✅ Catatan:

Untuk simpul kecil: XMPP cukup

Untuk simpul besar dan kreatif: Matrix lebih powerful

Keduanya bisa berdampingan

1. Menyusun Struktur Folder Final Dokumentasi

Ini akan menjadi fondasi untuk dokumen digital, website, bahkan GitHub nantinya.

Contoh struktur:

arduino

MandalaProject/

├── 00_Pendahuluan/

│   └── visi-misi.md

├── 01_Protokol_Mandala/

│   ├── prinsip-dasar.md

│   ├── struktur-folder.md

│   ├── file-konfigurasi.md

│   └── sinkronisasi-data.md

├── 02_Panduan_Implementasi/

│   ├── setup-simpul.md

│   ├── rsync-config.md

│   ├── webdav-setup.md

│   ├── nextcloud-setup.md

│   └── matrix-xmpp.md

├── 03_Peran_NeoNefos/

│   └── nilai-dan-peran.md

├── 04_Koordinasi_Forum/

│   └── mekanisme-koordinasi.md

├── 05_Visualisasi/

│   ├── diagram-jaringan.png

│   ├── flowchart-sinkronisasi.png

│   └── interface-admin.png

├── 06_Lisensi/

│   └── lisensi-cc-by-sa.md

└── README.md

✍️ 2. Menuliskan Semua Teks Hasil Diskusi ke dalam File Markdown (atau format lain)

Kita akan mulai dengan mengubah seluruh output ini ke dokumen markdown (.md) agar mudah dibaca dan bisa langsung dipakai di website statis (Hugo, Docusaurus), GitHub, atau WordPress block.

Jika Anda ingin, saya bisa bantu langsung menuliskan isi file README.md dan folder 00_Pendahuluan/visi-misi.md sebagai langkah awal.

🎯 3. Persiapan Akhir

Setelah dokumentasi rapi:

Baru kita unggah ke GitHub (jika diinginkan)

Atau langsung kita rancang tampilannya dalam website WordPress / Hugo / Docusaurus

Sementara versi cetak (PDF) bisa diekspor dari markdown jika dibutuhkan

README.md

Ini adalah pengantar utama dari keseluruhan dokumentasi Mandala Project, memberikan konteks singkat bagi siapa pun yang mengakses repositori atau situs dokumentasinya.

# Mandala Project: Jaringan Simpul Komunitas Desentralistik

Mandala Project adalah sebuah inisiatif kolektif untuk membangun jaringan komunitas yang berdaulat secara digital, kultural, dan sosial. Melalui simpul-simpul lokal yang saling terhubung tanpa pusat komando, Mandala mendorong semangat kemandirian teknologi, gotong-royong, dan keterbukaan.

## 🔍 Apa yang Disediakan Dalam Dokumentasi Ini

Dokumentasi ini memuat:

- Visi dan Misi Mandala Project

- Protokol teknis untuk konektivitas simpul (folder, metadata, konfigurasi, lisensi)

- Panduan mendirikan simpul lokal secara praktis

- Contoh penerapan dan visualisasi sistem

- Peran Neo Nefos sebagai penjaga nilai kolektif

- Mekanisme forum koordinasi komunitas

- Lisensi dan semangat berbagi

Semua materi ini bersifat terbuka (CC BY-SA 4.0) dan dapat disalin, dimodifikasi, serta disebarkan kembali dengan tetap mencantumkan sumber dan berbagi dalam semangat yang sama.

## 📚 Struktur Dokumentasi

MandalaProject/
├── 00_Pendahuluan/ → Visi & Misi
├── 01_Protokol_Mandala/ → Standar Teknis & Nilai Dasar
├── 02_Panduan_Implementasi/→ Tutorial Praktis
├── 03_Peran_NeoNefos/ → Peran & Spirit
├── 04_Koordinasi_Forum/ → Mekanisme Kolaborasi
├── 05_Visualisasi/ → Diagram, Flowchart, Interface
├── 06_Lisensi/ → Lisensi & Hak Cipta

## 🤝 Bergabung dan Berkontribusi

Semua komunitas dan individu dipersilakan untuk:

- Membentuk simpul baru

- Berkontribusi pada pengembangan protokol

- Menyebarluaskan semangat Mandala

- Menerjemahkan dokumentasi ini ke dalam bahasa lokal

Untuk bergabung, hubungi kami melalui kanal komunitas atau formulir kontak (tersedia di website resmi).

---

**Lisensi:**

Dokumentasi ini tersedia di bawah [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

00_Pendahuluan/visi-misi.md

# Visi & Misi Mandala Project

## 🌐 Visi

Membangun jaringan simpul komunitas yang merdeka, setara, dan saling terhubung secara desentralistik — baik dalam ranah digital, sosial, maupun kultural — demi memperkuat keberdayaan lokal dan solidaritas global.

Mandala bukan sekadar jaringan teknologi. Ia adalah bentuk hidup dari gotong-royong digital, tempat kreativitas rakyat, pengetahuan akar rumput, dan semangat pembebasan tumbuh bersama.

## 🎯 Misi

1. **Mendorong kedaulatan digital komunitas**

- Dengan menyediakan panduan dan alat berbasis protokol terbuka yang mudah diakses dan dijalankan.

2. **Menghubungkan simpul-simpul komunitas**

- Tanpa pusat kendali, dengan struktur yang fleksibel, aman, dan terbuka, memungkinkan pertukaran data dan pengetahuan secara adil.

3. **Menguatkan kebudayaan kolektif**

- Melalui arsip karya, dokumentasi perjuangan, serta pertukaran seni dan gagasan di antara simpul-simpul Mandala.

4. **Menjadi ruang eksperimentasi sosial dan teknologis**

- Mendorong adaptasi lokal atas protokol yang ada dan terbuka terhadap inovasi dari akar rumput.

5. **Menjaga nilai keterbukaan dan kesukarelaan**

- Tanpa paksaan, tanpa eksklusivitas, semua simpul tumbuh sesuai kebutuhan dan ritme masing-masing, tapi tetap saling belajar dan berbagi.

---

## 🌀 Mandala Adalah...

- Jaringan yang hidup karena niat kolektif, bukan infrastruktur modal.

- Desain yang berkembang bersama, bukan cetak biru yang dipaksakan.

- Tempat berbagi, bukan menumpuk.

- Alat perlawanan terhadap sentralisasi dan ekstraksi data.

- Jalan sunyi membangun teknologi pembebasan dari bawah.

01_Protokol_Mandala/prinsip-dasar.md

# Prinsip Dasar Protokol Mandala

Protokol Mandala dirancang untuk menciptakan ekosistem jaringan komunitas yang merdeka, fleksibel, dan saling terhubung tanpa mengorbankan otonomi lokal masing-masing simpul. Prinsip-prinsip berikut adalah fondasi dari seluruh sistem.

---

## ⚙️ 1. Desentralisasi Total

Tidak ada server pusat atau simpul pengendali. Setiap simpul berdiri sendiri dan berperan sebagai penyimpan, pengelola, sekaligus penjaga data dan kontennya. Koneksi antar simpul bersifat sukarela dan simetris.

---

## ✊ 2. Kesukarelaan

Setiap simpul bebas bergabung, menyesuaikan kapasitasnya, atau keluar tanpa konsekuensi teknis yang membebani simpul lain. Tidak ada paksaan, hanya saling percaya dan saling bantu.

---

## 🔐 3. Kedaulatan & Privasi Data

Setiap simpul mengatur sendiri data yang ia kelola. Tidak ada akses tanpa izin eksplisit. Data dibagikan hanya jika disetujui secara terbuka melalui file konfigurasi yang mudah dipahami.

---

## 🔁 4. Interoperabilitas Terbuka

Simpul-simpul Mandala tidak harus memakai alat yang sama, selama mereka menggunakan protokol terbuka (HTTP/S, rsync, IPFS, Matrix, XMPP, WebDAV, dll). Hal ini memungkinkan fleksibilitas alat dan tetap saling terhubung.

---

## 📂 5. Transparansi Berbasis Folder & File

Struktur direktori, file manifest (seperti `mandala.share`, `mandala.info`, `mandala.exit`) menjadi dasar komunikasi dan berbagi. Semua simpul memahami struktur yang sama, meski sistem operasinya bisa berbeda.

---

## 🔌 6. Plug-Out Safe

Simpul dapat keluar dari jaringan kapan saja tanpa mengganggu struktur. Sistem sinkronisasi berbasis *pull*, bukan *push*, memastikan bahwa ketiadaan satu simpul tidak merusak keseluruhan jaringan.

---

## 🌱 7. Adaptif dan Bertumbuh Bersama

Mandala tidak statis. Protokolnya dapat diperbarui berdasarkan hasil forum komunitas. Penyesuaian lokal dihormati selama prinsip utama dijaga. Dokumentasi selalu terbuka untuk versi-versi baru.

---

## 🌀 8. Seni, Pengetahuan, dan Kebebasan

Mandala bukan hanya teknologi, tetapi juga ruang ekspresi, belajar, dan keberanian. Teknologi diperlakukan sebagai alat pembebasan — bukan alat kontrol.

01_Protokol_Mandala/struktur-teknis.md

# Struktur Teknis Protokol Mandala

Bagian ini menjabarkan struktur teknis minimum yang disepakati agar semua simpul Mandala dapat saling terhubung tanpa kehilangan kebebasan memilih alat dan sistem operasinya sendiri.

---

## 📁 1. Struktur Direktori Standar

Setiap simpul Mandala menyusun data lokal dalam direktori berikut:

/mandala-data/
├── public/ 			→ konten yang dibagikan secara terbuka
├── private/ 			→ konten yang tidak dibagikan (lokal saja)
├── shared/
 │           ├── to-MDL-XXX/ 	→ konten untuk simpul tertentu
 │           └── from-MDL-YYY/ 	→ konten masuk dari simpul lain
 └── config/ 			→ file konfigurasi dan metadata simpul

---

## 📄 2. File Konfigurasi

### A. `mandala.info`

Metadata identitas simpul:

```ini

[identity]

name        = MDL-JKT-KRW01

type        = rt

location    = Jakarta Timur

admin       = Riko

version     = 1.0

B. mandala.share

Daftar konten yang dibagikan:

[public]

- mural_rt01.jpg

- resep_lokal.pdf

[conditional]

video_warga.mov = to: MDL-SMG-RT12, MDL-PLG-RT09

C. mandala.exit

Diperbarui saat simpul keluar:

[exit]

reason      = "Transisi organisasi lokal"

date        = 2025-06-10

3. Sistem Sinkronisasi

Mandala hanya menggunakan sinkronisasi berbasis pull (tarik data), bukan push. Keuntungannya:

Tidak membanjiri jaringan

Simpul bebas memilih apa yang ingin disinkronisasi

Tidak bergantung pada koneksi aktif setiap waktu

Protokol sinkronisasi yang direkomendasikan:

🔄 rsync → untuk jaringan lokal sederhana

🌐 HTTP/S → via server lokal (misalnya WebDAV, Nextcloud)

🧱 IPFS → untuk jaringan peer-to-peer desentral

📡 Syncthing → opsional, untuk sinkronisasi otomatis antar mesin

4. Akses dan Kontrol

Hanya file yang tercantum dalam mandala.share yang dianggap sah untuk diakses simpul lain. Folder private/ tidak pernah diakses dari luar.

5. Contoh Penamaan Simpul

Semua simpul menggunakan format identitas:

MDL-<WILAYAH>-<LOKASI>-<VERSI>

Contoh:

MDL-JKT-KRW01-v1

MDL-YOG-DESA07-v2

MDL-BDG-RW09-v1.2

6. Koneksi Mandala

Simpul dapat terhubung lewat:

Wi-Fi lokal / hotspot bersama

Kabel LAN

Internet (VPN / DDNS / MeshNet)

Peer-to-peer (via IPFS, Briar, dsb.)

Konektivitas tidak harus permanen — sinkronisasi bisa dilakukan saat jaringan tersedia.

---

01_Protokol_Mandala/peran-neo-nefos.md

# Peran Neo Nefos dalam Jaringan Mandala

Sebagai inisiator protokol Mandala, Neo Nefos Movement tidak bertindak sebagai otoritas pusat, melainkan sebagai penjaga nilai, penyedia panduan, dan simpul rujukan dalam jaringan.

---

## 🎯 1. Penjaga Nilai (Guardian of Values)

Neo Nefos menyusun prinsip-prinsip dasar Mandala berdasarkan:

- **Desentralisasi**: setiap simpul adalah mandiri

- **Sukarela**: tidak ada pemaksaan untuk bergabung atau berbagi

- **Privasi**: semua simpul berhak menjaga kerahasiaannya

- **Solidaritas**: saling bantu antar komunitas

---

## 📚 2. Penyedia Panduan (Custodian of Documentation)

Neo Nefos bertugas:

- Menyusun dan memperbarui protokol

- Menyediakan dokumentasi resmi

- Menyebarkan panduan teknis dan etis

- Menyediakan FAQ dan studi kasus

Semua materi akan tersedia secara daring dan dapat disalin ulang (copyleft).

---

## 💡 3. Simpul Rujukan (Reference Node)

Neo Nefos akan menjalankan satu atau lebih simpul permanen sebagai:

- Simpul pengarsipan (repository simpul-simpul lain)

- Simpul pembelajaran (berisi panduan, tutorial)

- Simpul distribusi (media berbagi tools dan update)

Alamat dan identitas simpul ini akan dibuka untuk publik dan dapat diuji keterhubungannya oleh simpul lain.

---

## 🧑🏽‍🤝‍🧑🏽 4. Fasilitator Kolaborasi

Kami mendorong simpul-simpul Mandala untuk:

- Membuat sub-jaringan (subnets) sesuai wilayah/tema

- Menginisiasi forum musyawarah (Matrix, XMPP, mail-list)

- Berbagi praktik terbaik (best practices)

Neo Nefos akan menyediakan ruang untuk koordinasi lintas simpul dan lintas gerakan.

---

## 🔁 5. Tidak Bersifat Sentral

Neo Nefos tidak:

- Mengendalikan isi simpul lain

- Mengumpulkan data pengguna simpul lain

- Memberi peringkat atau sertifikasi simpul

Setiap simpul tetap independen.

---

## ✨ 6. Ajakan Terbuka

Kami mengajak siapa pun yang:

- Ingin membangun kedaulatan data komunitas

- Ingin merintis arsip rakyat

- Ingin belajar teknologi terdistribusi

- Ingin membangun jaringan sosial alternatif

untuk bergabung, mereplikasi, atau memodifikasi simpul Mandala. Hubungi kami untuk koordinasi awal, atau mulai saja dari panduan kami.

_Mandala tidak dimiliki siapa pun, tapi bisa dijalankan oleh siapa saja._

01_Protokol_Mandala/forum-dan-koordinasi.md

# Forum dan Koordinasi dalam Jaringan Mandala

Agar jaringan Mandala tetap hidup, saling terhubung, dan terus berkembang, dibutuhkan mekanisme musyawarah serta pertukaran pengetahuan secara periodik dan horizontal.

---

## 📅 1. Jenis Forum

### a. Forum Lokal (RT/RW)

- Skala: antar simpul dalam satu lingkungan kecil

- Frekuensi: setiap 2 bulan

- Tujuan:

- Tukar cerita dan evaluasi

- Kolaborasi lintas simpul

- Sinkronisasi lokal

### b. Forum Wilayah (Kelurahan/Kecamatan)

- Skala: antar RW atau komunitas desa-kelurahan

- Frekuensi: 3–4 bulan sekali

- Tujuan:

- Koordinasi simpul dan server kolektif

- Pemutakhiran protokol regional

- Pelatihan lintas simpul

### c. Forum Nasional

- Skala: semua simpul yang aktif di satu negara

- Frekuensi: sekali setahun

- Tujuan:

- Pengesahan simpul baru

- Review versi protokol

- Pertukaran praktik terbaik

- Perayaan karya kolektif

### d. Forum Internasional

- Skala: jaringan global atau jaringan solidaritas selatan

- Format: daring atau fisik

- Diselenggarakan secara terbuka oleh simpul yang siap menjadi tuan rumah

---

## 📌 2. Mekanisme Forum

- Setiap simpul dapat mengusulkan agenda

- Notulen ditulis dan dibagikan ke seluruh simpul

- Hasil keputusan bersifat rekomendatif, bukan mengikat

- Forum dilakukan menggunakan media yang sesuai kapasitas:

- Tatap muka langsung

- Grup Matrix/XMPP

- Mailing list

- Web forum lokal

---

## 🛠 3. Dukungan Infrastruktur Forum

Neo Nefos menyarankan penggunaan perangkat bebas dan terbuka:

- Matrix (Synapse) atau XMPP untuk percakapan

- Etherpad atau CryptPad untuk notulen kolaboratif

- Lufi atau Nextcloud untuk berbagi dokumen

- Lemmy atau Discourse untuk forum daring

---

## 🔁 4. Hasil Forum sebagai Dokumentasi Kolektif

Hasil dari setiap forum akan:

- Diarsip oleh simpul regional dan/atau Neo Nefos

- Dapat diakses ulang oleh simpul-simpul lain

- Menjadi bahan refleksi dan perbaikan protokol

- Dituliskan dalam bahasa yang mudah dipahami

---

## 🧭 5. Etika Musyawarah Mandala

- Semua suara didengar, tidak ada hierarki partisipasi

- Ketidaksepakatan adalah bagian dari proses

- Setiap simpul boleh menjalankan eksperimen lokal

- Setiap simpul bebas untuk tidak setuju dan membuat jalurnya sendiri

---

_Mandala tumbuh dari perbedaan, bukan keseragaman._

01_Protokol_Mandala/lisensi.md

# Lisensi dan Kebebasan Protokol Mandala

Protokol Mandala adalah karya kolektif yang tumbuh dari semangat berbagi dan membangun dunia yang lebih adil melalui teknologi yang berpihak pada rakyat. Oleh karena itu, kami memilih lisensi yang memastikan kebebasan setiap individu dan komunitas untuk menggunakan, mengubah, serta menyebarluaskan protokol ini.

---

## 🔓 Lisensi

Seluruh dokumen dalam repositori Mandala Project dilisensikan di bawah:

**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**

> Anda bebas untuk:

> - **Berbagi** — menyalin dan menyebarluaskan ulang materi ini dalam format apapun

> - **Adaptasi** — menggubah, mengubah, dan membuat turunan dari materi ini untuk tujuan apapun, termasuk komersial

> Dengan syarat:

> - **Atribusi** — Anda harus memberikan kredit yang layak, menyertakan tautan lisensi, dan memberi tahu jika ada perubahan.

> - **ShareAlike** — Jika Anda menggubah, mengubah, atau membuat turunan dari materi ini, Anda harus mendistribusikan kontribusi Anda di bawah lisensi yang sama dengan yang asli.

[Lihat detail lisensi di sini → https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/)

---

## 🤝 Kebijakan Kontribusi

Kami mendorong partisipasi dan kontribusi dari semua komunitas dan individu:

- Kontributor diminta untuk menjaga semangat terbuka dan saling menghormati

- Perubahan besar sebaiknya melalui forum dan konsensus simpul

- Setiap simpul bebas membuat turunan lokal sesuai kebutuhan, tanpa kehilangan keterhubungan

---

## 🧬 Hak Cipta Kolektif

Mandala Project tidak dimiliki oleh individu atau organisasi tunggal. Semua dokumen ini adalah hasil dari upaya kolektif yang dibangun atas dasar:

- Sejarah perjuangan teknologi rakyat

- Pengetahuan bebas yang saling menghidupi

- Solidaritas lintas wilayah dan generasi

Nama "Mandala" dapat digunakan secara bebas selama digunakan dalam semangat yang sejalan.

---

## 🛡 Catatan

Kami tidak bertanggung jawab atas penyalahgunaan protokol ini untuk tujuan yang bertentangan dengan nilai-nilai dasar kami: desentralisasi, sukarela, solidaritas, privasi, dan kedaulatan data.

Silakan menghubungi Neo Nefos Movement jika Anda ingin berdiskusi lebih jauh mengenai adaptasi lisensi atau penyesuaian lokal.

---

_Sebagaimana jaringan Mandala bebas tumbuh, dokumennya pun bebas hidup dan diperbanyak._

02_Dokumentasi/struktur-folder-mandala.md

# Struktur Folder Mandala

_Arsitektur Sederhana untuk Kedaulatan Data_

Salah satu prinsip Mandala adalah _kesederhanaan yang dapat direplikasi_. Untuk itu, kami menyarankan struktur direktori standar agar simpul-simpul dapat saling membaca dan menyelaraskan isi lokalnya dengan simpul lain.

Berikut struktur direktori dasar dalam satu simpul:

/mandala-root/
│
├── mandala.info # Metadata tentang simpul ini (nama, lokasi, waktu sinkron, dsb)
├── mandala.share # File daftar isi konten yang dibagikan ke simpul lain
├── mandala.exit # (Opsional) File instruksi untuk ekspor konten keluar jaringan
│
├── dokumen/ # Teks, PDF, data tulisan
├── audio/ # Musik, podcast, rekaman
├── video/ # Dokumenter, klip, arsip audiovisual
├── gambar/ # Poster, selebaran, ikon, arsip visual
├── perangkat/ # Tools, skrip, template, dataset
│
└── log/ # Catatan sinkronisasi, error, dan pesan masuk dari simpul lain

---

## 📘 Penjelasan File Konfigurasi

- **mandala.info**

Format `.json` atau `.yaml`. Berisi info umum simpul:

- `nama`: "simpul-karangrejek"

- `lokasi`: "Gunung Kidul, DIY"

- `waktu_sync`: "setiap Senin pukul 20:00 WIB"

- `protokol`: ["rsync", "usb", "manual"]

- **mandala.share**

Format `.txt` atau `.csv`. Menyebutkan konten apa saja yang dapat diakses simpul lain, misalnya:

dokumen/panduan-pertanian-organik.pdf
audio/kumpulan-puisi.mp3
video/arsip-1998.avi

- **mandala.exit**

File opsional. Jika diisi, akan menginstruksikan simpul ini untuk menyalin konten tertentu ke media eksternal (flashdisk, harddisk offline, atau simpul gateway).

---

## 📁 Folder Konten

Folder konten disusun berdasarkan jenis file, bukan berdasarkan proyek. Ini untuk memudahkan:

- Penyelarasan antar simpul

- Pengarsipan

- Pengindeksan kolektif

Namun, dalam masing-masing folder, dapat dibuat subfolder berdasarkan proyek, inisiatif, atau kurasi lokal.

---

## 🧭 Catatan

- Struktur ini **bisa dimodifikasi** sesuai konteks simpul, namun kami mendorong minimal memiliki `mandala.info` dan `mandala.share` agar tetap terhubung.

- Simpul tidak wajib selalu _online_. Sinkronisasi bisa berlangsung dengan cara manual, dari flashdisk ke flashdisk.

---

_Dengan struktur ini, simpul-simpul Mandala tak sekadar berbagi data, melainkan membangun jaringan solidaritas berbasis arsip hidup._

02_Dokumentasi/panduan-setup-simpul.md

# Panduan Mendirikan Simpul Mandala

_Dari Nol Hingga Terkoneksi_

Simpul Mandala adalah unit dasar dari jaringan arsip otonom yang kita bangun bersama. Simpul dapat berupa komputer pribadi, server kecil, atau bahkan folder di dalam flashdisk. Panduan ini membimbing Anda dari awal mendirikan simpul hingga menghubungkannya dengan jaringan simpul lain.

---

## 1. Persiapan Dasar

### Perangkat yang Dibutuhkan

- Komputer/laptop atau Raspberry Pi

- Sistem operasi bebas: Linux (disarankan), Windows, atau MacOS

- Koneksi internet (opsional – bisa sinkronisasi offline)

- Aplikasi pendukung: rsync, editor teks, terminal/command prompt

### Buat Struktur Folder Mandala

Buat folder utama:

```bash

mkdir -p ~/mandala-root/{dokumen,audio,video,gambar,perangkat,log}

touch ~/mandala-root/mandala.info

touch ~/mandala-root/mandala.share

2. Menulis File mandala.info

Buka mandala.info dengan editor teks favorit, lalu isi informasi dasar simpul Anda:

{

"nama": "simpul-sukasari",

"lokasi": "Ciamis, Jawa Barat",

"waktu_sync": "Setiap Jumat, 19:00 WIB",

"protokol": ["rsync", "XMPP"],

"kontak": "simpul-sukasari@riseup.net"

}

3. Menentukan File yang Dibagikan (mandala.share)

File ini berisi daftar file atau folder yang boleh diakses simpul lain.
Contoh isi:

dokumen/panduan-pertanian-organik.pdf

audio/kumpulan-ceramah.mp3

video/arsip-mei1998.avi

4. Memasang rsync (opsional, jika pakai sinkronisasi jarak jauh)

Di Linux

sudo apt install rsync

Di Windows

Unduh cwRsync atau gunakan Git Bash yang sudah menyertakan rsync.

5. Simulasi Sinkronisasi Antar Simpul (Lokal)

Misalnya Anda dan rekan Anda saling menyalin konten dengan USB:

rsync -av ~/mandala-root/ /media/usb/simpul-lain/

Untuk jaringan:

rsync -avz ~/mandala-root/ user@ip-tujuan:/home/user/mandala-root/

6. Tambahan (Opsional)

Integrasi Matrix (obrolan)

Buat akun Matrix di 
Masuk ke ruang komunitas Mandala, atau buat ruang lokal di server Matrix komunitas Anda.

Simpul Offline

Jika simpul Anda tidak terhubung ke internet, gunakan media seperti flashdisk atau harddisk eksternal. Sinkronisasi tetap bisa dilakukan secara manual.

📎 Catatan Penting

Mandala tidak mengharuskan format tetap – tapi struktur standar sangat membantu interoperabilitas.

Simpul bisa hanya menyimpan, berbagi, atau hanya mendengar (read-only).

Setiap simpul tetap sepenuhnya berdaulat atas data mereka.

Bersama, kita membangun jaringan dokumentasi yang merdeka, lentur, dan anti-sentralistik.

02_Dokumentasi/contoh-kasus-desa.md

# Contoh Kasus: Implementasi Simpul Mandala di Desa Sukasari

Dokumentasi ini memberikan contoh konkret bagaimana sebuah desa dapat mengimplementasikan simpul Mandala untuk kebutuhan lokal mereka—dari pengarsipan kearifan lokal hingga sinkronisasi dengan simpul lain di wilayah berbeda.

---

## 1. Latar Belakang

Desa Sukasari adalah desa kecil di lereng gunung Galunggung, dengan sejarah panjang dalam pertanian organik dan pelestarian seni tradisional. Banyak pengetahuan dan praktik lokal yang tidak terdokumentasi dengan baik. Komunitas pemuda desa membentuk simpul Mandala untuk mendokumentasikan dan membagikannya secara otonom.

---

## 2. Langkah-Langkah Implementasi

### a. Mendirikan Simpul

- Komputer tua disiapkan ulang dengan sistem Linux ringan (misal: Xubuntu).

- Folder `mandala-root` dibuat di direktori utama.

- Pemuda desa membagi tugas dokumentasi: beberapa mewawancarai petani, lainnya mendigitalisasi dokumen lama.

### b. Pengisian Konten Awal

- **dokumen/**: transkrip wawancara, dokumen adat, naskah kuno

- **audio/**: rekaman wawancara dengan tetua adat, lagu-lagu rakyat

- **gambar/**: foto-foto pameran seni dan pertanian

- **video/**: dokumenter pendek tentang sejarah desa

### c. Menulis `mandala.info` dan `mandala.share`

```json

{

"nama": "simpul-sukasari",

"lokasi": "Desa Sukasari, Tasikmalaya",

"waktu_sync": "Setiap minggu, Sabtu 20:00 WIB",

"protokol": ["rsync", "flashdisk"],

"kontak": "simpul-sukasari@riseup.net"

}

mandala.share:

dokumen/sejarah-desa.pdf

audio/wawancara-mbah-aminah.mp3

video/pertanian-berkelanjutan.mp4

d. Sinkronisasi Offline

Flashdisk dibawa ke simpul kecamatan atau kota.

Rsync digunakan untuk menyalin konten antar simpul.

Konten baru dari simpul lain diseleksi dan diarsipkan kembali.

3. Dampak Awal

Warga mulai tertarik mendokumentasikan kegiatan harian.

Sekolah dasar lokal meminta pelatihan penggunaan simpul.

Beberapa simpul desa lain menghubungi Sukasari untuk belajar sistem ini.

4. Tantangan

Keterbatasan daya listrik dan perangkat keras.

Pelatihan teknis masih diperlukan untuk sebagian warga.

Perlu sistem labeling dan metadata yang lebih seragam.

5. Peluang Pengembangan

Penyusunan kamus lokal Sunda-Galunggung digital.

Kolaborasi dengan simpul urban untuk pameran hasil dokumentasi.

Pengembangan sistem cerita interaktif untuk anak-anak berbasis konten lokal.

Contoh ini hanyalah satu dari banyak kemungkinan. Mandala lahir dari konteks, tumbuh dari bawah, dan hidup dari kolaborasi sukarela.

02_Dokumentasi/struktur-folder.md

# Struktur Folder Simpul Mandala

Struktur folder ini bersifat anjuran, bukan kewajiban. Tujuannya adalah memudahkan pengarsipan dan sinkronisasi lintas simpul. Setiap simpul bebas menyesuaikan berdasarkan kebutuhan lokal, selama file `mandala.info` dan `mandala.share` tetap tersedia di akar direktori.

---

## 🌐 Struktur Dasar

mandala-root/
├── dokumen/
│ └── *.pdf / *.txt / *.odt
├── gambar/
│ └── *.jpg / *.png / *.svg
├── audio/
│ └── *.mp3 / *.ogg / *.wav
├── video/
│ └── *.mp4 / *.webm
├── proyek/
│ └── [folder sub-proyek kolaboratif atau eksperimen lokal]
├── arsip/
│ └── [salinan hasil sinkronisasi simpul lain]
├── mandala.info
├── mandala.share
└── mandala.exit (opsional)

---

## 📄 Deskripsi Folder

### `dokumen/`

Untuk naskah, makalah, dokumen hukum, catatan sejarah, transkrip wawancara, dsb.

### `gambar/`

Visual seperti foto kegiatan, hasil karya seni, poster aksi, ilustrasi dokumentasi.

### `audio/`

Rekaman wawancara, musik lokal, pengarsipan suara, siaran komunitas.

### `video/`

Video pendek, dokumenter, tutorial, pertunjukan seni, liputan peristiwa.

### `proyek/`

Folder untuk sub-kegiatan atau inisiatif berbasis proyek. Bisa berupa karya kolaboratif, eksperimen teknologi, atau seni kolektif.

### `arsip/`

Tempat menyimpan salinan konten dari simpul-simpul lain hasil sinkronisasi. Disarankan untuk membuat subfolder berdasar nama simpul asal.

---

## 📁 File Protokol

### `mandala.info`

File JSON berisi identitas simpul, waktu sinkronisasi, metode distribusi, dan kontak.

### `mandala.share`

File teks berisi daftar file yang ingin dibagikan ke simpul lain. Contoh:

dokumen/panduan-pertanian.pdf
audio/lagu-rakyat.mp3

### `mandala.exit` (Opsional)

Jika ingin menonaktifkan simpul atau memutus sinkronisasi sementara, file kosong ini bisa dibuat sebagai sinyal bagi simpul lain.

---

_Standarisasi bukan bentuk kontrol, tapi upaya untuk memperkuat kolaborasi lintas simpul dalam semangat otonomi dan gotong royong._

02_Dokumentasi/file-standar.md

# Format File Standar dalam Protokol Mandala

Dokumen ini menjelaskan format standar untuk file `mandala.info`, `mandala.share`, dan `mandala.exit` yang digunakan dalam setiap simpul Proyek Mandala. Standarisasi ini bertujuan untuk memastikan interoperabilitas antar simpul, sekaligus menjaga fleksibilitas dan kesederhanaan.

---

## 📘 1. `mandala.info` (Format JSON)

File ini wajib ada dan berisi informasi dasar tentang simpul. Contoh isi:

```json

{

"nama_simpul": "Rumah Arunika",

"lokasi": "Yogyakarta, Indonesia",

"pengelola": "kolektif mandiri",

"kontak": {

"email": "arunika@riseup.net",

"matrix": "@arunika:matrix.org"

},

"metode_sinkronisasi": ["rsync", "webdav"],

"sinkronisasi_terakhir": "2025-05-28T13:25:00+07:00",

"versi_protokol": "0.8-beta"

}

Jika ada tambahan metadata seperti jenis simpul (arsip, distribusi, riset), tambahkan sebagai key baru.

2. mandala.share (Format Plaintext)

dokumen/panduan-permabudaya.pdf

gambar/poster-2025.jpg

audio/lagu-rakyat.mp3

video/dokumenter-kampung.mp4

proyek/seni-pelintas-batas/

Satu entri per baris.

Folder diakhiri dengan /.

Jika ingin menyertakan deskripsi atau anotasi, gunakan awalan # sebagai komentar.

3. mandala.exit (File Kosong)

Jika simpul ingin menghentikan partisipasi sementara, cukup buat file kosong bernama mandala.exit.

Simpul lain yang mendeteksi file ini akan menghentikan sinkronisasi secara otomatis.

File ini bisa dihapus jika simpul ingin kembali aktif.

🔐 Catatan Privasi

Jangan cantumkan data sensitif atau pribadi tanpa izin.

Simpul bebas menambah sistem enkripsi atau autentikasi di tingkat sinkronisasi.

🌀 Tentang Standarisasi

Semua format file ini adalah saran, bukan kewajiban mutlak. Selama simpul lain dapat membaca dan memahami file yang Anda buat, Anda bebas menyesuaikan isinya.

---

Dengan ini, dokumentasi di folder `02_Dokumentasi/` selesai seluruhnya. Apakah kita lanjut ke direktori `03_Tutorial/`? Jika ya, kita bisa mulai dengan file `setup-simpul.md`.

Logo mandala full colour version (atas latar gelap ; bawah latar terang)

Logo mandala mono chrome  version (atas latar gelap ; bawah latar terang)