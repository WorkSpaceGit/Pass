Зміна пароля / посилання

Крок 1 — отримай хеш пароля:
// Підключи бібліотеку
var s = document.createElement('script');
s.src = 'https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.2.0/crypto-js.min.js';
document.head.appendChild(s);

// Через 2 секунди запусти: тут вставляєш свій пароль
CryptoJS.SHA256("__пароль").toString()
+ отримуєш ХЕШ_ПАРОЛЯ

Крок 2 — зашифруй посилання:
CryptoJS.AES.encrypt(
  "__https://",
  "__пароль").toString()
+ отримуєш ЗАШИФРОВАНИЙ_РЯДОК ПОСИЛАННЯ

Отримаєш два рядки відкриваєш HTML — вставляєш їх у файл:
ВСТАВИТИ_SHA256_ХЕШ_ПАРОЛЯ "__пароль"
ВСТАВИТИ_ЗАШИФРОВАНИЙ_РЯДОК_AES "__https://"
