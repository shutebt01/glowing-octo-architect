DIVIDER PLUS
========

##What is it
It is an adaption of the divider program that also calculates remainder.

##Arguments
I/O|Function|Notes
------------|--------------|----------------------
First input | First number |(Number to be divided)
Second Input| Second Number |(Number to be divided by)
Output One| Answer |(Less remainder)
Output Two| Remainder |(Optional)

##Code
```
DIV LDA NULL
INP
STA FIRST
INP
STA SECOND
LDA NULL
STA COUNT
DIVLOOP LDA FIRST
SUB SECOND
STA FIRST
LDA COUNT
ADD ONE
STA COUNT
LDA FIRST
BRZ END
BRP DIVLOOP
BRA ERR
HLT
END LDA COUNT
OUT
HLT
ERR LDA COUNT
SUB ONE
OUT
LDA SLEEPBASE
STA SLEEP
SLEEPBRA LDA SLEEP
SUB ONE
STA SLEEP
BRP SLEEPBRA
LDA FIRST
ADD SECOND
STA REMAINDER
OUT
HLT
ONE DAT 1
FIRST DAT
SECOND DAT
COUNT DAT
NULL DAT 0
NEGATIVE DAT -1
REMAINDER DAT 0
SLEEPBASE DAT 25
SLEEP DAT 0
```
