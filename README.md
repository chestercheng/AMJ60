# AMJ60
AMJ60 Keyboard tmk firmware

## Requirement

* [CrossPack-AVR](https://www.obdev.at/products/crosspack/index.html)

> ` brew cask install crosspack-avr `

* [dfu-programmer](https://github.com/dfu-programmer/dfu-programmer)

> ` brew install dfu-programmer `


## Keymap

* Keymap 0: Default Layer

```
,-----------------------------------------------------------.
|ESC| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 | - | = | BSPC  |
|-----------------------------------------------------------|
| TAB | Q | W | E | R | T | Y | U | I | O | P | [ | ] |  \  |
|-----------------------------------------------------------|
| CAPS | A | S | D | F | G | H | J | K | L | ; | ' |  ENT   |
|-----------------------------------------------------------|
|  LSFT  | Z | X | C | V | B | N | M | , | . | / | RSFT |FN0|
|-----------------------------------------------------------|
|LCTL|LALT|LGUI|         SPACE          |LEFT|DOWN| UP |RGHT|
`-----------------------------------------------------------'
```

* Keymap 1: Fn Layer

```
,-----------------------------------------------------------.
| ` | F1| F2| F3| F4| F5| F6| F7| F8| F9|F10|F11|F12| POWER |
|-----------------------------------------------------------|
| TAB |   |   |   |   |   |   |MPR|MPL|MNT|MUT|VLD|VLU|     |
|-----------------------------------------------------------|
| CAPS |   |   |   |   |   |   |   |   |   |   |   |  ENT   |
|-----------------------------------------------------------|
|  LSFT  |   |   |   |   |   |   |   |   |   |   | RSFT |FN0|
|-----------------------------------------------------------|
|LCTL|LALT|LGUI|         SPACE          |HOME|PGDN|PGUP| END|
`-----------------------------------------------------------'
```


## Flashing Firmware

```
export PATH=/usr/local/CrossPack-AVR/bin:$PATH
make KEYMAP=tkg dfu
```
> Output:
>
> ```
> dfu-programmer atmega32u4 erase --force
> Erasing flash...  Success
> Checking memory from 0x0 to 0x6FFF...  Empty.
> dfu-programmer atmega32u4 erase
> Checking memory from 0x0 to 0x6FFF...  Empty.
> Chip already blank, to force erase use --force.
> dfu-programmer atmega32u4 flash AMJ60_lufa.hex
> Checking memory from 0x0 to 0x4FFF...  Empty.
> 0%                            100%  Programming 0x5000 bytes...
> [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
> 0%                            100%  Reading 0x7000 bytes...
> [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
> Validating...  Success
> 0x5000 bytes written into 0x7000 bytes memory (71.43%).
> dfu-programmer atmega32u4 reset
> ```
