ETC_FILES = cgroup.release_common.example init.d.slurmdbd init.d.slurm \
	    slurmctld.service slurmdbd.service slurmd.service

CLEANFILES = $(ETC_FILES)

edit = sed \
        -e 's|@bindir[@]|$(bindir)|g' \
        -e 's|@libdir[@]|$(libdir)|g' \
        -e 's|@sbindir[@]|$(sbindir)|g' \
        -e 's|@sysconfdir[@]|$(sysconfdir)|g' \
	-e 's|@BLUEGENE_LOADED_FALSE[@]|$(BLUEGENE_LOADED_FALSE)|g'

noinst_DATA = $(ETC_FILES)

cgroup.release_common.example: Makefile $(srcdir)/cgroup.release_common.example.in
	$(edit) $(srcdir)/cgroup.release_common.example.in > cgroup.release_common.example

init.d.slurmdbd: Makefile $(srcdir)/init.d.slurmdbd.in
	$(edit) $(srcdir)/init.d.slurmdbd.in > init.d.slurmdbd

init.d.slurm: Makefile $(srcdir)/init.d.slurm.in
	$(edit) $(srcdir)/init.d.slurm.in > init.d.slurm

slurmctld.service: Makefile $(srcdir)/slurmctld.service.in
	$(edit) $(srcdir)/slurmctld.service.in > slurmctld.service

slurmdbd.service: Makefile $(srcdir)/slurmdbd.service.in
	$(edit) $(srcdir)/slurmdbd.service.in > slurmdbd.service

slurmd.service: Makefile $(srcdir)/slurmd.service.in
	$(edit) $(srcdir)/slurmd.service.in > slurmd.service
