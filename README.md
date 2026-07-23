# Portfolio Website

## Progress

### Navigasi (Navbar)

Membuat komponen navigasi (`app/components/Navbar.tsx`) dengan fitur:

- Logo dan background dekoratif menggunakan `next/image`.
- Menu navigasi desktop (Home, About me, Services, My Work, Contact me) dengan smooth-scroll ke masing-masing section (`#top`, `#about`, `#services`, `#work`, `#contact`).
- Tombol dark mode (ikon bulan) dan tombol Contact di sisi kanan navbar.
- Menu mobile (off-canvas) yang bisa dibuka lewat ikon burger dan ditutup lewat ikon close atau saat salah satu link menu diklik, digerakkan dengan `useRef` + manipulasi `style.transform` langsung ke elemen `<ul>`.

