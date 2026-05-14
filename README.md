Зміна пароля

Крок 1 — підключи бібліотеку у консолі браузера (F12 → Console):
javascriptvar s = document.createElement('script');
s.src = 'https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.2.0/crypto-js.min.js';
document.head.appendChild(s);

Крок 2 — через 2 секунди генеруй хеш нового пароля:
javascriptCryptoJS.SHA256("НОВИЙ_ПАРОЛЬ").toString()

Крок 3 — шифруй посилання новим паролем:
javascriptCryptoJS.AES.encrypt("ТВОЄ_ПОСИЛАННЯ", "НОВИЙ_ПАРОЛЬ").toString()

Крок 4 — встав обидва результати у файл index.html:
javascriptconst ENCRYPTED_URL = "результат кроку 3";
const PASSWORD_HASH  = "результат кроку 2";

Крок 5 — збережи файл і завантаж на GitHub.

Зміна тільки посилання (пароль той самий)

Крок 1 — підключи бібліотеку (якщо ще не підключена):
javascriptvar s = document.createElement('script');
s.src = 'https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.2.0/crypto-js.min.js';
document.head.appendChild(s);

Крок 2 — шифруй нове посилання старим паролем:
javascriptCryptoJS.AES.encrypt("НОВЕ_ПОСИЛАННЯ", "СТАРИЙ_ПАРОЛЬ").toString()

Крок 3 — встав результат у файл index.html:
javascriptconst ENCRYPTED_URL = "результат кроку 2";

Крок 4 — збережи файл і завантаж на GitHub.

⚠️ При зміні пароля — ENCRYPTED_URL і PASSWORD_HASH завжди міняються разом.
