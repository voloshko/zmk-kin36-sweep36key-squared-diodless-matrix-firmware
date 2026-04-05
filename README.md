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

Press two keys simultaneously (within 40ms) to output an entire word with a trailing space. Works on default and windows layers. A 150ms prior-idle guard prevents misfires during fast typing.

Defined in =config/combos.dtsi=. Tune =timeout-ms= (combo window) and =require-prior-idle-ms= (misfire guard) to taste.

**** Word chords

| Chord | Word | Chord | Word | Chord | Word |
|-------+------+-------+------+-------+------|
| T+H | the | T+A | that | A+N | and |
| H+V | have | R+F | for | O+N | not |
| W+I | with | Y+U | you | T+I | this |
| U+B | but | F+M | from | T+Y | they |
| W+L | will | W+D | would | R+T | there |
| E+T | their | W+A | what | A+B | about |
| W+C | which | W+N | when | S+J | just |
| K+N | know | K+L | like | I+N | into |
| R+Y | your | D+C | could | T+O | other |
| T+K | think | A+L | also | A+F | after |
| C+B | because | S+H | should | T+G | through |
| F+B | before | T+B | between | W+O | without |
| S+M | something | R+A | already | P+L | people |
| T+S | these | | | | |

**** Utility chords

| Chord | Output |
|-------+--------|
| J+K | Escape |
| U+I | =(= |
| I+O | =)= |
| W+F | Caps Word |

*** Mouse

- hold left tab (to enter left layer), and press space key to enter mouse layer
- press =p= or =q= to quit mouse layer
- =MB4= is for going backward and =MB5= is for going forward

#+caption: mouse layer
[[file:images/mouse-layer.png]]

