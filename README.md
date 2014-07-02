project-2
=========
//  main.c
//  analysis 2
//
//  Created by susan hua on 14-6-29.
//  Copyright (c) 2014年 susan hua. All rights reserved.
//

#include <stdio.h>
/* count digits, white space, others */
int main()
{
    int c, i,j,k, nwhite, nother;
    int ndigit[10],nlow[26],nup[26];
    
    printf("Please input a string:\n");
    scanf("%d",&c);
    
    nwhite = nother = 0;
    for (i = 0; i < 10; ++i)
        ndigit[i] = 0;
    for (j = 0; j < 26; ++j)
        nlow[j] = 0;
    for (k = 0; k < 26; ++k)
        nup[k] = 0;
    
    while ((c = getchar()) != EOF)
        if (c >= '0' && c <= '9')
            ++ndigit[c-'0'];
        else if (c>='a' && c<='z')
            ++nlow[c-'a'];
        else if (c>='A' && c<='Z')
            ++nup[c-'Z'];
        else if (c == ' ' || c == '\n' || c == '\t')
            ++nwhite;
        else
            ++nother;
    printf("digits =");
    for (i = 0; i < 10; ++i)
    printf(" %d\n", ndigit[i]);
    printf("low letter =");
    for (j = 0; j < 26; ++j)
    printf(" %d\n", nlow[j]);
    printf("up letter =");
    for (k = 0; k < 26; ++k)
    printf(" %d\n", nup[k]);
    
    printf(", white space = %d, other = %d\n",
           nwhite, nother);
}
