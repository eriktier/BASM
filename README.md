# BASM
Inline Basic Z80 assembler for CPC464 and later home computers

This is a reproduction (from 30+ old memory) of the first z80 'assembler' that I've ever used (when I was somewhere between 12-14 years old).

Somewhere during that time, I found the basic code for the assembler in some magazine (and had to type it all in manually). It allowed the assembler code to be written in the first 9999 lines of the basic program behind "rem" (or "'") statements (comments). The assembler itself started at line 10000 (or so) and it would read (using peek statements) the comments from line 0 up to 9999, parse the asm code, generate the opcodes, poke them into memory from the address specified by an 'org' statement and then call that address.

This would run the assembled machine code. This allowed full use of the basic editor of the CPC464 (or newer), which alleviated the need for writing a full editor (though things like syntax highlighting were missing of course).

I always loved the ingeniuity of this solution. It made it very easy to start writing z80 assembler code and it also made it fully transparent how z80 assembler code could actually be parsed and turned into machine language opcodes.

Most importantly, it meant that I didn't have to calculate the opcodes by hand (actually using my first programmers calculator) and poke them into memory myself. As the assembler code was pretty basic, I extended it to make it easier to work with.

But all that is a loooooong time ago.

As a personal hobby project I decided that I'd try to reconstruct this tool, using a cpc464 emulator (winape and arnold). It is very interesting to be forced to deal with the extreme (by modern standards) primitiveness of the programming experience of coding in Locomotive Basic on that old 8bit machine. At the same time, this is what makes it a lot of fun.

Anyway, my plan is to complete BASM and to then write a simple game using it ;).

## Output of current version

The current version is able to parse and generate opcodes for the following kind of 'ld' instructions:
<pre>
10 ' org &8100
20 ' label: ld   a , l 
30 ' ld a,ixh
40 ' ld ixh,a
50 ' ld ixh, ixl
60 ' ld ixl,ixh
70 ' ld iyh,iyl
80 ' ld iyl,iyh
90 ' ld a, 100
100 ' ld a,(hl)
1000 ' ld x,(xy)
</pre>
The resulting output (currently just pretty printing):

![screenshot](https://user-images.githubusercontent.com/796635/39574287-800c5012-4ece-11e8-9302-b8b6ead3ab96.png)

And the machine code in memory:

![screenshot](https://user-images.githubusercontent.com/796635/39574275-734324dc-4ece-11e8-9918-98d7b6eb835f.png)

## First test case

BASM now succesfully assembles and runs the first code example from: http://www.chibiakumas.com/z80/.

![screenshot](https://user-images.githubusercontent.com/796635/39595755-42b755f6-4f08-11e8-9e71-00609f55870d.png)

## How to run

First you need to download winape: http://www.winape.net.

Clone this repo, run winape and open BASM.atp through: File/Auto type...

Once the Auto type window shows the file, click ok and it will 'type' the full code and run it using the built-in test asm.

You can open the tests by opening them in Autotype. They will overwrite the asm code in the first lines. Then just type run to run the assembler and the assembled code.
