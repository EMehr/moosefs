chunkserver_mans = mfschunkserver.8 mfschunktool.8 mfschunkdbdump.8 mfscsstatsdump.8 mfschunkserver.cfg.5 mfshdd.cfg.5
master_mans = mfsmaster.8 mfsmetarestore.8 mfsstatsdump.8 mfsmetadump.8 mfsmetadirinfo.8 mfsmetasearch.8 mfsmaster.cfg.5 mfsexports.cfg.5 mfstopology.cfg.5 mfsipmap.cfg.5 mfssupervisor.8 moosefs.7
gui_mans = mfsgui.8 mfsgui.cfg.5
cli_mans = mfscli.1
metalogger_mans = mfsmetalogger.8 mfsmetalogger.cfg.5
netdump_mans = mfsnetdump.8
mount_mans = mfsmount.8 mfsmount.cfg.5
mount_extra_man = mount.moosefs.8
bdev_mans = mfsbdev.8 mfsbdev.cfg.5
tools_mans = \
	mfstools.1 mfsgoal.1 mfssclass.1 mfstrashtime.1 mfstrashretention.1 \
	mfseattr.1 mfsfacl.1 mfsquota.1 mfssnapshots.1 mfsdiagtools.1 mfsscadmin.1 mfspatadmin.1 mfsarchive.1 \
	mfscheckfile.1 mfsdirinfo.1 mfsfileinfo.1 mfsfilerepair.1 mfsfilepaths.1 \
	mfsgetgoal.1 mfssetgoal.1 mfscopygoal.1 \
	mfsgettrashtime.1 mfssettrashtime.1 mfscopytrashtime.1 \
	mfsgettrashretention.1 mfssettrashretention.1 mfscopytrashretention.1 \
	mfsgetfacl.1 mfssetfacl.1 \
	mfssetsclass.1 mfsgetsclass.1 mfscopysclass.1 mfsxchgsclass.1 \
	mfscreatesclass.1 mfsmodifysclass.1 mfsdeletesclass.1 mfsclonesclass.1 mfsrenamesclass.1 mfsimportsclass.1 mfslistsclass.1 \
	mfscreatepattern.1 mfsdeletepattern.1 mfslistpattern.1 \
	mfsgeteattr.1 mfsseteattr.1 mfsdeleattr.1 mfscopyeattr.1 \
	mfsgetquota.1 mfssetquota.1 mfsdelquota.1 mfscopyquota.1 \
	mfschkarchive.1 mfsclrarchive.1 mfssetarchive.1 \
	mfsappendchunks.1 mfsmakesnapshot.1 mfsrmsnapshot.1
#	mfstrashtools.1 mfstrashlist.1 mfstrashrecover.1 mfstrashpurge.1 mfssustainedlist.1
pro_mans = $(supervisor_mans) $(tools_pro_mans)

all_mans = $(chunkserver_mans) $(master_mans) $(gui_mans) $(cli_mans) $(mount_mans) $(tools_mans) $(metalogger_mans) $(netdump_mans) $(mount_extra_man) $(bdev_mans) 

EXTRA_DIST = $(all_mans)

man_MANS =

if BUILD_MASTER
man_MANS += $(master_mans)
endif

if BUILD_CHUNKSERVER
man_MANS += $(chunkserver_mans)
endif

if BUILD_GUI
man_MANS += $(gui_mans)
endif

if BUILD_CLIENT
man_MANS += $(tools_mans)
if WITH_MOUNT
man_MANS += $(mount_mans)
endif
if INSTALL_MOOSEFS_MOUNT
man_MANS += $(mount_extra_man)
endif
if WITH_BDEV
man_MANS += $(bdev_mans)
endif
endif

if BUILD_METALOGGER
man_MANS += $(metalogger_mans)
endif

if BUILD_NETDUMP
man_MANS += $(netdump_mans)
endif

if INSTALL_CLI
man_MANS += $(cli_mans)
endif

man-html: $(all_mans)
	$(MKDIR_P) html
	for f in $(all_mans) ; do \
		man2html -r $$f | tail -n +3 > html/$${f}.html ; \
	done
