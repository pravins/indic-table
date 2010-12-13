SCIM_TABLES_DIR=/usr/share/scim/tables
SCIM_ICONS_DIR=/usr/share/scim/icons

SRC_DIR=./src
BIN_DIR=./bin
ICON_DIR=./icons

SCIM_MAKE_TABLE=scim-make-table

compile: compile-marathi-trans

compile-marathi-trans: $(BIN_DIR)/marathi-trans.bin

install:	compile-marathi-trans
	cp	$(BIN_DIR)/marathi-trans.bin	$(SCIM_TABLES_DIR)
	cp	$(ICON_DIR)/mr-inscript.png	$(SCIM_ICONS_DIR)

uninstall:
	rm	$(SCIM_TABLES_DIR)/marathi-trans.bin
	rm	$(SCIM_ICONS_DIR)/mr-inscript.png

clean:
	rm	-f	$(BIN_DIR)/*

$(BIN_DIR)/marathi-trans.bin: $(SRC_DIR)/marathi-trans.txt.in
	sed -e \\'s,@SCIM_ICONDIR@,$(SCIM_ICONS_DIR),g\\' $(SRC_DIR)/marathi-trans.txt.in	> $(BIN_DIR)/marathi-trans.txt
	$(SCIM_MAKE_TABLE) $(BIN_DIR)/marathi-trans.txt -b -o $(BIN_DIR)/marathi-trans.bin
	rm $(BIN_DIR)/marathi-trans.txt
