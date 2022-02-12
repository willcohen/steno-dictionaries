# Steno Dictionaries
My personal steno dictionaries for Plover theory.
 - [plover-base.json](#plover-basejson)
 - [rh-numpad.json](#rh-numpadjson)
 - [plover-uk.json](#plover-ukjson)

## plover-base.json
This dictionary is intended to replace Plover's main.json that comes by default. It's not intended to be as extensive (hence **base**) but it should hopefully be more consistent and easier to use, especially as it does not contain any misstrokes.

While the majority of Plover theory have been left untouched, there are several additions to the underlying theory that make this a little problematic if one were to switch to this dictionary after being accustomed to main.json.

> While I believe this dictionary follows more rigorous rules (especially syllable splitting) this is still my personal dictionary and is subject to mistakes. If you spot any misstrokes or bad entries, please let me know as soon as possible so I can fix them. It is also still work in progress with only about 32k entries at time of this writing.

### About this dictionary
 - [Compound words](#Compound-words)
 - [Proper nouns](#Proper-nouns)
 - [Movement keys](#Movement-keys)
 - [Commands and keyboard shortcuts](#Commands-and-keyboard-shortcuts)
 - [Punctuation](#Punctuation)
 - [Right hand number pad](#Right-hand-number-pad)
 - [Fingerspelling](#Fingerspelling)
 - [Phonetics and orthography](#Phonetics-and-orthography)
 - [Breaking up multisyllable words](#Breaking-up-multisyllable-words)
 - [Exceptions to syllable breaks](#Exceptions-to-syllable-breaks)
 - [Prefixes and suffixes](#Prefixes-and-suffixes)

#### Compound words
Compound words are always written with the asterisk on the first stroke of the second word. For example, to write the word "storybooks" would be as `STOR/KWREU/PWAO*BG/-S`.

Examples:
 - `KAOE/PWAO*RD` → keyboard
 - `TEGT/PWAO*BG` → textbook
 - `PHOUS/PA*D` → mousepad

#### Proper nouns
Proper nouns are always written with the number key on the first stroke. Everything else is written with the same rules.
 - `#A/HREU/SA` → Alyssa
 - `#PWOB` → Bob
 - `#PAOE/TER` → Peter
 - `#AP/-L` → Apple
 - `#AUS/TRAEUL/KWRA` → Australia

> I highly recommend mapping the top `S-` key to the number key to make it easier to stroke. This also opens up the possibility for more briefs and decreases hesitation when deciding which finger to use for the number key.

> Unfortunately, entries using the number key will not be displayed as I have above, but rather with numbers. So viewing the dictionary you would see `350ER/TER` instead of `#PAOE/TER`.

#### Movement keys
This dictionary contains arrow key movements and a few selecting movements. By pressing down `STPH` on the left hand, the `-RPBG` cluster becomes arrow keys. `-FR` chorded together would be home, and `-LG` would be end. Pageup and pagedown resemble arrows pointing up and down respectively `-RPG` and `-FBL`.

By pressing `STPH*` instead, the shift modifier is used together with the movement keys in order to select text.

To move word by word (equivalent to pressing `Ctrl+Shift` and left/right), `-RB` and `-BG` are used. On macOS, `Alt+Shift` is used instead so that will have to be changed.

#### Commands and keyboard shortcuts
Many of the commands from main.json have stayed the same.
 - `KPA` → capitalize the next word
 - `KPA*` → capitalize the next word and supress the next space
 - `HRO*ER` → uncapitalize the next word

Retroactive commands have also been added.
 - `KA*PD` → capitalize the last word
 - `HRO*ERD` → uncapitalize the last word

Common keyboard keys have also carried over from main.json.
 - `R-R` → enter/return (capitalization of next word depends on previous punctuation)
 - `#R-R` → `Shift+Enter`
 - `PW-FP` → backspace one character
 - `PW*FP` → backspace one word (`Ctrl+Backspace`; change to `Alt+Backspace` on macOS)
 - `TKHRE` → delete one character
 - `TKHR*E` → delete one word (`Ctrl+Delete`; change to `Alt+Delete` on macOS)
 - `TA*B` → `Tab`
 - `#TAB` → `Shift+Tab`

For writing every single keyboard shortcut possible, I recommend [Emily's modifiers dictionary](https://github.com/EPLHREU/emily-modifiers).

#### Punctuation
 - `H-F` → `?` question mark
 - `KW-PL` → `?` shape can be thought of rising inflection as if asking a question
 - `TP-BG` → `!` shape can be thought of as falling inflection when exclaiming
 - `TP-PL` → `.` period
 - `P-P` → `.` period with no space on either side (when writing decimals)
 - `KW-BG` → `,` comma
 - `KW-GS` → `"` opening quotation mark
 - `KW*GS` → `"` closing quotation mark
 - `KH-FG` → `` ` `` opening backtick
 - `KH*FG` → `` ` `` closing backtick
 - `PREPB` → `(` opening parenthesis
 - `PR*EPB` → `)` closing parenthesis
 - `TPR-BGT` → `{` opening French bracket
 - `TPR*BGT` → `}` closing French bracket
 - `PWR-BGT` → `[` opening bracket
 - `PWR*BGT` → `]` closing bracket
 - `KHR-PB` → `:` colon with no spacing
 - `STPH-FPLT` → `:` regular colon with a space on the right
 - `STPH*FPLT` → `;` regular semicolon with a space on the right
 - `TR*PL` → `™` trademark symbol with a space on the right

For symbols beyond these where you might require different spacing and capitalization, I recommend [Emily's symbols dictionary](https://github.com/EPLHREU/emily-symbols).

#### Right hand number pad
> The conventional number system does not work in plover-base.json. You will have to delete all entries containing the glue operator and a number (e.g. `{&8}`) if you want to use the conventional number system.

plover-base.json has this system by default. See [rh-numpad.json](rh-numpadjson).

#### Fingerspelling
In addition to normal fingerspelling with `*`, using `-FPLT` of `*` will put a period after the letter. `*FPLT` will capitalize the word. `-RBGS` is used for stitching (requires `plover-stitching` plugin).

Examples:
 - `PW*FPLT/KR*FPLT/*EFPLT` → B.C.E.
 - `AFPLT/P-FPLT/P-FPLT/HR-FPLT/EFPLT` → a.p.p.l.e.
 - `PW*RBGS/KR*RBGS/*ERBGS` → B-C-E
 - `ARBGS/P-RBGS/P-RBGS/HR-RBGS/ERBGS` → a-p-p-l-e

Stroking `-FPLT` and `-RBGS` n times will stitch the n words with periods and hyphens retroactively.

Examples
 - `AP/-L/-FPLT` → a.p.p.l.e
 - `PHEU/TPHAEUPL/S/#TOD/-RBGS/-RBGS/-RBGS/-RBGS` → M-y n-a-m-e i-s T-o-d-d

> Note: stroking `-FPLT` does not leave a trailing period.

#### Phonetics and orthography
The main principles of Plover theory have been left unchanged and Learn Plover! or Art of Chording are fully compatible with this dictionary (apart from word breaks as well as suffixes and prefixes). The following list includes changes I've made as well as any rules or tips not necessarily mentioned in any main learning resources for stock Plover.
 - `*PL` is used as the -mp cluster intsead of `-FRP`
 - `-P` can be used by itself to end syllables with a p sound
    - `HEL/-P` → help
 - `OR` is used for the "or" sound
    - `OER` is only used in briefs and suffix sounds
 - `KWR` is used in certain diphthongs such as:
    - `SREUD/KWROE` → video
    - `AEUR/KWRA` → area
    - `EUPB/SOPL/TPHEU/KWRA` → insomnia
    - `RAOE/KWRAL/TEU` → reality
    - Essentially, if the vowel can be approximated with "Y", it is used
 - `KHUR` is always used for the "chur" sound
    - In main.json, there are many inconsistent ways to write a word such as "culture"
        - `KUL/KHAOUR`, `KUL/TAOUR`, `KUL/KHUR`, `KUL/TUR`, etc
    - In this dictionary, culture is written only as `KUL/KHUR`
    - Other examples:
        - `HREBG/KHUR` → lecture
        - `KAP/KHUR` → capture
        - `PHA/KHUR` → mature
 - `TK*EU` is always used for the initial `TKEU` sound when starting a word
    - `TK*EU/REBGT` → direct
    - `TK*EU/HREU/SKWREPBT` → diligents

#### Breaking up multisyllable words
main.json relies a lot on dropping unstressed vowels in order to break up words. Words such as "memorize" benefit from a rule like this as the middle syllable is essentially dropped, leaving it unambiguous as to where to break it up: `PHEPL/RAOEUZ`.

This dictionary tries to follow this principle, but also includes some entries where unstressed vowels haven't been dropped. It is recommended to not rely on these entries entirely as it is slower to use more strokes and these entries may not be complete.

If it is still ambiguous as to where a syllable break starts (even if unstressed vowels have been dropped) then the rule is to carry each syllable as far as possible so that every stroke can start with a consonant.

Syllables should be split in a way that consonants are not doubled and that every stroke that's not an affix begins with a consonant. I'll refer to this as the "normal" splitting method.

"Normal" splitting method:
 - `TPOE/TPHE/TEUBG` → phonetic
 - `PEUBG/KHUR` → picture
 - `KAL/KAOU/HRAEU/TOR` → calculator
 - `RE/KOG/TPHEUGS` → recognition
 - `ABG/TEUF` → active

Invalid ways to break up a word
 - `RAPBD/OPL` (random) ❌
 - `KAOEB/ORD` (keyboard) ❌
 - `HRAPT/OP` (laptop) ❌

However, some words will not be able to be broken up like this such as words starting with vowels. These are handled exactly the same, except that it is acceptable for the first stroke to begin with a vowel.

"Normal" splitting with first stroke starting with a vowel:
 - `EUPL/POR/TAPBT` → important
 - `OE/PWAEU` → obey
 - `ABG/SES` → access

It is also important to use prefixes and suffixes whenever possible to break up words. Many entries containing prefixes and suffixes exist in the dictionary. However, given the nature of how Plover handles suffixes, writing words using these strokes that aren't defined in the dictionary will not show up when using the lookup tool.

Using suffixes:
 - `HRAOBG/SKWRUP` → lookup
 - `HRERPB/*ER` → learner
 - `KOP/KWREU` → copy
 - `TPOE/TPHE/TEUBG/A*L/KWREU` → phonetically

Some words can also be stroked using suffixes, even if whatever was previously written is not a word. This may be because some strokes would be too short and would cause word boundary issues.

Suffixes on root "words":
 - `UT/*ER` → utter (as opposed to `U/TER`)
 - `ED/KWREUGS` → edition (as opposed to `E/TKEUGS`)
 - `HR*ET/*ER` → leather
 - `ALD/*ER` → alder
 - `KEUT/KWREU` → kitty (as opposed to `KEU/TEU`)
 - `A/TOPL/KWREUBG` → atomic
 - `TPOE/TPHET/KWREUBG` → phonetic

> Note that the suffixes "-ic" and "-ition" differ from main.json. See [Prefixes and suffixes](#Prefixes-and-suffixes) for a more complete list of suffixes.

If there are two vowels next to each other that have to be represented in two strokes, `KWR` is used as a linker between the vowels.

`KWR` as a linker between vowels:
 - `AOEU/KWROE/HREU` → aioli
 - `PAOE/KWRA/TPHOE` → piano

`KWR` is can also be used to start a stroke. This can be preferred if a word break using the "normal" method can result in word boundary issues.

`KWR` as a starter:
 - `ER/KWROR` → error
    - Normal method: `E/ROR`
 - `PHEUR/KWROR` → mirror
    - Normal method: `PHEU/ROR`
 - `ES/KWRAEU` → essay
    - Normal method: `E/SAEU`

In the above examples, the normal method would split each word in a way that is less natural and can run into conflicts.

> While doubling the R consonant would be more natural, I wanted to reduce the ambiguity that comes with doubling consonants between strokes as found in main.json. Thus, doubling a consonant is used very rarely in this dictionary.

In general, every word in the dictionary will have at least one of these ways to break up a word. Generally, the "normal" method and using suffixes is preferred, followed by suffixes on non-words and finally `KWR` as a linker.

Other invalid examples of splitting a word:
 - `TERPL/KWRAOEUT` (termite) ❌
    - Use normal method, `TER/PHAOEUT`
 - `EBGS/SAOED` (exceed) ❌
    - `-BGS` already contains the "ks" sound, and the S in the second stroke repeats a consonant
    - Instead use `EBG/SAOED`
 - `TPRAFRPB/AOEUZ` (franchise) ❌
    - Normal method is sufficient `TPRAPB/KHAOEUZ` or `TPRAPB/KHAOEUS`

#### Exceptions to syllable breaks

Sometimes a stroke should not begin with a certain chord as it is a common brief and would lead to word boundary issues. The following chords should not be used as strokes to start an outline.
 - `KO`
 - `PWU`
 - `TKO`

Instead carry the first stroke far enough so that there is a consonant on the right hand and use other means to complete the word.
 - `KOL/KWREBGT` → collect
 - `KOR/KWREBGT` → correct
 - `PWUZ/KWRARD` → buzzard
 - `PWUT/*ER` → butter
 - `TKOBG/KWRAOU/-PLT` → document

If the first stroke of an outline is a prefix, there is no need to use the `KWR` starter on the next stroke:
 - `KOE/OR/TKEU/TPHAEUT` → coordinate
 - `PRE/EPLT` → preempt
 - `TK*EU/AOE/HREBG/TREUBG` - dielectric
 - `TKEUS/AEUBL` → disable

Consonants can also be doubled if the previous stroke is a prefix and the strokes that follow form a valid word on their own:
 - `TKEUS/SOFLS` → dissolves
 - `TKEUS/SEU/PHEU/HRAR` → dissimilar

#### Prefixes and suffixes
 - Since doubling consonants isn't used, `KWREU` is default for adding "-y"
    - `KEUT/KWREU` → kitty
    - `STOR/KWREU` → story
 - `OER` is used for the "-ory" sound but not by itself
    - `SA/TEUS/TPABG/TOER` → satisfactory
    - `TPABG/TOER` → factory
 - `O*R/KWREU` can still be used for the "-ory" suffix
    - `AUTD/O*R/KWREU` → auditory
 - `KWREPB` → "-en"
    - `HRAOEUT/KWREPB` → lighten
    - `SOFT/KWREPB` → soften
 - `KWREPBT` → "-ent"
    - `A/STREUPBG/KWREPBT` → astringent
    - `STAOUD/KWREPBT` → student
    - `AOE/TPEURB/KWREPBT` → efficient
 - `-PLT` → "-ment"
 - Words ending in "-ous" and "-us" always use `KWRUS` or some variation
    - `STAOU/PEPB/TKUS` → stupendous
    - `RAOEUT/KWRUS` → righteous
    - `KHAOEUT/KHUS` → righteous
 - `-LT` → "-let" suffix
    - `A/PHAOU/-LT` → amulet
    - `STAR/-LT` → starlet
 - `-L` → "-le" suffix
 - `KWREUFT` → "-ist"
 - `KWREUBG` → "-ic"
 - `KWREUFT/KWREUBG` and `ST-BG` → "-istic"
    - `RAEL/KWREUFT/KWREUBG` → realistic
    - `A/TPHA/KROPB/ST-BG` → anachronistic
 - `SH-PBS` → "-ishness" suffix
    - `TPAOL/SH-PBS` foolishness
    - `PWHRU/SH-PBS` → bluishness
 - `{^ally}` is `A*EL` or `A*L/KWREU` but these are not defined in the dictionary
    - Usually `HREU` can also work as these are explicitly defined in the dictionary
        - For example, `TKE/PHO/TKPWRAF/EUBG/HREU` → demographically (in the dictionary)
        - `TKE/PHO/TKPWRA/TPEUBG/A*EL` → demographically (not in the dictionary)
        - `TKE/PHO/TKPWRA/TPEUBG/A*L/KWREU` → demographically (not in the dictionary)

## rh-numpad.json

> I highly recommend mapping the top `S-` key to the number key to make it easier to stroke. This also opens up the possibility for more briefs and decreases hesitation when deciding which finger to use for the number key.

With this system, pressing the number key will turn `-FRPBLG` into a keypad of sorts. The bottom three keys are 1, 2, and 3 (from left to right) while the top three keys are 7, 8, 9 and chording two keys in a column will get 4, 5, and 6 (from left to right). If the `E` key is used in the stroke, 0 will be appended to whatever digit is being chorded. The `U` key will append a 00 on the digit, and `EU` will append a 000 on the digit.

Examples:
 - `#-G/#-R/-FR/#-R/#-PB/#-L` → 314159
 - `#EB` → 20
 - `#UPB`→ 500

## plover-uk.json
Soon™
