# Portfolio Website

## Progress

### Navigasi (Navbar)

Membuat komponen navigasi (`app/components/Navbar.tsx`) dengan fitur:

- Logo dan background dekoratif menggunakan `next/image`.
- Menu navigasi desktop (Home, About me, Services, My Work, Contact me) dengan
  smooth-scroll ke masing-masing section (`#top`, `#about`, `#services`,
  `#work`, `#contact`).
- Tombol dark mode (ikon bulan) dan tombol Contact di sisi kanan navbar.
- Menu mobile (off-canvas) yang bisa dibuka lewat ikon burger dan ditutup lewat
  ikon close atau saat salah satu link menu diklik, digerakkan dengan `useRef` +
  manipulasi `style.transform` langsung ke elemen `<ul>`.

### Header (Hero Section)

Membuat komponen header/hero (`app/components/Header.tsx`) dengan fitur:

- Foto profil bulat (`assets.profile_img`) menggunakan `next/image`.
- Sapaan "Hi! I'm William Mark" dengan ikon tangan (`assets.hand_icon`).
- Judul utama (h1) berisi tagline "frontend web developer based in London" dan
  paragraf deskripsi singkat.
- Dua tombol CTA: "contact me" (scroll ke `#contact`, ikon panah kanan) dan "my
  resume" (link download `sample-resume.pdf`, ikon download).
- Layout di-center secara vertikal dan horizontal dengan `h-screen` + flexbox,
  responsif lewat breakpoint `sm`, `md`, `lg`.

Komponen ini dirender di `app/page.tsx` setelah `Navbar`, dan `app/layout.tsx`
ditambahkan class `leading-8 overflow-x-hidden` untuk mendukung layout halaman
penuh.

### About (Tentang Saya)

Membuat komponen About (`app/components/About.tsx`) dengan fitur:

- Section dengan id `about` (target scroll dari Navbar) berisi heading
  "Introduction" dan judul "About me".
- Foto profil (`assets.user_image`) menggunakan `next/image`, disusun
  berdampingan dengan konten teks lewat layout flex (`flex-col` di mobile,
  `lg:flex-row` di desktop).
- Paragraf deskripsi singkat pengalaman sebagai Frontend Developer.
- Grid info (`infoList` dari `assets/assets`) yang menampilkan ikon, judul, dan
  deskripsi tiap poin (mis. pengalaman, edukasi, project) dalam kartu dengan
  efek hover (`-translate-y-1`, `hover:shadow-black`).
- Daftar "Tools I use" (`toolsData` dari `assets/assets`) berupa ikon-ikon tool
  dalam kotak dengan efek hover yang sama.

Komponen ini dirender di `app/page.tsx` setelah `Header`.

### Services (Layanan)

Membuat komponen Services (`app/components/Services.tsx`) dengan fitur:

- Section dengan id `Services` (target scroll dari Navbar) berisi heading "What
  I offer" dan judul "My Services".
- Paragraf deskripsi singkat tentang pengalaman sebagai frontend developer.
- Grid daftar layanan (`serviceData` dari `assets/assets`) yang menampilkan
  ikon, judul, deskripsi, dan link "Read more" tiap layanan dalam kartu dengan
  efek hover (`-translate-y-1`, `hover:shadow-black`, `hover:bg-light-hover`).
- Layout grid menggunakan class custom `grid-cols-auto`, didefinisikan lewat
  `--grid-template-columns-auto: repeat(auto-fit, minmax(200px, 1fr))` di
  `@theme` (`app/globals.css`) — mengikuti cara konfigurasi Tailwind CSS v4
  (tanpa `tailwind.config.mjs`).

Komponen ini dirender di `app/page.tsx` setelah `About`.

### Work (Portfolio/My Latest Work)

Membuat komponen Work (`app/components/Work.tsx`) dengan fitur:

- Heading "My Portfolio" dan judul "My latest work", diikuti paragraf deskripsi
  singkat portofolio.
- Grid daftar project (`workData` dari `assets/assets`) berupa kartu persegi
  (`aspect-square`) dengan background image project (`bgImage`), memakai class
  custom `grid-cols-auto` yang sama seperti di `Services.tsx`.
- Overlay info di setiap kartu (judul & deskripsi project) muncul di bagian
  bawah, bergeser naik saat hover (`group-hover:bottom-7`) beserta ikon panah
  kirim (`send_icon`) yang berubah warna saat hover.
- Tombol "show more" di bagian bawah section untuk melihat project lainnya.

Catatan: berbeda dari section lain, `div` pembungkus di komponen ini belum
memiliki atribut `id`, sehingga smooth-scroll ke `#work` dari Navbar belum
berfungsi.

Komponen ini dirender di `app/page.tsx` setelah `Services`.

### Contact (Formulir Kontak)

Membuat komponen Contact (`app/components/Contact.tsx`) dengan fitur:

- Section dengan id `contact` (target scroll dari Navbar) berisi heading
  "Connect with me" dan judul "Get in touch", dengan background dekoratif
  (`footer-bg-color.png`).
- Form dengan input `name`, `email`, dan `textarea` `message` (semua
  `required`), dikirim lewat handler `onSubmit` menggunakan layanan
  [Web3Forms](https://web3forms.com/) — data form (`FormData`) di-POST ke
  endpoint `https://api.web3forms.com/submit` beserta `access_key`, tanpa
  memerlukan backend sendiri.
- Status pengiriman ("Sending....", sukses, atau pesan error dari API)
  ditampilkan lewat state `result` di bawah tombol submit, dan form direset
  otomatis setelah berhasil terkirim.
- Tombol "Submit now" dengan ikon panah kanan (`assets.right_arrow_white`).

Komponen ini dirender di `app/page.tsx` setelah `Work`.

### Footer

Membuat komponen Footer (`app/components/Footer.tsx`) dengan fitur:

- Logo (`assets.logo`) dan alamat email dengan ikon (`assets.mail_icon`)
  ditampilkan center di bagian atas footer.
- Baris bawah dipisahkan garis (`border-t`), berisi teks copyright dan daftar
  link sosial (GitHub, LinkedIn, Twitter) yang terbuka di tab baru
  (`target="_blank"`), disusun berdampingan lewat `sm:flex justify-between`.

Catatan: teks copyright dan alamat email masih memakai data placeholder
("William Mark", `william@gmail.com`), berbeda dari link sosial yang sudah
mengarah ke akun asli.

Komponen ini dirender di `app/page.tsx` setelah `Contact`.
