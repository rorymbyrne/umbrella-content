---
index: 93
title: Шифрование с открытым ключом
---
# Шифрование с открытым ключом

Традиционные системы шифрования используют один и тот же секрет или ключ для шифрования и расшифровки сообщения. Поэтому, если я зашифровал файл с паролем «bluetonicmonster», вам понадобится как сам файл, так и секретный пароль «bluetonicmonster» для его декодирования. Шифрование с открытым ключом использует два ключа: один для шифрования и другой - для дешифрования. Это имеет всевозможные полезные выводы. Во-первых, это означает, что вы можете передать ключ для шифрования сообщений от вас, и до тех пор, пока вы сохраняете другой ключ в секрете, любой, у кого есть открытый ключ, может безопасно поговорить с вами. Ключ, который вы раздаете публично, называется «открытым ключом»: отсюда и название метода. Шифрование с открытым ключом используется для шифрования электронной почты и файлов с помощью Pretty Good Privacy (PGP), OTR для обмена мгновенными сообщениями и SSL/TLS для просмотра веб-страниц.