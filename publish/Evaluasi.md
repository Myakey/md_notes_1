Perkenalan Prodi ga bisa bareng maxima, jadi desak BPH turunin MoU

Terlalu lama mikirin deploynya padahal susah, dan planningnya ga rapi, pake prinsip SoftEng.

Paling fatal mid-trans karena terlalu mepet, jadi h-seminggu baru bisa pada beli via website, jadi kalo bisa urusin midtrans dari awal urusin dari awal, fokusin di ticketing dulu, karna tahun lalu tiba2 berubah.

	Good
	Set up CI/CD dan Load Balancer ga down
Bug fatal tentang type-zone, masalah UTC-7 di servernya UTC-0 ntah kenapa ga keubah UTC-7 jadinya error, benerin hotfix di server production lagi running mau ga mau benerin

Karna ada CI/CD nya jadi lebih cepet

	Ugly
	Sebenernya website ga harus selalu standby di tempat, mendingan remote aja, karna pengalamannya berdiri ga jelas. agak buang2 tenaga. buat rotasi jaga secara online, mantau web nya server down atau nggak.

DOCKER :
App aplikasi ini dibikin jadi aplikasi lah ditaro di vps. Pake Digital Ocean. Tarik aplikasi terus di run. Misalnya CPU usage di atas 80% bisa dikasih notif.

Dokumen perusahaan dari bph jangan lupa.
Foto tempat jualan fotoin aja umn, stage (Foto panggung) (Foto dokumentasi tahun lalu, ambil dari ig)

Maxima Tahun lalu:
Ada dua , ada web internal, ada web maba

yang internal buat ngedit2 informasi organisator statenya kek gimana gitu2

web maba

Laragon
APDP

Web Internal :
Otentikasi pake sso umn 
![[Pasted image 20260208205058.png]]
Verifikasi : Udah bener belum ornmagnya ini yang ngurus ke divisi acara baru verifikasi baru bisa login

![[Pasted image 20260208205211.png]]
Toggle ini fungsinya supaya si mahasiswa bisa akses atau enggakl

![[Pasted image 20260208205314.png]]
Data state bentrok ini gara2 ada demo (KEMUNGKINAN TIDAK DIBUTUHKAN)

![[Pasted image 20260208205342.png]]

![[Pasted image 20260208205357.png]]

![[Pasted image 20260208205410.png]]

![[Pasted image 20260208205433.png]]


![[Pasted image 20260208205448.png]]
Bikin akun pake OAuth



![[Pasted image 20260208205547.png]]


MUI (Library UI), kalo bisa langsung excel jangan csv


![[Pasted image 20260208205747.png]]
Data tiket internal yang bisa diklaim

Di eksternal, itu ada beberapa yang udah bayar cuma tiketnya ga muncul disini, dugaannya adalah setelah payment diback diback, makanya ada fitur tambah tiket baru
Kemungkinan :
Masalah : Bergantung sama frontend, dari frontend ini gagal ngirim ke backend. (Kemaren nggak ngeintegrasiin midtransnya (Callback midtrans ke backend))

Masalahnya backend nunggu frontend buat ngejawab

Erronya pas udah banyak yang beli

Untuk organisator, mereka harus register dulu,

Anggaran pembelian :
Midtrans : Tergantung metode pembayaran
Domain : 300 rb
Server : 2 Jt
Mailer : 700rb
Claude : 300 rb

APIS
Rate limit : 5 MB
Internal make googleOAuth, karna hari - h maxima Tnggl 17, nah tanggal 17 akun sso umn ga bisa jadi makenya googleOAuth

Nama Docs :
Apereo CAS

JOI, Zort

Middlewares :
1. CheckDivisi : Panitia dari divisi mana 
2. CheckRole : Ngecek ini rolenya panitia, organisator, atau mahasiswa
3. JWT : Validasi JWT Token masih valid atau enggak

Flow middleware gak perlu sama persis yang penting running aja

TIMESTAMP
-> Make library buat ngurusin timestamp, librarynya udah deprecated, cari alternatif timestamp (Moment.js)
-> Problem : Di browser nyimpennya local (WIB), terus masukin ke backend, masalahnya yang dimasukin ke backend udah jadi UTC-7, habis tu masukin timestampnya, salahnya adalah yang dicek adalah WIB. Pastiin yang distore di backend sama dengan dari depan. (Jangan lupa dicek pake timestamp) Moment js tanggal berupa object, waktu itu bikinnya if (now < ...) ternyata ga boleh kek gitu, harus pake function bawaan function.

JANGAN LUPA SAMA TESTING 
Backend ga bisa dites barengan dengan frontend.

Optional : Bisa pake testing library namanya (JEST), perfunction ditesting (function testing buat backend)

Cloudflare : Dipake buat DNS (Disetting maximaumn.id) itu diarahinnya kemana

CDN pake R2 Bucket:Sat
Pake buat foto - foto state, jadi kalo misalnya ada organisator yang upload logo buat state disimpennya di R2 bucket.
Turnstile : Captcha nya yang buat centang

WA Mas Rafpo :
087753036926
WA Mas Deswandy :
081290949233


