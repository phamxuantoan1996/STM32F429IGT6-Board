# 1.FMC
FMC (Flexible Memory Controller). Support:
+ SDRAM
+ NOR/SRAM/PSRAM
+ NAND Flash
+ LCD parallel interface


# 2. IS42S16400J SDRAM

IC overview:
+ Manufacturer: ISSI (Integrated Silicon Solution Inc.)
+ Type: Synchronous Dynamic RAM (SDRAM)
+ Density: 64 Mbit (megabit) = 8 MB (megabyte)
+ Organization: 4M x 16-bit x 4 banks

Memory Organization
+ Bank : 4 Bank (BA0, BA1)
+ Row Address : 12 bits (A0 - A11 -> 4096 rows per bank)
+ Column Address : 8 Bits (A0 -> A7 -> 256 columns per row)
+ Word Width : 16 bit data bus (DQ0 - DQ15)
+ Total capacity : 4 banks x 4096 rows x 256 columns x 16 bits = 64 Mbit = 8 MB

Key Features
+ CAS Latency (CL) : 2 or 3 cycle
+ Burst Length : 1,2,4,8, full page
+ Clock Frequency : upto 166 MHz

Mode Register:
+ Burst Length
+ Burst Type
+ CAS Latency
+ Operating Mode
+ Write Burst Mode

# Application with STM32 FMC
Connect:
+ CLK → SDCLK
 
+ CKE → SDCKE

+ CS# → SDNE

+ RAS# → SDRAS

+ CAS# → SDCAS

+ WE# → SDWE

+ BA0/BA1 → FMC_BA0/1

+ A0–A11 → FMC_A0–A11

+ DQ0–15 → FMC_D0–D15

+ LDQM, UDQM → FMC_NBL0, FMC_NBL1

Mode setting in STM32 FMC
+ Column bits : 8
+ Row bits : 12
+ CAS latency : 3
+ Data bus : 16-bit
+ Internal bank : 4

<img width="927" height="553" alt="image" src="https://github.com/user-attachments/assets/6e920ac7-af08-49cc-859a-ab81e7d1ec81" />







