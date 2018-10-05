---
Linux Commands
---


#### *Navigation and Directory Control Commands*

`mkdir`
        
		Create the DIRECTORY(ies), if they do not already exist.
		Usage: mkdir DirectoryName

		Arguments:
		-m, --mode=MODE			Set file mode (as in chmod), not a=rwx - umask
		-p, --parents					 No error if existing, make parent directories as needed
		-v, --verbose             	     Print a message for each created directory
</br>

`ls`

		ls command lists the directory content
		Usage: ls argument(s)

        Arguments:
        -a, --all								Display all files including idden files
        -d, --directory                 	List directories themselves, not their contents
        -i, --inode							  Print the index number of each file
        -k, --kibibytes            			Default to 1024-byte blocks for disk usage
        -h, --human-readable 		With -l and/or -s, print human readable sizes
        -l 										  Use a long listing format
        -n, --numeric-uid-gid      	   Like -l, but list numeric user and group IDs
        -r, --reverse                   	Reverse order while sorting
        -t                                    	 Sort by modification time, newest first
 </br>
  
  
`cd`

	 	cd command change the shell working directory
		Usage: cd .. / cd directoryname

      	Arguments:
		cd ..              	It will move to the parent directory
		cd ../../..			It will move to the third parent directory
		cd ~               It will move to the home directory

 </br> 

`pwd`

	 	pwd (print working directory) command displays the current working directory
		Usage: pwd

</br> 

`rmdir`

	 	rmdir command removes the directory(ies), if they are empty 
		Usage: rmdir directryname

      	Arguments:
		p, --parents   	Remove DIRECTORY and its ancestors</br>
		-v, --verbose  	Output a diagnostic for every directory processed </br>

 </br> 

#### *File Maintenance Commands*

`touch`

	 	Update the access and modification times of each FILE to the current time.
		A FILE argument that does not exist is created empty, unless -c or –h is supplied.
		A FILE argument string of - is handled specially and causes touch to change the times of the file associated with standard output.
		
        Usage: touch filename

      	Arguments:
		-a	                     	    Change only the access time
		-c, --no-create	      	  Do not create any files
  		-d, --date=STRING 	Parse STRING and use it instead of current time
  		-f                     			(ignored)
  		-h, --no-dereference   	Affect each symbolic link instead of any referenced file (useful only on systems that can change the timestamps of a symlink)
  		-m                    		Change only the modification time
  		-r, --reference=FILE   	Use this file's times instead of current time
  		-t STAMP               	Use [[CC]YY]MMDDhhmm[.ss] instead of current time
  		--time=WORD        	Change the specified time:
        			                   WORD is access, a time, or use: equivalent to -a
                    			       WORD is modify or mtime: equivalent to -m

 </br>

`find`

		find command can be used to find files and directories and perform subsequent operations on them. It supports searching by file, folder, name, creation date, modification date, owner 			and permissions
		Usage: find [-H] [-L] [-P] [-Olevel] [-D help|tree|search|stat|rates|opt|exec][expression]

      	Arguments:
		Operators (decreasing precedence; -and is implicit where no others are given):
      	( EXPR )   ! EXPR   -not EXPR   EXPR1 -a EXPR2   EXPR1 -and EXPR2
      	EXPR1 -o EXPR2   EXPR1 -or EXPR2   EXPR1 , EXPR2
		
        Positional options (always true): -daystart -follow -regextype
        
		Normal options (always true, specified before other expressions):
 		-depth --help -maxdepth LEVELS -mindepth LEVELS -mount -noleaf
    	--version -xdev -ignore_readdir_race -noignore_readdir_race

		Tests (N can be +N or -N or N): -amin N -anewer FILE -atime N -cmin N
		-cnewer FILE -ctime N -empty -false -fstype TYPE -gid N -group NAME -ilname PATTERN -iname PATTERN -inum N -iwholename PATTERN -iregex PATTERN -links N -lname 						PATTERN -mmin N -mtime N -name PATTERN -newer FILE -nouser -nogroup -path PATTERN -perm [-/]MODE -regex PATTERN -readable -writable –executable -wholename 						PATTERN -size N[bcwkMG] -true -type [bcdpflsD] -uid N     -used N -user NAME -xtype [bcdpfls] -context CONTEXT

		Actions: -delete -print0 -printf FORMAT -fprintf FILE FORMAT -print
		-fprint0 FILE -fprint FILE -ls -fls FILE -prune -quit
		-exec COMMAND ; -exec COMMAND {} + -ok COMMAND ;
		-execdir COMMAND ; -execdir COMMAND {} + -okdir COMMAND ;

 </br>

`locate`

		locate command is used to search for the location of the file or group of files
		Usage: locate arguments
    	
        Arguments:
		locate [-d path | --database=path] [-e | -E | --[non-]existing] [-i | --ignore-case] [-w | --wholename] [-b | --basename]
      	[--limit=N | -l N] [-S | --statistics] [-0 | --null] [-c | --count] [-P | -H | --nofollow] [-L | --follow] [-m | --mmap] [-s | --stdio]
		[-A | --all] [-p | --print] [-r | --regex] [--regextype=TYPE] [--max-database-age D]

`updatedb`

		locate uses a previously built database, If database is not updated then locate command will not show the output. To sync the database it is must to execute updatedb command
		Usage: updated

  </br>

`umask`

		Display or set file mode mask.
		Sets the user file-creation mask to MODE.  If MODE is omitted, prints the current value of the mask.
		If MODE begins with a digit, it is interpreted as an octal number; Otherwise it is a symbolic mode string like that accepted by chmod(1).
		Usage: umask [-p] [-S] [mode]
    	
        Arguments:
		-p        if MODE is omitted, output in a form that may be reused as input
 		-S        makes the output symbolic; otherwise an octal number is output

		Exit Status:
		Returns success unless MODE is invalid or an invalid option is given.
        
        	Root umask value is 				 022
			Normal user umask value is 	    002
			Base permissions for file 			666

 
 </br>
 
`chmod`

		Chmod command is used to change the file permissions
		Usage: chmod filepermissons filename
        Example: chmod 777 filename
        				chmod u+rwx filename
                        chmod ugo+rwx
    	
        Arguments:
		-c, --changes          		like verbose but report only when a change is made
  		-f, --silent, --quiet  		  Suppress most error messages
  		-v, --verbose          		 output a diagnostic for every file processed
      	--no-preserve-root  	 do not treat '/' specially (the default)
      	--preserve-root    			fail to operate recursively on '/'
      	--reference=RFILE  		use RFILE's mode instead of MODE values
  		-R, --recursive        		 change files and directories recursively
 
</br>

`chown`

		Chown command is used to change the ownership of the file
        Only root user can execute this command
        Usage: chown owner filename
        
        Arguments:
		 -c, --changes          	like verbose but report only when a change is made
  		-f, --silent, --quiet  			suppress most error messages
  		-v, --verbose          		output a diagnostic for every file processed
      	--dereference      			affect the referent of each symbolic link (this is the default), rather than the symbolic link itself
  		-h, --no-dereference   	affect symbolic links instead of any referenced file
                         					(useful only on systems that can change the ownership of a symlink)
      	--from=CURRENT_OWNER:CURRENT_GROUP
                        				change the owner and/or group of each file only if its current owner and/or group match those specified here.  Either may be omitted, in which case a match is not 											required for the omitted attribute
      	--no-preserve-root  	do not treat '/' specially (the default)
      	--preserve-root    			fail to operate recursively on '/'
      	--reference=RFILE  		use RFILE's owner and group rather than specifying OWNER:GROUP values
  		-R, --recursive       	operate on files and directories recursively
 
 		Examples:
          chown root /u         Change the owner of /u to "root".
          chown root:staff /u  Likewise, but also change its group to "staff".
          chown -hR root /u   Change the owner of /u and subfiles to "root".

 
</br>

`chgrp`

		chgrp command is used to change the ownership of the group
        Only root user can execute this command
        Usage: chown owner groupname
        
        Arguments:
		 -c, --changes          	like verbose but report only when a change is made
  		-f, --silent, --quiet  			suppress most error messages
  		-v, --verbose          		output a diagnostic for every file processed
      	--dereference      			affect the referent of each symbolic link (this is the default), rather than the symbolic link itself
  		-h, --no-dereference   	affect symbolic links instead of any referenced file
                         					(useful only on systems that can change the ownership of a symlink)
      	--from=CURRENT_OWNER:CURRENT_GROUP
                        				change the owner and/or group of each file only if its current owner and/or group match those specified here.  Either may be omitted, in which case a match is not 											required for the omitted attribute
      	--no-preserve-root  	do not treat '/' specially (the default)
      	--preserve-root    			fail to operate recursively on '/'
      	--reference=RFILE  		 use RFILE's group rather than specifying a GROUP value
  		-R, --recursive       	operate on files and directories recursively
 
 		Examples:
         chgrp staff /u      	Change the group of /u to "staff".
 		 chgrp -hR staff /u  Change the group of /u and subfiles to "staff".

</br>

`cp`

		cp command is used to copy SOURCE to DESTination, or multiple SOURCE(s) to DIRECTORY
        Usage: cp source destination
        
        Arguments:
        -a,    --archive                		   same as -dR --preserve=all
      			--attributes-only        		 don't copy the file data, just the attributes
      			--backup[=CONTROL]     make a backup of each existing destination file
      	-b                           					like --backup but does not accept an argument
      			--copy-contents          	   copy contents of special files when recursive
      	-d                           					same as --no-dereference --preserve=links
      	-f, --force                  				 if an existing destination file cannot be opened, remove it and try again (this option is ignored when the -n option is also used) 
    	-i, --interactive            			   Prompt before overwrite (overrides a previous -n option)
  		-H                           				   follow command-line symbolic links in SOURCE
  		-l, --link                   				   hard link files instead of copying
  		-L, --dereference            		   always follow symbolic links in SOURCE
  		-n, --no-clobber             		    do not overwrite an existing file (overrides a previous -i option)
  		-P, --no-dereference         		 never follow symbolic links in SOURCE
  		-p                           					same as --preserve=mode,ownership,timestamps
      			--preserve[=ATTR_LIST]  preserve the specified attributes (default: mode,ownership,timestamps), if possible additional attributes: context, links, xattr, all
      			--no-preserve=ATTR_LIST  
                										 don't preserve the specified attributes
      			--parents                			use full source file name under DIRECTORY
  		-R, -r, --recursive          			 copy directories recursively
      			--reflink[=WHEN]         	  control clone/CoW copies.
      			--remove-destination     	remove each existing destination file before attempting to open it (contrast with --force)
      			--sparse=WHEN            	control creation of sparse files. See below
      			--strip-trailing-slashes 	   remove any trailing slashes from each SOURCE argument
  		-s, --symbolic-link          			make symbolic links instead of copying
  		-S, --suffix=SUFFIX          		override the usual backup suffix
  		-t, --target-directory=DIRECTORY  
        												copy all SOURCE arguments into DIRECTORY
  		-T, --no-target-directory    		treat DEST as a normal file
  		-u, --update                 			 copy only when the SOURCE file is newer than the destination file or when the destination file is missing
  		-v, --verbose                			explains what is being done
  		-x, --one-file-system        		stays on this file system

</br>

`mv`

		mv command is used to rename SOURCE to DESTination, or move SOURCE(s) to DIRECTORY.
        Usage: mv source destination
        
        Arguments:
      			--backup[=CONTROL]     make a backup of each existing destination file
      	-b                           					like --backup but does not accept an argument
      	-f, --force                  				 if an existing destination file cannot be opened, remove it and try again (this option is ignored when the -n option is also used) 
    	-i, --interactive            			   Prompt before overwrite (overrides a previous -n option)
  		-n, --no-clobber             		    do not overwrite an existing file (overrides a previous -i option)
        If you specify more than one of -i, -f, -n, only the final one takes effect. 
        		--strip-trailing-slashes  remove any trailing slashes from each SOURCE argument
  		-S, --suffix=SUFFIX          		override the usual backup suffix
  		-t, --target-directory=DIRECTORY  
        												copy all SOURCE arguments into DIRECTORY
  		-T, --no-target-directory    		treat DEST as a normal file
  		-u, --update                 			 move only when the SOURCE file is newer than the destination file or when the destination file is missing
  		-v, --verbose                			explains what is being done
  		-x, --one-file-system        		stays on this file system

</br>

`rm`

		rm command is used to remove or unlink the files
        Usage: rm oprtin filename
        
        Arguments:
		-f, --force           	ignore nonexistent files and arguments, never prompt
  		-i                    		prompt before every removal
  		-I                    		prompt once before removing more than three files, or
                          			when removing recursively; less intrusive than -i, while still giving protection against most mistakes
      	--interactive[=WHEN]  
        							prompt according to WHEN: never, once (-I), or always (-i); without WHEN, prompt always
      --one-file-system   when removing a hierarchy recursively, skip any directory that is on a file system different from that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root   	do not remove '/' (default)
 	 -r, -R, --recursive   	remove directories and their contents recursively
 	 -d, --dir             		 remove empty directories
     
     By default, rm does not remove directories.  Use the --recursive (-r or -R) option to remove each listed directory, too, along with all of its contents.
 	To remove a file whose name starts with a '-', for example '-foo', use one of these commands:
  		rm -- -foo
  		rm ./-foo

</br>

`file`

		file command is used to determines type of FILEs
        Usage: file filename
        
        Arguments:
		 -m, --magic-file LIST      use LIST as a colon-separated list of magic number files
  		-z, --uncompress           	try to look inside compressed files
  		-Z, --uncompress-noreport  
        										only print the contents of compressed files
  		-b, --brief                			do not prepend filenames to output lines
  		-c, --checking-printout    	
        										print the parsed form of the magic file, use in conjunction with -m to debug a new magic file before installing it
  		-e, --exclude TEST     		exclude TEST from the list of test to be performed for file. Valid tests are: apptype, ascii, cdf, compress, elf, encoding, soft, tar, text, tokens
  		-f, --files-from FILE      	   read the filenames to be examined from FILE
  		-F, --separator STRING   use string as separator instead of `:'
  		-i, --mime                 		   output MIME type strings (--mime-type and --mime-encoding)
            --apple                				   output the Apple CREATOR/TYPE
            --extension            				output a slash-separated list of extensions
          	--mime-type            			   output the MIME type
      		--mime-encoding        		   output the MIME encoding
  		-k, --keep-going           		don't stop at the first match
  		-l, --list                 				list magic strength
  		-L, --dereference          	   follow symlinks
  		-h, --no-dereference       	don't follow symlinks (default)
  		-n, --no-buffer            		do not buffer output
  		-N, --no-pad               		do not pad output
  		-0, --print0               			terminate filenames with ASCII NUL
  		-p, --preserve-date        	preserve access times on files
  		-P, --parameter            	set file engine parameter limits
                               indir        	15 recursion limit for indirection
                               name         30 use limit for name/use magic
                               elf_notes   256 max ELF notes processed
                               elf_phnum 128 max ELF prog sections processed
                               elf_shnum 32768 max ELF sections processed
  		-r, --raw                  			don't translate unprintable chars to \ooo
  		-s, --special-files        		treat special (block/char devices) files as ordinary ones
  		-C, --compile              		compile file specified by -m
  		-d, --debug                		print debugging messages

</br>  

`wc

		Print newline, word, and byte counts for each FILE, and a total line if more than one FILE is specified.  A word is a non-zero-length sequence of characters delimited by white space.
		With no FILE, or when FILE is -, read standard input
        Usage: wc argument filename
        
        Arguments:
		-c, --bytes            		print the byte counts
  		-m, --chars            	print the character counts
  		-l, --lines  	          	print the newline counts
      	--files0-from=F 	   read input from the files specified by
        		                   		NUL-terminated names in file F;
                		           		If F is - then read names from standard input
 		-L, --max-line-length  print the maximum display width
  		-w, --words            print the word counts

</br> 

`ln`

		Create hard links by default, symbolic links with --symbolic.
        By default, each destination (name of new link) should not already exist. When creating hard links, each TARGET must exist.  Symbolic links can hold arbitrary text; if later resolved, a 			relative link is interpreted in relation to its parent directory.
        Usage: ln [OPTION]... [-T] TARGET LINK_NAME   	(1st form)
  					or:  ln [OPTION]... TARGET                  		 (2nd form)
                    or:  ln [OPTION]... TARGET... DIRECTORY  (3rd form)
                    or:  ln [OPTION]... -t DIRECTORY TARGET..(4th form)
                    
                    In the 1st form, create a link to TARGET with the name LINK_NAME.
                    In the 2nd form, create a link to TARGET in the current directory.
                    In the 3rd and 4th forms, create links to each TARGET in DIRECTORY.
        
        Arguments:
          			--backup[=CONTROL]      make a backup of each existing destination file
          -b                          like --backup but does not accept an argument
          -d, -F, --directory         allow the superuser to attempt to hard link
                                        directories (note: will probably fail due to
                                        system restrictions, even for the superuser)
          -f, --force                 remove existing destination files
          -i, --interactive           prompt whether to remove destinations
          -L, --logical               dereference TARGETs that are symbolic links
          -n, --no-dereference        treat LINK_NAME as a normal file if
                                        it is a symbolic link to a directory
          -P, --physical              make hard links directly to symbolic links
          -r, --relative              create symbolic links relative to link location
          -s, --symbolic              make symbolic links instead of hard links
          -S, --suffix=SUFFIX         override the usual backup suffix
          -t, --target-directory=DIRECTORY  specify the DIRECTORY in which to create the links
          -T, --no-target-directory   treat LINK_NAME as a normal file always

</br>

`vim`

		vim\vi command is used to open files
        Usage: vim [arguments] [file ..]       edit specified file(s)
                   or: vim [arguments] -               read text from stdin
                   or: vim [arguments] -t tag          edit file where tag is defined
                   or: vim [arguments] -q [errorfile]  edit file with first error

		Arguments:
           --                   Only file names after this
           -v                   Vi mode (like "vi")
           -e                   Ex mode (like "ex")
           -E                   Improved Ex mode
           -s                   Silent (batch) mode (only for "ex")
           -d                   Diff mode (like "vimdiff")
           -y                   Easy mode (like "evim", modeless)
           -R                   Readonly mode (like "view")
           -Z                   Restricted mode (like "rvim")
           -m                   Modifications (writing files) not allowed
           -M                   Modifications in text not allowed
           -b                   Binary mode
           -l                   Lisp mode
           -C                   Compatible with Vi: 'compatible'
           -N                   Not fully Vi compatible: 'nocompatible'
           -V[N][fname]  Be verbose [level N] [log messages to fname]
           -D                   Debugging mode
           -n                   No swap file, use memory only
           -r                   List swap files and exit
           -r (with file name)  Recover crashed session

</br>

`cat`

		Concatenate FILE(s) to standard output. 
        With no FILE, or when FILE is -, read standard input.

        Usage: cat argument file        
        Arguments:
          -A, --show-all           			equivalent to -vET
          -b, --number-nonblank    	number nonempty output lines, overrides -n
          -e                       				 equivalent to -vE
          -E, --show-ends          		display $ at end of each line
          -n, --number             		   number all output lines
          -s, --squeeze-blank      	   suppress repeated empty output lines
          
          Examples:
  			cat f - g  Output f's contents, then standard input, then g's contents.
  			cat        Copy standard input to standard output.


</br>

`grep`

		Search for PATTERN in each FILE or standard input
        Usage: grep [OPTION]... PATTERN [FILE]...
        	
		Arguments:
           -E, --extended-regexp     PATTERN is an extended regular expression (ERE)
          -F, --fixed-strings       PATTERN is a set of newline-separated strings
          -G, --basic-regexp        PATTERN is a basic regular expression (BRE)
          -P, --perl-regexp         PATTERN is a Perl regular expression
          -e, --regexp=PATTERN      use PATTERN for matching
          -f, --file=FILE           obtain PATTERN from FILE
          -i, --ignore-case         ignore case distinctions
          -w, --word-regexp         force PATTERN to match only whole words
          -x, --line-regexp         force PATTERN to match only whole lines
          -z, --null-data           a data line ends in 0 byte, not newline

        Miscellaneous:
          -s, --no-messages         suppress error messages
          -v, --invert-match        select non-matching lines
          -V, --version             display version information and exit
              --help                display this help text and exit

        Output control:
          -m, --max-count=NUM       stop after NUM matches
          -b, --byte-offset         print the byte offset with output lines
          -n, --line-number         print line number with output lines
              --line-buffered       flush output on every line
          -H, --with-filename       print the file name for each match
          -h, --no-filename         suppress the file name prefix on output
              --label=LABEL         use LABEL as the standard input file name prefix
          -o, --only-matching       show only the part of a line matching PATTERN
          -q, --quiet, --silent     suppress all normal output
              --binary-files=TYPE   assume that binary files are TYPE;
                                    TYPE is 'binary', 'text', or 'without-match'
          -a, --text                equivalent to --binary-files=text
          -I                        equivalent to --binary-files=without-match
          -d, --directories=ACTION  how to handle directories;
                                    ACTION is 'read', 'recurse', or 'skip'
          -D, --devices=ACTION      how to handle devices, FIFOs and sockets;
                                    ACTION is 'read' or 'skip'
          -r, --recursive           like --directories=recurse
          -R, --dereference-recursive  likewise, but follow all symlinks
              --include=FILE_PATTERN  search only files that match FILE_PATTERN
              --exclude=FILE_PATTERN  skip files and directories matching FILE_PATTERN
              --exclude-from=FILE   skip files matching any file pattern from FILE
              --exclude-dir=PATTERN  directories that match PATTERN will be skipped.
          -L, --files-without-match  print only names of FILEs containing no match
          -l, --files-with-matches  print only names of FILEs containing matches
          -c, --count               print only a count of matching lines per FILE
          -T, --initial-tab         make tabs line up (if needed)
          -Z, --null                print 0 byte after FILE name

        Context control:
          -B, --before-context=NUM  print NUM lines of leading context
          -A, --after-context=NUM   print NUM lines of trailing context
          -C, --context=NUM         print NUM lines of output context
          -NUM                      same as --context=NUM
              --color[=WHEN],
              --colour[=WHEN]       use markers to highlight the matching strings;
                                    WHEN is 'always', 'never', or 'auto'
          -U, --binary              do not strip CR characters at EOL (MSDOS/Windows)
          -u, --unix-byte-offsets   report offsets as if CRs were not there
                                    (MSDOS/Windows)

        'egrep' means 'grep -E'.  'fgrep' means 'grep -F'. 
        Direct invocation as either 'egrep' or 'fgrep' is deprecated.
        When FILE is -, read standard input.  With no FILE, read . if a command-line -r is given, - otherwise.  If fewer than two FILEs are given, assume -h.
        Exit status is 0 if any line is selected, 1 otherwise;
        if any error occurs and -q is not given, the exit status is 2.

</br>
