### IOLI

##### 0x00 - OK / MOD / EXP

###### anal

- see strcmp with "250382"
- 250382

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"

###### exp(overflow)

- stack string 24 - 4 bytes nothing - return address
- scanf("%s", stack)
- <28 chars>\x80\x84\x04\x08

##### 0x01 - OK / MOD

###### anal

- see scanf with fmt 0x804854c
- 0x804854c "%d"
- see cmpl 0x149a 
- 5274

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"

##### 0x02 - OK / MOD

###### anal

- see scanf with fmt addr to "%d"
- follow a bunch of memory operations on vars
- input == pow(0x5a + 0x1ec, 2)
- 338724

###### mod

- seek to "password:" string move, overwrite with jmp to "OK"


##### 0x03 - OK / MOD

###### anal

- see same memory operations as in 0x02
- see mean shift operations
- try 338742
- 338742

###### mod

- jmp over password prompt directly to sym.test
- overwrite je for mod result with unconditional jmp

##### 0x04 - MOD / EXP

###### anal

###### mod

- jmp over password prompt directly into checks ok part, since it terminates with exit()

###### exp(overflow)

- stack string 120 bytes - 4 bytes nothing - return address
- scanf("%s", stack)
- <124 chars>\xdc\x84\x04\x08
