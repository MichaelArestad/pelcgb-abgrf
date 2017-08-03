# The Caesar cipher
* 1:1 substitution cipher
* "Caesar shift" is rot(3) or three to the right

## Tools
* [dcode](http://www.dcode.fr/caesar-cipher) (connection required)

#### Pycipher
This is a tool for terminal. It's not automated so could be slow, but works offline. To install: `pip install pycipher`.

```
$ python
>>>from pycipher import Caesar
>>>Caesar(key=1).encipher('defend the east wall of the castle')
'EFGFOEUIFFBTUXBMMPGUIFDBTUMF'
>>>Caesar(key=1).decipher('EFGFOEUIFFBTUXBMMPGUIFDBTUMF')
'DEFENDTHEEASTWALLOFTHECASTLE'
```

As explained on [this site](http://practicalcryptography.com/cryptanalysis/stochastic-searching/cryptanalysis-caesar-cipher/), there is a way to automate pychipher to decipher the message using [this python script](http://practicalcryptography.com/media/cryptanalysis/files/break_caesar_4.py).

### Using English letter frequencies
Break down the frequency of letters used in a message. Then match them up with the English letter frequency table to make better guesses.

#### English letter frequencies

A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z
--|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|--
73 | 9 | 30 | 44 | 130 | 28 | 16 | 35 | 74 | 2 | 3 | 35 | 25 | 78 | 74 | 27 | 3 | 77 | 63 | 93 | 27 | 13 | 16 | 5 | 19 | 1

#### The Chi-square statistic
Determines how close English frequency distribution matches frequency distribution of the coded message.

`ef(c)` - english frequency `ef` of letter `c`
`mf(c)` - message frequency `mf` of letter `c`

* For each possible shift s between 0 and 25:
* For each letter c of the alphabet
* Compute the sum of squares of mf((c + s) mod 26) divided by ef(c)

Would be good to build a JS tool for this (probably exists, but would be fun).

#### Tips
* single letter words are likely A or I (assuming spacing is accurate)
* repeating letter groups could be TH, SH, RE, CH, TR, ING, ION, and ENT.
* The most common three-letter words, in order of frequency, are THE, AND, FOR, WAS, and HIS. [#](http://www.dummies.com/games/cryptograms/cracking-codes-cryptograms-for-dummies-cheat-sheet/)
* look for double letters

## References
Concepts here taken from: http://www.cs.trincoll.edu/~crypto/historical/caesar.html
