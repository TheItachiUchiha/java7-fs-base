## Read me first

This project is licensed under both LGPLv3 and ASL 2.0. See file LICENSE for
more details.

## What this is

This is a package designed to ease the creation of custom Java 7
[`FileSystem`](https://docs.oracle.com/javase/7/docs/api/java/nio/file/FileSystem.html)s.

## And what is a "Java 7 `FileSystem`" anyway?

More generally, we are talking here about the [`java.nio.file`
API](http://docs.oracle.com/javase/8/docs/api/java/nio/file/package-frame.html) which made its
appearance in Java 7.

A `FileSystem` can be, in theory, written for anything which has a filesystem-like structure or for
which you can emulate one; the JRE of course provides it for the native filesystems of the platform
you are running the JRE on, but it also provides a `FileSystem` view for ZIP files -- yes, that's
right, you can view a ZIP file (therefore also jars) as `FileSystem`s and copy from/to them, etc.

Other examples of existing, third party filesystems are:

* [a `FileSystem` over FTP](https://github.com/fge/java7-fs-ftp) (by yours truly);
* [an in-memory `FileSystem`](https://github.com/google/jimfs) (by Google).
* [a `FileSystem` over DropBox](https://github.com/fge/java7-fs-dropbox) (by yours truly);


## So, why this package?

Well, the API is quite a beast; if you want to program a `FileSystem` from scratch, you're setting
yourself a very, very big task. Just look [how many methods are defined by
`Path`](http://docs.oracle.com/javase/8/docs/api/java/nio/file/Path.html), for instance -- and
that's only the "user level" view of the API.

This package therefore brings facilities to allow you to develop custom file systems in a much
easier way; see [the wiki](https://github.com/fge/java7-fs-base/wiki) for more information.

**THIS IS STILL A WORK IN PROGRESS**. The real test will be when I write an actual implementation
over this package ;) Javadoc is not online yet etc. All of this is in the plans, however.

## NOTE: JDK/JRE restrictions

You **must** use either the JDK provided by Oracle or OpenJDK for compilation, and an Oracle/OpenJDK
JRE to run. At this moment, this package depends on a package in... `sun.nio.fs`. More precisely, it
depends on it for generating patterns suitable for use in a glob
[`PathMatcher`](https://docs.oracle.com/javase/7/docs/api/java/nio/file/PathMatcher.html).

