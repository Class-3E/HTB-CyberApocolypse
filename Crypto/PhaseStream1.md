# PhaseStream 1

>The aliens are trying to build a secure cipher to encrypt all our games called "PhaseStream". They've heard that stream ciphers are pretty good. The aliens have learned of the XOR operation which is used to encrypt a plaintext with a key. They believe that XOR using a repeated 5-byte key is enough to build a strong stream cipher. Such silly aliens! Here's a flag they encrypted this way earlier. Can you decrypt it (hint: what's the flag format?) 2e313f2702184c5a0b1e321205550e03261b094d5c171f56011904

after help
```
from itertools import cycle

encoded = bytes.fromhex('2e313f2702184c5a0b1e321205550e03261b094d5c171f56011904')

flag_start = 'CHTB{'

# decrypt the first part of the encoded
key = [encoded[i] ^ ord(c) for i, c in enumerate(flag_start)]
print('Decrypted key part:', ''.join(chr(i) for i in key))
```
>Decrypted key part: mykey

* the hint here was flag format = CHTB{ and repeated 5-byte key which the length of CHTB{ is 5, so we have the string of the key

used [xor-cipher](https://www.dcode.fr/xor-cipher) with **use ASCII key = mykey**

>CHTB{u51ng_kn0wn_pl41nt3xt}

[BL4CKC0FF33 ☕](https://github.com/BL4CKC0FF33/)
