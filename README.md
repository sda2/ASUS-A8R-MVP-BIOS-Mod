# ASUS A8R-MVP — BIOS 0605 O.C. Profile Mod

Modified AMIBIOS8 firmware for the **ASUS A8R-MVP**, based on ASUS BIOS **0605**.

Image: `A8RSDA01.ROM`, 512 KiB.

<img width="2656" height="2784" alt="grafik" src="https://github.com/user-attachments/assets/5e12ecdd-efcc-4569-905c-f483719d7a81" />

## Features

- Two BIOS setup profiles stored in flash NVRAM.
- Save/load menu: **Exit → ASUS O.C. Profile**. Apply loaded settings with **Save & Exit**.
- New menu **Advanced → DRAM Configuration**: live timings, memory clock, command rate, all timings, interleaving and ECC on one page (moved out of CPU Configuration).
- AI Overclocking no longer forces *User Config Mode = Manual* and *2T* at FSB ≥ 220 MHz.
- *Memclock Value* shows the DDR rate with the FSB:DRAM ratio, e.g. `DDR400 (1:1)`.
- *HT Link Speed* shows the HT multiplier `1x`–`5x`.
- Help texts for the DRAM timings (written-out names) and the voltage items.

The main module uses AMI LH5 compression. Module and main BIOS checksums are valid for ASUS AFUDOS 1.19.

## Validation

Hardware testing confirmed correct operation with all BIOS settings and successful DOS flashing. Both profiles remain persistent after mains power removal and a CMOS reset.

## Flashing

Back up the existing chip contents before flashing. Copy the included `AFUDOS.EXE` (ASUS AFUDOS 1.19) and `A8RSDA01.ROM` to the DOS drive, then run:

```text
AFUDOS /iA8RSDA01.ROM
```

Use only on the specified board; recovery from a failed flash may require an external programmer.

## NVRAM

The supplied image contains the backup NVRAM with empty profile slots. Existing profiles on the board may be overwritten depending on the flashing method.

This is an unofficial modification; original firmware and AFUDOS rights remain with their respective owners.
