# CH6502
My ramblings about creating a cheap hobby computer besed on the 65C02 for code execution and an AT89C55WD for I/O and video.
## Note
These are just ramblings, no schematics, diagrams or board layout yet. But it may happen someday....
## Terminology
μC - AT89C55WD
6502 - 65C02
## 6502 & μC bus

000x xxxx xxxx xxxx - RAM Begin
100x xxxx xxxx xxxx - RAM End

101x xxxx xxxx xxxx - Bank RAM start
101x xxxx xxxx xxxx - Bank RAM end

110x xxxx xxxx xxxx - Bank ROM start
111x xxxx xxxx xxxx - Bank ROM end
abcd

## RAM chip bus
yyyy yyyy xxxx xxxx xxxx (x - last address line, UB/LB select)

## Letters
x - shared bus between μC, 65C02, RAM
y - RAM bank select

## MMU Rig
The μC polls the IO space on its own, but I still need to figure out how to attach more RAM to it.
ROM = a & b         -> ROM access (RAM disable)
RAM = !ROM          -> RAM access (RAM enable, top 8 bits driven to zero)
RAM & c             -> Bank RAM access (RAM enable, top 8 bits fron 0000h of non-banked RAM)

