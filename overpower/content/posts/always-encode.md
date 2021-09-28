---
title: "Always Encode / Decode Query String in URL"
date: 2021-09-28T11:21:58+07:00
description: 'Query strings can be very handy in web development, for example query string is very useful for adding wild card variable that we can use in our sites...'
image: images/lock.png
draft: true
---

# Preface
Query strings can be very handy in web development, for example query string is very useful for adding wild card variable that we can use in our sites. For example tracking UTM (Urchin Tracking Module) Parameter (www.example.com?utm_source=Facebook) or we can passing any wildcard variable that needed for our application to produce something (www.example.com/pages?page=5).
But in order for us to take this benefit of query strings, we have to be careful on how we used it, what i mean by "be careful" is, as stated here [URL DOCS](https://www.w3schools.com/tags/ref_urlencode.ASP) we cannot put some symbol on the query string, for example we cant put '\', '/', '+' and spaces ' '.

# The Truth
URL Encoding (Percent Encoding) URLs can only be sent over the Internet using the ASCII character-set. Since URLs often contain characters outside the ASCII set, the URL has to be converted into a valid ASCII format. URL encoding replaces unsafe ASCII characters with a "%" followed by two hexadecimal digits.
By this will raise a problem if you want to put value string symbol in query parameter, because most browser will automatically encode unsafe ASCII symbol.

# Lesson Learned
We recently got an issue regarding this url things, so the use case is like this:
1. Site A redirect user to Site B with their name, email & phone number being encrypted by AES-256 passed in query string named 'uid' (www.example-b.com?uid=jasdoij812yJhshg)
2. Site B look up the query string named 'uid' and decrypt the value and auto populate to respective field such as name, email, phone number

Since the output of encryption AES-256 is possible to produce '+', '/', '\\', when the browser open the url with such 'uid' contain unsafe ASCII symbol, browser will automatically escape the string and Site B will get the wrong encrypted value because browser automatically encode those unsafe ASCII symbols (Heaven Forbid), so Site B is failed when decrypt the 'uid'.

# The Cure

When this particular problem occur, lucky us javascript is already provide us with a function 
```javascript
encodeURIComponent(YOUR_QUERY_STRING_VALUE)
```

with this function being called, it will produce encoded string that very safe to be put into url without the browser automatically escape your encrypted string :)
You can freely put any string when you encode it before you throw that string into URL, and also dont forget that you have to decode it after you encode the string.

```javascript
decodeURIComponent(YOUR_ENCRYPTED_QUERY_STRING_VALUE);
```

by encoding and decoding you also increase your site security for someone whom tries to inject anything into your query param, because you already safely decode it.