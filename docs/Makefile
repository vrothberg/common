PREFIX := /usr/local
DATADIR := ${PREFIX}/share
MANDIR := $(DATADIR)/man
GOMD2MAN ?= $(shell command -v go-md2man || echo '$(GOBIN)/go-md2man')

docs: $(patsubst %.md,%.1,$(wildcard *.md))

%.1: %.md
	$(GOMD2MAN) -in $^ -out $@

.PHONY: install
install:
	install -d ${DESTDIR}/${MANDIR}/man1
	install -m 0644 common*.1 ${DESTDIR}/${MANDIR}/man1

.PHONY: clean
clean:
	$(RM) common*.1