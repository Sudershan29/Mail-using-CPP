#include<iostream.h>
#include<conio.h>
#include<stdlib.h>
#include<graphics.h>
#include<ctype.h>
#include<dos.h>
#include<string.h>
#include<stdio.h>
#include<iomanip.h>
#include<fstream.h>
fstream file;
class small
{
 int userid;
 char mailid[30],recieved[100];
 int nofmr,nofms;
 public:
 int returnuserid()
 {
   return userid;
 }
 char* returnmailid()
 {
  return mailid;
 }
 int totsize();
 void sendmail(char ch[],int c);
 void compose();
}s1;
class mail
{
 int userno;
 char mailid[30],recieved[500];
 char nofmr,nofms;
 char sent[500],password[30],phno[10];
 public:
 void forgotpassword();
 mail()
 {
  nofmr='1';
  nofms='0';
  strcpy(recieved,"#nomailid@mail.com#Welcome to our mail services....Enjoy mailing and if you have any errors then send it to mailerrors@mail.com&-&-&");
  strcpy(sent,"#nomailid@mail.com#&-&-&");
 }
 void getdata()
 {
  nofmr='1';
  nofms='0';
  strcpy(recieved,"#nomailid@mail.com# Welcome to our mail services....Enjoy mailing and if you have any errors then send it to mailerrors@mail.com&-&-&");
  strcpy(sent,"#nomail@mail.com#&-&-&");
  cout<<"\n\nEnter mail id: ";
  cin>>mailid;
  cout<<"\n\nPassword :";
  cin>>password;
  cout<<"Enter phone number ";
  cin>>phno;
 }
 int returnuserno()
 {
  return userno;
 }
char* returnmailid()
 {
  return mailid;
 }
void copypassword(char* p)
{
  strcpy(password,p);
 }
char* returnpassword()
{
 return password;
}
void sendmail(char ch[],char temp[]);
int size(int arg);
void inbox();
int login();
void registering();
void sentbox();
void viewmail(char ch,int r);
void copy(char temp[]);
void copyinsent(char ch[], int ch1);
void compose();
}sample,h;
void main()
{
 int gd=DETECT,gm;
 initgraph(&gd,&gm,"c:/turboc3/bgi");
 void startingoutput();
 clrscr();
 cleardevice();
 char cj,hm[2]="rs",fr;
 int ctr,cd=1;
start:startingoutput();
 fr=getch();
 switch(fr)
 {
  case '1':if(sample.login())
	     goto start;
	   else
	    break;
  case '2':sample.registering();
	   file.open("mailfile.dat",ios::app|ios::binary);
	   file.write((char*)&sample,sizeof(sample));
	   file.close();
	   break;
  case 'X':clrscr();
	   file.open("mailfile.dat",ios::out|ios::binary);
	   sample.getdata();
	   file.write((char*)&sample,sizeof(sample));
	   file.close();
	   goto start;
  case 'E':
  case 'e': exit(0);
	    break;
  default:goto start;
 }
vj:cleardevice();
 sample.inbox();
 ctr=0;
do
{
 cj=getch();
 switch(cj)
 {
  case 'c':
  case 'C':clrscr();
	   cleardevice();
	   sample.compose();
	   break;
  case 'S':
  case 's':clrscr();
	   cleardevice();
	   sample.sentbox();
	   ctr=1;
	   break;
  case 'i':
  case 'I':clrscr();
	   cleardevice();
	   sample.inbox();
	   ctr=0;
	   break;
  case 'b':
  case 'B':goto vj;
  case 'e':
  case 'E':exit(0);
  case '1':
  case '2':
  case '3':
  case '4':
  case '5':
  case '6':
  case '7':
  case '8':
  case '9':sample.viewmail(hm[ctr],int(cj)-48);
	   break;
 }
}while(cd);
}
void viewboxoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
line(0,90,getmaxx(),90);
line(0,getmaxy()-50,getmaxx(),getmaxy()-50);
line(0,90,0,getmaxy()-50);
line(0,140,getmaxx(),140);
line(getmaxx(),90,getmaxx(),getmaxy()-50);
settextstyle(EUROPEAN_FONT,HORIZ_DIR,3);
outtextxy(getmaxx()/2,135,"VIEW BOX");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()-50,60,"Press b to ");
outtextxy(getmaxx()-60,70,"      get back");
}
void inboxoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
settextstyle(EUROPEAN_FONT,HORIZ_DIR,2);  //european,small.
outtextxy(getmaxx()/2+75,130,"(i)  INBOX");
settextstyle(EUROPEAN_FONT,HORIZ_DIR,1);
outtextxy(getmaxx()/2-190,310,"(c)COMPOSE");
outtextxy(getmaxx()/2-190,400,"(s)SENT MAIL");
outtextxy(getmaxx()/2-190,355,"(e)EXIT");
line(30,90,getmaxx()-50,90);
line(30,getmaxy()-50,getmaxx()-50,getmaxy()-50);
line(30,90,30,getmaxy()-50);
line(220,140,getmaxx()-50,140);
line(220,90,220,getmaxy()-50);
line(getmaxx()-50,90,getmaxx()-50,getmaxy()-50);
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-190,180,"s= To see sent mails");
outtextxy(getmaxx()/2-190,200,"c= To send a mail");
outtextxy(getmaxx()/2-190,220,"i= To get to indox");
outtextxy(getmaxx()/2-190,140,"Select to perform");
outtextxy(getmaxx()/2-190,150,"a particular action");
outtextxy(getmaxx()/2-190,240,"Select the number of");
outtextxy(getmaxx()/2-190,250,"the mail you want to view");
}
void sentboxoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
settextstyle(EUROPEAN_FONT,HORIZ_DIR,2);  //european,small.
outtextxy(getmaxx()/2+75,130,"(s)  SENT MAIL");
settextstyle(EUROPEAN_FONT,HORIZ_DIR,1);
outtextxy(getmaxx()/2-190,310,"(c)COMPOSE");
outtextxy(getmaxx()/2-190,400,"(i)INBOX");
outtextxy(getmaxx()/2-190,355,"(e)EXIT");
line(30,90,getmaxx()-50,90);
line(30,getmaxy()-50,getmaxx()-50,getmaxy()-50);
line(30,90,30,getmaxy()-50);
line(220,140,getmaxx()-50,140);
line(220,90,220,getmaxy()-50);
line(getmaxx()-50,90,getmaxx()-50,getmaxy()-50);
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-190,180,"s= To see sent mails");
outtextxy(getmaxx()/2-190,200,"c= To send a mail");
outtextxy(getmaxx()/2-190,220,"i= To get to indox");
outtextxy(getmaxx()/2-190,140,"Select to perform");
outtextxy(getmaxx()/2-190,150,"a particular action");
outtextxy(getmaxx()/2-190,240,"Select the number of");
outtextxy(getmaxx()/2-190,250,"the mail you want to view");
}
void composeboxoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
line(0,90,getmaxx(),90);
line(0,getmaxy()-50,getmaxx(),getmaxy()-50);
line(0,90,0,getmaxy()-50);
line(0,140,getmaxx(),140);
line(0,160,getmaxx(),160);
line(0,180,getmaxx(),180);
line(getmaxx(),90,getmaxx(),getmaxy()-50);
settextstyle(EUROPEAN_FONT,HORIZ_DIR,3);
outtextxy((getmaxx()+30)/2,130,"COMPOSE");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(45,153,"From : ");
outtextxy(45,173,"To   : ");
outtextxy(getmaxx()-135,75,"Type &-&-& to end mail..MAX 125 char");
}
void registeringoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
settextstyle(EUROPEAN_FONT,HORIZ_DIR,2);
outtextxy(getmaxx()/2-220,180,"REGISTER");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-130-10,275-8,"MAIL ID:");
outtextxy(getmaxx()/2-130-10,320-5,"PASSWORD:");
outtextxy(getmaxx()/2-160-20,340-10,"CONFIRM PASSWORD:");
outtextxy(getmaxx()/2-145-20,390-10,"PHONE NUMBER:");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()-100,120,"Type B@CK to get");
outtextxy(getmaxx()-100,135,"back to the main menu");
outtextxy(getmaxx()-100,150,"Type F*RG*T if you forgot");
outtextxy(getmaxx()-110,167,"your password in passwordbox");
}
void loginoutput()
{
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
outtextxy(getmaxx()/2-30,50,"MAIL");
settextstyle(EUROPEAN_FONT,HORIZ_DIR,2);  //european,small.
outtextxy(getmaxx()/2-250,150,"LOGIN");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-60,253,"MAIL ID:_________________________________________");
outtextxy(getmaxx()/2-65,300,"PASSWORD:________________________________________");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()-100,120,"Type B@CK to get");
outtextxy(getmaxx()-100,135,"back to the main menu");
outtextxy(getmaxx()-100,150,"Type F*RG*T if you forgot");
outtextxy(getmaxx()-100,165,"your password");
}
void startingoutput()
{
clrscr();
cleardevice();
settextjustify(1,0);
settextstyle(DEFAULT_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-30,50,"MAIL");
line(340+40,15,390+40,15);
line(340+40,45,390+40,45);
line(340+40,15,340+40,45);
line(390+40,15,390+40,45);
line(340+40,15,365+40,30);
line(365+40,30,390+40,15);
settextstyle(SANS_SERIF_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()/2-220,160,"1.LOGIN");
outtextxy(getmaxx()/2-180,300,"2.REGISTER");
settextstyle(SMALL_FONT,HORIZ_DIR,6);
outtextxy(getmaxx()/2-100,200,"MAIL ID: _______________________");
outtextxy(getmaxx()/2-100,230,"PASSWORD:_______________________");
settextstyle(SMALL_FONT,HORIZ_DIR,5);
outtextxy(getmaxx()-110,120,"To EXIT, Press E or e");
outtextxy(getmaxx()-110,100,"Select either 1 or 2 ");
settextstyle(EUROPEAN_FONT,HORIZ_DIR,1);
outtextxy(getmaxx()/2,330+10,"Create a new account");
outtextxy(getmaxx()/2,350+20,"and get exposed to the world's");
outtextxy(getmaxx()/2,380+20,"favourite mail !!");
}
void mail::registering()
{
c:file.open("mailfile.dat",ios::in|ios::binary);
 char temp1[30],temp2[30],temp3[30],temp4[10];
 clrscr();
 cleardevice();
 for(int i=0;i<16;i++)
  cout<<"\n";
 cout<<"\t\t\t   ";
 registeringoutput();
 cin>>temp1;
 int go;
 go=0;
 int h;
 file.seekg(0,ios::beg);
 while(!file.eof())
 {
  mail m;
  file.read((char*)&m,sizeof(m));
  if(!strcmpi(m.returnmailid(),temp1))
  {
   go=1;
   file.close();
   break;
  }
 }
 if(go)
 {
  cout<<"Mail id already exists....try something else ";
  getch();
  goto c;
 }
p:clrscr();
 cleardevice();
 for(i=0;i<16;i++)
  cout<<"\n";
 cout<<"\t\t\t   "<<temp1;
 cout<<"\n\n\n\t\t\t   ";
 registeringoutput();
 cin>>temp2;
 clrscr();
 cleardevice();
 for(i=0;i<16;i++)
 cout<<"\n";
 cout<<"\t\t\t   "<<temp1<<"\n\n\n\t\t\t   "<<temp2<<"\n\t\t\t   ";
 registeringoutput();
 cin>>temp3;
 if(strcmp(temp2,temp3))
 {
   cout<<"\nPASSWORD DOESNT MATCH...Try again after pressing enter";
   getch();
   goto p;
 }
 clrscr();
 cleardevice();
 for(i=0;i<16;i++)
  cout<<"\n";
 cout<<"\t\t\t   "<<temp1<<"\n\n\n\t\t\t   "<<temp2<<"\n\t\t\t   "<<temp3<<"\n\n\n\t\t\t   ";
 registeringoutput();
 cin>>temp4;
 strcpy(mailid,temp1);
 strcpy(password,temp2);
 strcpy(phno,temp4);
 file.open("mailfile.dat",ios::in|ios::binary);
 mail m;
 file.seekg(-sizeof(m),ios::end);
 file.read((char*)&m,sizeof(m));
 userno=m.returnuserno()+1;
 cout<<"Your userno is "<<userno;
 file.close();
}
int mail::login()
{
l:file.open("mailfile.dat",ios::in|ios::binary);
 file.seekg(0,ios::beg);
 clrscr();
 cleardevice();
 char temp[30],temp1[30];
 cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t";
 loginoutput();
 cin>>temp;
 while(!file.eof())
 {
  mail m;
  file.read((char*)&m,sizeof(m));
  if(!strcmpi(m.returnmailid(),temp))
  {
 j:clrscr();
   cleardevice();
   cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t";
   cout<<temp;
   cout<<"\n\n\n\t\t";
   loginoutput();
   cin>>temp1;
   if(!strcmp(temp1,"F*RG*T"))
     m.forgotpassword();
   else if(strcmp(m.returnpassword(),temp1))
    {
     cout<<"\n\t\t\t WRONG PASSWORD..Try again after pressing enter or type F*RG*T if forgot ur password ";
     getch();
     goto j;
    }
   sample=m;
   goto lh;
  }
 else if(!strcmp(temp,"B@CK"))
   return 1;
 }
 cout<<"\nWrong email id....Try again";
 file.close();
 getch();
 goto l;
 lh:return 0;
}
int mail::size(int ahn)
{
  file.open("mailfile.dat",ios::in|ios::binary);
  int h;
  while(!file.eof())
  {
   mail h1;
   file.read((char*)&h1,sizeof(h1));
   if(h1.returnuserno()==ahn)
   { h=sizeof(h1);
     file.close();
     return h;
   }
  }
 return 0;
}
void mail::inbox()                              //introduce exit for inbox...create 2 mail ids n work on them!!!
 {
  clrscr();
  cleardevice();
  cout<<"\n\n\n\n\n\n\n\n\n\t\t\t    ";
  int i,ctr,x,j,m,z;
  for(i=0,ctr=1;i<(int(nofmr)-48);i++)
  {
   line(490,140+20*i,490,140+20*i);
   line(230,140+20*i,230,140+20*i);
   line(230,160+20*i,getmaxx()-50,160+20*i);
   line(470,140+20*i,470,160+20*i);
   line(240,140+20*i,240,160+20*i);
   cout<<i+1<<" ";
   for(z=ctr,m=0;recieved[z]!='#';z++)
   {
    if(m++<12)
     cout<<recieved[z];
   }
   cout<<"...";
   ctr=z+1;
  for(j=ctr,x=0;!((recieved[j]=='&')&&(recieved[j+1]=='-')&&(recieved[j+2]=='&')&&(recieved[j+3]=='-')&&(recieved[j+4]=='&'));j++)
  {
   if(x++<23)
    cout<<recieved[j];
  }
  cout<<"...";
  ctr=j+6;
  cout<<"\n\t\t\t    ";
 }
 inboxoutput();
}
void mail::sentbox()
{
  clrscr();
  cleardevice();
  cout<<"\n\n\n\n\n\n\n\n\n\t\t\t     ";
  int i,ctr,x,z,m,j;
  for(i=0,ctr=0;i<(int(nofms)-48);i++)
  {
   line(490,140+20*i,490,140+20*i);
   line(240,140+20*i,240,140+20*i);
   line(220,160+20*i,getmaxx()-50,160+20*i);
   cout<<i+1<<" ";
   for(z=ctr,m=0;sent[z]!='#';z++)
   {
    if(m++<12)
     cout<<sent[z];
   }
   cout<<"...";
   ctr=z+1;
  for(j=ctr,x=0;!((sent[j]=='&')&&(sent[j+1]=='-')&&(sent[j+2]=='&')&&(sent[j+3]=='-')&&(sent[j+4]=='&'));j++)
  {
   if(x++<23)
    cout<<sent[j];
  }
  cout<<"...";
  ctr=j+6;
  cout<<"\n\t\t\t    ";
 }
 sentboxoutput();
}
void mail::viewmail(char ch,int c)
{
 if(((ch=='r')&&(c<=(int(nofmr)-48)))||((ch=='s')&&(c<=(int(nofmr)-48))))
  clrscr();
  int ctr,i,j,k;
  ctr=0;
  char temp[300];
  switch(ch)
   {
    case 'r': for(j=0,ctr=0;ctr<(c-1);j++)
	      {
	       if(((recieved[j]=='&')&&(recieved[j+1]=='-')&&(recieved[j+2]=='&')&&(recieved[j+3]=='-')&&(recieved[j+4]=='&')))
		   ctr++;
	      }
	      j+=6;
	      if(c==1)
	       j=1;
	      char temp1[30];
	      for(k=0;recieved[j]!='#';j++,k++)
	       temp1[k]=recieved[j];
	      for(i=0;!((recieved[j]=='&')&&(recieved[j+1]=='-')&&(recieved[j+2]=='&')&&(recieved[j+3]=='-')&&(recieved[j+4]=='&'));i++)
	      {
	       temp[i]=recieved[++j];
	      }
	      clrscr();
	      cleardevice();
	      cout<<"\n\n\n\n\n\n\n\n\n\nFROM: ";
	      viewboxoutput();
	      for(int m=0;m<k-1;m++)
	      {
	       cout<<temp1[m];
	       delay(100);
	      }
	      cout<<"\n\n\t";
	      for(m=0;m<i-1;m++)
	      {
	       cout<<temp[m];
	       delay(100);
	      }
	      break;
    case 's': for(j=0,ctr=0;ctr<(c-1);j++)
	      {
	       if(((sent[j]=='&')&&(sent[j+1]=='-')&&(sent[j+2]=='&')&&(sent[j+3]=='-')&&(sent[j+4]=='&')))
		   ctr++;
	      }
	      j+=6;
	      if(c==1)
	       j=1;
	      char temp2[30];
	      for(k=0;sent[j]!='#';j++,k++)
	       temp1[k]=sent[j];
	      for(i=0;!((sent[j]=='&')&&(sent[j+1]=='-')&&(sent[j+2]=='&')&&(sent[j+3]=='-')&&(sent[j+4]=='&'));j++,i++)
	      {
	       temp2[i]=sent[j];
	      }
	      clrscr();
	      cleardevice();
	      cout<<"\n\n\n\n\n\n\n\n\n\nTO: ";
	      viewboxoutput();
	      for(m=0;m<k-1;m++)
	      {
	       cout<<temp1[m];
	       delay(100);
	      }
	      cout<<"\n\n\t";
	      for(m=0;m<i-1;m++)
	      {
	       cout<<temp[m];
	       delay(100);
	      }
	      break;
  }
}
void mail::forgotpassword()
 {
  file.open("mailfile.dat",ios::in|ios::binary|ios::ate);
  char ch[10];
  h:clrscr();         //1 \n shifts 17 y coordinates down.......
  cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t"<<mailid;
  cout<<"\n\n\n\n\n\n\t\t\t";
  loginoutput();
  outtextxy(getmaxx()/2-100,355,"Enter your PHONE NUMBER: ");
  cin>>ch;
  cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t"<<mailid;
  cout<<"\n\n\n\n\n\n\t\t\t"<<ch<<"\n\n\t\t\t";
  loginoutput();
  if(strcmpi(ch,phno)==0)
  {
   outtextxy(getmaxx()/2-100,390,"Enter new password: ");
   cin>>ch;
   strcpy(password,ch);
   file.seekg(0,ios::beg);
   while(!file.eof())
   {
    int t;
    mail ss;
    t=file.tellg();
    file.read((char*)&ss,sizeof(ss));
    if(!strcmpi(ss.returnmailid(),mailid))
    {
     file.seekg(t);
     ss.copypassword(password);
     file.write((char*)&ss,sizeof(ss));
    }
   else
   {
   outtextxy(getmaxx()/2-150,380,"Wrong..Try another number ");
   getch();
   goto h;
   }
  }
 }
 file.close();
}
int small::totsize()
{
 return sample.size(userid);
}
void mail::copy(char temp[])
{
 nofmr++;
 strcpy(recieved,temp);
}
void mail::compose()
{
 clrscr();
 cleardevice();
 char from[30],to[30],temp[125];
 int go,i,j,z;
 cout<<"\n\n\n\n\n\n\n\n\n\t ";
 composeboxoutput();
 cin>>from;
jkr:clrscr();
 cleardevice();
 cout<<"\n\n\n\n\n\n\n\n\n\t ";
 cout<<from;
 cout<<"\n\t ";
 composeboxoutput();
 cin>>to;
 go=0;
 file.close();
 file.open("mailfile.dat",ios::in|ios::binary);
 while(!file.eof())
 {
  mail a;
  file.read((char*)&a,sizeof(a));
  if(!strcmpi(a.returnmailid(),to))
  {
    go=1;
    goto sbh;
  }
 }
sbh:file.close();
 if(!go)
 {
  cout<<"\t MAIL ID DOESNT EXISTS,TRY AGAIN";
  getch();
  goto jkr;
 }
 clrscr();
 cleardevice();
 cout<<"\n\n\n\n\n\n\n\n\n\t ";
 cout<<from;
 cout<<"\n\t ";
 cout<<to;
 cout<<"\n\n \t ENTER:";
 composeboxoutput();
 i=0;
 do
 {
back:cin>>temp[i++];
  if(i<=5)
   goto back;
 }while(!((temp[i-5]=='&')&&(temp[i-4]=='-')&&(temp[i-3]=='&')&&(temp[i-2]=='-')&&(temp[i-1]=='&')));
 for(j=0,z=0;z<int(nofms)-48;j++)
 {
  if(((sent[j]=='&')&&(sent[j+1]=='-')&&(sent[j+2]=='&')&&(sent[j+3]=='-')&&(sent[j+4]=='&')))
   z++;
 }
 j+=5;
 sent[j++]='#';
 for(i=0;i<strlen(to);i++)
 {
  sent[j++]=to[i];
 }
 sent[j++]='#';
 for(i=0;i<strlen(temp);i++)
 {
  sent[j++]=temp[i];
 }
 file.close();
 file.open("mailfile.dat",ios::in|ios::binary);
 while(!file.eof())
 {
  file.read((char*)&h,sizeof(h));
  if(!strcmpi(h.returnmailid(),to))
  {
   goto mn;
  }
 }
mn:file.close();
 h.sendmail(from,temp);
 file.close();
 file.open("mailfile.dat",ios::in|ios::out|ios::binary);
 int g;
 while(!file.eof())
 {
  mail b;
  g=file.tellg();
  file.read((char*)&b,sizeof(b));
  if(!strcmpi(b.returnmailid(),mailid))
  {
   file.seekg(g);
   file.write((char*)&h,sizeof(h));
  }
 }
 file.close();
 file.open("mailfile.dat",ios::in|ios::out|ios::binary);
 while(!file.eof())
 {
  mail k;
  i=file.tellg();
  file.read((char*)&k,sizeof(k));
  if(!strcmpi(k.returnmailid(),mailid))
  {
   file.seekg(i);
   file.write((char*)&sample,sizeof(sample));
  }
 }
 cout<<"\n\n\nSUCCESSFULLY SENT";
 nofms++;
 getch();
 file.close();
}
void mail::sendmail(char from[],char temp[])
{
 int j,z,g,i;
 for(j=0,z=0;z<int(nofmr)-48;j++)
 {
  if(((recieved[j]=='&')&&(recieved[j+1]=='-')&&(recieved[j+2]=='&')&&(recieved[j+3]=='-')&&(recieved[j+4]=='&')))
   z++;
 }
 j+=5;
 recieved[j++]='#';
 for(i=0;i<strlen(from);i++)
 {
  recieved[j++]=from[i];
 }
 recieved[j++]='#';
 for(i=0;i<strlen(temp);i++)
 {
  recieved[j++]=temp[i];
 }
 file.close();
 nofmr++;
}
