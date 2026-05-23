
# WCH ch32v20x/30x bootloader replace functions

With the implemented functions you can recover bootloader in ch32v20x/30x chips.

I have not tested ch32F family, but if the flash controller is the same, it "should" work.


sfdp parser from: https://raw.githubusercontent.com/petris/sfdp-parser/master/sfdp-parser.c


More here:
[https://michaldemin.wordpress.com/2023/05/06/wch-ch32v20x-30x-risc-v-flash-memory/](https://michaldemin.wordpress.com/2023/09/27/wch-ch32v20x-30x-risc-v-flash-memory/)https://michaldemin.wordpress.com/2023/09/27/wch-ch32v20x-30x-risc-v-flash-memory/


Connect a WCH-Link tool to the board using SWCLK, SWDIO, 5v/3v and Ground.  Then use use MounRiver Studio or WCH Link Utility to burn the boot.bin or boot-small.bin to the board.  The board will reset and it will program itself with the new bootloader.  Essentially the boot.bin is a program that runs on the chip and re-flash the boot loader using the binary embedded within the program.

Read the src/main.c file for more details.
