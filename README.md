# crsync

Configuration-based RSYNC Script

***`crsync`*** is wrapper around *`rsync`* to use config files specified in
directories to set the parameters and options of an *`rsync`* invocation.

## Syncing a Project Directory:
A project should contain an crsync config (`.crsync`) file in its top-level
directory.  The directory containing the config file is considered the root of
the directory tree to be synced.  Invoking ***`crsync`*** from any subdirectory
of the project will sync the entire project

## Config File
The config file should be named `.crsync` and include a definition for the
variable `DEST` which defines the sync target destination server.  For example:
```
DEST=user@example.com
```

By default, the destination folder name is set to the root project directory
name. However, the destination folder name can be overridden by setting the
`DEST_DIR` variable.  For example:
```
DEST_DIR=MyRemoteProjDir
```

## Ignoring (Excluding) Files from the Sync
A `.crsyncignore` file can also be created and placed in the same directory as
the config file.  This file will be passed to *`rsync`* as an argument to the
`--exclude-from` flag.
