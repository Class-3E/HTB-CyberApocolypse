# Compromised

After downloading given file and extracting zip file all we get is .sal file i had no idea that file supposed to be or what it is .So as usual we got researching.

Which ended up with nothing so I tried basic strings doing it i found out it had 3 files in it so i used binwalk to extract those files.

![](https://i.imgur.com/dFuPejk.png)

![](https://i.imgur.com/g3a1f0e.png)


After some time i found that it is SALEAE was saleae-logic file which has recorded waves or data for analysis or debugging purposes.
 
some more digging around i found there doc page.

After some reading through documentation i had to [download](https://www.saleae.com/downloads/) there application then opened file compromised file in it.

![](https://i.imgur.com/E5GJFQM.png)

Documentation was big help in solving this but main issue was that there were some extra data was missed in. I wasnt able to figure it out what was the issue there but my teammate noticed that there was pattern to it.

![](https://i.imgur.com/YCO8nCk.png)

* write to 0x34 ack data: 0x00 there was 34 request was main issue after some workfu and we were able to get flag.


Now all that remained was to convert hex to ascii.

## Resources
https://support.saleae.com/tutorials/example-projects/how-to-analyze-i2c