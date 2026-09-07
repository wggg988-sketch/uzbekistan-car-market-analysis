# 🚗 O‘zbekiston Avtomobil Bozori Tahlili va Savdo Dinamikasi (2022–2025)

## 📌 Loyiha Haqida (Project Overview)
Ushbu loyiha 2022–2025 yillar oralig‘ida O‘zbekiston avtomobil bozoridagi savdo tendensiyalari, iste’molchilar xatti-harakati, brendlar o‘rtasidagi raqobat va avtomobil turlari (dvigatel va narx segmentlari) bo‘yicha talabni chuqur tahlil qiluvchi interaktiv Power BI dashboardi hisoblanadi.

Loyiha maqsadi — xom ma'lumotlarni tozalash, relyatsion modelga keltirish va biznes qarorlar qabul qilish uchun qulay vizual vosita yaratish.

---

## 📊 Dashboard Ko‘rinishi
![Dashboard Preview](preview.png)

---

## 🔑 Asosiy Metrikalar (KPIs)
* **Jami Sotuv Hajmi:** 167,000 dona transport vositasi.
* **Jami Bozor Tushumi:** ~$3.0 mlrd AQSH dollari.
* **O‘rtacha Avtomobil Narxi:** ~$16,460.

---

## 📈 Tahliliy Xulosalar (Key Insights)

### 1. Brendlar Dinamikasi va Bozor Transformatsiyasi
* **Chevrolet:** Bozorda mutlaq yetakchilikni saqlab qolgan, biroq 2023-yil oxiridan boshlab uning bozor ulushida turg‘unlik va biroz pasayish tendensiyasi kuzatilgan.
* **BYD O‘sishi:** 2024-yilning 1-choragidan boshlab BYD brendi savdosida eksponentsial (keskin) o‘sish kuzatilgan va u xususiy segmentdagi eng tez rivojlanayotgan brendga aylangan.
* **Boshqa Brendlar:** Chery, Geely, Haval va Jetour kabi brendlar o‘rta narx toifasida o‘z o‘rnini barqaror saqlab kelmoqda.

### 2. Hududiy Taqsimot va Segmentatsiya
* **Toshkent Shahri:** Premium toifadagi va elektromobillar savdosining eng katta qismini o‘ziga jamlagan mutlaq yetakchi hudud (umumiy savdoning salmoqli qismi).
* **Viloyatlar:** Farg‘ona, Samarqand, Toshkent viloyati va Andijon ommaviy xarid hajmi bo‘yicha keyingi o‘rinlarda turadi. Bu hududlarda asosan byudjet segmenti ($15,000 gacha) ustunlik qiladi.

### 3. Dvigatel Turlari va Ekologik O‘tish
* **Benzinli Dvigatellar:** Umumiy savdoning **57.7%** qismini egallab, asosiy yoqilg‘i turi bo‘lib qolmoqda.
* **Gibridlar (PHEV):** Bozorning **20.4%** ulushini egallab, an'anaviy dvigatellarga asosiy muqobilga aylangan.
* **Benzin (Turbo) & EV:** Turbo dvigatellar **16.3%**, toza elektromobillar (EV) esa **5.3%** ulushga ega bo‘lib, infratuzilma rivojlanishi bilan EV ulushi tez sur'atlarda ortib bormoqda.

### 4. Narx Segmentlari
* **Byudjet (<$15k):** Eng katta jismoniy savdo hajmini tashkil qiladi.
* **O‘rta ($15k–$25k):** Iste'molchilar xarid qobiliyati o‘sishi hisobiga eng faol kengayayotgan toifa.
* **Yuqori-o‘rta va Premium (>$25k):** Asosan Toshkent shahri va yirik viloyat markazlarida to‘plangan.

---

## 🏗 Ma'lumotlar Modeli (Data Architecture)
Loyiha **Star Schema** (Yulduzsimon arxitektura) tamoyili asosida qurilgan:

* **Fact_Sales (Faktlar jadvali):** Har bir bitim bo‘yicha savdo miqdori, sanasi, narxi va tushum ko‘rsatkichlari.
* **Dim_Date (Sana jadvali):** Sana, Yil, Chorak, Oy iyerarxiyasi.
* **Dim_Car (Avtomobillar o‘lchov jadvali):** Brend, Model, Dvigatel turi, Narx segmenti ma'lumotlari.
* **Dim_Region (Hududlar o‘lchov jadvali):** Viloyatlar va bozor toifalari.

---

## 💻 Qo‘llanilgan Texnologiyalar
* **Power BI Desktop:** Relyatsion model yaratish, ma'lumotlar vizualizatsiyasi va foydalanuvchi interfeysi (UI/UX).
* **Power Query:** Ma'lumotlarni tozalash, bo‘sh (blank) qiymatlarni filtrlash va turlarni standartlashtirish.
* **DAX (Data Analysis Expressions):** Dinamik o‘lchovlar (Measures) yaratish:
  * `Jami Sotuv = SUM(Fact_Sales[Sotilgan_Soni])`
  * `Jami Tushum = SUM(Fact_Sales[Tushum_USD])`
  * `O'rtacha Narx = AVERAGE(Fact_Sales[Narx_USD])`
