---
id: iot
title: iot
type: docs
path: the-notebook/iot
---

## Generating an RSA key

- public to gcp
- private to iot

```
openssl genpkey -algorithm RSA -out rsa_private.pem -pkeyopt rsa_keygen_bits:2048
openssl rsa -in rsa_private.pem -pubout -out rsa_public.pem
```

tunnel

```
./localproxy -r ap-southeast-1 -s 5555 -t AQGAAXj83PoH6CxcjaIGI_oAttgcABsAAgABQQAMMjQ4MTg3MDk1ODg0AAFUAANDQVQAAQAHYXdzLWttcwBQYXJuOmF3czprbXM6YXAtc291dGhlYXN0LTE6NzYzNDYzNDQwNDEzOmtleS9jMTE2NTNiMS1lMTJmLTRhNzktYTE5Zi03MDJhYWZjMDViMDIAuAECAQB45qqa-_bXrUEP7lLaVaT_B5vcZTKyxoqxHI_m9DqBB7cBXp187uUu0Fy1l-VKazWTRAAAAH4wfAYJKoZIhvcNAQcGoG8wbQIBADBoBgkqhkiG9w0BBwEwHgYJYIZIAWUDBAEuMBEEDPyoMK5qV7BdfmjeVQIBEIA75QdO1N4NOGkNZmcugETN3Yw3tnXpDxpBVWAaSg6vAL4c4Jt50eAyzqM_3w4Om_4jeY3zSAwqTavpYnYCAAAAAAwAABAAAAAAAAAAAAAAAAAAdT791naK7hnlVijQCIsTov____8AAAABAAAAAAAAAAAAAAABAAAAL4Q46_F5Ow2LftcSyEWg6uUVZnCDCIT8g4K-9H1S7lOhW8IXMLURhjRELCQC3i_2OLco5K7yFNVkfCRWzybRnA==
```
