# CH6502
My ramblings about creating a cheap hobby computer besed on the 65C02 for code execution and an AT89C55WD for I/O and video.
## Note
These are just ramblings, no schematics, diagrams or board layout yet. But it may happen someday....
## Terminology
μC - AT89C55WD <br>
6502 - 65C02 <br>
## 6502 & μC bus
<br>
000x xxxx xxxx xxxx - RAM Begin <br>
100x xxxx xxxx xxxx - RAM End <br>
<br>
101x xxxx xxxx xxxx - Bank RAM start <br>
101x xxxx xxxx xxxx - Bank RAM end <br>
<br>
110x xxxx xxxx xxxx - Bank ROM start <br>
111x xxxx xxxx xxxx - Bank ROM end <br>
abcd <br>

## RAM chip bus
yyyy yyyy xxxx xxxx xxxx (x - last address line, UB/LB select) <br>

## Letters
x - shared bus between μC, 65C02, RAM <br>
y - RAM bank select <br>

## MMU Rig
The μC polls the IO space on its own, but I still need to figure out how to attach more RAM to it. <br>
ROM = a & b         -> ROM access (RAM disable) <br>
RAM = !ROM          -> RAM access (RAM enable, top 8 bits driven to zero) <br>
RAM & c             -> Bank RAM access (RAM enable, top 8 bits fron 0000h of non-banked RAM) <br>

