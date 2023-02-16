---
description: >-
  At the same time .dao avoids name fraud through several mechanisms.  A
  character set whitelist system is used. You cannot register .dao with
  characters that are not in the whitelist (e.g. blank charac
---

# Fraud Prevention

Character set combination rules：

| CharSetType |                               | Emoji Expressions | Numbers and punctuation | English letters | Japanese Kana and Kanji | Proverbial alphabet | Turkish alphabet | Thai letters | Vietnamese alphabet |
| ----------- | ----------------------------- | ----------------- | ----------------------- | --------------- | ----------------------- | ------------------- | ---------------- | ------------ | ------------------- |
| 0           | Emoji Emoticons               | ✅                 | ✅                       | ✅               | ✅                       | ✅                   | ✅                | ✅            | ✅                   |
| 1           | Numbers and punctuation marks | ✅                 | ✅                       | ✅               | ✅                       | ✅                   | ✅                | ✅            | ✅                   |
| 2           | English alphabet              | ✅                 | ✅                       | ✅               | ❌                       | ❌                   | ❌                | ❌            | ❌                   |
| 5           | Japanese Kana and Kanji       | ✅                 | ✅                       | ❌               | ✅                       | ❌                   | ❌                | ❌            | ❌                   |
| 6           | Proverbial alphabet           | ✅                 | ✅                       | ❌               | ❌                       | ✅                   | ❌                | ❌            | ❌                   |
| 8           | Turkish alphabet              | ✅                 | ✅                       | ❌               | ❌                       | ❌                   | ✅                | ❌            | ❌                   |
| 9           | Thai alphabet                 | ✅                 | ✅                       | ❌               | ❌                       | ❌                   | ❌                | ✅            | ❌                   |
| 10          | Vietnamese alphabet           | ✅                 | ✅                       | ❌               | ❌                       | ❌                   | ❌                | ❌            | ✅                   |

✅ indicates that the characters of both character sets are combinable and can appear in the same .dao account name. And ❌ means that the characters of these two character sets are not combinable.

> ChatSetType Definition
