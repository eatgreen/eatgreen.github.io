filter and report writer

executate
1. write as shell script
2. write as any file, use awk -f
3. #!/bin/awk -f
   BEGIN { print "File\tOwner" }
   { print $8, "\t", $3}
   END { print " - DONE -" }


if ( conditional ) statement [ else statement ]
while ( conditional ) statement
for ( expression ; conditional ; expression ) statement
for ( variable in array ) statement
break
continue
{ [ statement ] ...}
variable=expression
print [ expression-list ] [ > expression ]
printf format [ , expression-list ] [ > expression ]
next 
exit