# The Autokey cipher
This is an iteration of the Vigenere cipher, but more secure.
* 1:1 substitution cipher
* Uses two alphabets (tabula recta)
* Uses keyword followed by message (instead of repeating keyword)
* Don't use a keyword with letter length of 7 (easier to decipher)

```
A   A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
B   B C D E F G H I J K L M N O P Q R S T U V W X Y Z A
C   C D E F G H I J K L M N O P Q R S T U V W X Y Z A B
D   D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
E   E F G H I J K L M N O P Q R S T U V W X Y Z A B C D
F   F G H I J K L M N O P Q R S T U V W X Y Z A B C D E
G   G H I J K L M N O P Q R S T U V W X Y Z A B C D E F
H   H I J K L M N O P Q R S T U V W X Y Z A B C D E F G
I   I J K L M N O P Q R S T U V W X Y Z A B C D E F G H
J   J K L M N O P Q R S T U V W X Y Z A B C D E F G H I
K   K L M N O P Q R S T U V W X Y Z A B C D E F G H I J
L   L M N O P Q R S T U V W X Y Z A B C D E F G H I J K
M   M N O P Q R S T U V W X Y Z A B C D E F G H I J K L
N   N O P Q R S T U V W X Y Z A B C D E F G H I J K L M
O   O P Q R S T U V W X Y Z A B C D E F G H I J K L M N
P   P Q R S T U V W X Y Z A B C D E F G H I J K L M N O
Q   Q R S T U V W X Y Z A B C D E F G H I J K L M N O P
R   R S T U V W X Y Z A B C D E F G H I J K L M N O P Q
S   S T U V W X Y Z A B C D E F G H I J K L M N O P Q R  
T   T U V W X Y Z A B C D E F G H I J K L M N O P Q R S
U   U V W X Y Z A B C D E F G H I J K L M N O P Q R S T
V   V W X Y Z A B C D E F G H I J K L M N O P Q R S T U
W   W X Y Z A B C D E F G H I J K L M N O P Q R S T U V
X   X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
Y   Y Z A B C D E F G H I J K L M N O P Q R S T U V W X
Z   Z A B C D E F G H I J K L M N O P Q R S T U V W X Y
```

### Example
This example uses the keyword, TRON.

```
Keyword: TRON NEVE RGON NAGI VEYO UUON EVER GONN ALET YOU
Message: NEVE RGON NAGI VEYO UUPN EVER GONN ALET YOUD OWN
Result:  GVJR EKJR EGUV IEEW PYNB YPTE KJRE GZRG YZYW MKH
```

## Tools

### Pycipher

```
>>>from pycipher import Autokey
>>>Autokey('HELLO').encipher('defend the east wall of the castle')
'KIQPBGXMIRDLAAELDHBTSPQFLAPG'
>>>Autokey('HELLO').decipher('KIQPBGXMIRDLAAELDHBTSPQFLAPG')
'DEFENDTHEEASTWALLOFTHECASTLE'
```

Can be broken with [this python script](http://practicalcryptography.com/media/cryptanalysis/files/break_autokey.py).

## References
* http://practicalcryptography.com/ciphers/autokey-cipher/
