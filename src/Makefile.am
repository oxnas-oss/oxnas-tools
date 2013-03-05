bin_SCRIPTS = mkoxnasblob.sh setupoxnasmbr.sh
CLEANFILES = $(bin_SCRIPTS)

install-exec-hook:
	cd $(DESTDIR)$(bindir) && \
		$(LN_S) mkoxnasblob.sh $(DESTDIR)$(bindir)/mkoxnasblob$(EXEEXT) && \
		$(LN_S) setupoxnasmbr.sh $(DESTDIR)$(bindir)/setupoxnasmbr$(EXEEXT)

uninstall-hook:
	rm -f $(DESTDIR)$(bindir)/mkoxnasblob$(EXEEXT)
	rm -f $(DESTDIR)$(bindir)/setupoxnasmbr$(EXEEXT)
