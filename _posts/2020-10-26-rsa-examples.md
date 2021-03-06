---
layout: post
title: RSA Examples
feature-img: "assets/img/pexels/computer.jpeg"
thumbnail: "assets/img/pexels/computer.jpeg"
author: vinxue
tags: [Essay]
---

## RSA Examples

### Generate a new Private Key in pem format:
> openssl.exe genrsa -out NewPrivateKey.pem 2048

```
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEA3u2fT4kvnNtp5Uw/wIqTvm2MSYmD7UU4/wMUSQkTl1bptVxO
taWC0HZdy3qBT/YxYG6/J94y9yzqdXcZ2wtJIlglEcRi2mpUUZb3LGA0fXM6duaN
MOvhVpPlN6Xk6SWzV14m7spupVh+M60f2U+6RlLlekgoddJlL4gK9Dww8fTA8m81
hP0/YO8TBvXFvQ7OZfKmdrVe4Pk2DL8fGZ+n+hHLzsVKsSqQdkTOFMopjAS+XUhe
obs33FLYAjvdizCMB3EqXldKJ+nMv8E387Xmm0y6cyBEzvW3YxN0IXy9wuhYiSDf
+AzxWVLZr6XFwtvucG7IUq+5EO3erOYQZLNMaQIDAQABAoIBAHgXmG/3Xl/oz3ZI
CjwGKys1xpJC84AZf2fZV880hYpMtuANlxVB0WPNsB+SoiDaZqUlY/LtP5Vqa+/V
tmcLAF3xEB8vJXW2PDAr3IHaXcyLC57L+pm1KJJEYAIHa3ax6ZgST3TqNor6Tho2
lGa0DYwe0iJ6xtkZ+4qMhiImXtOoXbJGrIolWEHnMNaDiTXfiilp1a6uV8ZflT68
RSyPi3n4LzdOW01nmTFkZnYVWUkxjnU1tt5Mm/j4e24mza7z7W5Fz3h5XGOklCDD
JzPB6ducMrDb5XlKWabZ//7RjP09FboxvjxoWwUJaSINUKibPCLEJ0Fz2Px196yQ
ytwS8oECgYEA+kSjy0H9WehjH3VLR0tk+ttvYfkZoLYFi+pHuMQYN7yIF98XPfRs
gRvVPl+7gU/eEALUalBUb3Ib5UHP0qONMyslHO7/DmvVlUrpm4xh+bNJipTTEtxk
TCFX1Zkj2oVhwKMZtK75Vv3Q0X0zCqcAUAY96vovDsFf2bTnmphNRjkCgYEA5Aiv
Nau6YI50zPHOOrViGSUKemJjN5x4725aR618pgZ5vA+pCsYiIMcYr+B6a5jsO4T3
AphkvkugT6BZRyft20q1MfxUN5vZG3qtZTOgbWJ7q0Y95JO0BYly4nZTBAJzVa3z
rM2wBx0jXEcGBkgRj8SATrgv9RbO2boAP4Krt7ECgYEAmfHI80mXR0u8VWh4MtW8
utZqMFDjI8lzpfopvgzZfMd6y3xONqz4ZX6ycFjA5S00wpKLCQ56scb2Q9J0vPQf
8f6zKJYWzE8mpVvcUPNMfSV8skMTh0GMbIwCFIDL3io31CA/urX66Djez039LKtH
dPIx+i2E7sWiaS9vW9gdiHkCgYAKDHfsHY0xBBYRkfZMkAGqqf80NXG52aNaqbpA
vlxn1JE4wFfqqaCHYT6tQW8jnrGKTem0q5KE8EA4QhCtGg1ZRImHkl8DtFJ064sI
kqXXLCfW/Flt4TRlqhDt+djerFz4wZmjW80OAzKztk2FqVdcxoQA9Azo+ABVh+TK
5685gQKBgCeuS07hwfXJsMIjTJJVUdXLvZ4f2s1oJnDLYlTTdLwosfY+KLM0LdBj
AdqF02kdc58BofTwCntG0k5Cp8XMQF7SlHovUqlF8CpwJaC9X3O9WUKJ1utdfcQA
qQmbdVZoUHdsUnw4PBCzQZIr1N8+MH1vcT+llGnPD5MRwVokdKIP
-----END RSA PRIVATE KEY-----
```
---
### Generate public key from private key in pem format:
> openssl.exe rsa -in NewPrivateKey.pem -pubout -out NewPublicKey.pem

---
### Public key in hex format:
> openssl.exe rsa -in NewPrivateKey.pem -modulus -noout

```
WARNING: can't open config file: /usr/local/ssl/openssl.cnf
Modulus=DEED9F4F892F9CDB69E54C3FC08A93BE6D8C498983ED4538FF03144909139756E9B55C4EB5A582D0765DCB7A814FF631606EBF27DE32F72CEA757719DB0B4922582511C462DA6A545196F72C60347D733A76E68D30EBE15693E537A5E4E925B3575E26EECA6EA5587E33AD1FD94FBA4652E57A482875D2652F880AF43C30F1F4C0F26F3584FD3F60EF1306F5C5BD0ECE65F2A676B55EE0F9360CBF1F199FA7FA11CBCEC54AB12A907644CE14CA298C04BE5D485EA1BB37DC52D8023BDD8B308C07712A5E574A27E9CCBFC137F3B5E69B4CBA732044CEF5B7631374217CBDC2E8588920DFF80CF15952D9AFA5C5C2DBEE706EC852AFB910EDDEACE61064B34C69
```
---
### Generate Public key to a binary file:
> openssl.exe base64 -d -in NewPublicKey.pem -out publickey.bin

```
Offset(h) 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F  Decoded text
00000000  30 82 01 22 30 0D 06 09 2A 86 48 86 F7 0D 01 01  0???."0...*???H?????...
00000010  01 05 00 03 82 01 0F 00 30 82 01 0A 02 82 01 01  ....???...0???...???..
00000020  00 DE ED 9F 4F 89 2F 9C DB 69 E5 4C 3F C0 8A 93  .??????O???/????i??L????????
00000030  BE 6D 8C 49 89 83 ED 45 38 FF 03 14 49 09 13 97  ??m??I???????E8??..I..???
00000040  56 E9 B5 5C 4E B5 A5 82 D0 76 5D CB 7A 81 4F F6  V????\N?????????v]??z.O??
00000050  31 60 6E BF 27 DE 32 F7 2C EA 75 77 19 DB 0B 49  1`n??'??2??,??uw.??.I
00000060  22 58 25 11 C4 62 DA 6A 54 51 96 F7 2C 60 34 7D  "X%.??b??jTQ?????,`4}
00000070  73 3A 76 E6 8D 30 EB E1 56 93 E5 37 A5 E4 E9 25  s:v??.0????V?????7??????%
00000080  B3 57 5E 26 EE CA 6E A5 58 7E 33 AD 1F D9 4F BA  ??W^&????n??X~3..??O??
00000090  46 52 E5 7A 48 28 75 D2 65 2F 88 0A F4 3C 30 F1  FR??zH(u??e/??.??<0??
000000A0  F4 C0 F2 6F 35 84 FD 3F 60 EF 13 06 F5 C5 BD 0E  ??????o5??????`??..??????.
000000B0  CE 65 F2 A6 76 B5 5E E0 F9 36 0C BF 1F 19 9F A7  ??e????v??^????6.??..????
000000C0  FA 11 CB CE C5 4A B1 2A 90 76 44 CE 14 CA 29 8C  ??.??????J??*.vD??.??)??
000000D0  04 BE 5D 48 5E A1 BB 37 DC 52 D8 02 3B DD 8B 30  .??]H^????7??R??.;?????0
000000E0  8C 07 71 2A 5E 57 4A 27 E9 CC BF C1 37 F3 B5 E6  ??.q*^WJ'????????7??????
000000F0  9B 4C BA 73 20 44 CE F5 B7 63 13 74 21 7C BD C2  ???L??s D??????c.t!|????
00000100  E8 58 89 20 DF F8 0C F1 59 52 D9 AF A5 C5 C2 DB  ??X??? ????.??YR????????????
00000110  EE 70 6E C8 52 AF B9 10 ED DE AC E6 10 64 B3 4C  ??pn??R????.????????.d??L
00000120  69 02 03 01 00 01                                i.....

```
---
### RSASSA-PSS signing scheme with SHA-384:
Signing:
> openssl dgst -binary -sign [PRIVATE_KEY] -sha384 -sigopt rsa_padding_mode:pss -sigopt rsa_pss_saltlen:-2 -out [SIGNATURE] [INPUT_FILE]

Verification:
> openssl dgst -sha384 -verify public.pem -sigopt rsa_padding_mode:pss -sigopt rsa_pss_saltlen:-2 -signature [SIGNATURE] [INPUT_FILE]

---
