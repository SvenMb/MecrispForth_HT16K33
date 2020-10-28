# MecrispForth_HT16K33

## Forth Words for HT16K33

### 14 segment LED Display with HT16K33

#### init

    i2c-init i2c. \ init i2c and display avaiable devices
    i2c-addr $21 >i2c 0 i2c-xfer \ set oscilator on (bit 0)
    i2c-addr $81 >i2c 0 i2c-xfer \ set display on (bit 0)
    i2c-addr $EF >i2c 0 i2c-xfer \ set max brightness (bit 0-3)
    i2c-addr $E0 >i2c 0 i2c-xfer \ set min brightness
    
    $70 i2c-addr $00 >i2c $FF >i2c 0 i2c-xfer \ first digit 8 segments for "7-segment"
    $70 i2c-addr $01 >i2c $FF >i2c 0 i2c-xfer \ first digit other 8 segments
    

    
**words need to be writen :)**
