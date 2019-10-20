CC = gcc
LD = gcc
TARGET = libcups.so
SYMLINK = libcups.so.2


.PHONY: default clean install uninstall reinstall

default: $(TARGET)

clean:
	rm $(TARGET)

install:
	test -e "/usr/lib/$(TARGET)" && exit 1 || true;
	cp $(TARGET) "/usr/lib/$(TARGET)";
	ln -s $(TARGET) "/usr/lib/$(SYMLINK)";

uninstall:
	rm -f "/usr/lib/$(TARGET)" "/usr/lib/$(SYMLINK)";

reinstall: uninstall install



$(TARGET): source.c
	gcc -o $@ -shared $^
