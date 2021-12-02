###############################################################################
# Makefile for project 
###############################################################################

## General options
PROJECT = 
MCU = PIC12F675
COMPILER = "MPASM (Proteus)"
TARGET = Debug
SHELL = C:\Windows\system32\cmd.exe

## Tools general options
ASMFLAGS=/q+ /p12f675
LDFLAGS=/x /p12f675

## Processing Tools
ASM=MPASMWIN.exe
LD=mplink.exe
LIB=mplib.exe
#  C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab06/PIC12F675__/Debug/Debug.cof: TOOL=LD
#     C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab06/PIC12F675__/Debug/main.o: TOOL=ASM
#        C:/Users/Mihai/Documents/BMSTU/7 semester/ASVT/Labs/All Labs/Lab06/PIC12F675__/main.asm

# Build tree:
all:	Debug

Debug:	Debug.cof

Debug.cof:	main.o 
	$(LD) $(LDFLAGS) /o "./Debug.cof" 12f675_g.lkr "main.o"

main.o:	../main.asm 
	$(ASM) /e"./main.err" /l"./main.lst" /o"main.o" $(ASMFLAGS)  "..\main.asm"

# tidy - delete all temporary files which are not involved in the target generation
tidy:
	rm -rf ./main.err
	rm -rf ./main.hex
	rm -rf ./main.lst

# cleanup - delete all generated files
clean:	tidy
	rm -rf Debug.cof
	rm -rf main.o
