# Portfolio Website

## Progress

### Navigasi (Navbar)

Membuat komponen navigasi (`app/components/Navbar.tsx`) dengan fitur:

- Logo dan background dekoratif menggunakan `next/image`.
- Menu navigasi desktop (Home, About me, Services, My Work, Contact me) dengan smooth-scroll ke masing-masing section (`#top`, `#about`, `#services`, `#work`, `#contact`).
- Tombol dark mode (ikon bulan) dan tombol Contact di sisi kanan navbar.
- Menu mobile (off-canvas) yang bisa dibuka lewat ikon burger dan ditutup lewat ikon close atau saat salah satu link menu diklik, digerakkan dengan `useRef` + manipulasi `style.transform` langsung ke elemen `<ul>`.

### Header (Hero Section)

Membuat komponen header/hero (`app/components/Header.tsx`) dengan fitur:

- Foto profil bulat (`assets.profile_img`) menggunakan `next/image`.
- Sapaan "Hi! I'm William Mark" dengan ikon tangan (`assets.hand_icon`).
- Judul utama (h1) berisi tagline "frontend web developer based in London" dan paragraf deskripsi singkat.
- Dua tombol CTA: "contact me" (scroll ke `#contact`, ikon panah kanan) dan "my resume" (link download `sample-resume.pdf`, ikon download).
- Layout di-center secara vertikal dan horizontal dengan `h-screen` + flexbox, responsif lewat breakpoint `sm`, `md`, `lg`.

Komponen ini dirender di `app/page.tsx` setelah `Navbar`, dan `app/layout.tsx` ditambahkan class `leading-8 overflow-x-hidden` untuk mendukung layout halaman penuh.

