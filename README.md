# Ex. No : 4	
# RECOGNITION OF A VALID VARIABLE WHICH STARTS WITH A LETTER FOLLOWED BY ANY NUMBER OF LETTERS OR DIGITS USING YACC
## Register Number : 212225230152 

## AIM   
To write a YACC program to recognize a valid variable which starts with a letter followed by any number of letters or digits.

## ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the keywords int, float and double and for the identifier.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with YACC compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter a statement as input and the valid variables are identified as output.

## PROGRAM
```
%{
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

extern int yylex();
void yyerror(const char *msg);

%}

%union {
    char *str;
}

%token <str> IDENTIFIER

%%
start:
    IDENTIFIER '\n' {
        printf("Valid variable: %s\n", $1);
        free($1);  // clean up strdup memory
    }
    ;
%%

int main() {
    printf("Enter a variable name:\n");
    return yyparse();
}

void yyerror(const char *msg) {
    printf("Invalid variable name\n");
}
```

## OUTPUT

<img width="1036" height="482" alt="image" src="https://github.com/user-attachments/assets/eb260e91-7ef1-44c0-a6c1-036e3004ef8b" />


## RESULT
A  YACC program to recognize a valid variable which starts with a letter followed by any number of letters or digits is executed successfully and the
output is verified.





..






..





..





..


..



..

...



....
















..












..









..










..












..









..













..








..


...
