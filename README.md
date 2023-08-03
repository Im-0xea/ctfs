### IOLI

##### 0x00 - OK / MOD

###### static anal

- see strcmp with "250382"
- 250382

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"

##### 0x01 - OK / MOD

###### static anal

- see scanf with fmt 0x804854c
- 0x804854c "%d"
- see cmpl 0x149a 
- 5274

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"

##### 0x02 - OK / MOD

###### static anal

- see scanf with fmt addr to "%d"
- follow a bunch of memory operations on vars
- input == pow(0x5a + 0x1ec, 2)
- 338724

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"


##### 0x03 - OK / MOD

###### static anal

- see same memory operations as in 0x02
- see mean shift operations
- try 338742
- 338742

###### mod

- jmp over password prompt directly to sym.test
- overwrite je for mod result with unconditional jmp
