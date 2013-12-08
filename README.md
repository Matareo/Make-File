# This programs is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.

# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.

# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.

CFLAGS = -Wall -ansi -pedantic

all : test1 test2 test3 test4 test5

clean :
	@rm -f *~ zad-1 zad-2 zad-3 zad-4 zad-5 *.ps

autor :
	@echo "##########################################"
	@echo "#                                        #"
	@echo "# Autorem programow jest Andrzej Bistram #"
	@echo "#                                        #"
	@echo "##########################################"
help :
	@echo ""
	@echo "Dostepne opcje: all, clean, autor,"
	@echo "  zad1, zad2, zad3, zad4, zad5, sito,"
	@echo "  test1, test2, test3, test4, test5"
	@echo ""

zad1 : zad-1.c
	@gcc $(CFLAGS) -o zad-1 zad-1.c
zad2 : zad-2.c
	@gcc $(CFLAGS) -o zad-2 zad-2.c
zad3 : zad-3.c
	@gcc $(CFLAGS) -o zad-3 zad-3.c
zad4 : zad-4.c
	@gcc $(CFLAGS) -o zad-4 zad-4.c
zad5 : zad-5.c
	@gcc $(CFLAGS) -o zad-5 zad-5.c

test1 : zad1
	@echo ""
	@echo "Zadanie 1."
	@cat zad-1.txt
	@echo ""
	@./zad-1 
test2 : zad2
	@echo ""
	@echo "Zadanie 2."
	@cat zad-2.txt
#	@echo "Make: ***[test2] Uruchomic recznie."
	@./zad-2 < zad-2.test
test3 : zad3
	@echo ""
	@echo "Zadanie 3."
	@cat zad-3.txt
	@echo ""
#	@./zad-3
	@./zad-3 < zad-3.test
test4 : zad4
	@echo ""
	@echo "Zadanie 4."
	@cat zad-4.txt
	@echo ""
#	@./zad-4
	@./zad-4 < zad-4.test
test5 : zad5
	@echo ""
	@echo "Zadanie 5."
	@cat zad-5.txt
	@echo ""
	@./zad-5 < zad-5.test
