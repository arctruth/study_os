# デフォルト
default :
	../../z_tools/make.exe img

# ファイル生成規則
ipl.bin : ipl.nas Makefile
	../../z_tools/nask.exe ipl.nas ipl.bin ipl.lst

helloos.img : ipl.bin Makefile
	type ipl.bin > helloos.img

# コマンド
asm :
	../../z_tools/make.exe -r ipl.bin

img :
	../../z_tools/make.exe -r helloos.img

run :
	../../z_tools/make.exe img
	../../qemu/qemu-system-i386 -fda helloos.img

clean :
	-del ipl.bin
	-del ipl.lst

src_only :
	../../z_tools/make.exe clean
	-del helloos.img