BCCPATH=c:\borland\bcc55

CC=$(BCCPATH)\bin\bcc32
OPT=-O2 -5 -d -ff -k- -OS -Q -X
MODEL=-W -WM
CFLAGS=-I$(BCCPATH)\include -I../lib $(OPT) $(MODEL)
LDFLAGS=-L$(BCCPATH)\lib -L$(BCCPATH)\lib\psdk -W -WM -M

moac.exe:	Makefile gui.obj client.obj skill.obj dd.obj font.obj gfx.obj main.obj sprite.obj game.obj neuquant.obj resource.res edit.obj edit_tool.obj sound.obj questlog.obj
		$(BCCPATH)\bin\ilink32 /aa -L$(BCCPATH)\lib -L$(BCCPATH)\lib\psdk $(BCCPATH)\lib\c0w32.obj gui.obj client.obj skill.obj dd.obj neuquant.obj font.obj gfx.obj main.obj sprite.obj game.obj edit.obj edit_tool.obj sound.obj questlog.obj,moac.exe,,cw32.lib import32.lib ..\lib\zlib.lib ..\lib\libpng.lib ddraw.lib dsound.lib,,resource.res
		copy moac.exe backup.exe

dd.obj:		dd.c main.h dd.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c dd.c
		
gfx.obj:	gfx.c main.h dd.h neuquant.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c gfx.c
		
sprite.obj:	sprite.c main.h sprite.h client.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c sprite.c

gui.obj:	gui.c gui.h main.h dd.h client.h skill.h sprite.h resource.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c gui.c

main.obj:	main.c main.h dd.h client.h resource.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c main.c

font.obj:	font.c dd.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c font.c

client.obj:	client.c main.h client.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c client.c

skill.obj:	skill.c main.h skill.h client.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c skill.c

game.obj:	game.c main.h dd.h client.h sprite.h gui.h spell.h edit.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c game.c

edit.obj:	edit.c main.h dd.h client.h gui.h edit.h edit.h sprite.h resource.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c edit.c

edit_tool.obj:	edit_tool.c main.h edit.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c edit_tool.c

sound.obj:	sound.c main.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c sound.c

questlog.obj:	questlog.c main.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c questlog.c

neuquant.obj:	neuquant.c neuquant.h
		$(BCCPATH)\bin\bcc32 $(CFLAGS) -c neuquant.c

resource.res:	resource.rc
		$(BCCPATH)\bin\brcc32 -fo resource.res resource.rc

clean:	
		del *.obj
		del moac.exe
