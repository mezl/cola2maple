# ------------------------------------------------------- #
#  util/tran/Makefile	( NTHU CS MapleBBS Ver 3.10 )	  #
# ------------------------------------------------------- #
#  target : Makefile for 寄信、統計、備份、系統維護工具	  #
#  create : 01/03/02				 	  #
#  update :   /  /  				 	  #
# ------------------------------------------------------- #


# ------------------------------------------------------ #
# 下列的 make rules 不需修改				 #
# ------------------------------------------------------ #


EXE =	brd2gem transacct transbrd \
	ats2bmw ats2brd ats2gem ats2mf ats2pal ats2usr \
	cola2brd cola2gem cola2post cola2usr \
	fb2brd fb2gem fb2pal fb2usr \
	mag2brd mag2gem mag2usr \
	snap2usr snap2brd \
	sob2brd sob2gem sob2pal sob2usr \
	wd2bmw wd2brd wd2gem wd2list wd2mf wd2pal wd2pip wd2usr \
	windtop2brd windtop2mf windtop2pip windtop2usr
CLA =	brd2gem transacct transbrd \
	cola2brd cola2gem cola2post cola2usr \
	
all: 
	@echo "Please enter 'make sys-type', "
	@echo " make cola: for cola Linux"
	@echo " make sun     : for Sun-OS 4.x and maybe some BSD systems, cc or gcc" 
	@echo " make linux   : for Linux"
	@echo " make solaris : for Sun-OS 5.x gcc" 
	@echo " make sol-x86 : for Solaris 7 x86"
	@echo " make freebsd : for BSD 4.4 systems" 
	@echo " make bsd     : for BSD systems, cc or gcc, if not in the above lists" 
	@echo " make cygwin  : for Microsoft Windows and Cygwin gcc"

sun:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -fomit-frame-pointer -Wunused -I../../include" LDFLAGS="-s -L../../lib -ldao" $(EXE)

linux:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao" $(EXE)

cola:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao" $(CLA)
solaris:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao -lsocket -lnsl -L/usr/ucblib -lucb" $(EXE)

sol-x86:
	@$(MAKE) CC=gcc CFLAGS="-O2 -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao -lsocket -lnsl" $(EXE)

freebsd:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao" $(EXE)

bsd:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao" $(EXE)

cygwin:
	@$(MAKE) CC=gcc CFLAGS="-O2 -pipe -I../../include -fomit-frame-pointer -Wunused" LDFLAGS="-s -L../../lib -ldao" $(EXE)


.c:	;  $(CC) -o $@ $@.c $(CFLAGS) $(LDFLAGS)


install: $(EXE)
# 不複製到 bin/ 下
#	install -m 0700 $? $(HOME)/bin
	@echo "ok!"

clean:
	rm -f $(EXE) *.exe *.o *~
