# crsync

Configuration-based RSYNC Script

***crsync*** is wapper around *rsync* to use config files specified in directories
to set the parameters and options of an *rsync* invocation.

## Syncing a Project Directory:
A project should contain an crsync config in its top level directory.  The
directory containing the config file is considered the root of the directory
tree to be synced.  Invoking ***crsync*** from any subdirectory of the project
will sync the entire project
