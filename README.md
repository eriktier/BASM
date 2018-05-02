# BASM
Inline Basic Z80 assembler for CPC464 and later home computers

This is a reproduction (from 30+ old memory) of the first z80 'assembler', I've ever used (when I was somewhere between 12-14 years old).
Somewhere during that time I found the basic code for the assembler in some magazine. It allowed the assembler code to be written in the first 9999 lines of the basic program behind "rem" (comments) statements. The assembler itself started at line 10000 (or so) and it would read (using peek statements) the comments from line 10 up to 9999, parse the asm code, generate the opcodes, poke them into memory from the address specified by an 'org' statement and then call that address.
This would run the assembled machine code and thus run your program. This allowed full use of the basic editor of the CPC464 (or newer), which alleviated the need for writing a full editor (though things like syntax highlighting were missing of course).
I always loved the ingeniuity of this solution. It made it very easy to start writing z80 assembler and it also made it fully transparent how z80 assembler code could actually be parsed and turned into machine language opcodes.
Most importantly, it meant that I didn't have to calculate the opcodes by hand (or better my first programers calculator) and poke them into memory myself.
As the assembler code was pretty basic, I extended it to make it easier to work with.
But all that is a loooooong time ago.
As a personal hobby project I decided that I'd try to reconstruct this tool using a cpc464 emulator (winape and arnold). It is very interesting to be forced to deal with the extreme (by modern standards) primitiveness of the programming experience of coding in Locomotive basic on that old 8bit machine. At the same time, this is what makes it a lot of fun.
Anyway, my plan is to complete BASM and to then write a simple game using it ;).