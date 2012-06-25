csvutils
========

clone of csvutils for libcsv [http://csvutils.sourceforge.net/]

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

This is a set of programs to inspect and manipulated CSV data.  
These programs use the libcsv library available at
http://sourceforge.net/projects/libcsv/.

This release contains the following programs:

csvcount - print the number of fields and rows in CSV files
csvcheck - determine the validity of CSV data
csvfix   - convert a mal-formed CSV data into a well formed data and convert
           to CSV data with different quotes and/or delimiters
csvgrep  - search specific fields of CSV data for a pattern
csvcut   - output only the specified fields of a CSV file
csvbreak - break a file into multiple pieces based on the value of the
           specified field

This is a BETA release which means that functionality and behavior, as well
as option names, etc. may change before a production release, keep this in
mind when upgrading and consult the Changelog for any such changes.

Although these programs have been fairly well tested they are beta for a
reason, namely that only a couple of people have used them so far.  There
are likely to be bugs and if you find any I would be very grateful if you would
let me know.  You can email me feature requests, bugs, questions, comments,
etc. at rgamble@sourceforge.net.  Any feedback is very much appreciated, I
read every single email and the direction of this project is largely based on
them.  Feedback is especially important during the beta phase, if you have
been using csvutils for a while without any problems, feel free to let me know.

The provided programs are written in ANSI C and except for csvgrep do not rely
on any non-standard functionality outside of the getopt_long() option handling
function for which implementations are readily available if your C library
doesn't include one.  csvgrep uses the POSIX regular expresssion functions
regcomp/regexec/regerror/regfree as well as the Perl Compatible Regular
Expressions library available at www.pcre.org.  You can compile csvgrep without
support for one or both of these libraries by setting the macros WITHOUT_POSIX 
and WITHOUT_PCRE.


Roadmap

The goal of this project is to provide about a set useful CSV utilities to
perform tasks that cannot easily be accomplished using the standard UNIX 
utilities.  Below is the current plan for future releases, please feel free to
email me with any features/programs you would like considered for inclusion or
just general suggestions about functionality etc.

Next release (0.9.x)
  * Do something better than a sequential search in csvbreak which makes
    splitting on fields that contain many different values time consuming.
  * add several features to csvgrep/csvcut/csvcount from their non-csv
    counterparts.
  * fix reported bugs, add requested features, etc.

Future releases
  * add csvsort program to sort a CSV file on a specific field
    This will likely be the next program I work on as it is probably the
    most useful.

  * add either or csvsub program or the ability to perform substitutions
    with csvgrep using pcre.  Input welcome.

  * programs to convert between CSV and delimited formats
  * programs to convert between CSV and fixed length formats

    The last two programs are on the drawing board  but I may wait until
    I receive requests to write them before I start work on them.
