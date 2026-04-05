# ZMK firmware for Kin36, Sweep36, Sweep Squared
ZMK Firmware for Kin36, Sweep36(ZMK Cradio shield but with 36 keys), Sweep Squared, Swoop36 and other 3x5 keyboards with full diodless matrix and default ProMicro-compatible BLE MCU(nice!nano, ProMicro NRF52840, TENSTAR ROBOT NRF52840, etc).



* Quick Start

** flash new firmware

1. Fork this repo
2. (optional) update keymap and config file
3. wait github action to build the firmware, then you download and decompress the zip file
4. connect left or right half to your computer with use cable
5. left or right half enter bootloader, you can enter bootloader by
   1) double-clicking the reset button
   2) quickly short-circuiting the reset button twice (if the button is not working)
   3) quickly short-circuiting the gnd & rst pins of the controller twice(not the VCC 3.3v or RAW 5v pins!) 
6. copy firmware to your half of keyboard (updating keymap and changing keyboard name do not have to flash the right half)
   1) filename with 'left' is for the left half of keyboard
   2) filename with 'right' is for the right half of keyboard
   3) filename with 'reset' is for the left/right half to forget its bluetooth connection info (when left & right half is not able to connect, to forget paired devices)


*** Characters

- The default layer and windows layer is where you would type characters.
- they both have modifier keys =CTRL=, =OPTION (ALT)=, =COMMAND (WINDOWS)= sharing same position with character keys on your ring finger, middle finger and pointing finger on both hands. Hold the key to trigger the modifier, or tap the key to type in character.

#+caption: default layer
[[file:images/default-layer.png]]

#+caption: windows layer
[[file:images/windows-layer.png]]

*** Numbers and Navigation

- Hold the right tab to enter right layer, then you can type in numbers or do some navigation.
- Release your right tab to return to default or windows layer.
- Special keys:
  - =&bootloader= :: make right part of the split keyboard enter bootloader, then you can copy in your new firmware.

#+caption: right layer
[[file:images/right-layer.png]]

*** Punctuations

- Hold the left tab to enter left layer, then you can type in punctuations.
- Release your left tab to return to default or windows layer.
- Special keys:
  - =&default_report= :: type out battery information
  - =&bootloader= :: make left part of the split keyboard enter bootloader, then you can copy in your new firmware.
  - =5= :: switch to mouse layer

#+caption: left layer
[[file:images/left-layer.png]]

*** Functions

- Hold both the left and right tab to enter tri layer, then you can type function keys.
  - =BT_SEL_#= :: select position of bluetooth device you are connecting or want to connect with.
  - =BT_CLR= :: clear the connection on selected position, then you can reconnect to this position with your device.
  - =OUT_TOG= :: toggle between usb and bluetooth connection, so you can connect up to 6 devices (5 with bluetooth, and 1 with usb)
  - =&tog 1= :: toggle windows layer, so you can switch between default and windows layer.
  - =&studio_unlock= :: unlock keyboard so that you can use [[https://zmk.dev/docs/features/studio#keymap-changes][zmk studio]] to setup keys
  - =&soft_off= :: enter soft off, like deep sleep which enters after an hour of inactivity, but soft off can only be woke up with wake up keys (set to left thumb key: =shift=)
- Release your tab keys to return to default or windows layer.

#+caption: tri layer
[[file:images/tri-layer.png]]

*** Chords (Combos)

Press two or more keys simultaneously (within 40ms) to output an entire word with a trailing space. Works on default and windows layers. A 150ms prior-idle guard prevents misfires during fast typing.

Defined in =config/combos.dtsi=. Tune =timeout-ms= (combo window) and =require-prior-idle-ms= (misfire guard) to taste.

**** 2-key word chords (58)

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| T+H | the | A+N | and | T+A | that |
| H+V | have | W+H | with | F+O | for |
| N+T | not | Y+U | you | T+S | this |
| B+U | but | F+M | from | T+Y | they |
| W+L | will | W+D | would | W+A | what |
| A+B | about | W+C | which | W+N | when |
| J+S | just | K+N | know | L+C | like |
| Y+R | your | C+D | could | S+H | should |
| B+F | before | B+C | because | T+K | think |
| A+L | also | A+F | after | T+M | time |
| A+G | again | S+M | some | G+D | good |
| M+R | more | N+V | never | E+V | even |
| V+R | very | W+K | work | W+Y | way |
| M+K | make | N+D | need | N+L | only |
| B+N | been | H+L | while | C+N | can |
| C+M | come | O+E | one | G+E | great |
| M+G | might | F+N | found | U+D | under |
| O+T | other | P+E | people | R+L | really |
| H+R | her | H+S | his | A+E | are |
| W+S | was | | | | |

**** 3-key word chords (91) — common English

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| T+H+R | through | T+H+E | there | T+H+A | than |
| T+H+I | their | T+H+O | those | T+H+G | thing |
| T+H+U | though | T+R+E | three | T+G+R | together |
| A+N+T | another | W+H+R | where | W+H+T | whether |
| B+T+N | between | S+M+T | something | A+R+D | already |
| A+W+S | always | A+R+N | around | D+F+R | different |
| M+P+R | important | S+T+L | still | E+V+R | every |
| F+S+R | first | W+R+L | world | L+T+I | little |
| R+G+T | right | B+N+G | being | S+M+L | small |
| T+A+K | take | W+E+L | well | I+N+T | into |
| H+E+R | here | S+I+N | since | S+T+R | story |
| W+R+T | write | U+S+N | using | A+C+L | actually |
| L+R+N | learn | P+N+T | point | L+O+G | long |
| K+E+P | keep | S+A+M | same | E+C+H | each |
| H+L+P | help | | | | |

**** 3-key — ML/AI

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| D+F+N | diffusion | E+M+B | embedding | G+R+D | gradient |
| I+N+F | inference | T+R+N | training | A+C+T | activation |
| B+P+R | backprop | N+R+L | neural | D+R+P | dropout |
| D+S+T | dataset | T+K+N | tokenize | L+T+N | latent |
| S+F+M | softmax | R+S+D | residual | C+K+P | checkpoint |
| L+G+T | logit | E+P+C | epoch | B+T+C | batch |
| M+D+L | model | L+N+G | language | P+R+M | parameter |
| M+A+B | mamba | C+N+V | convolutional | | |

**** 3-key — Rust

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| T+R+A | trait | A+W+T | await | I+M+L | impl |
| R+S+L | Result< | O+T+N | Option< | E+N+M | enum |
| M+T+C | match | R+E+T | return | D+R+V | derive |
| C+L+S | closure | L+F+T | lifetime | B+R+W | borrow |
| M+U+T | mut | | | | |

**** 3-key — Haskell

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| M+N+D | monad | F+C+T | functor | M+A+Y | Maybe |
| M+N+I | monoid | L+M+B | lambda | T+P+C | typeclass |

**** 3-key — other

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| F+N+C | function | C+L+D | Claude | A+T+P | Anthropic |
| A+Z+R | Azure | D+C+K | duckdb | I+C+B | iceberg |

**** 4-key word chords (10)

| Chord | Word | Chord | Word |
|-------+------+-------+------|
| T+R+N+F | transformer | K+W+N+T | quantization |
| I+M+P+L | implementation | S+T+R+C | struct |
| A+S+N+C | async | H+S+K+L | haskell |
| F+R+L+A | forall | S+K+N+L | Skinly |
| B+R+D+F | Beiersdorf | A+R+C+H | architecture |

**** Utility chords

| Chord | Output |
|-------+--------|
| J+K | Escape |
| D+F | Tab |
| K+L | Tab |
| W+F | Caps Word |
| U+I | =(= |
| I+O | =)= |
| H+J | =[= |
| J+L | =]= |
| N+M | Enter |
| H+N | Backspace |

*** Mouse

- hold left tab (to enter left layer), and press space key to enter mouse layer
- press =p= or =q= to quit mouse layer
- =MB4= is for going backward and =MB5= is for going forward

#+caption: mouse layer
[[file:images/mouse-layer.png]]

