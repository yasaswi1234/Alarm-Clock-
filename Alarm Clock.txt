#include <stdio.h>
#include <conio.h>
#include <windows.h>
#include <time.h>
struct time{
 int h;
 int m;
 int s;
 }alarm;
int main()
{
 time_t rawtime;
 struct tm * current;
time ( &rawtime );
 current = localtime ( &rawtime );
 printf ( "Current local time and date: %s\n", asctime (current) );
 int Hr, Min, Sec, x=0;
 printf("Enter hour in 24 hr format: ");
 scanf("%d",&alarm.h);
 printf("Enter minutes : ");
 scanf("%d",&alarm.m);
 printf("Enter seconds : ");
 scanf("%d",&alarm.s);
 Hr = current->tm_hour; //retrieved from system time using localtime function
 Min = current->tm_min;
 Sec = current->tm_sec;
 if(alarm.h<24 && alarm.m<60 && alarm.s<60){
 loop:
 if(alarm.h==Hr && alarm.m==Min && alarm.s==Sec){
 loop1:
 if(x<=20){
 system("cls");
 printf("**time up**\a");
 Sleep(3000);
 x++;
 }//for a minute
 goto loop1;
 }
 // current time
 system("cls");
 printf("%d:%d:%d",Hr,Min,Sec);
 Sleep(1000);
 Sec++;
 if(Sec==60)
 {
 Sec=0;
 Min++;
 }
 if(Min==60)
 {
 Min=0;
 Hr++;
 }
 if(Hr==24)
 {
 Hr=0;
 }
 goto loop;
 }
 else
 printf("You entered invalid time format");
 return 0;
}