# 🎮 Hangman O‘yini

**MIT 6.0001 Problem Set 2** doirasida ishlab chiqilgan hamda Python dasturlash tilida yozilgan ananaviy so‘z topish o‘yini. So‘zlarni harflar orqali topib, lug‘at boyligingizni sinab ko‘ring!

> [!NOTE]
> Ushbu Hangman o‘yini vazifasi Otabek Sadiridinov tomonidan yechilgan va AI tomonidan tekshirilgan. Fikr-mulohaza yoki muammolar uchun [GitHub issue](https://github.com/otabekoff/hangman-task/issues/new) oching.

> Ingliz tilidagi qo'llanma [bu yerda](README.md)

## 📋 Mundarija

- [Xususiyatlar](#xususiyatlar)
- [O‘yin qoidalari](#oyin-qoidalari)
- [O‘rnatish](#ornatish)
- [O‘ynash tarzi](#qanday-oynash)
- [O‘yin rejimlari](#oyin-rejimlari)
- [Baholash tizimi](#baholash-tizimi)
- [Fayl tuzilishi](#fayl-tuzilishi)
- [Dasturlash](#dasturlash)
- [Misollar](#misollar)
- [Hissa qo‘shish](#hissa-qoshish)

## ✨ Xususiyatlar

- **Klassik Hangman O‘yin Mexanikasi** – So‘zni harflar orqali toping
- **Aqlli Ogohlantirish Tizimi** – Noto‘g‘ri kiritmalar uchun 3 ogohlantirish
- **Unli/Undosh Jarimalar** – Unli harflar (2) va undoshlar (1) uchun turli jarimalar
- **Maslahat Tizimi** – Qiyin holatda so‘z variantlarini ko‘rish (3-qism)
- **Katta So‘z Bazasi** – `words.txt` faylida 55,000+ so‘z
- **Baholash** – Qolgan urinishlar va noyob harflarga asoslanadi
- **Kiritmani Tekshirish** – Noto‘g‘ri belgilar va takroriy harflarni aniqlaydi

## 🎯 O‘yin Qoidalari

### Asosiy Qoidalar
- **Boshlang‘ich Urinishlar**: 6 ta
- **Boshlang‘ich Ogohlantirishlar**: 3 ta
- **So‘z Manbasi**: 55,900+ so‘zdan tasodifiy tanlanadi

### Jarimalar
- **Noto‘g‘ri Kiritma**: 1 ogohlantirish (yoki ogohlantirish tugasa 1 urinish)
- **Takroriy Harf**: 1 ogohlantirish (yoki ogohlantirish tugasa 1 urinish)
- **Noto‘g‘ri Undosh**: 1 urinish yo‘qotiladi
- **Noto‘g‘ri Unli** (a, e, i, o, u): 2 urinish yo‘qotiladi
- **To‘g‘ri Harf**: Jarima yo‘q

### G‘alaba va Baholash
- **G‘alaba Sharti**: So‘zdagi barcha harflarni topish
- **Yutqazish Sharti**: Urinishlar tugasa
- **Baholash**: `qolgan_urinishlar × so‘zdagi_noyob_harflar`

## 🚀 O‘rnatish

1. **Repodan klonlash yoki yuklab olish**
2. **Python 3.x** o‘rnatilganligiga ishonch hosil qiling
3. **Loyihaga o‘ting:**
    ```bash
    cd hangman-task
    ```

## 🎮 Qanday O‘ynash

### Tez Start
```bash
python hangman.py
```

### So‘zni Qo‘lda Tanlash (test uchun)
`hangman.py` faylining oxirini tahrirlang:
```python
if __name__ == "__main__":
     # Test uchun
     secret_word = "apple"  # Test so‘zni belgilang
     hangman(secret_word)
```

### Tasodifiy So‘z Tanlash
```python
if __name__ == "__main__":
     secret_word = choose_word(wordlist)
     hangman(secret_word)
```

## 🎯 O‘yin Rejimlari

### 1-Rejim: Klassik Hangman
```python
secret_word = choose_word(wordlist)
hangman(secret_word)
```

### 2-Rejim: Maslahatli Hangman
```python
secret_word = choose_word(wordlist)
hangman_with_hints(secret_word)
```

**Maslahat xususiyati**: `*` belgisi orqali mos so‘zlarni ko‘ring!

## 📊 Baholash Tizimi

Yakuniy baho quyidagicha hisoblanadi:
```
Baho = Qolgan Urinishlar × Noyob Harflar Soni
```

**Misol**:
- So‘z: "tact" (4 noyob harf: t, a, c)
- Qolgan urinishlar: 3
- Baho: 3 × 4 = 12 ball

## 📁 Fayl Tuzilishi

```
hangman-task/
├── hangman.py              # Asosiy o‘yin kodi
├── words.txt               # So‘zlar bazasi (55,900+ so‘z)
├── README.md               # Ushbu fayl
├── MIT6_0001F16_Pset2.pdf  # Asl vazifa
├── .editorconfig           # Kod formatlash konfiguratsiyasi
├── .vscode/                # VS Code sozlamalari
│   └── settings.json
└── test_files/             # Test skriptlari (agar bo‘lsa)
```

## 🛠️ Dasturlash

### Asosiy Funksiyalar

#### O‘yin Funksiyalari
- `hangman(secret_word)` – Asosiy o‘yin sikli
- `hangman_with_hints(secret_word)` – Maslahatli o‘yin

#### Yordamchi Funksiyalar
- `is_word_guessed(secret_word, letters_guessed)` – So‘z to‘liq topilganini tekshirish
- `get_guessed_word(secret_word, letters_guessed)` – Hozirgi holatni ko‘rsatish
- `get_available_letters(letters_guessed)` – Qolgan harflarni olish
- `match_with_gaps(my_word, other_word)` – Qisman so‘z mosligini tekshirish
- `show_possible_matches(my_word)` – Maslahat uchun mos so‘zlarni ko‘rsatish

#### Foydali Funksiyalar
- `load_words()` – Fayldan so‘zlarni yuklash
- `choose_word(wordlist)` – Tasodifiy so‘z tanlash

### Kod Uslubi
- Python PEP 8 standartiga amal qilinadi
- 4 bo‘shliqli indentsiya
- 79 belgili qatordan oshmaslik
- Batafsil docstringlar

## 📖 Misollar

### G‘alaba O‘yini
```
Welcome to the game Hangman!
I am thinking of a word that is 4 letters long.
You have 3 warnings left.
-------------
You have 6 guesses left.
Available letters: abcdefghijklmnopqrstuvwxyz
Please guess a letter: a
Good guess: a_ _ _
------------
You have 6 guesses left.
Available letters: bcdefghijklmnopqrstuvwxyz
Please guess a letter: p
Good guess: app_
------------
You have 6 guesses left.
Available letters: bcdefghijklmnopqrstuvwxyz
Please guess a letter: l
Good guess: appl
------------
You have 6 guesses left.
Available letters: bcdefghijkmnopqrstuvwxyz
Please guess a letter: e
Good guess: apple
------------
Congratulations, you won!
Your total score for this game is: 24
```

### Maslahatdan Foydalanish
```
You have 4 guesses left.
Available letters: bcdefghijkmnopqrstuvwxyz
Please guess a letter: *
Possible word matches are:
apple ample
------------
```

### Noto‘g‘ri Kiritma Misoli
```
Please guess a letter: 123
Oops! That is not a valid letter. You have 2 warnings left: a_ _ _
```

## 🤝 Hissa Qo‘shish

Bu loyiha MIT 6.0001 kursi asosida o‘quv maqsadida yaratilgan. Quyidagilarni bajaring:

1. **Repodan fork qiling**
2. **Yangi branch oching**
3. **O‘zgartirishlarni kiriting**
4. **Pull request yuboring**

### Takliflar
- Qiyinchilik darajalarini qo‘shish
- Kategoriyalar (hayvonlar, davlatlar va h.k.) qo‘shish
- GUI interfeys yaratish
- Multiplayer rejimi
- So‘z ma’nolarini ko‘rsatish
- O‘yin holatini saqlash/yuklash

## 📚 O‘quv Maqsadi

Ushbu loyiha MIT 6.0001 Problem Set 2 ni amalga oshiradi va quyidagilarga e’tibor qaratadi:
- **Stringlar bilan ishlash**
- **Ro‘yxatlar bilan amallar**
- **Nazorat oqimi** (sikl, shartlar)
- **Funksiya dizayni**
- **Kiritmani tekshirish**
- **O‘yin logikasini amalga oshirish**

## 🏆 Mualliflar

- **Asl Vazifa**: MIT 6.0001 Python kursi
- **Dasturlash**: Otabek Sadiridinov
- **So‘zlar Bazasi**: MIT lug‘ati

---

**Hangman o‘yinidan zavqlaning! 🎯**

*Klassik so‘z o‘yinida o‘zingizni sinab ko‘ring va lug‘atingizni boyiting!*
