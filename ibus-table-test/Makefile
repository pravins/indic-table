IBUS_TABLES_DIR=/usr/share/ibus-table/tables
IBUS_ICONS_DIR=/usr/share/ibus-table/icons


IBUS_MAKE_TABLE=ibus-table-createdb

compile: compile-marathi-trans

compile-marathi-trans: marathi-trans.db

install:	compile-marathi-trans
	cp	marathi-trans.db	$(IBUS_TABLES_DIR)
	cp	mr-inscript.png	$(IBUS_ICONS_DIR)

uninstall:
	rm	$(IBUS_TABLES_DIR)/marathi-trans.db
	rm	$(IBUS_ICONS_DIR)/mr-inscript.png

clean:
	rm	-f	marathi-trans.db

marathi-trans.db: 
	$(IBUS_MAKE_TABLE) -s marathi-trans.txt -n marathi-trans.db
