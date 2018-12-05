# Hebrew-QWERTZ-Windows-keyboard
The purpose of this project is to develop Windows keyboard which maps Hebrew letters according their phonetic or visual similarity with English (ASCII) letters.
## Letters
22 Hebrew letters are mapped to 21 keys (because of a, e, i, o, and u are reserved for vowels - see below) following way:
- according phonetic similarity
	- g, d, h, z (y on QWERTZ layout), t, j, l, m, n, s, c, q, r
- according phonetic similarity of letter with dagesh
	- b, k, p
- according visual similarity
	- x for alef
	- y (z in QWERTZ layout) for ayin
	- w/W for sin/shin
- specialities
	- v for waw as "w" is  pronounced close to "v" in some languages
	- f for ta*f*
	- H for chet
	- AltGr (Ctrl+Alt)+s for sin *without* dot
- the final forms are written with Shift
- the wide forms are written with AltGr (Ctrl+Alt) including final mem

|Key   |Normal|Shift |AltGr (Ctrl+Alt)|
|----- |------|------|------|
|x|א alef||wide ﬡ|
|b|ב vet (bet)|||
|g|ג gimmel|||
|d|ד dalet||wide ﬢ|
|h|ה he|ח chet|wide ﬣ|
|v|ו waw|||
|y*|ז zajin|||
|t|ט tet|||
|j|י yod|||
|k|כ chaf (kaf)|ך final|wide ﬤ|
|l|ל lamed||wide ﬥ|
|m|מ mem|ם final|wide ﬦ final|
|n|נ nun|ן final||
|s|ס samech||ש sin (without dot)|
|z*|ע (ayin)|||
|p|פ fe(pe)|ף final||
|c|צ tsade|ץ final||
|q|ק qof|||
|r|ר resh||wide ﬧ|
|w|שׂ sin|שׁ shin||
|f|ת taf||wide ﬨ|
(*) Similar to Y and Z interchanging in QWERTZ layouts (e.g. Czech, German etc.)

### Letters with dagesh / mappiq
Because of many modern Hebrew fonts contain special characters for letters with dagesh or mappiq I've decided to implement dagesh as dead key mapped to "." (period)
- e.g. "." followed by b results in בּ
- if neither nor mappiq is allowed with letter (ayin, chet, final forms instead of pe and kaf) the result is same letter as without dead key; such behaviour is not implemented for wide forms
- "." followed by "." result in separate dagesh (mappiq) in case the font doesn't include letter with dagesh and there is necessary to composite final character
	- such way the dagesh is typed *after* the letter
	- e.g. b followed by two "." results in
### Composite sin/shin
If font doesn't contain glyph for sin/shin with dot (very rare) or if you just want to type the sin/shin without dot, you can
- use AltGr (Ctrl+Alt) + s to type ש
- ש followed by AltGr (Ctrl+Alt) + q to type שׂ as composite
- ש followed by Shift + AltGr (Ctrl+Alt) + q to type שׁ as composite
## Vowels
To type nikkud, the vowels - typed after previous letter - are mapped following way (the alef is used just a pattern, same way the waw for holam haser):
|Key   |Normal|Shift |AltGr (Ctrl+Alt)|Shift+AltGr (Ctrl+Alt)|
|-----|-------|------|------|------|
|a| אַ patah| אָ kamats| אֲ hataf patah| אֳ hataf kamats|
|e| אֶ segol | אֵ tsere| אֱ hataf segol|  |
|i| אִ hiriq | אִי hiriq yod|  |  |
|o| אֹ holam | אוֹ holam male| אׇ kamats hatuf| וֺ holam haser for waw|
|u| אֻ kubuts | אוּ shuruk|  |  |

### Sheva
The sheva is mapped to ";" (semicolon) as dead key. The ";" followed by any key results in sheva. Just ";" followed by ";" results in ":" (colon)
- so e.g. שְׁוָא is typed as W;vAx

## Punctuation, special accents
I've tried to by compatible with SIL keyboard (https://www.sbl-site.org/Fonts/BiblicalHebrewSILManual.pdf) if possible, differences are either marked with (*) or commented below table
- empty position means characters mentioned above (letters, vowels, dead key for dagesh adn sheva, sin{shin dots})
- the "x" means same character as on standard US keyboard
- 
|Key   |Normal|Shift |AltGr (Ctrl+Alt)|Shift+AltGr (Ctrl+Alt)|
|-----|-------|------|------|------|
| ` | . | ₪ sheqel *20aa*| $ dollar| ~ tilde|
| 1 | . | . | ◌ֽ meteg *05bd*| ◌֮ revia *0597*|
| 2 | . |  zarqa *0598*|  atnah hafukh *05a2*|  zinor *05ae*|
| 3 | . |  qadma *05a8*|  tipeha *0596*|  pashta *0599*|
| 4 | . |  geresh (accent) *059c*|  merkha *05a5*|  telisha gedola *05a0*|
| 5 | . |  gershayim (accent) *059e*|  kefula *05a6*|  telisha qetana *05a9*|
| 6 | . |  |  degi *05ad*|  qarnez para *059f*|
| 7 | . |  ilum *05ac*|  munah *05a3*|  payer *05a1*|
| 8 | . |  geresh muqdam *059d*|  tevir *059b*|  zaqef gadol *0595*|
| 9 | . | . |  darga *05a7*|  masora circle *05af*|
| 0 | . | . |  |  rafe *05bf*|
| - | ◌־◌ maqaf *05be*|  en dash *2013*|  em dash *2014*|  dotted circle *25cc*|
| = | . | . |  yerah ben yomo *05aa*|  |
| q | x |  | x | x |
| o | x | x | x | x |
| p | x | x |  |  combine grapheme joiner *034f*|
| [ | . | . |  yetiv *059a*|  zaqef qatam *0594*|
| ] | . | . |  mahapakh *05a4*|  segolta *0592*|
| \ |  paseq *05c0*| \ (\*)|  ole *05ab*|
| f | x |  |  |  (\*)white bullet *25e6*|
| g | x |  |  |  bullet 2022|
| h | x | x | x(\*) |  ring above *030a*|
| j | x |  |  |  (\*)long stroke *0336*|
| ; | x |  gershayim (punctuation) *05f4*|  semicolon *003b*|  sof pasuq *05c3*|
| ' | ’ right single quotation *2019*|  right single quotation *201d*|  punctum *0323*|  upper dot *05c4*|
| z | x |  | # number sign|  |
| x | x |  | x |  |
| c | x | x | & ampersand |  |
| v | x  |  | @ at sign| (\*) left-to-right *200e*|
| n | x | x | \* asterisk|  (\*) right-to-left *200f*|
| m | x | x | x | (\*) zero width non-joiner *200c*|
| , | . | . |  guillemets left|  zero width joiner *200d*|
| . | x | . |  guillemets right|  masora dot above *0307*|
| / | . | . |  geresh (punctuation) *05f3*|  thousands *0308*|






## ToDo
- add Unicode codes