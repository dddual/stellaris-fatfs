stellaris-fatfs
===============

FatFs adaptation to work with the Stellaris Launchpad. Inside sources you will find FatFs with the mmc.c driver adapted to the Stellaris Launchpad, and some extra files implementing useful syscalls and UART support. UART0 is used for stdout, so connect to the UART (115200,N,1) in the debug port to see output from printf() calls.

You will not find fancy speed tests or anything like that. Only a plain test file that writes "Hello World!" to a file inside the SD.

The SD card must be wired as follows:

		RA2 (SSI_CLK)	-->	CLK
		RA3 (SSI_FSS)	-->	CD/DAT3/CS
		RA4 (SSI_RX)	-->	DAT0/DOUT
		RA5 (SSI_TX)	-->	CMD/DI

Of course you will also have to connect VDD to 3.3V and VSS to GND. Two decoupling capacitors of 10 uF and 100 nF connected between VDD and VSS as near as possible to the SD card are also highly recommended.

Everything I wrote is GPLv3 licensed. FatFs has its own free non-restricted license.

Warning: Startup file startup_gcc.c and linker file lm4f120.ld are from Texas Instruments, and altouth license terms are not clear, might be conflicting with GPLv3 license. If there's a problem I'll try to replace them with GPLv3 compatible reimplementations.
