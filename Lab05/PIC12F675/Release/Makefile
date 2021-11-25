###############################################################################
# Makefile for project 
###############################################################################

## General options
PROJECT = 
MCU = PIC12F675
COMPILER = "MPASM (Proteus)"
TARGET = Release
SHELL = C:\Windows\system32\cmd.exe

## Tools general options
ASMFLAGS=/q+ /p12f675
LDFLAGS=/p12f675

## Processing Tools
ASM=MPASMWIN.exe
LD=mplink.exe
LIB=mplib.exe
#  C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab05/PIC12F675/Release/Release.hex: TOOL=LD
#     C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab05/PIC12F675/Release/main.o: TOOL=ASM
#        C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab05/PIC12F675/main.asm

# Build tree:
all:	Release

Release:	Release.hex
	cp "Release.hex" "C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab05/PIC12F675.hex"

Release.hex:	main.o 
	$(LD) $(LDFLAGS) /o "./Release.cof" 12f675_g.lkr "main.o"

main.o:	../main.asm 
	$(ASM) /e"./main.err" /l"./main.lst" /o"main.o" $(ASMFLAGS)  "..\main.asm"

# tidy - delete all temporary files which are not involved in the target generation
tidy:
	rm -rf Release.cof
	rm -rf ./main.err
	rm -rf ./main.hex
	rm -rf ./main.lst

# cleanup - delete all generated files
clean:	tidy
	rm -rf Release.hex
	rm -rf main.o
