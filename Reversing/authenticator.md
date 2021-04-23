This is a basic reversing challenge rated one star and to do this we have to basically get a userid and a password.

Lets first run the Binary and see how and whats asking us for :
![](authenticator.png)

So we see its asking us for ID at first so the first thing we should do is use ltrace and see what dynamic library calls the binary is doing and maybe its comapring the input to a string directly.
![](ltraceauthenticator.png)
and we can see here that its comparing our input using a strcmp operation with 11337 which is the username now lets try using the username we got with ltrace again and see what we get.

and we see after putting ID we get it asking us for a pin which tells us to sumbit pin in the flag format like so.
![](authenticatorprepin.png)

So thats still not giving us the flag so lets analyse the code in Ghidra and see whats its doing with flag, analysing the code in Ghidra we get this intresting fucntion called checkpin and thats exactly what we are looking for here we that its getting our input and setting a variable local_24 with the value of 0 and then XORING it with 9U and comparing it our input as the PIN.
```c
if ((byte)("}a:Vh|}a:g}8j=}89gV<p<}:dV8<Vg9}V<9V<:j|{:"[local_24] ^ 9U) != param_1[local_24])

break;
```

So basically its like : 
```c
theristring[0] ^ 9U = ourinput[0]
```

So lets XOR their string with 9U and we should get the flag. For this you can use pyhton or cyberchef.
![](flagauthentication.png)