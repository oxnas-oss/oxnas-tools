bin_SCRIPTS = mkoxnasblob.sh
CLEANFILES = $(bin_SCRIPTS)

install-exec-hook:
	cd $(DESTDIR)$(bindir) && \
		$(LN_S) mkoxnasblob.sh $(DESTDIR)$(bindir)/mkoxnasblob$(EXEEXT)

uninstall-hook:
	rm -f $(DESTDIR)$(bindir)/mkoxnasblob$(EXEEXT)
