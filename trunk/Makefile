VERSION=0.4.0
NAME=svncl

FILES=ChangeLog gpl-3.0.txt Makefile README sample.svnclrc svncl.pl

.PHONY: install dist test clean

install:
	install svncl.pl /usr/local/bin

dist:
	rm -rf $(NAME)-$(VERSION)
	mkdir -p $(NAME)-$(VERSION)
	cp -av $(FILES) $(NAME)-$(VERSION)
	tar cvzf $(NAME)-$(VERSION).tar.gz $(NAME)-$(VERSION)

log.xml:
	svn log -v --xml > $@

test: log.xml
	./svncl.pl $^

clean:
	rm -rf *~ $(NAME)-$(VERSION) $(NAME)-$(VERSION).tar.gz
