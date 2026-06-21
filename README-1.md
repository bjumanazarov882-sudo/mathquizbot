# Matematika Test Bot (Telegram)

Python (aiogram 3.x) asosida yozilgan oddiy Telegram quiz bot. Foydalanuvchilarga
tasodifiy tartibda matematika savollari beradi, ballarni saqlaydi va reyting
jadvalini ko'rsatadi.

## 1. Bot tokenini olish

1. Telegramda **@BotFather** ga yozing.
2. `/newbot` buyrug'ini yuboring va ko'rsatmalarga amal qiling.
3. Sizga beriladigan tokenni saqlab qo'ying (masalan: `123456789:ABCdefGhIJKlmNoPQRstuVWXyz`).

## 2. O'rnatish

```bash
cd mathquizbot
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## 3. Tokenni sozlash

Terminalda muhit o'zgaruvchisi sifatida bering:

```bash
export BOT_TOKEN="sizning_tokeningiz"      # Windows: set BOT_TOKEN=sizning_tokeningiz
```

Yoki `bot.py` faylining boshidagi `BOT_TOKEN` qatorini to'g'ridan-to'g'ri
o'zgartirishingiz mumkin (bu usul faqat sinov uchun tavsiya etiladi, chunki
tokenni kod ichida ochiq saqlash xavfsiz emas).

## 4. Botni ishga tushirish

```bash
python bot.py
```

Konsolda xatolik chiqmasa, bot ishlay boshlaydi. Telegramda botingizni toping
va `/start` buyrug'ini yuboring.

## 5. Buyruqlar

- `/start` — botni boshlash, qisqa yo'riqnoma
- `/quiz` — yangi test boshlash (10 ta tasodifiy savol)
- `/top` — eng yaxshi 10 natija

## 6. Savollarni tahrirlash yoki qo'shish

Barcha savollar `questions.py` faylida joylashgan. Yangi savol qo'shish uchun
ro'yxatga shu formatda yozing:

```python
{
    "question": "Savol matni",
    "options": ["A", "B", "C", "D"],
    "correct": 0,  # to'g'ri javobning options ichidagi o'rni (0 dan boshlanadi)
},
```

`bot.py` faylidagi `QUESTIONS_PER_ROUND` o'zgaruvchisi orqali har bir o'yinda
nechta savol berilishini o'zgartirishingiz mumkin (hozirda 10 ta).

## 7. Ma'lumotlar bazasi

Foydalanuvchilarning eng yaxshi natijalari `quiz.db` (SQLite) faylida
avtomatik saqlanadi — alohida sozlash shart emas.

## 8. Botni doimiy ishlatish (serverda)

Kompyuteringizni o'chirib qo'ysangiz ham bot ishlashda davom etishi uchun uni
serverga joylashtirish kerak. Oddiy va tekin variantlar: Railway, Render yoki
arzon VPS (masalan, Timeweb, Contabo). Bularning har birida loyihani GitHub'ga
yuklab, keyin ulanган xizmatga bog'lashingiz kifoya. Agar shu bosqichda
yordam kerak bo'lsa, ayting — qaysi xizmatni tanlaganingizga qarab aniq
qadamlarni ko'rsataman.
