# MecrispForth_HT16K33

## Forth Words for HT16K33

### 14 segment LED Display with HT16K33

#### init

    i2c-init i2c. \ init i2c and display avaiable devices
    $70 i2c-addr $21 >i2c 0 i2c-xfer \ set oscilator on (bit 0)
    $70 i2c-addr $20 >i2c 0 i2c-xfer \ standby (lowest current)
    
    $70 i2c-addr $80 >i2c 0 i2c-xfer \ set display off
    $70 i2c-addr $81 >i2c 0 i2c-xfer \ set display on
    $70 i2c-addr $83 >i2c 0 i2c-xfer \ set display on, blink 2Hz
    $70 i2c-addr $85 >i2c 0 i2c-xfer \ set display on, blink 1Hz
    $70 i2c-addr $87 >i2c 0 i2c-xfer \ set display on, blink 0,5Hz
    
    $70 i2c-addr $EF >i2c 0 i2c-xfer \ set max brightness (bit 0-3)
    $70 i2c-addr $E0 >i2c 0 i2c-xfer \ set min brightness

    $70 i2c-addr $00 >i2c $FF >i2c 0 i2c-xfer \ first digit 8 segments for "7-segment"
    $70 i2c-addr $01 >i2c $FF >i2c 0 i2c-xfer \ first digit other 8 segments
    $70 i2c-addr $02 >i2c $FF >i2c 0 i2c-xfer \ second digit 8 segments for "7-segment"
    $70 i2c-addr $03 >i2c $FF >i2c 0 i2c-xfer \ second digit other 8 segments
    $70 i2c-addr $04 >i2c $FF >i2c 0 i2c-xfer \ third digit 8 segments for "7-segment"
    $70 i2c-addr $05 >i2c $FF >i2c 0 i2c-xfer \ third digit other 8 segments
    $70 i2c-addr $06 >i2c $FF >i2c 0 i2c-xfer \ fourth digit 8 segments for "7-segment"
    $70 i2c-addr $07 >i2c $FF >i2c 0 i2c-xfer \ fourth digit other 8 segments
    
**words need to be writen :)**

## Schematics

* SDA and SCl need pullup via 10k resistor (if other i2c devices are connected, most often they already have it)

