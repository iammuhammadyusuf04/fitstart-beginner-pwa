# FitStart

FitStart — zalga endi kelayotganlar uchun yengil, mobilga mos PWA. U 4 haftalik boshlang‘ich A/B full-body reja, mashq va odatlar kuzatuvi, vazn trendi va offline ishlashni taklif qiladi. Ma’lumotlar faqat shu brauzer qurilmasida saqlanadi.

## Texnologiyalar

- Vanilla JavaScript (build step yoki tashqi kutubxona talab qilmaydi)
- CSS, responsive va safe-area insets bilan
- IndexedDB qurilma ichidagi baza (LocalStorage faqat IndexedDB mavjud bo‘lmagan fallback)
- Web App Manifest va Service Worker
- GitHub Pages (main branch’dan avtomatik deploy)

## Mahalliy ishga tushirish

Statik fayllar `file://` orqali ochilganda service worker ishlamaydi. Mahalliy serverdan oching:

```bash
python3 -m http.server 4173
```

Keyin `http://localhost:4173` manziliga o‘ting.

## Tekshirish va build

```bash
npm test
```

Ilova statik bo‘lgani sabab alohida compile/build buyrug‘i talab qilinmaydi. Production fayllari repository root’dagi `index.html`, `app.js`, `styles.css`, `manifest.webmanifest` va `sw.js` hisoblanadi.

## GitHub Pages deploy

1. Repository → **Settings → Pages → Build and deployment → Source** bo‘limida **Deploy from a branch** ni tanlang.
2. Branch sifatida `main`, papka sifatida `/ (root)` ni tanlab saqlang.
3. Har bir `main` push’dan keyin GitHub Pages saytni avtomatik yangilaydi: https://iammuhammadyusuf04.github.io/fitstart-beginner-pwa/

Ilova root’dagi statik fayllardan iborat, build qadami talab qilinmaydi. Asset manzillari repository subpath’da ham ishlashi uchun relative yozilgan.

## iPhone’da o‘rnatish

1. Public HTTPS URL’ni iPhone’dagi **Safari**’da oching.
2. **Share** tugmasini bosing.
3. **Add to Home Screen** ni tanlang, nomini tasdiqlab **Add** bosing.
4. Home Screen’dagi FitStart ikonkasidan oching. Ilova standalone ko‘rinishda ishlaydi; sahifalar internet bo‘lmaganda ham cache’dan ochiladi.

## Ma’lumot va backup

Profile, check-in, mashg‘ulotlar, vazn yozuvlari va odatlar telefonning shu Safari/PWA originiga tegishli IndexedDB bazasida saqlanadi. Server bilan sinxronizatsiya yo‘q. **Sozlama → JSON export/import** orqali zaxiralang yoki boshqa qurilmaga ko‘chiring. Ilovani o‘chirib tashlash yoki Safari sayt ma’lumotlarini tozalash qurilma bazasini ham olib tashlashi mumkin; shuning uchun vaqti-vaqti bilan JSON backup yuklab oling.

## Sog‘liq va xavfsizlik

FitStart tibbiy tashxis yoki davolash vositasi emas. Yengil vazn tanlab, takrorlarni to‘g‘ri texnika bilan bajaring; maksimal og‘irlik sinamang. O‘tkir og‘riq, bosh aylanishi, ko‘krak og‘rig‘i yoki odatdagidan kuchli nafas qisishi sezilsa, darhol to‘xtang va tibbiy yordam so‘rang.
