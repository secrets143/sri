#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#include<malloc.h>
#define max 50
void getdata();
void insert();
void display();
void del();
int a[max],count=0,mov;
void main()
{
int n;
clrscr();
printf("\nARRAY IMPLEMENTATION OF LIST\n");
while(1)
{
printf("\n 1.getdata\n 2.insert\n 3.display\n 4.delete\n 5.exit");
printf("\nEnter your choice: ");
scanf("%d",&n);
switch(n)
{
case 1:
getdata();
break;
case 2:
insert();
break;
case 3:
display();
break;
case 4:
del();
break;
case 5:
exit(0);
break;
 }
 }
}
void getdata()
{
int item;
printf("\n Enter the Data :");
scanf("%d",&item);
a[count]=item;
count++;
}
void display()
{
int i;
printf("\nThe list is : ");
for(i=0;i<count;i++)
printf("[%d]",a[i]);
}
void insert()
{
int item,pos,i;
printf("\nEnter the data\n");
scanf("%d",&item);
printf("Enter the position:");
scanf("%d",&pos);
if(pos>=max-1||pos>count)
{
printf("Enter the valid position");
return;
}
if(pos==count)
{
a[count]=item;
count++;
return;
}
if(pos<count)
{
i=count;
a[i]=a[pos];
a[pos]=item;
count++;
}
}
void del()
{
int pos,mov;
printf("\nEnter the position:");
scanf("%d",&pos);
if(pos<0||pos>count-1)
{
printf("The deleted item is %d", a[count]);
count++;
return;
}
else
{
mov=pos;
while(mov<count-1)
{
a[mov]=a[mov+1];
mov++;
}
count--;
return;
}
}
