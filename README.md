# my-first-C-program
/* when I study the C programming language and do the excerisees,it happend to me to write this program as a celebration. This program is about two excercises, I tried to use them to build sth to show my wife that love her! */

#include "pch.h"
#include <iostream>
#include<stdio.h>

void stract(char *s, char *t);
int strend(char *s,char *t);

int main()
{
	char s[200] = "I love you";
	char t[200]= " very much";
	stract(s, t);
	printf("%s\n", s);
	strend(s, t);
	if (strend(s, t) ==1) {
		printf(" the love is true\n");
	}
	else if (strend(s, t) == 0){
		printf("the love is not true\n");
	}
}

void stract(char *s, char *t) //练习5-3 将t复制到s的尾部
{
	while (*s != '\0') {
		s++;
	}
	while ((*s++ = *t++) != '\0') {
		;
	}
}

int strend(char *s, char *t) //练习5-4 如果t出现在s的尾部，则返回1，否则返回0
{
	int lens = 0;
	while (*s != '\0') {
		s++;
		lens++;
	}
	int lent = 0;
	while (*t != '\0') {
		t++;
		lent++;
	}
	if (lens < lent) {
		return 0;
	}
		while ((*s == *t) && lent > 0) { 
		--s;
		--t;
		--lent;
	}
	if (lent == 0){
		return 1;
	}
	else {
		return 0;
	}
}
