1. \# is  comment
2. ; semicolon, Command separator [semicolon]. Permits putting two or more commands on the same line.
3. ;; end in case
4. .  dot, leading dot as hidden file
5. " and ', " (double quote) preserves most of special characters while ' (single quote) preserves all special characters
6. , comma op,  The comma operator [1] links together a series of arithmetic operations. All are evaluated, but only the last one is returned.
7. \ backslash, A quoting mechanism for single characters.
8. / forward slash, file name path separator
9. ` backquotes, backticks. command substitution
10. : colon, null command, like true.
11. ! reverse the sense 
12. * wildcard, asterisk
13. ? wildcard, or test op, condition?result-if-true:result-if-false
14. $ variable substitution
15. $ parameter substitution
16. $? holds the exit status variable
17. $$ process ID variable
18. () command group
19. {xxx,yyy,zzz,...} 
20. {a..z}
21. {} curly brackets, black of code.
22. [] array element, in re as a range of characters
23. [[]] for evaluation
24. $[...] integer evaluation
25. (()) double parenrheses construct, arithmetic expansion and evaluation.
26. > &> >& >> < <> redirection
      >
      &>
      >&2
      >>
      <> [i]<>filename opens file filename for reading and writing, and assigns file descriptor i to it. If filename does not exist, it is created.
      <  
27. \<,\> word boundary in a re.
28. | pipe
29. || or
30. & run job in background
31. && and
32. - option prefix
33. - redirection from/to stdin or stdout [dash].
34. =~ re match