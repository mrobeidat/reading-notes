
# Regular Expression (regex)
A special sequence of characters that helps you match or find other strings or sets of strings, using a specialized syntax held in a pattern.
The Python module re provides full support for Perl-like regular expressions in Python

+  match function 
This function attempts to match RE pattern to string with optional flags.

`re.match(pattern, string, flags=0)`

+ search function
This function searches for first occurrence of RE pattern within string with optional flags.

`re.search(pattern, string, flags=0) `

+ Matching Versus Searching


+ Search and Replace
One of the most important re methods that use regular expressions is sub.

`re.sub(pattern, repl, string, max=0)`

## Automation
Automation is the creation and application of technologies to produce and deliver goods and services with minimal human intervention. The implementation of automation technologies, techniques and processes improve the efficiency, reliability, and/or speed of many tasks that were previously performed by humans.


### shutil
Purpose:	High-level file operations.

The shutil module includes high-level file operations such as copying and archiving.
Copying Files

copyfile() copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.

The implementation of copyfile() uses the lower-level function copyfileobj(). While the arguments to copyfile() are filenames, the arguments to copyfileobj() are open file handles. The optional third argument is a buffer length to use for reading in blocks.

The copy() function interprets the output name like the Unix command line tool cp. If the named destination refers to a directory instead of a file, a new file is created in the directory using the base name of the source.

Copying File Metadata

By default when a new file is created under Unix, it receives permissions based on the umask of the current user. To copy the permissions from one file to another, use copymode().

BEFORE: 0o100444
AFTER : 0o100644

Finding Files

The which() function scans a search path looking for a named file. The typical use case is to find an executable program on the shell’s search path defined in the environment variable PATH.

Archives

Python’s standard library includes many modules for managing archive files such as tarfile and zipfile. There are also several higher-level functions for creating and extracting archives in shutil. get_archive_formats() returns a sequence of names and descriptions for formats supported on the current system.

File System Space

It can be useful to examine the local file system to see how much space is available before performing a long running operation that may exhaust that space. disk_usage() returns a tuple with the total space, the amount currently being used, and the amount remaining free.
