** Using du command

1. The du command is usefull for displaying how much space directories and files
take up 
1. Here is an example :
`du --all --human-readable \
--one-file-system \
--max-depth=1 /var`
- --all (-a): Print all files and folders.
- --human-readable (-h): Print sizes in big chunks rather than in bytes 
(for instance, 1K instead of 1024).
- --one-file-system (-x): Skip directories on different filesystems.
The result is that if /var/log is mounted separately, it isn't counted because
it's on a separate filesystem. 
This ensures I see the disk space used under only one directory path and not 
across physical media.
- --max-depth=1 (-d): Print the total for a directory (or file, with --all)
only if it is, in this case, one level below /var. If you use 2 instead, it 
prints folders two levels below /var. Unlike the --one-file-system option,
the size reported remains the same with this option; I just don't have to see
as much output.

- The real magic is how it sorts `du -ahx --max-depth=1 /var | sort -k1 -rh`
- The good news is I can sort the output in any order I want by passing sort
-k1 -rh as input. For example, here's what I get when I run a command to 
sort the output by the first column (capacity)

   #zet #du #linux #Commands


