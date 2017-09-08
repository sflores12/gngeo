#INCLUDES = -DDATA_DIRECTORY='"${pkgdatadir}"'
AM_CPPFLAGS = -DDATA_DIRECTORY=\"$(pkgdatadir)\"

SUBDIRS = effect blitter ym2610 $(m68k_subdir) $(z80_subdir) $(gui_subdir)

bin_PROGRAMS = gngeo
gngeo_SOURCES = pd4990a.c		gngeo_icon.h		list.c		\
		sound.h			video.c			profiler.c	\
		main.c			pd4990a.h		video.h		\
		memory.c		profiler.h		list.h		\
		blitter.h		font.h			memory.h	\
		timer.c			effect.h		frame_skip.c	\
		screen.c		timer.h			emu.c		\
		messages.h		screen.h		unzip.h		\
		neocrypt.c		sound.c			unzip.c		\
		debug.c			debug.h			neocrypt.h	\
		state.h			video_template.h	conf.c		\
		transpack.h		transpack.c             resfile.c	\
		menu.c			menu.h           	messages.c	\
		roms.h			roms.c			mame_layer.h	\
		frame_skip.h		emu.h			resfile.h	\
		state.c			conf.h			event.c		\
		stb_zlib.h		mame_layer.c		neoboot.c	\
		stb_zlib.c		stb_image.c		stb_image.h

# Platform dependant source and lib
if USE_STARSCREAM
m68k_subdir = star
m68k_lib = star/libstar.a
gngeo_SOURCES += star_interf.c
endif
if USE_GENERATOR68K
m68k_subdir = generator68k
m68k_lib = generator68k/libgenerator68k.a
gngeo_SOURCES += generator68k_interf.c
endif
if USE_CYCLONE
m68k_subdir = cyclone
m68k_lib = cyclone/libcyclone.a
gngeo_SOURCES += cyclone_interf.c
endif
if USE_RAZE
z80_subdir = raze
z80_lib = raze/libraze.a
gngeo_SOURCES += raze_interf.c
endif
if USE_MAMEZ80
z80_subdir = mamez80
z80_lib = mamez80/libmamez80.a
gngeo_SOURCES += mamez80_interf.c
endif
if USE_DRZ80
z80_subdir = drz80
z80_lib = drz80/libdrz80.a
gngeo_SOURCES += drz80_interf.c
endif

if PROCESSOR_ARM
gngeo_SOURCES += video_arm.s memcpy.S
endif
if USE_GP2X
gngeo_SOURCES += gp2x.h gp2x.c
endif
if HAVE_NASM
asm_lib = screen_i386.o video_i386.o
endif

EXTRA_DIST = c32.mac screen_i386.asm video_i386.asm video_i386.inc getopt.h

if USE_GP2X
gngeo_LDADD = blitter/libblitter.a $(m68k_lib)
else
gngeo_LDADD = effect/libeffect.a blitter/libblitter.a ym2610/libym2610.a $(m68k_lib) $(z80_lib) $(asm_lib)
endif

video_i386.o : video_i386.inc
video_i386.o screen_i386.o : %.o: %.asm
	nasm -f elf -I $(srcdir)/ $<  -o $@ 
