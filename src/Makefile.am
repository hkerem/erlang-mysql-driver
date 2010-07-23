dist_erl_DATA = \
	mysql.erl \
	mysql_conn.erl \
	mysql_auth.erl \
	mysql_recv.erl

dist_hrl_DATA = \
	mysql.hrl

beam_DATA = \
	$(dist_erl_DATA:.erl=.beam)


erldir = $(ERLANG_INSTALL_LIB_DIR_mysql_driver)/src
hrldir = $(ERLANG_INSTALL_LIB_DIR_mysql_driver)/include
beamdir = $(ERLANG_INSTALL_LIB_DIR_mysql_driver)/ebin
privdir = $(ERLANG_INSTALL_LIB_DIR_mysql_driver)/priv
htmldir = $(ERLANG_INSTALL_LIB_DIR_mysql_driver)/doc
bootdir = $(libdir)/erlang/bin
CLEANFILES = $(beam_DATA)
ERLCFLAGS += -W

$(beam_DATA): $(dist_hrl_DATA)

.erl.beam:
	@echo "Compiling $<..."
	@$(ERLC) $(ERLCFLAGS) $<

console:
	@echo "Running application..."
	@$(ERL) -boot start_sasl -sname console-$$$$ 
