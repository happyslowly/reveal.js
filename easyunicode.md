# EASY UNICODE #

Simon Xu

Mar 2017

---

## Bytes v.s. Text ##

Computers are built base on bytes

Everything is binary

<br>
Humans only recognize text

---

## Charset ##

Charset defines a mapping

---

## ASCII ##

ASCII = American Standard Code for Information Interchange

A 7-bit charset, 0 ~ 127

letter 'a' is assigned 97

     Dec Hex    Dec Hex    Dec Hex  Dec Hex  Dec Hex  Dec Hex   Dec Hex   Dec Hex
      0 00 NUL  16 10 DLE  32 20    48 30 0  64 40 @  80 50 P   96 60 `  112 70 p
      1 01 SOH  17 11 DC1  33 21 !  49 31 1  65 41 A  81 51 Q   97 61 a  113 71 q
      2 02 STX  18 12 DC2  34 22 "  50 32 2  66 42 B  82 52 R   98 62 b  114 72 r
      3 03 ETX  19 13 DC3  35 23 #  51 33 3  67 43 C  83 53 S   99 63 c  115 73 s
      4 04 EOT  20 14 DC4  36 24 $  52 34 4  68 44 D  84 54 T  100 64 d  116 74 t
      5 05 ENQ  21 15 NAK  37 25 %  53 35 5  69 45 E  85 55 U  101 65 e  117 75 u
      6 06 ACK  22 16 SYN  38 26 &  54 36 6  70 46 F  86 56 V  102 66 f  118 76 v
      7 07 BEL  23 17 ETB  39 27 '  55 37 7  71 47 G  87 57 W  103 67 g  119 77 w
      8 08 BS   24 18 CAN  40 28 (  56 38 8  72 48 H  88 58 X  104 68 h  120 78 x
      9 09 HT   25 19 EM   41 29 )  57 39 9  73 49 I  89 59 Y  105 69 i  121 79 y
     10 0A LF   26 1A SUB  42 2A *  58 3A :  74 4A J  90 5A Z  106 6A j  122 7A z
     11 0B VT   27 1B ESC  43 2B +  59 3B ;  75 4B K  91 5B [  107 6B k  123 7B {
     12 0C FF   28 1C FS   44 2C ,  60 3C <  76 4C L  92 5C \  108 6C l  124 7C |
     13 0D CR   29 1D GS   45 2D -  61 3D =  77 4D M  93 5D ]  109 6D m  125 7D }
     14 0E SO   30 1E RS   46 2E .  62 3E >  78 4E N  94 5E ^  110 6E n  126 7E ~
     15 0F SI   31 1F US   47 2F /  63 3F ?  79 4F O  95 5F _  111 6F o  127 7F DEL

---

## In a real world... ##

There're way more different language scripts

Hello World

你好世界

नमस्ते दुनिया

...

---

## Solution ? ##

Invent different charsets: ISO-8859-X, GB1312, KOI8 ...

<br>
But how about multilingual text?

---

## Unicode ##

Unicode is a computing industry standard

Lastest version contains 128,000 characters covering 135 modern and hsitroic scripts and symbol sets

---

## A brief history ##

Unicode started out 16-bits charset

16bits = 65,536 distinct values

<br>
Sadly, it is still not enough...

---

## UCS ##

UCS = Universal coded Character Set

31bit, cover 100,000 characters

---

## Character ##
A *character* is the smallest possible component of a text, depends on the lanuage or context

<br>
synmbol for electrical resistance: Ω (ohm)

synmbol for capital letter omega in Greek: Ω

---

## Code Points ##
Each character is UCS has a meaning and a number (code point)

The character 'H' has the name 'LATIN CAPITAL LETTER H' and the number 72

*Code points* are integer values, usually expressed in hex, with prefix 'U+'

    U+0048    'H'    LATIN CAPITAL LETTER H 
    U+0049    'I'    LATIN CAPITAL LETTER I 
    U+004A    'J'    LATIN CAPITAL LETTER J
    ...
    
---

## More examples ... ##
    U+090F  'ए'     Unicode Character 'DEVANAGARI LETTER E'
    
    U+091A  'च'     Unicode Character 'DEVANAGARI LETTER CA'
    
    U+4E2D  '中'    Unicode Han Character 'central; center, middle; in the midst of...
    
    U+56FD  '国'    Unicode Han Character 'nation, country, nation-state'
   
---

## Encoding ##

*Encoding* is the rule for translating a Unicode text into a sequence of bytes

---

## First approach ##

Store the text into an array of integers,

each of them is 31 bit, aka 4 bytes...

<br>
Way too inefficient

Problem of endianness (platform dependent)

---

## UTF ##

UTF = Unicode Transformation Formats

UTF-8, UTF-16, UTF-32