---
editable: false
---

# Метод encrypt
Шифрует заданный текст с помощью указанного ключа.
 

 
## HTTP-запрос {#https-request}
```
POST https://kms.yandex/kms/v1/keys/{keyId}:encrypt
```
 
## Path-параметры {#path_params}
 
Параметр | Описание
--- | ---
keyId | Обязательное поле. Идентификатор симметричного ключа KMS, который следует использовать для шифрования.  Максимальная длина строки в символах — 50.
 
## Параметры в теле запроса {#body_params}
 
```json 
{
  "versionId": "string",
  "aadContext": "string",
  "plaintext": "string"
}
```

 
Поле | Описание
--- | ---
versionId | **string**<br><p>Идентификатор версии ключа, которую следует использовать для шифрования текста. По умолчанию используется основная версия, если версия не указана явно.</p> <p>Максимальная длина строки в символах — 50.</p> 
aadContext | **string** (byte)<br><p>Дополнительные аутентифицированные данные (контекст AAD), необязательное поле. Если данные указаны, то их потребуется передать для расшифровки с помощью `SymmetricDecryptRequest`. Необходимо закодировать в формате base64.</p> <p>Максимальная длина строки в символах — 8192.</p> 
plaintext | **string** (byte)<br><p>Обязательное поле. Открытый текст, который следует зашифровать. Должен быть в кодировке base64.</p> <p>Максимальная длина строки в символах — 32768.</p> 
 
## Ответ {#responses}
**HTTP Code: 200 - OK**

```json 
{
  "keyId": "string",
  "versionId": "string",
  "ciphertext": "string"
}
```

 
Поле | Описание
--- | ---
keyId | **string**<br><p>Обязательное поле. Идентификатор симметричного ключа KMS, который использовался для шифрования.</p> <p>Максимальная длина строки в символах — 50.</p> 
versionId | **string**<br><p>Идентификатор версии ключа, которая использовалась для шифрования.</p> <p>Максимальная длина строки в символах — 50.</p> 
ciphertext | **string** (byte)<br><p>Полученный шифртекст.</p> 