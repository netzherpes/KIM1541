# KIM1541
Dave McMurtrie's 1541 Routines dor the KIM-1<br>
(c)2022 Dave McMurtrie<br>

![https://github.com/netzherpes/KIM1541/raw/main/1541l.jpg](https://github.com/netzherpes/KIM1541/raw/main/1541l.jpg)
# Instructions on KIM1541

Get the original Program by Dave McMurtrie here:<br>
https://commodore.international/kim-iec/kim1541_public.asm<br>
https://commodore.international/kim-iec/kim1541.bin<br>

visit https://commodore.international<br>
and the youtube channel https://www.youtube.com/channel/UCWYuahcuxawiFujBmL6E1cg<br>

This instruction is taken from the video<br>
https://youtu.be/cK7mzGhBfHs


Start:

1. Set $00F1 to $00 to ensure the CPU is in decimal mode<br>
2. Set up the interrupt vectors for BRK:<br>
   $17FA 00<br>
   $17FB 1C<br>
3. Load the KIM1541 Program (or burn it on an EPROM)<br>

4. Loading and saving uses the same procedure as loading and saving to tape:

	To save:<br>
	1. Save start address (low/high) in $17F5, $17F6.<br>
	2. Save end address+1 (low/high) in $17F7, $17F8.<br>
	3. Write Programs ID ($01-$FE) in $17F9. (this will be the filename)<br>
	4. Run address $2148 to save to disk<br>

	To load:
	1. Write Programs ID (the name on the Floppy - $01-$FE) to $17F9.<br>
	2. Run address $2000 to load from disk.<br>


Update: I've also changed one version to be loaded to $A000 for my ROM Module

Have fun,<br>
webdoc.
