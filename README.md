/*In an encryption scheme each lowercase or uppercase letter is shifted by 13 positions.For example:the string "You are Here" is encoded as "lbh ner urer".
Class definition:
Class name : Encrypt
Data Members :
Message    Stores the actual message
Enc_Msg    Stores the encoded message
Methods :
void input()               -  accept message from the user
String encode(String s)    -  Encrypts the string passed using the scheme discuused above
void display()             -  displays the actual and encrypted message
Specify the class Encrypt giving the details of all the functions . Also define the main() functions to create an object and call the methods accordingly to enable the task.*/

Step-1    input()
Step-2    print "Enter Message"
Step-3    input Message 
Step-4    end input()
Step-5    encode(String s)
Step-6    s=s.toLowerCase()
Step-7    w=""
Step-8    for i=0 to i=s.length()-1 inc=+1
Step-9    c=s.charAt(i)
Step-10   if c==' ' then goto Step-11 else goto Step-13
Step-11   w=w+c
Step-12   goto Step-19
Step-13   ascii=(int)c
Step-14   ascii=ascii+13
Step-15   if ascii>122 then goto Step-16 else goto Step-18
Step-16   ascii=(ascii-122)+96
Step-17   end if
Step-18   w=w+(char)ascii
Step-19   end if
Step-20   end for
Step-21   return w
Step-22   end encode(String)
Step-23   display()
Step-24   print("The Actual Message is :"+Message)
Step-25   print("The Encoded Message is :"+Enc_Msg)
Step-26   end display()
Step-27   main(String ar[])
Step-28   Encrypt z=new Encrypt(Message)
Step-29   z.input()
Step-30   Enc_Msg=z.encode(Message)
Step-31   z.display()
Step-32   end main(String ar[])
Step-33   end















import java.util.*;
class Encrypt
{
  private static String Message;	 //data members
  private static String Enc_Msg;   //data members
  public static void input()
  {
    Scanner sc=new Scanner(System.in);   //creating an object of the scanner class
    System.out.println("Enter Message:");
    Message=sc.nextLine();              //input the message to be encoded
  }
  public static String encode(String s)
  {
     s=s.toLowerCase();                  //converting the string to lower case
     int i,ascii;
     char c;
     String w="";
     for(i=0;i<s.length();i++)
     {
        c=s.charAt(i);
	if(c==' ')
	    w=w+c;
        else
	{
	    ascii=(int)c;      //storing the ascii code of the characters in the string
	    ascii=ascii+13;
	    if(ascii>122)      //checking if the ascii codes are greater than 122 
	    {
		ascii=(ascii-122)+96;
	    }
	    w=w+(char)ascii;
	}
     }
     return w;
  }
  public static void display()
  {
     System.out.println("The Actual Message is :"+Message);
     System.out.println("The Encoded Message is :"+Enc_Msg);
  }
  public static void main(String ar[])      //main function
  {
     Encrypt z=new Encrypt();          //creating an object of Encrypt class 
     z.input();                               
     Enc_Msg=z.encode(Message);
     z.display();
  }
}












Enter Message:
You are Here
The Actual Message is :You are Here
The Encoded Message is :lbh ner urer



























/*to check whether the sudoku is valid or invalid*/

Step 1   a=0
Step 2   s=""
Step 3   arr[][]=new int[9][9]
Step 4   print "enter a sudoku"
Step 5   for i 0 to <9 inc=+1
Step 6   input s
Step 7   j=0
Step 8   for x 0 to <s.length() inc=+1
Step 9   c=s.charAt(x)
Step 10  if(Character.isDigit(c)) goto step 11 and 12
Step 11  ar[i][j]=Integer.parseInt(""+c)
Step 12  j++  
Step 13  end for step 8
Step 14  end for step 5
Step 15  for x 0 to <9 inc=+1
Step 16  for z 1 to 9 inc=+1
Step 17  for y 0 to <9 inc=+1 
Step 18  if(ar[x][y]==z) goto step 19 and 20
Step 19  a++
Step 20  break
Step 21  end for step 17   
Step 22  end for step 16
Step 23  if(a!=9) goto step 24 and 25
Step 24  s="invalid"       
Step 25  break 
Step 26  a=0
Step 27  end for step 15
Step 28  for x 0 to <9 inc=+1
Step 29  for z 1 to 9 inc=+1
Step 30  for y 0 to <9 inc=+1 
Step 31  if(ar[y][x]==z) goto step 32 and 33
Step 32  a++
Step 33  break
Step 34  end for step 28   
Step 35  end for step 29
Step 36  if(a!=9) goto step 37 and 38
Step 37  s="invalid"       
Step 38  break 
Step 39  a=0
Step 40  end for step 30
Step 41  for l 0 to 6 inc=+3  
Step 42  for b 0 to 6 inc=+3
Step 43  l1=l+3
Step 44  b1=b+3
Step 45  for z 1 to 9 inc=+1
Step 46  for x l to <l1 inc=+1
Step 47  for y b to <b1 inc=+1
Step 48  if(ar[x][y]==z) goto step 49 and 50
Step 49  a++
Step 50  break
Step 51  end for step 47
Step 52  if(y<b) goto step 53
Step 53  break
Step 54  end for step 46
Step 55  end for step 45
Step 56  if(a!=9) goto step 57 and 58
Step 57  s="invalid"
Step 58  break 
Step 59  a=0
Step 60  end for step 42
Step 61  end for step 41
Step 62  if(s.equalsIgnoreCse("invalid")) goto step 53 else goto step 64
Step 63  print s
Step 64  print "valid"
Step 65  end


























import java.util.*;
class sudoku
{
 public static void main(String ab[])
 {
  Scanner sc=new Scanner(System.in);
  int a=0,l,b,l1,b1,x,y,z,i,j;
  char c; 
  String s="";
  int ar[][]=new int[9][9];
  System.out.println("enter a sudoku");
  for(i=0;i<9;i++)
  {
   s=sc.nextLine();
   j=0;
   for(x=0;x<s.length();x++)
   {
    c=s.charAt(x);
    if(Character.isDigit(c))
    {
     ar[i][j]=Integer.parseInt(""+c);
     j++;
    }
   }
  }

  for(x=0;x<9;x++)              //checks for repetition in row
  {
   for(z=1;z<=9;z++)
   {
    for(y=0;y<9;y++)
    {
     if(ar[x][y]==z)
     {
      a++;
      break;
     }
    }
   }
   if(a!=9)
   {
    s="invalid";
    break;
   }
   a=0;
  }
  for(x=0;x<9;x++)           //checks for repetition in column
  {
   for(z=1;z<=9;z++)
   {
    for(y=0;y<9;y++)
    {
     if(ar[y][x]==z)
     {
      a++;
      break;
     }
    }
   }
   if(a!=9)
   {
    s="invalid";
    break;
   }
   a=0;
  }
  for(l=0;l<=6;l=l+3)                   //checks for repetition in a grid
  {		
   for(b=0;b<=6;b=b+3)
   {
    l1=l+3;
    b1=b+3;
    for(z=1;z<=9;z++)
    {
     for(x=l;x<l1;x++)
     {
      for(y=b;y<b1;y++)
      {
       if(ar[x][y]==z)
       {
        a++;
        break;
       }
      }
      if(y<b)
      break;
     }
    }
    if(a!=9)
    {
     s="invalid";
     break;
    }
    a=0;
   }
  }
  if(s.equalsIgnoreCase("invalid"))
  System.out.println(s);
  else
  System.out.println("valid");
 }
}






















enter a sudoku
8,2,7,1,5,4,3,9,6
9,6,8,3,2,7,1,4,5
3,4,1,6,8,9,7,5,2
5,9,3,4,6,8,2,7,1
4,7,2,5,1,3,6,8,9
6,1,8,9,7,2,4,3,5
7,8,6,2,3,5,9,1,4
1,5,4,7,9,6,8,2,3
2,3,9,8,4,1,5,6,7
invalid



















/*Write a program to perform binary search using recursion*/

Step 1 Main() 
Step 2 Scanner sc= new  Scanner( System.in);
Step 3 l=Input length of array
Step 4 a=new  int(l)
Step 5 for(x=0;x<l;x++)
Step 6 input array elements
Step 7 end of for loop
Step 8 input number to be searched
Step 9 BinarySearchRecursion q=new BinarySearchRecursion()
Step 10 if q.bsearch(a,n,0,l-1)
Step 11 print found
Step 12 else
Step 13 print not found
Step 14 bsearch(int a[],int n,int s,int e)
Step 15 if s>e
Step 16 return false
Step 17 else
Step 18 m=(s+e)/2
Step 19 if a[m]=n
Step 20 return true
Step 21 else
Step 22 if n>a[m]
Step 23 return bsearch(a,n,m+1,e)
Step 24 else
Step 25 return bsearch(a,n,s,m-1)
Step 26 end of else
Step 27 end


import java.util.*;
import java.io.*;
class BinarySearchRecursion
{
 public static void main(String at[])
 {
  Scanner sc=new Scanner(System.in);
  int l,a[],x,n;
  boolean p;
  System.out.println("Enter length of the array");
  l=sc.nextInt();
  a=new int[l];
  for(x=0;x<l;x++)//input
  {
   System.out.println("Enter an integer");
   a[x]=sc.nextInt();
  }
  System.out.println("Enter element to be searched");
  n=sc.nextInt();
  BinarySearchRecursion q=new BinarySearchRecursion();
  p=q.bsearch(a,n,0,l-1);
  if(p)
  System.out.println("Found");
  else
  System.out.println("Not found");
 }//end of main
 public boolean bsearch(int a[],int n,int s,int e)
 {
  if(s>e)
  return false;
  else
  {
   int m=(s+e)/2;
   if(a[m]==n)
   return true;
   else
   {
    if(n>a[m])
    return bsearch(a,n,m+1,e);
    else
    return bsearch(a,n,s,m-1);
   }
  }
 }//end of bsearch   
}















Enter length of the array
6
Enter an integer
7
Enter an integer
8
Enter an integer
9
Enter an integer
10
Enter an integer
11
Enter an integer
12
Enter element to be searched
9
Found













/*Write a program to input login time and logged out time in 24 hours format.
Calculate the time difference and print it.*/

Step 1 main
Step 2 scanner sc= new  scanner(system.in)
Step 3 input first time
Step 4 input second time
Step 5 k1=a.split
Step 6 k2=b.split
Step 7 sec1=Integer.parseInt(k1[0])*3600+Integer.parseInt(k1[1])*60+Integer.parseInt(k1[2])
Step 7 sec2=Integer.parseInt(k2[0])*3600+Integer.parseInt(k2[1])*60+Integer.parseInt(k2[2])
Step 8  if f sec2>sec1
Step 9 sec=sec2-sec1
Step 10 else
Step 11 sec=3600*24+sec2-sec1
Step 12 hrs=sec/3600
Step 13 min=(sec%3600)/60
Step 14 sec3=sec%60 
Step 15 if (hrs+"").length()!=2
Step 16 print "0"+hrs+":"
Step 17 else
Step 18 print hrs+":"
Step 19 if (min+"").length()!=2
Step 20 print "0"+min+":"
Step 21 else
Step 22 print min+":"
Step 23 if (sec3+"").length()!=2
Step 24 print  "0"+sec3
Step 25 else
Step 26 print sec3
Step 27 end

import java.util.*;
class Time
{
  public static void main(String at[])
  {
    Scanner sc=new Scanner(System.in);  //creating an object of the scanner class
    System.out.print("Enter first time  = ");
    String a=sc.nextLine();   //inputting the first time
    System.out.print("Enter second time = ");
    String b=sc.nextLine();   //inputting the second time
    String k1[]=a.split(":");
    String k2[]=b.split(":");
    int sec1=Integer.parseInt(k1[0])*3600+Integer.parseInt(k1[1])*60+Integer.parseInt(k1[2]); //converting the 1st time into seconds
    int sec2=Integer.parseInt(k2[0])*3600+Integer.parseInt(k2[1])*60+Integer.parseInt(k2[2]); //converting the 2nd time into seconds
    int sec;
    if(sec2>sec1)  //checking if the 2nd time is greater or not
      sec=sec2-sec1;  //calculating the time diff in seconds
    else
      sec=3600*24+sec2-sec1;
    int hrs,min,sec3;
    hrs=sec/3600;
    min=(sec%3600)/60;
    sec3=sec%60;
    System.out.println();
    System.out.print("Total time difference = ");  //from here the printing the time difference takes place
    if((hrs+"").length()!=2)
      System.out.print("0"+hrs+":");
    else
      System.out.print(hrs+":");
    if((min+"").length()!=2)
      System.out.print("0"+min+":");
    else
      System.out.print(min+":");
    if((sec3+"").length()!=2)
      System.out.print("0"+sec3);
    else
      System.out.print(sec3);
  }
}		




















Enter first time  = 06:27:43
Enter second time = 09:13:57

Total time difference = 02:46:14



























/*Write a program to check whether a number is Runaround number or not.
 A Runaround number is an integer with exactly N digits,each of which is between 1 and 9, inclusively.
The digits form a sequence with each digit telling where the next digit in the sequence occurs.
This is done by giving the number of digits to the right of the digit where the next digit in the sequence occurs.
If necessary,counting wraps around from the rightmost digit back to the leftmost.
The leftmost digit in the number is the first digit in the sequence, 
and the sequence must return to this digit after all digits in the number have been used exactly once.*/

Step 1 main()
Step 2 Scanner sc=new Scanner(System.in)
Step 3 input a number
Step 4 t=0
Step 5 while a!=0
Step 6 a=a/10
Step 7 t++
Step 8 end of while
Step 9 a=n
Step 10 arr=new int[t][2]
Step 11 for(i=t-1;i>=0;i–-)
Step 12 ar[i][0]=a%10
Step 13 a=a/10
Step 14 end of for
Step 15 p=0
Step 16 for(i=0;i<t;i++)
Step 17 if p>=t
Step 18 while p>=t
Step 19 p=p-t
Step 20 end of while
Step 21 end of if
Step 22 if ar[p][1] =1
Step 23 break
Step 24 end of if
Step 25 ar[p][1]=1
Step 26 p=p+ar[p][0]
Step 27 end of for
Step 28 for(i=0;i<t;i++)
Step 29 if ar[i][1]!=1
Step 30 break
Step 31 end of if
Step 32 end of for
Step 33 if i=t
Step 34 print runaround number
Step 35 else
Step 36 print not a runaround number
Step 37 end














import java.util.*;
class Runaround
{
 public static void main(String[] args)   
 {
  Scanner sc=new Scanner(System.in);
  System.out.println("Enter a number");
  int n=sc.nextInt();  
  int a=n,t=0,i;
  while(a!=0)
  {
   a=a/10;
   t++;
  }
  a=n;
  int ar[][]=new int[t][2];
  for(i=t-1;i>=0;i--)
  {
   ar[i][0]=a%10;
   a=a/10;
  }
  int p=0;
  for(i=0;i<t;i++)
  {
   if(p>=t)
   { 
    while(p>=t)
    p=p-t;
   }
   if(ar[p][1]==1)
   break;
   ar[p][1]=1;
   p=p+ar[p][0];
  }
  for(i=0;i<t;i++)
  {
   if(ar[i][1]!=1)
   break;
  }
  if(i==t)
  System.out.print("Runaround Number");
  else
  System.out.print("Not a Runaround Number");
 }
}

















Enter a number
81362
Runaround Number




























/*Program to find the lucky number by giving position to start.*/

Step-1    main(String at[])
Step-2    i=0
Step-3    b=0
Step-4    p=0
Step-5    print "Enter length of an array"
Step-6    input n
Step-7    a=new int[n]
Step-8    print "Enter the position to start checking"
Step-9    input i
Step-10   for x=0 to x<n inc=+1
Step-11   print "Enter an integer"
Step-12   input a[x]
Step-13   end for
Step-14   for x=0 to x<n-1 inc=+1
Step-15   b=a[i]
Step-16   a[i]=0
Step-17   if b>0 then goto Step-18 else goto Step-28
Step-18   for y=1 to y<=b inc=+1
Step-19   p=i+y
Step-20   p=p%n
Step-21   if a[p]==0 then goto Step-22 else goto Step-24
Step-22   b++
Step-23   end if
Step-24   end for
Step-25   i=i+b
Step-26   i=i%n
Step-27   goto Step-44
Step-28   for y=-1 to y>=b inc=-1
Step-29   p=i+y
Step-30   if p<0 then goto Step-31 else goto Step-35
Step-31   while p<0
Step-32   p=n+p
Step-33   end while
Step-34   end if
Step-35   if a[p]==0 then goto Step-36 else goto Step-38
Step-36   b--
Step-37   end if
Step-38   end for
Step-39   i=i+b
Step-40   while i<0
Step-41   i=i+n
Step-42   end while
Step-43   end if
STep-44   end for
Step=45   for x=0 to x<n inc=+1
Step-46   if a[x]!=0 then goto Step-47 else goto Step-50
Step-47   print("Lucky number="+a[x])
Step-48   break
Step-49   end if
Step-50   end for
Step-51   end main(String at[])
Step-52   end








import java.util.*;
import java.io.*;
class LuckyNumber
{
 public static void main(String at[])
 {
  Scanner sc=new Scanner(System.in);
  int n,a[],x,y,i=0,b=0,p=0;
  System.out.println("Enter length of an array");
  n=sc.nextInt();
  a=new int[n];
  System.out.println("Enter the position to start checking");
  i=sc.nextInt();
  for(x=0;x<n;x++)  //inputing
  { 
   System.out.println("Enter an integer");
   a[x]=sc.nextInt();
  }  //end of loop
  for(x=0;x<n-1;x++)  //for numbers to be deleted
  {
   b=a[i];
   a[i]=0;
   if(b>0)
   {
    for(y=1;y<=b;y++)  //Find 0's in the path
    {
     p=i+y;
     p=p%n;
     if(a[p]==0)
      b++;
    }  //end of loop
    i=i+b; 
    i=i%n; 
   }  //end of if
   else
   {
    for(y=-1;y>=b;y--)  //Find 0's in the path
    {
     p=i+y;
     if(p<0)
     {
      while(p<0)
       p=n+p;
     }
     if(a[p]==0)
      b--; 
    }  //end of loop
    i=i+b;
    while(i<0)  //for finding appropriate indexes
     i=i+n;
   }  //end of else
  }  //end of loop
  for(x=0;x<n;x++)  //for finding the lucky number
  {
   if(a[x]!=0)
   {
    System.out.print("Lucky number="+a[x]);
    break; 
   }
  }  //end of loop
 }  //end of main
}  //end of class
Enter length of an array
4
Enter the position to start checking
0
Enter an integer
2
Enter an integer
4
Enter an integer
1
Enter an integer
5
Lucky number=4


















/*Stack*/

Step-1    Stack(int size)
Step-2    a=new int[size]
Step-3    tos=-1
Step-4    end Stack(int size)
Step-5    push(int p)
Step-6    if tos==a.length-1 then goto Step-7 else goto Step-9
Step-7    print "Overflow"
Step-8    goto Step-10
Step-9    a[++tos]=p
Step-10   end if
Step-11   end push(int p)
Step-12   pop()
Step-13   if tos==-1 then goto Step-14 else goto Step-16
Step-14   return -9999
Step-15   goto Step-17
Step-16   return a[tos--]
Step-17   end if
Step-18   end pop()
Step-19   peek()
Step-20   if tos==-1 then goto Step-21 else goto Step-23
Step-21   return -9999
Step-22   goto Step-24
Step-23   return a[tos]
Step-24   end if
Step-25   end peek()
Step-26   end
Step-27   main(String at[])
Step-28   print "Enter length of Stack array
Step-29   input l
Step-30   s1=new Stack(l)
Step-31   do
Step-32   print "1-Push\n2-Pop\n3-Peek\n4-exit"
Step-33   input ch
Step-34   switch(ch)
Step-35   case 1:
Step-36   print "Enter element to be pushed"
Step-37   input p
Step-38   s1.push(p)
Step-39   break
Step-40   case 2:
Step-41   p=s1.pop()
Step-42   if p==-9999 then goto Step-43 else goto Step-45
Step-43   print "Underflow"
Step-44   goto Step-46
Step-45   print ("Popped value="+p)
Step-46   end if
Step-47   break
Step-48   case 3:
Step-49   p=s1.peek()
Step-50   if p==-9999 then goto Step-51 else goto Step-53
Step-51   print "Underflow"
Step-52   goto Step-54
Step-53   print("Peeked value="+p)
Step-54   end if
Step-55   break
Step-56   case 4:
Step-57   break
Step-58   default:
Step-59   print "Wrong Option");
Step-60   break
Step-61   end switch(ch)
Step-62   while(ch!=4)
Step-63   end do while
Step-64   end main(String at[])
Step-65   end


























import java.util.*;
import java.io.*;
class Stack
{
 private int a[],tos;
 public Stack(int size)
 {
  a=new int[size];
  tos=-1;
 }  //end of Stack constructor
 public void push(int p)
 {
  if(tos==a.length-1)
   System.out.println("Overflow");
  else
  {
   a[++tos]=p;
  }
 }  //end of push
 public int pop()
 {
  if(tos==-1)
   return -9999;
  else
  {
   return a[tos--];
  }
 }  //end of pop
 public int peek()
 {
  if(tos==-1)
   return -9999;
  else
   return a[tos];
 }
}  //end of class Stack

class q3_stack
{
 public static void main(String at[])
 {
  Scanner sc=new Scanner(System.in);
  int l,ch,p;
  System.out.println("Enter length of stack array");
  l=sc.nextInt();
  Stack s1=new Stack(l);
  do
  {
   System.out.println("1-Push\n2-Pop\n3-Peek\n4-Exit");
   ch=sc.nextInt();
   switch(ch)
   {
    case 1:
    System.out.println("Enter element to be pushed");
    p=sc.nextInt();
    s1.push(p);
    break;
    case 2:
    p=s1.pop(); 
    if(p==-9999)
     System.out.println("Underflow");
    else
     System.out.println("Poped value="+p);
    break;
    case 3:
    p=s1.peek();
    if(p==-9999)
     System.out.println("Underflow");
    else
     System.out.println("Peeked value="+p);
    break;
    case 4:
    break;
    default:
    System.out.println("Wrong option");
    break;
   }  //end of switch
  }  //end of do while loop
  while(ch!=4);
 }  //end of main
}  //end of class q3_stack












Enter length of stack array
5
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
1
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
2
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
3
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
4
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
5
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
6
Overflow
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=5
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=4
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=3
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=2
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=1
1-Push
2-Pop
3-Peek
4-Exit
4













/*Stack In Data Structures Using FIFO Technique(QUEUE)*/

Step-1   queue(int size)
Step-2   a=new int[size]
Step-3   f=-1
Step-4   r=-1
Step-5   end Stack(int size)
Step-6   push(int p)
Step-7   if r==a.length-1 then goto Step-8 else goto Step-10
Step-8   print "Overflow"
Step-9   goto Step-14
Step-10  if f==-1 then goto Step-11 else goto Step-12
Step-11  f=0
Step-12  r++
Step-13  a[r]=p
Step-14  end if
Step-15  end push(int p)
Step-16  pop()
Step-17  if f==-1||f>r then goto Step-18 else goto Step-20
Step-18  return -9999
Step-19  goto Step-23
Step-20  t=a[f]
Step-21  f++
Step-22  return t
Step-23  end if
Step-24  end pop()
Step-25  peek()
Step-26  if f==-1||f>r then goto Step-27 else goto Step-30
Step-27  f=r=-1
Step-28  return -9999
Step-29  goto step-31
Step-30  return a[f]
Step-31  end if
Step-32  end peek()
Step-33  end
Step-34  main(String at[])
Step-35  print "Enter length of queue array"
Step-36  input l
Step-37  q=new queue(l)
Step-38  do
Step-39  print "1-PUSH\t2-POP\t3-PEEK\t4-EXIT"
Step-40  input ch
Step-41  switch(ch)
Step-42  case 1:
Step-43  print "Element to be pushed"
Step-44  input w
Step-45  q.push(w)
Step-46  break;
Step-47  case 2:
Step-48  w=q.pop()
Step-49  if w==-9999 then goto Step-50 else goto Step-52
Step-50  print "Underflow"
Step-51  goto Step-53
Step-52  print ("Element popped"+w)
Step-53  end if
Step-54  break
Step-55  case 3:
Step-56  w=q.peek()
Step-57  if w=-9999 then goto Step-58 else goto Step-60
Step-58  print "Underflow"
Step-59  goto Step-61
Step-60  print ("Element peeked"+w)
Step-61  end if
Step-62  break
Step-63  case 4:
Step-64  break
Step-65  default:
Step-66  print "Invalid choice"
Step-67  end switch(ch)
Step-68  while ch!=4
Step-69  end do while
Step-70  end





















import java.util.*;
class queue
{
 private int a[];
 private int f ,r;
 public queue(int size)
 {
  a=new int[size];
  f=r=-1;
 }
 public void push(int p)  //entering element in the array
 {
  if(r==a.length-1)
   System.out.println("OVERFLOW");
  else
  {
   if(f==-1)
   f=0;
   r++;
   a[r]=p;
  }
 }
 public int pop()  // removing element from array
 {
  if(f==-1 || f>r)
   return -9999;
  else
  {
   int t=a[f];
   f++;
   return t;
  }
 }
 public int peek()
 {
  if(f==-1 || f>r)
  {
   f=r=-1;
   return -9999;
  }
  else 
   return a[f];
 }
}

class all
{
 public static void main(String at[])
 {
  Scanner sc=new Scanner (System.in);
  int ch,w,l;
  System.out.println("Enter length of queue array");
  l=sc.nextInt();
  queue q=new queue(l);
  do
  {
   System.out.println("1-PUSH\t2-POP\t3-PEEK\t4-EXIT");  //choice to user
   ch=sc.nextInt();
   switch(ch)
   {
    case 1:
    System.out.println("Element to be pushed");
    w=sc.nextInt();
    q.push(w);
    break;
    case 2:
    w=q.pop();
    if(w==-9999)
     System.out.println("Underflow");
    else
     System.out.println("Element popped"+w);
    break;
    case 3:
    w=q.peek();
    if(w==-9999)
     System.out.println("Underflow");
    else
     System.out.println("Element peeked"+w);
    break;
    case 4:
    break;
    default:
    System.out.println("Invalid choice");
   }
  }
  while(ch!=4);
 }
}





1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
12
1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
13
1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
14
1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
15
1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
16
1-PUSH  2-POP   3-PEEK  4-EXIT
1
enter value to be pushed
17
OVERFLOW
1-PUSH  2-POP   3-PEEK  4-EXIT
2
element popped12
1-PUSH  2-POP   3-PEEK  4-EXIT
2
element popped13
1-PUSH  2-POP   3-PEEK  4-EXIT
2
element popped14
1-PUSH  2-POP   3-PEEK  4-EXIT
2
element popped15
1-PUSH  2-POP   3-PEEK  4-EXIT
2
element popped16
1-PUSH  2-POP   3-PEEK  4-EXIT
2
underflow
1-PUSH  2-POP   3-PEEK  4-EXIT
3
underflow
1-PUSH  2-POP   3-PEEK  4-EXIT
4














/*Write a program to convert infix notation to postfix.*/

Step 1 start of class postfix
Step 2 main()
Step 3 s1=""
Step 4 z=0
Step 5 print enter infix expression
Step 6 input s
Step 7 arr[]=new char[s.length()]
Step 8 for(x=0;x<s.length();x++)
Step 9 c=s.charAt(x)
Step 10 if(('a'<=c && c<='z') || ('A'<=c && c<='Z'))
Step 11 s1=s1+c 
Step 12 else
Step 13 if(c=='-' || c=='+')
Step 14 for(y=arr.length-1;y>=0;y--)
Step 15 if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(') then break the loop
Step 16 if(arr[y]!='\u0000') then s1=s1+arr[y] and arr[y]='\u0000'
Step 17 end of inner for loop
Step 18 end of if block
Step 19 else
Step 20 if(c=='*' || c=='/')
Step 21 for(y=arr.length-1;y>=0;y--)
Step 22 if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(') the break the loop
Step 23 if((arr[y]!='\u0000') && (arr[y]!='+' && arr[y]!='-')) then s1=s1+arr[y] and arr[y]='\u0000'
Step 24 end of inner for loop
Step 25 end of if block
Step 26 else
Step 27 if(c=='^')
Step 28 for(y=arr.length-1;y>=0;y--)
Step 29 if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(') then break
Step 30 if((arr[y]!='\u0000') && (arr[y]!='+' && arr[y]!='-' && arr[y]!='*' && arr[y]!='/'))
Step 31 s1=s1+arr[y] and arr[y]='\u0000'
Step 32 end of inner for loop
Step 33 end of if block
Step 34 else
Step 35 if(c==']' || c=='}' || c==')')
Step 36 for(y=arr.length-1;y>=0;y--)
Step 37 if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(') then arr[y]='\u0000' and break
Step 38 if(arr[y]!='\u0000') then s1=s1+arr[y];
Step 39 arr[y]='\u0000'
Step 40 end of inner for
Step 41 end of if block
Step 42 for(y=0;y<arr.length-1;y++)
Step 43 if(arr[y]=='\u0000')
Step 44 for(z=y+1;z<arr.length-1;z++)
Step 45 if(arr[z]!='\u0000') then arr[y]=arr[z] and arr[z]='\u0000' and the break
Step 46 end of inner for loop
Step 47 if(c!=']' && c!='}' && c!=')')
Step 48 for(y=0;y<arr.length;y++)
Step 49 if(arr[y]=='\u0000') then arr[y]=c and break
Step 50 end of if
Step 51 if(x==s.length()-1)
Step 52 for(y=arr.length-1;y>=0;y--)
Step 53 if(arr[y]!='\u0000') then s1=s1+arr[y]
Step 54 end of outer for
Step 55 print postfix expression
Step 56 end of main()
Step 57 end of class postfix



import java.util.*;
class postfix
{
 public static void main(String ar[])
 {
  String s,s1="";
  int x,y,z=0;
  char c;
  Scanner sc=new Scanner(System.in);
  System.out.println("Enter infix expression");
  s=sc.nextLine();  //inputting the infix expression 
  char arr[]=new char[s.length()];
  for(x=0;x<s.length();x++)
  {
   c=s.charAt(x);
   if(('a'<=c && c<='z') || ('A'<=c && c<='Z'))//checking if the character is a letter or not
   s1=s1+c; 
   else
   {
    if(c=='-' || c=='+')
    {
     for(y=arr.length-1;y>=0;y--)
     { 
      if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(')
      break;
      if(arr[y]!='\u0000')
      s1=s1+arr[y];
      arr[y]='\u0000';
     }
    }
    else
    if(c=='*' || c=='/')
    { 
     for(y=arr.length-1;y>=0;y--)
     {
      if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(')
      break;
      if((arr[y]!='\u0000') && (arr[y]!='+' && arr[y]!='-'))
      {
       s1=s1+arr[y];
       arr[y]='\u0000';
      }
     }
    }
    else
    if(c=='^')
    {
    for(y=arr.length-1;y>=0;y--)
     {
      if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(')
      break;
      if((arr[y]!='\u0000') && (arr[y]!='+' && arr[y]!='-' && arr[y]!='*' && arr[y]!='/'))
      {
       s1=s1+arr[y];
       arr[y]='\u0000';
      }
     }
    }
    else
    if(c==']' || c=='}' || c==')')
    {
     for(y=arr.length-1;y>=0;y--)
     {
      if(arr[y]=='[' || arr[y]=='{' || arr[y]=='(')
      {
       arr[y]='\u0000';
       break;
      }
      if(arr[y]!='\u0000')
      s1=s1+arr[y];
      arr[y]='\u0000';
     }            
    }
    for(y=0;y<arr.length-1;y++)
    {
     if(arr[y]=='\u0000')
     {
      for(z=y+1;z<arr.length-1;z++)
      {
       if(arr[z]!='\u0000')
       {
        arr[y]=arr[z];
        arr[z]='\u0000';
        break;
       } 
      }
     }
    }
    if(c!=']' && c!='}' && c!=')')
    {
     for(y=0;y<arr.length;y++)
     {
      if(arr[y]=='\u0000')
      {
       arr[y]=c;
       break;
      }    
     }
    }
   }
   if(x==s.length()-1)
   {  
    for(y=arr.length-1;y>=0;y--)
    {
     if(arr[y]!='\u0000')
     s1=s1+arr[y];
    }
   }
  }
  System.out.println("Postfix expression:"+s1);  //command to print the postfix expression
 }
}












Enter infix expression
a/b+c*d-e^f+g/h
Postfix expression:ab/cd*+ef^-gh/+



























/*TO perform File Handling in character stream and changing a students' name and marks.*/

Step 1 start of class filehandling
Step 2 start of main()
Step 3 while(true)
Step 4 f1=new FileWriter("temp.txt")
Step 5 p1=new PrintWriter(f1)
Step 6 f2=new FileReader("xyz.txt")
Step 7 b1=new BufferedReader(f2)
Step 8 print enter choice
Step 9 start of main switch
Step 10 case 1
Step 11 print Enter Roll no. & New name
Step 12 input r
Step 13 input n
Step 14 while((m=b1.readLine())!=null)
Step 15 k=m.split("@")
Step 16 if(Integer.parseInt(k[0])==r) then print k[0]+"@"+n+"@"+k[2]+"@"+k[3] on text file
Step 17 else print value of m on text file
Step 18 end of while
Step 19 close the streams b1,f2,p1 and f1
Step 20 f=new File("xyz.txt")
Step 21 f.delete()
Step 22 create a temporary file
Step 23 rename the file
Step 24 end of case 1
Step 25 case 2
Step 26 ask for user's choice
Step 27 start of nested switch
Step 28 case 1
Step 29 input r
Step 30 input m1
Step 31 while((m=b1.readLine())!=null) 
Step 32 k=m.split("@")
Step 33 if(Integer.parseInt(k[0])==r) then print k[0]+"@"+k[1]+"@"+m1+"@"+k[3] on text file
Step 34 else print value of m on text file
Step 35 end of while
Step 36 close the streams b1,f2,p1,f1
Step 37 f=new File("xyz.txt")
Step 38 f.delete()
Step 39 create a temporary file
Step 40 rename the file
Step 41 case 2
Step 42 print "Enter new marks in Computer"
Step 43 while((m=b1.readLine())!=null)
Step 44 input m1
Step 45 k=m.split("@")
Step 46 print k[0]+"@"+k[1]+"@"+m1+"@"+k[3] on text file
Step 47 end of while
Step 48 close the streams b1,f2,p1,f1
Step 49 f=new File("xyz.txt")
Step 50 f.delete()
Step 51 create a temporary file
Step 52 rename the file
Step 53 default case
Step 54 end of nested switch
Step 55 end of case 2
Step 56 case 3
Step 57 start of nested switch
Step 58 case 1
Step 59 input r
Step 60 input m1
Step 61 while((m=b1.readLine())!=null)
Step 62 k=m.split("@")
Step 63 if(Integer.parseInt(k[0])==r) then print k[0]+"@"+k[1]+"@"+k[2]+"@"+m1 on the file
Step 64 else print value of m on text file
Step 65 end of while
Step 66 close the streams b1,f2,p1,f1
Step 67 f=new File("xyz.txt")
Step 68 f.delete()
Step 69 create a temporary file
Step 70 rename the file
Step 71 case 2
Step 72 print Enter new marks in English
Step 73 while((m=b1.readLine())!=null)
Step 74 input m1
Step 75 k=m.split("@")
Step 76 print k[0]+"@"+k[1]+"@"+k[2]+"@"+m1 on the file
Step 77 end of while
Step 78 close the streams b1,f2,p1,f1
Step 79 f=new File("xyz.txt")
Step 80 f.delete()
Step 81 create a temporary file
Step 82 rename the file
Step 83 default case
Step 84 print wrong option
Step 85 end of nested switch
Step 86 end of case 3
Step 87 case 4
Step 88 break labelled while loop
Step 89 default case
Step 90 print wrong option
Step 91 end of main switch
Step 92 end of while
Step 93 end of main()
Step 94 end of class filehandling




























import java.io.*;
class filehandling
 {
 public static void main(String ar[])throws Exception
 {
 DataInputStream z=new DataInputStream(System.in);
 String n,m;
 String k[];
 int r;
 double m1;
 FileWriter f1;
 PrintWriter p1;
 FileReader f2;
 BufferedReader b1;
 File f;
 ab:while(true)
  {
   f1=new FileWriter("temp.txt");
   p1=new PrintWriter(f1);
   f2=new FileReader("xyz.txt");
   b1=new BufferedReader(f2);
   System.out.println("Enter choice \n1. To change Name\n2. To change Computer marks\n3. To change English marks\n4. Exit");
   switch(Integer.parseInt(z.readLine()))  //main loop
    {
     case 1:
     System.out.println("Enter Roll no. & New name");
     r=Integer.parseInt(z.readLine());   //asking input
     n=z.readLine();
     while((m=b1.readLine())!=null)
      {
       k=m.split("@");
       if(Integer.parseInt(k[0])==r)
       p1.println(k[0]+"@"+n+"@"+k[2]+"@"+k[3]);
       else
       p1.println(m);
      }
     b1.close();
     f2.close();
     p1.close();
     f1.close();
     f=new File("xyz.txt");      
     f.delete();
     f=new File("temp.txt");
     f.renameTo(new File("xyz.txt"));   //renaming file
     break;
    case 2:
    System.out.println("Enter Choice\n1.Particular Student\n2.All Students");
    switch(Integer.parseInt(z.readLine()))   //asking choice from user
    {
      case 1:
      System.out.println("Enter Roll number and new marks in Computer");
      r=Integer.parseInt(z.readLine());
      m1=Double.parseDouble(z.readLine());
      while((m=b1.readLine())!=null) 
       {
        k=m.split("@");
        if(Integer.parseInt(k[0])==r)
        p1.println(k[0]+"@"+k[1]+"@"+m1+"@"+k[3]);
        else
        p1.println(m);
       }
      b1.close();         //closing the streams
      f2.close();
      p1.close();
      f1.close();
      f=new File("xyz.txt");
      f.delete();
      f=new File("temp.txt");
      f.renameTo(new File("xyz.txt")); 
      break;
      case 2:
      System.out.println("Enter new marks in Computer");
      while((m=b1.readLine())!=null)
        {
         m1=Double.parseDouble(z.readLine());
         k=m.split("@");
         p1.println(k[0]+"@"+k[1]+"@"+m1+"@"+k[3]);
        }
      b1.close();
      f2.close();
      p1.close();
      f1.close();
      f=new File("xyz.txt");
      f.delete();
      f=new File("temp.txt");
      f.renameTo(new File("xyz.txt")); 
      break;
      default:
      System.out.println("Wrong Input");
    }
    break;
    case 3:
    System.out.println("Enter Choice\n1.Particular Student\n2.All Students");
    switch(Integer.parseInt(z.readLine()))
    {
    case 1:
    System.out.println("Enter Roll Number & new marks in English");
    r=Integer.parseInt(z.readLine());
    m1=Double.parseDouble(z.readLine());
    while((m=b1.readLine())!=null)
    {
    k=m.split("@");
    if(Integer.parseInt(k[0])==r)
    p1.println(k[0]+"@"+k[1]+"@"+k[2]+"@"+m1);
    else
    p1.println(m);
    }
    b1.close();
    f2.close();
    p1.close();
    f1.close();
    f=new File("xyz.txt");
    f.delete();
    f=new File("temp.txt");
    f.renameTo(new File("xyz.txt")); 
    break;
    case 2:
    System.out.println("Enter new marks in English");
    while((m=b1.readLine())!=null) 
     {   
      m1=Double.parseDouble(z.readLine()); 
      k=m.split("@");
      p1.println(k[0]+"@"+k[1]+"@"+k[2]+"@"+m1);
     }
     b1.close();
     f2.close();
     p1.close();
     f1.close();
     f=new File("xyz.txt");
     f.delete();
     f=new File("temp.txt");
     f.renameTo(new File("xyz.txt")); 
     break;
     default:
     System.out.println("Wrong Option");
   }
    break;
    case 4:
    break ab; 
    default:
    System.out.println("Wrong Option");
   }
  }
 }
}









type xyz.txt
1@rmn@23.0@32.0
2@def@43.0@45.0
3@fgh@56.0@65.0
4@rts@78.0@89.0
5@xyz@99.0@100.0

 java filehandling
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
1
Enter Roll no. & New name
2
erfg
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
2
Enter Choice
1.Particular Student
2.All Students
1
Enter Roll number and new marks in Computer
1
88.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
2
Enter Choice
1.Particular Student
2.All Students
2
Enter new marks in Computer
11.0
12.0
13.0
14.0
15.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
3
Enter Choice
1.Particular Student
2.All Students
1
Enter Roll Number & new marks in English
3
67.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
3
Enter Choice
1.Particular Student
2.All Students
2
Enter new marks in English
17.0
18.0
19.0
20.0
21.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
4

type xyz.txt
1@rmn@11.0@17.0
2@erfg@12.0@18.0
3@fgh@13.0@19.0
4@rts@14.0@20.0
5@xyz@15.0@21.0




/*Write a Program to input 2 words.
Rotate one word both leftwards and rightwards to obtain the second word*/

Step 1 main()
Step 2 input s
Step 3 input b
Step 4 w=b
Step 5 w1=b
Step 6 c=0
Step 7 while(true)
Step 8 w=w.charAt(w.length()-1)+w.substring(0,w.length()-1)
Step 9 w1=w1.substring(1,w1.length())+w1.charAt(0)
Step 10 c++
Step 11 if(w.equals(s)||w1.equals(s)) 
Step 12 break
Step 13 else if(w.equals(b) && w1.equals(b))
Step 14 System.out.println("NOT POSSIBLE")
Step 15 if(w.equals(s))
Step 16 System.out.println("Right rotation")
Step 17 System.out.println("No. of rotations = "+c)
Step 18 if(w1.equals(s))
Step 19 System.out.println("Left rotation")
Step 20 System.out.println("No. of rotations = "+c)
Step 21 end







import java.util.*;
class rotate
{
 public static void main(String at[])
 {
  Scanner sc=new Scanner(System.in);
  String s=sc.nextLine();
  String b=sc.nextLine();
  String w=b,w1=b;
  int c=0;
  while(true)
  {
   w=w.charAt(w.length()-1)+w.substring(0,w.length()-1);
   w1=w1.substring(1,w1.length())+w1.charAt(0);
   c++;
   if(w.equals(s)||w1.equals(s))
   break;
   else
   if(w.equals(b) && w1.equals(b))
   {
    System.out.println("NOT POSSIBLE");
    break;
   } 
  }
  System.out.println();
  if(w.equals(s))
  {
   System.out.println("Right rotation");
   System.out.println("No. of rotations = "+c);
  }
  if(w1.equals(s))
  {
   System.out.println("Left rotation");
   System.out.println("No. of rotations = "+c);
  }
 }
}

























abcde
cdeab

Right rotation
No. of rotations = 2


























/*Write the code of circular queue*/

Step 1   CircularQueue(int size)
Step 2   a=new int[size]
Step 3   f=r=-1
Step 4   max=size
Step 5   void push(int p)
Step 6   if(f==0 && r==max-1|| f==r+1) goto step 7 else goto step 8
Step 7   print "overflow"
Step 8   if(f==-1) goto step 9
Step 9   f=0;
Step 10  r=(r+1)%max
Step 11  a[r]=p
Step 12  end push(int p)
Step 13  int pop()
Step 14  if(f==-1)
Step 15  return -9999
Step 16  n=a[f];
Step 17  if(f==r) goto step 17 else goto step 18 
Step 18  f=r=-1
Step 19  f=(f+1)%max
Step 20  return n
Step 21  end pop()   
Step 22  int peek()
Step 23  if(f==-1) goto step 22 else goto step 23
Step 24  return -9999        
Step 25  return a[f]
Step 26  end peek()
Step 27  main()
Step 28  print "enter size"
Step 29  q=new Circularqueue(input size)
Step 30  do
Step 31  print"1 - Push\n2 - Pop\n3 - Peek\n4 - Exit"
Step 32  input ch
Step 33  case 1
Step 34  print "element to be pushed"
Step 35  input w
Step 36  q.push(w)
Step 37  break
Step 38  case 2
Step 39  w=q.pop()
Step 40  if(w==-9999) goto step 38 else goto step 39
Step 41  print "underflow"
Step 42  print "elememt popped"+w
Step 43  break
Step 44  case 3
Step 45  w=q.peek()
Step 46  if(w==-9999) goto step 44 else goto step 45
Step 47  print "underflow"
Step 48  print "element peeked is"+w
Step 49  break
Step 50  case 4
Step 51  default
Step 52  print "invalid choice"
Step 53  while(ch!=4)
Step 54  end dowhile
Step 55  end





import java.util.*;
class CircularQueue
{
 private int a[];
 private int f,r,max;
 public CircularQueue(int size)
 {
  a=new int[size];
  f=r=-1;
  max=size;
 }
 public void push(int p)
 {
  if(f==0&&r==max-1||f==r+1)
  System.out.println("Overflow");
  else
  {
   if(f==-1)
   f=0;
   r=(r+1)%max;
   a[r]=p;
  }
 }
 public int pop()
 {
  if(f==-1)
  return -9999;
  else
  {
   int n=a[f];
   if(f==r)
   f=r=-1;
   else 
   f=(f+1)%max;
   return n;
  }
 }
 public int peek()
 {
  if(f==-1)
  return -9999;
  else 
  return a[f];
 }
}
class exec
{
 public static void main(String at[])
 {
  System.out.println("Enter size");
  Scanner sc=new Scanner(System.in);
  CircularQueue q=new CircularQueue(sc.nextInt());
  int ch,w;
  do
  {
   System.out.println("1 - Push\n2 - Pop\n3 - Peek\n4 - Exit");
   ch=sc.nextInt();
   switch(ch)
   {
    case 1:
    System.out.println("Enter element to push");
    w=sc.nextInt();
    q.push(w);
    break;
    case 2:
    w=q.pop();
    if(w==-9999)
    System.out.println("Underflow");
    else
    System.out.println("Element popped is "+w);
    break;
    case 3:
    w=q.peek();
    if(w==-9999)
    System.out.println("Underflow");
    else 
    System.out.println("Element peeked is "+w);
    break;
    case 4:
    break;
    default:
    System.out.println("Invalid choice");
   }
  }
  while(ch!=4);
 }
}






Enter size
5
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
4
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
3
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
8
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
5
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
1
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
22
Overflow
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 4
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
22
1 - Push
2 - Pop
3 - Peek
4 - Exit
3
Element peeked is 3
1 - Push
2 - Pop
3 - Peek
4 - Exit
1
Enter element to push
33
Overflow
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 3
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 8
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 5
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 1
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Element popped is 22
1 - Push
2 - Pop
3 - Peek
4 - Exit
2
Underflow
1 - Push
2 - Pop
3 - Peek
4 - Exit
4










/* Program to find out the shortest possible substring from a given string. Both the strings are given by the user and the substring must contain all the characters of the smallest string given in any order.*/

Step 1  main
Step 2  DataInputStream z = new DataInputStream(System.in);
Step 3  input s1,s2
Step 4  l1 = s1.length();
Step 5  l2 = s2.length();
Step 6  k1 = s1.toCharArray();
Step 7  k2 = s2.toCharArray();
Step 8  int ll1 = l1, ll2 = l2;
Step 9  String arr[] = new String[l1];
Step 10  for x=0 t0 l1 inc +1
Step 11  arr[x] = "";
Step 12  int check = 0, crosscheck = 0;
Step 13  for x=0 to ll1-ll2 inc +1
Step 14  for i=0 to l1 inc i++
Step 15  for j=0 to l2 inc j++
Step 16  if (k1[i] == k2[j] || k1[i] == (char)(k2[j] + 32) || k1[i] == (char)(k2[j] - 32))
         then go to Step 17 else go to step 21
Step 17  arr[x] = arr[x] + k1[i];
Step 18  k2[j] = '\u0000';
Step 19  check++;
Step 20  break;
Step 21  end if
Step 22  if (crosscheck != 0 && check != 0) 
Step 23  if (crosscheck == check)
Step 24  arr[x] = arr[x] + k1[i];
Step 25  crosscheck = check;
Step 26  if (check == k2.length) then go to Step 27 else go to step 28
Step 27  break;
Step 28  end for
Step 29  if (check != k2.length) then go to Step 30 else go to step 31
Step 30  arr[x] = "";
Step 31  check = 0;
Step 32  crosscheck = 0;
Step 33  sb = new StringBuffer(s1);
Step 34  sb.deleteCharAt(0);
Step 35  s1 = sb.toString();
Step 36  k1 = s1.toCharArray();
Step 37  k2 = s2.toCharArray();
Step 38  l1 = s1.length();
Step 39  l2 = s2.length();
Step 40  end for
Step 41  s = arr[0];
Step 42  for x=0 to x<= ll1-ll2 inc +1
Step 43  if (arr[x].equals("")) then go to Step 44 else go to step 45
Step 44  continue;
Step 45  if (arr[x].length() < s.length()) then go to Step 46 else go to step 47
Step 46  s = arr[x];
Step 47  end for
Step 48  if (s.equals(""))
Step 49  print "NO  POSSIBLE SUBSTRING WAS FOUND"
Step 50  else
Step 51  print "Your Substring:    " + s 
Step 52  end main





import java.util.*;
import java.lang.*;
import java.io.*;
class SubString {
    public static void main(String[] args) throws java.lang.Exception {
        DataInputStream z = new DataInputStream(System.in);
        String s2, s1, s;
        int i, j, x, l1, l2;
        System.out.println("Enter the String");
        s1 = z.readLine();                                                    //Input
        System.out.println("Enter another string");
        s2 = z.readLine();
        l1 = s1.length();
        l2 = s2.length();
        char k1[], k2[];
        k1 = s1.toCharArray();
        k2 = s2.toCharArray();
        int ll1 = l1, ll2 = l2;
        StringBuffer sb;
        String arr[] = new String[l1];
        for (x = 0; x < l1; x++)
            arr[x] = "";
        int check = 0, crosscheck = 0;
        for (x = 0; x <= ll1 - ll2; x++) {
            for (i = 0; i < l1; i++) {
                for (j = 0; j < l2; j++) {
                    if (k1[i] == k2[j] || k1[i] == (char)(k2[j] + 32) || k1[i] == (char)(k2[j] - 32)) {
                        arr[x] = arr[x] + k1[i];
                        k2[j] = '\u0000';
                        check++;
                        break;
                    }
                }
                if (crosscheck != 0 && check != 0)
                    if (crosscheck == check)
                        arr[x] = arr[x] + k1[i];
                crosscheck = check;
                if (check == k2.length)
                    break;
            }
            if (check != k2.length)
                arr[x] = "";
            check = 0;
            crosscheck = 0;
            sb = new StringBuffer(s1);
            sb.deleteCharAt(0);
            s1 = sb.toString();
            k1 = s1.toCharArray();
            k2 = s2.toCharArray();
            l1 = s1.length();
            l2 = s2.length();
        }
        s = arr[0];
        for (x = 0; x <= ll1 - ll2; x++) {
            if (arr[x].equals(""))
                continue;
            if (arr[x].length() < s.length())
                s = arr[x];
        }
        if (s.equals(""))
            System.out.println("\n" + "NO  POSSIBLE SUBSTRING WAS FOUND" + "\n");
        else
            System.out.println("\n" + "Your Substring:    " + s + "\n");
    }
}




























Enter the String
rfuyeruyhbhvhdshghddf
Enter another string
Yhds

Your Substring:    yhbhvhds

























/* Decode.*/

Step 1  main 
Step 2  DataInputStream z1 = new DataInputStream(System.in);
Step 3  input s1,s2
Step 4  l1=s1.length();
Step 5  l2 = s2.length();
Step 6  if (l1 < l2) then goto Step 7 else goto 9
Step 7  print "Invalid Input"
Step 8  System.exit(0);
Step 9  for x=0 to l1-l2 inc +1 
Step 10  for y=-20 to 100 inc +1
Step 11  if (s1.charAt(x) == (char)(s2.charAt(0) + y))
Step 12  count++
Step 13  for z=1 to l2 inc++
Step 14  if (s1.charAt(x + z) == (char)(s2.charAt(z) + y))
Step 15  count++
Step 16  else
Step 17  break
Step 18  end if
Step 19  end for
Step 20  if (count == l2)
Step 21  break
Step 22  else
Step 23  count =0;
Step 24  end for
Step 25  if (y != 101)
Step 26  break;
Step 27  end for
Step 28  if (y != 101) then goto Step 29 else goto 31
Step 29  for x=0 to l1 inc +1
Step 30  print (char)(s1.charAt(x) - y)
Step 31  else 
Step 32  print "The encoding variable is out of range"
Step 33  end main



























import java.util.*;
import java.lang.*;
import java.io.*;
class decode {
    public static void main(String[] args) throws java.lang.Exception {
        DataInputStream z1 = new DataInputStream(System.in);
        String s1, s2;
        System.out.println("\n" + "Enter the encoded string");
        s1 = z1.readLine();                                                                            //Input	                       
        System.out.println("\n" + "Enter the Substring of original String");
        s2 = z1.readLine();
        int l1, l2, x, y = 0, z, count = 0;
        l1 = s1.length();
        l2 = s2.length();
        if (l1 < l2) {
            System.out.println("\n" + "Inavlid Input");
            System.exit(0);
        }

        for (x = 0; x <= l1 - l2; x++) {
            for (y = -20; y < 101; y++) {
                if (s1.charAt(x) == (char)(s2.charAt(0) + y)) {
                    count++;
                    for (z = 1; z < l2; z++) {
                        if (s1.charAt(x + z) == (char)(s2.charAt(z) + y))
                            count++;
                        else
                            break;
                    }
                }

                if (count == l2)
                    break;
                else
                    count = 0;
            }
            if (y != 101)
                break;
        }
        if (y != 101) {
            System.out.println();
            for (x = 0; x < l1; x++) {
                System.out.print((char)(s1.charAt(x) - y));
            }
            System.out.println();
        } else
            System.out.println("The encoding variable is out of range");
    }
}













Enter the encoded string:
h\]g4]g4am4gW\cc`B4]h4]g4]b4_]XkU]4bU[UfB
Enter the Substring of original String:
IS

Origianl String:
THIS IS MY SCHOOL. IT IS IN KIDWAI NAGAR.
























/* program to check whether the coordinates of the inputted cell are correct or not.*/

Step 1  main 
Step 2  DataInputStream dr=new DataInputStream(System.in) 
Step 3  input cell
Step 4  int x1[]=new int[cell] 
Step 5  int y1[]=new int[cell] 
Step 6  int x2[]=new int[cell] 
Step 7  int y2[]=new int[cell] 
Step 8  String loc[]=new String[cell] 
Step 9  for x=0 to cell inc +1
Step 10  loc[x]=dr.readLine()    
Step 11  int length=loc[x].length() 
Step 12  while(loc[x].charAt(l)!=',')
Step 13  X1=X1+loc[x].charAt(l) 
Step 14  l=l+1 
Step 15  end while
Step 16  x1[x]=Integer.parseInt(X1);
Step 17  l=l+1;
Step 18  while(loc[x].charAt(l)!=' ')
Step 19  Y1=Y1+loc[x].charAt(l);
Step 20  l=l+1;
Step 21  end while
Step 22  y1[x]=Integer.parseInt(Y1);
Step 23  l=l+1;
Step 24  while(loc[x].charAt(l)!=',')
Step 25  X2=X2+loc[x].charAt(l);
Step 26  l=l+1;
Step 27  end while
Step 28  x2[x]=Integer.parseInt(X2);
Step 29  l=l+1;
Step 30  while(l<length)
Step 31  Y2=Y2+loc[x].charAt(l);
Step 32  l=l+1;
Step 33  end while
Step 34  y2[x]=Integer.parseInt(Y2);
Step 35  l=0;
Step 36  if(x1[x]>x2[x]&&y1[x]>y2[x]) then goto Step 37 else go to Step 40 
Step 37  r1=x1[x];
Step 38  x1[x]=x2[x];
Step 39  x2[x]=r1;
Step 40  end if
Step 41  if(x1[x]>x2[x]&&y2[x]>y1[x]) then goto Step 42 else go to Step 47
Step 42  r1=x1[x];
Step 43  r2=y1[x];
Step 44  x1[x]=x2[x]
Step 45  y1[x]=y2[x];
Step 46  x2[x]=r1;
Step 47  end if
Step 48  if(x2[x]>x1[x]&&y2[x]>y1[x]) then goto Step 49 else go to Step 52 
Step 49  r1=y1[x];
Step 50  y1[x]=y2[x];
Step 51  y2[x]=r1;
Step 52  end if
Step 53  sum1=sum1+(int)(((Math.abs(y2[x]-y1[x]))-1)*((Math.abs(x2[x]-x1[x]))-1));  
Step 54  sum2=sum2+(int)((Math.abs(y2[x]-y1[x])+1)*(Math.abs(x2[x]-x1[x])+1));
Step 55  end for
Step 56  String inner[]=new String[sum1+sum2];
Step 57  for x=0 to cell inc +1
Step 58  for a=x1[x]+1 to x2[x]-1 inc +1
Step 59  for b=y1[x]-1 to y2[x]-1 inc -1
Step 60  inner[pos] = "" + a + b
Step 61  pos++;
Step 62  end for
Step 63  end for
Step 64  end for
Step 65  for x=0 to cell inc +1
Step 66  for a=x1[x] to x2[x] inc +1
Step 67  for b=y1[x] to y2[x] inc -1 
Step 67  inner[pos] = "" + a + b;
Step 68  pos++;
Step 69  end for
Step 70  end for
Step 71  end for
Step 72  for x=0 to sum1 inc +1
Step 73  for y=0 to sum1+sum2 inc +1
Step 74  if (inner[x].equals(inner[y])) then goto Step 75 else go to Step 76
Step 75  check = check + 1;
Step 76  end for
Step 77  end for
Step 78  if (check == (sum1 * 2)) then goto Step 79 else go to Step 80
Step 79  print "Valid Data"
Step 80  print "Invalid Data" 
Step 81  end main









import java.util.*;
import java.lang.*;
import java.io.*;
class zoocells{
	public static void main (String[] args) throws java.lang.Exception{
        DataInputStream dr=new DataInputStream(System.in);		
	int cell=Integer.parseInt(dr.readLine());
	int x1[]=new int[cell];
	int y1[]=new int[cell];
	int x2[]=new int[cell];
	int y2[]=new int[cell];
	String loc[]=new String[cell];
	String X1="",Y1="",X2="",Y2="";
	int x,y,sum1=0,a,b,pos=0,sum2=0,check=0,l=0,r1,r2;
	
	for(x=0;x<cell;x++){
	    loc[x]=dr.readLine();                                           //Input
	    int length=loc[x].length();
	    while(loc[x].charAt(l)!=',') {
	    X1=X1+loc[x].charAt(l);
	    l=l+1;
	    }
	    x1[x]=Integer.parseInt(X1);
	    l=l+1;
	    while(loc[x].charAt(l)!=' '){	
	    	Y1=Y1+loc[x].charAt(l);
	    	l=l+1;
	    }
	    y1[x]=Integer.parseInt(Y1);
	    l=l+1;
	     while(loc[x].charAt(l)!=','){
	    X2=X2+loc[x].charAt(l);
	    l=l+1;
	    }
	    x2[x]=Integer.parseInt(X2);
	    l=l+1;
	    while(l<length){
	    	Y2=Y2+loc[x].charAt(l);
	    	l=l+1;
	    }
	    y2[x]=Integer.parseInt(Y2);
	    l=0;
	    X1="";Y1="";X2="";Y2="";
	  	if(x1[x]>x2[x]&&y1[x]>y2[x]){
			r1=x1[x];
			x1[x]=x2[x];
			x2[x]=r1;
		}
		if(x1[x]>x2[x]&&y2[x]>y1[x]){
			r1=x1[x];
			r2=y1[x];
			x1[x]=x2[x];
			y1[x]=y2[x];
			x2[x]=r1;
			y2[x]=r2;
		}
		if(x2[x]>x1[x]&&y2[x]>y1[x]){
			r1=y1[x];
			y1[x]=y2[x];
			y2[x]=r1;
		}
		sum1=sum1+(int)(((Math.abs(y2[x]-y1[x]))-1)*((Math.abs(x2[x]-x1[x]))-1));
		sum2=sum2+(int)((Math.abs(y2[x]-y1[x])+1)*(Math.abs(x2[x]-x1[x])+1));
	        }
	        String inner[]=new String[sum1+sum2];
                for (x = 0; x < cell; x++) {
                 for (a = x1[x] + 1; a < x2[x]; a++) {
                  for (b = y1[x] - 1; b > y2[x]; b--) {
                      inner[pos] = "" + a + b;
                      pos++;
                      }
                    }
                  }
                for (x = 0; x < cell; x++) {
                 for (a = x1[x]; a <= x2[x]; a++) {
                  for (b = y1[x]; b >= y2[x]; b--) {
                    inner[pos] = "" + a + b;
                    pos++;
                     }
                   }
                 }
               for (x = 0; x < sum1; x++) {
                 for (y = 0; y < (sum1 + sum2); y++) {
                  if (inner[x].equals(inner[y])) check = check + 1;
                   }
                 }
                if (check == (sum1 * 2)) System.out.println("Valid Data");
                 else 
                 System.out.println("Invalid Data");
             }
       }


Enter the no of cells
5
Enter the coordinates of the cells
6 , 7     3 , 4
1 , 1     2 , 2
0 , 0     1 , 1
3 , 4     2 , 2
5 , 3     7 , 4
Valid Data






















/*program to check whether the given number is a disarium number or not*/

Step 1  disarium(int nn)
Step 2  num=nn
Step 3  size=0
Step 4  end disarium(int nn)
Step 5  void countDigit()
Step 6  int temp=num
Step 7  while (temp!=0)
Step 8  size++
Step 9  temp=temp/10
Step 10  end while
Step 11  end void countDigit()
Step 12  int sumOfDigits(int n,int p)
Step 13  if (n==0) then go to step 15 else go to step 16
Step 14  return 0
Step 15  return (int)(Math.pow(n%10,p--))+sumOfDigits(n/10,p)
Step 16  end sumOfDigits(int n,int p)
Step 17  void check()
Step 18  call countDigit()
Step 19  if(sumOfDigits(num,size)==num) then go to step 21 else step 22
Step 20  print ("It is a disarium number")
Step 21  print ("It is not a disarium number")
Step 22  end void check()
Step 23  main 
Step 24  input n
Step 25  disarium d1=new disarium(n)
Step 26  d1.check();
Step 27  end main


import java.util.*;
class disarium
{
	private int num,size;
	public disarium(int nn) //parameterized constructor
	{
		num=nn;
		size=0;
	}
	public void countDigit()
	{
		int temp=num;
		while(temp!=0)
		{
			size++;
			temp/=10;
		}
	}
	public int sumOfDigits(int n,int p)
	{
		if(n==0)
			return 0;
		else
			return (int)(Math.pow(n%10,p--))+sumOfDigits(n/10,p);
	}
	public void check()
	{
		countDigit();
		if(sumOfDigits(num,size)==num)
			System.out.print("It is a disarium number");
		else
			System.out.print("It is not a disarium number");
	}
	public static void main(String a[])
	{
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		disarium d1=new disarium(n);
		d1.check();
	}
}





















123
It is not a disarium number

175
It is a disarium number

























/*Program to input positions of points in an array of mxn. Calculate the area of largest rectangle made by those points.*/

Step 1  main
Step 2  input row,column
Step 3  array[][]=int[row][column]
Step 4  for i=0 to row inc +1
Step 5  for j=0 to column inc +1
Step 6  array[i][j]=s.nextInt()
Step 7  for i=0 to row inc +1
Step 8  for j=0 to column inc +1
Step 9  for m=i to row inc +1
Step 10  for n=j to column inc +1
Step 11  if((m-i)!=(n-j)&&(m-i)!=0&&(n-j)!=0) then go to step 12 else go to step 21
Step 12  labelled for k=i to m inc +1
Step 13  for l=j to n inc +1
Step 14  if(array[k][l]==0) then go to step 15 else go to step 16
Step 15  break the labelled for
Step 16  if(k==m+1&&l==n+1) then go to step 17 else go to step 18
Step 17  area=(m-i+1)*(n-j+1)
Step 18  if(area>largest) then go to step 19 else go to step 20
Step 19  largest=area
Step 20  end if
Step 21  print largest
Step 22  end main






import java.util.*;
class HighestArea
{
	public static void main(String jk[])
	{
		Scanner s=new Scanner(System.in);
		int row,column,i,j,lengthy,breadth,k,l=0,area=0,largest=0,m,n;
                System.out.println("Enter no. of rows");
		row=s.nextInt(); //inputting dimensions of array
                System.out.println("Enter no. of columns");
		column=s.nextInt();
		int array[][]=new int[row][column];
		for(i=0;i<row;i++)
			for(j=0;j<column;j++)
				array[i][j]=s.nextInt();
		for(i=0;i<row;i++) //to calculate area of every possible combination of rectangle
			for(j=0;j<column;j++)
				for(m=i;m<row;m++)
					for(n=j;n<column;n++)
						if((m-i)!=(n-j) && (m-i)!=0 && (n-j)!=0)
						{
							first:for(k=i;k<=m;k++)
								for(l=j;l<=n;l++)
									if(array[k][l]==0)
										break first;
									if(k==m+1 && l==n+1)
										area=(m-i+1)*(n-j+1);
									if(area>largest) //finding largest area
										largest=area;
						}
		System.out.print(largest);
	}//end of main
}//end of class




























Enter number of rows 
3
Enter number of columns
4
Enter points
1 1 1 0
1 1 1 0
1 1 1 0
Largest Area
9




















/*define a superclass Product to store the details of a product sold by a wholesaler to a retailer. Define a subclass Sales to compute the total amount paid by the retailer with or without fine along with service tax.
Some of the members of both classes are given below:
Class name: Product
Data members/instance variables:
name: stores the name of the product
code: integer to store the product code
amount: stores the total sale amount of the product (in decimals)
Member functions/methods:
Product (String n, int c, double p): parameterized constructor to assign data members: name = n, code = c and amount = p
void show(): displays the details of the data members
Class name: Sales
Data members/instance variables:
day: stores number of days taken to pay the sale amount
tax: to store the sen ice tax (in decimals)
totamt: to store the total amount (in decimals)
Member functions/methods:
Sales(….): parameterized constructor to assign values to data members of both the classes
void compute(): calculates the service tax @ 12.4% of the actual sale amount
calculates the fine @ 2.5% of the actual sale amount only if the amount paid by the retailer to the wholesaler exceeds 30 days calculates the total amount paid by the retailer as (actual sale amount + service tax + fine)
void show (): displays the data members of the superclass and the total amount
main(): inputs required data and prints the total amount.*/

Step - 1   class Product()
Step - 2   Product(String n,int c,double p)
Step - 3   name=n
Step - 4   code=c
Step - 5   amount=p
Step - 6   end Product()
Step - 7   show()
Step - 8   print("Name- "+name)
Step - 9   print("Code- "+code)
Step - 10  print("Amount- "+amount)
Step - 11  end show()
Step - 12  end class Product()
Step - 13  class Sales() extends Product
Step - 14  Sales(String n,int c,double p,int d)
Step - 15  super(n,c,p)
Step - 16  day=d
Step - 17  tax=totamt=0.0
Step - 18  end Sales()
Step - 19  compute()
Step - 20  tax=(12.4*amount)/100
Step - 21  if day>30 then goto Step - 22 else goto Step - 24
Step - 22  tax+=2.5*amount/100;
Step - 23  end if
Step - 24  totamt=amount+tax;
Step - 25  end compute()
Step - 26  show()
Step - 27  super.show()
Step - 28  print("total amount-"+totamt);
Step - 29  end show()
Step - 30  main(String hjk[])
Step - 31  print("Enter name, code ,amount and days taken to pay")
Step - 32  input name
Step - 33  input code
Step - 34  input amount
Step - 35  input day
Step - 36  Sales o1=new Sales(name,code,amount,day)
Step - 37  o1.compute()
Step - 38  o1.show()
Step - 39  end main()
Step - 40  end class Sales()


























import java.util.*;
class Product //base class
{
protected String name;
protected int code;
protected double amount;
public Product(String n,int c,double p)
{ //parameterized constructor
name=n;
code=c;
amount=p;
}
public void show()
{
System.out.println("Name- "+name);
System.out.println("Code- "+code);
System.out.println("Amount- "+amount);
}
}
class Sales extends Product //child class
{
private int day;
private double tax,totamt;
public Sales(String n,int c,double p,int d)
{
super(n,c,p);
day=d;
tax=totamt=0.0;
}
public void compute()
{
tax=(12.4*amount)/100;
if(day>30)
tax+=2.5*amount/100;
totamt=amount+tax;
}
public void show()
{
super.show(); //calling show function of parent class
System.out.print("Total amount-"+totamt);
}
public static void main(String hjk[])
{
Scanner s=new Scanner(System.in);
System.out.println("Enter name, code ,amount and days taken to pay");
String name=s.nextLine();
int code=s.nextInt();
double amount=s.nextDouble();
int day=s.nextInt();
Sales o1=new Sales(name,code,amount,day);
o1.compute();
o1.show();//function overriding
}
}// end of class








Enter name, code ,amount and days taken to pay
Raman Gupta
1101
50000
12
Name- Raman Gupta
Code- 1101
Amount- 50000.0
Total amount-56200.0






















/*A PROGRAM TO REVERSE EACH ELEMENT OF A DOUBLE DIMENSIONAL ARRAY*/

Step-1   MatRev(int mm, int nn)
Step-2   m=mm
Step-3   n=nn
Step-4   arr=new int[m][n]
Step-5   End MatRev(int mm, int nn)
Step-6   fillarray()
Step-7   i=0
Step-8   j=0
Step-9   Print "ENTER ALL THE ELEMENTS OF ARRAY"
Step-10  for i=0 to i<m inc=+1
Step-11  for j=0 to j<n inc=+1
Step-12  Input arr[i][j]
Step-13  End for
Step-14  End for
Step-15  return
Step-16  End fillarray()
Step-17  reverse(int x)
Step-18  p=0
Step-19  if x<10 return else go to Step-20
Step-20  while(x!=0)
Step-21  p=p*10+(x%10)
Step-22  x=x/10
Step-23  End while
Step-24  return p to Step-31
Step-25  End reverse(int x)
Step-26  revMat(MatRev p)
Step-27  i=0
Step-28  j=0
Step-29  for i=0 to i<m inc=+1
Step-30  for j=0 to j<m inc=+1
Step-31  this.arr[i][j]=reverse(p.arr[i][j])
Step-32  End revMat(MatRev p)
Step-33  show()
Step-34  s="%"+10+"d"
Step-35  i=0
Step-36  j=0
Step-37  for i=0 to i<m inc=+1
Step-38  for j=0 to j<n inc=+1
Step-39  printf s,arr[i][j]
Step-40  End show()
Step-41  main(String ar[])
Step-42  print "ENTER ROW AND COLUMNS"
Step-43  input r
Step-44  input c
Step-45  MatRev x1=new MatRev(r,c)
Step-46  MatRev x2=new MatRev(r,c)
Step-47  x1.fillarray()
Step-48  print "ORIGINAL ARRAY"
Step-49  x1.show()
Step-50  x2.revMat(x1)
Step-51  print "REVERSED ARRAY"
Step-52  x2.show()
Step-53  End main(String ar[])
Step-54  End






import java.util.*;
class MatRev
{
private int arr[][],m,n;
    public MatRev(int mm,int nn)
    {
        m=mm;
        n=nn;                                                                                                       //PARAMETERISED CONSTRUCTOR
        arr=new int[m][n];
    }

    public void fillarray()throws Exception
    {
        Scanner sc=new Scanner(System.in);
        int i=0,j=0;
        System.out.println("ENTER ALL THE ELEMENTS OF ARRAY");
        for(i=0;i<m;i++)
        {
            for(j=0;j<n;j++)                                                                                //ARRAY INITIALIZATION
                arr[i][j]=sc.nextInt();
            sc.nextLine();
        }
        return;
    }

    public int reverse(int x)
    {
        int p=0;
        if(x<10)
            return x;
        else
        {
            while(x!=0)
            {
                p=p*10+(x%10);
                x=x/10;
            }
            return p;
        }
    }

    public void revMat(MatRev p)
    {
        int i,j;
        i=j=0;
        for(i=0;i<m;i++)
            for(j=0;j<n;j++)
                this.arr[i][j]=reverse(p.arr[i][j]);
    }

    public void show()
    {
        String s="%"+10+"d";
        int i=0,j=0;
        for(i=0;i<m;i++)                                           //PRINTING THE DETAILS
        {
            for(j=0;j<n;j++)
                System.out.printf(s,arr[i][j]);
            System.out.println();
        }
    }

    public static void main(String ar[])throws Exception
    {
        Scanner sc=new Scanner(System.in);
        System.out.println("ENTER ROW AND COLUMNS");
        int r=sc.nextInt();
        int c=sc.nextInt();
        MatRev x1=new MatRev(r,c);
        MatRev x2=new MatRev(r,c);
        x1.fillarray();                              
        System.out.println("ORIGINAL ARRAY");
        x1.show();
        System.out.println();    
        x2.revMat(x1);
        System.out.println("REVERSED ARRAY");
        x2.show();
}
}













ENTER ROW AND COLUMNS
4 5
ENTER ALL THE ELEMENTS OF ARRAY
12 13 454 6 100
41 12 34 78 99
142 42 31 64 47
24 45 64 82 97
ORIGINAL ARRAY
        12        13       454         6       100
        41        12        34        78        99
       142        42        31        64        47
        24        45        64        82        97

REVERSED ARRAY
        21        31       454         6         1
        14        21        43        87        99
       241        24        13        46        74
        42        54        46        28        79













/*program to create binary tree using linked list and print it using inorder*/

Step 1 - class node
Step 2 - public node(int k)
Step 3 - a=k
Step 4 - left=right=null
Step 5 - endnode(int k)
Step 6 - class btree
Step 7 - void add(int k)
Step 8 - M=add(M,k)
Step 9 - endadd(M,k)
Step 9 - node add(node R,int k)
Step 10 - if R==null
Step 11 - R=new node(k)
Step 12 - endif
Step 13 - if R.a==k
Step 14 - println "Node already exists"
Step 15 - endif
Step 16 - if k>R.a goto step 17 else goto step 18
Step 17 - R.right=add(R.right,k)
Step 18 - R.left=add(R.left,k)
Step 19 - return R
Step 20 - endnodeadd(node R, int k)
Step 21 - void inorder()
Step 22 - inorder(M)
Step 23 - endinorder()
Step 24 - void inorder(node R)
Step 25 - if R==null goto step 26 else goto step 27
Step 26 - return 
Step 27 - inorder(R.left)
Step 28 - print R.a+", "
Step 29 - inorder(R.right)
Step 30 - endif
Step 31 - endinorder(node R)
Step 32 - endclassbtree
Step 33 - class d
Step 34 - btree b1=new btree()
Step 35 - Scanner s=new Scanner(System.in)
Step 36 - println "Enter number of values-"
Step 37 - input n
Step 38 - for i=1 to n inc 1
Step 39 - b1.add(input value)
Step 40 - b1.inorder()
Step 41 - endfor
Step 42 - endclassd
Step 43 – end
















import java.util.*;
class node
{
	public node left;
	public int a;
	public node right;
	public node(int k)
	{
		a=k;
		left=right=null;
	}
}
class btree
{
	private node M;
	public void add(int k)
	{
		M=add(M,k);
	}
	public node add(node R,int k)
	{
		if(R==null)
			R=new node(k);
		else if(R.a==k)
			System.out.println("Node already exists");
		else if(k>R.a)
			R.right=add(R.right,k);
		else
			R.left=add(R.left,k);
		return R;
	}
	public void inorder()
	{
		inorder(M);
	}
	public void inorder(node R)
	{
		if(R==null)
			return;
		else
		{
			inorder(R.left);
			System.out.print(R.a+", ");
			inorder(R.right);
		}
	}
}
class d
{
	public static void main(String gh[])
	{
		btree b1=new btree();
		Scanner s=new Scanner(System.in);
		System.out.println("Enter number of values-");
		int n=s.nextInt();
		for(int i=1;i<=n;i++)
			b1.add(s.nextInt());
		b1.inorder();
	}
}


Enter number of values-
4
3
6
7
8
3, 6, 7, 8
























/*program to depict insert sort technique using linked list*/

Step 1 - class insertsort
Step 2 - l1=l2=null
Step 3 - val=0
Step 4 - Scanner s=new Scanner(System.in)
Step 5 - println "Enter number of values"
Step 6 - input n
Step 7 - for i=0 to N-1 inc 1
Step 8 - input k
Step 9 - if l1==null goto step 10 else goto step 14
Step 10 - l1=l2=new link()
Step 11 - l1.data=k
Step 12 - l1.next=null
Step 13 - l1.previous=null
Step 14 - l2.next=new link()
Step 15 - l2.next.previous=l2
Step 16 - l2=l2.next
Step 17 - l2.data=k
Step 18 - l2.next=null
Step 19 - endif
Step 20 - endfor
Step 21 - l3=l1
Step 22 - m=0,n=0
Step 23 - for i=0 to N-1 inc 1
Step 24 - l3=l1
Step 25 - for j=0 to i-1 inc 1
Step 26 - l3=l3.next
Step 27 - val=l3.data
Step 28 - while l3.previous!=null && l3.previous.data>val
Step 29 - l3.data=l3.previous.data
Step 30 - l3=l3.previous
Step 31 - endwhile
Step 32 - if l3==null goto step 33 else goto step 35
Step 33 - l3=l1
Step 34 - l3.data=val
Step 35 - l3.data=val
Step 36 - endif
Step 37 - l3=l1
Step 38 - while l3.next!=null
Step 39 - print l3.data+" "
Step 40 - l3=l3.next
Step 41 - endwhile
Step 42 - println l3.data
Step 43 - endfor
Step 44 - endfor
Step 45 – end















import java.util.*;
class link
{
	int data;
		link next;
			link previous;
}
class insertsort
{
	public static void main(String hj[])throws Exception
	{
		link l1,l2,l3,l4;
		l1=l2=null;
		int i,N,k,val=0,j;
		Scanner s=new Scanner(System.in);
		System.out.println("Enter number of values");
		N=s.nextInt();
		for(i=0;i<N;i++)
		{
			k=s.nextInt();
			if(l1==null)
			{
				l1=l2=new link();
				l1.data=k;
				l1.next=null;
				l1.previous=null;
			}
			else
			{
				l2.next=new link();
				l2.next.previous=l2;
				l2=l2.next;
				l2.data=k;
				l2.next=null;
			}
		}
		l3=l1;
		int m=0,n=0;
		for(i=0;i<N;i++)
		{
			l3=l1;
			for(j=0;j<i;j++)
				l3=l3.next;
			val=l3.data;
			while(l3.previous!=null && l3.previous.data>val)
			{
				l3.data=l3.previous.data;
				l3=l3.previous;
			}
			if(l3==null)
			{
				l3=l1;
				l3.data=val;
			}
			else
				l3.data=val;
		}
		l3=l1;
		while(l3.next!=null)
		{
			System.out.print(l3.data+" ");
			l3=l3.next;
		}
		System.out.println(l3.data);
	}
}




























Enter number of values
8
5 67 14 95 34 57 64 21
5 14 21 34 57 64 67 95


























/*Program to find the pairs of the given number*/

Step 1 -   public static void main(String hj[])
Step 2 -   Scanner sc=new Scanner(System.in);
Step 3 -   input n
Step 4 -   a[]=new int[n]
Step 5 -   for i=0 to n
Step 6 -   a[i]=s.nextInt()
Step 7 -   end for
Step 8 -   for i=0 to n
Step 9 -   if a[i]>12 or a[i]<1 then go to step 10 else go to step 11
Step 10 - continue
Step 11 - end if 
Step 12 - print a[i]+”Pairs for”+a[i]+”:”
Step 13 - for j=1 to 11
Step 14 - for k=j+1 to 11
Step 15 - if j+k==a[i] then go to step 16 else go to step 17
Step 16 - print j+” “+k”,”
Step 17 - end if
Step 18 - end for
Step 19 - end for
Step 20 - println()
Step 21 - end for
Step 22- end main
Step 23- end







import java.util.*;
class pairs
{
    public static void main(String hj[])
    {
        Scanner s=new Scanner(System.in);
        int n,i,j,k;
        n=s.nextInt();
        int a[]=new int[n];
        for(i=0;i<n;i=i+1)
            a[i]=s.nextInt();
        for(i=0;i<n;i=i+1)
        {
            if(a[i]>12|| a[i]<1)
                continue;
            System.out.print(a[i]+" Pairs for "+a[i]+": ");
            for(j=1;j<12;j=j+1)
                for(k=j+1;k<12;k=k+1)
                    if(j+k==a[i])
                        System.out.print(j+" "+k+", ");
            System.out.println();
        }
    }
}







4
2
3
5
6
2
2 Pairs for 2: 
5 Pairs for 5: 1 4, 2 3, 
6 Pairs for 6: 1 5, 2 4,





















/*Program to input every unique word of a sentence along with their position in the sentence. Use the given info to recreate the sentence*/

Step 1 -   public static void main(String at[])
Step 2 -   Scanner s=new Scanner(System.in)
Step 3 -   int I,j,numberOfWords=0,k=0,max=0
Step 4 -   String input,rawInput=””,position[],outputString[]
Step 5 -   while !((input=s.nextLine()).equals(“#”))
Step 6 -   rawInput+=input+” “
Step 7 -   numberOfWords++
Step 8 -   end while
Step 9 -   String words[]=rawInput.split(“ “)
Step 10 - String inputArray[][]=new String[numberOfWords][2]
Step 11 - for i=0 till numberOfWords
Step 12 - for j=0 till 2
Step 13 - inputArray[i][j]=words[k++]
Step 14 - end for
Step 15 - end for
Step 16 - for i=0 till numberOfWords
Step 17 - positions=inputArray[i][1].split(“,”)
Step 18 - for j=0 till positions.length
Step 19 - if max<Integer.valueOf(positions[j]) then go to step 20 else go to step 21
Step 20 - max=Integer.valueOf(positions[j])
Step 21 - end if
Step 22 - end for
Step 23 - end for
Step 24 - outputString=new String[max]
Step 25 - for i=0 till numberOfWords
Step 26 - positions=inputArray[i][1].split(“,”)
Step 27 - for j=1 to max
Step 28 - for k=0 till positions.length
Step 29 - if Integer.valueOf(positions[k])==j then go to step 30 else go to step 31
Step 30 - outputString[j-1]=inputArray[i][0]
Step 31 - end if
Step 32 - end for
Step 33 - end for
Step 34 - end for
Step 35 - for i=0 till max
Step 36 - print outputString[i]+” “
Step 37 - end for
Step 38 - end main
Step 39 - end
























import java.util.*;
class extract
{
	    public static void main(String h[])
	    {
		        Scanner s=new Scanner(System.in);
		        int i,j,numberOfWords=0,k=0,max=0;	//declaring variables
		        String input,rawInput="",positions[],outputString[];
		        while(!((input=s.nextLine()).equals("#")))
		        {  						//to input words and positions
			            rawInput+=input+" ";
			            numberOfWords++;
		        }
		        String words[]=rawInput.split(" ");
		        String inputArray[][]=new String[numberOfWords][2];
		        for(i=0;i<numberOfWords;i++)
			            for(j=0;j<2;j++)
				                inputArray[i][j]=words[k++];
		        for(i=0;i<numberOfWords;i++)
		        {
			            positions=inputArray[i][1].split(",");
			            for(j=0;j<positions.length;j++)  		 //finding max position
				                if(max<Integer.valueOf(positions[j]))
					                    max=Integer.valueOf(positions[j]);
		        }
		        outputString=new String[max];
		        for(i=0;i<numberOfWords;i++)
		        {
			            positions=inputArray[i][1].split(",");
			            for(j=1;j<=max;j++)
				                for(k=0;k<positions.length;k++)
				                    if(Integer.valueOf(positions[k])==j)
					                        outputString[j-1]=inputArray[i][0];
		        }
		        for(i=0;i<max;i++)
			            System.out.print(outputString[i]+" ");
	    }
}




















this is that and that is this
this 1,7,
is 2,6,
that 3,5,
and 4,

java is great.javac is also great
java-1
javac-4
also-6

This is my pen. this is my eraser
pen-4
eraser-8
















/*Write a program to input size of an array and input its elements and check whether a ring can be formed using them or not.*/

Step 1-   public Ring(intN)
Step 2-   n=N
Step 3-   n=new int[n]
Step 4-   getnum()
Step 5-   input s
Step 6-   k[]=s.split(",")
Step 7-   for i=0 to n
Step 8-   input a[]
Step 9-    end for
Step 10-  end getnum
Step 11- isRing()
Step 12- lr=n-1
Step 13- for i=0 to n
Step 14- for j=i+1 to n
Step 15- for a[j]<a[I] then step 17 else step 21
Step 16- t=a[i]
Step 17- a[i]=a[j]
Step 18- a[j]=t
Step 19- end if
Step 20- end for
Step 21- end for
Step 22- for i=0 to n
Step 23-  if a[i]! a[b] then wstep.25 else step 26
Step 24- break
Step 25- b=b-1
Step 26- end for
Step 27- if i==n then step 29 esle step 31
Step 28- return true
Step 29- goto step 32
Step 30  return false
Step 31- end getnum()
Step 32- print()
Step 33- if(isRing()) then goto step 35 else goto step 37
Step 34- print ring can be formed
Step 35- goto step 38
Step 36- print ring cannote be formed
Step 37- end print 
Step 38- input N
Step 39-  r=new Ring(N)
Step 40- r.getNum()
Step 41- r.print()
Step 42- end 

















import java.io.*;
class Ring
{
    private int a[];
    private int n;
    public Ring(int N)
    {
        n=N;                                  //To assign the size of array
        a=new int[n];
    }
    public void getnum()throws Exception
    {
        DataInputStream z=new DataInputStream(System.in);
        String s=z.readLine();               //To input a string
        String k[]=s.split(",");
        for(int i=0;i<n;i=i+1)
            a[i]=Integer.parseInt(k[i]);
    }
    public boolean isRing()
    {
        int b=n-1,i,j,t;
        for(i=0;i<n;i=i+1)
        {
            for(j=i+1;j<n;j=j+1)
            {
                if(a[i]>a[j])              //To sort the array
                {
                    t=a[i];
                    a[i]=a[j]; 
                    a[j]=t;
                }
            }
        }
        for(i=0;i<n;i=i+1)
        {
            if(a[i]!=(-a[b]))
                break;
            b=b-1;
        }
        if(i==n)
            return true;
        else 
            return false;
    }
    public void print()
    {
        if(isRing())               //To check whether elements of array form a ring or not
            System.out.println("Ring can be formed");
        else
            System.out.println("Ring cannot be formed");
    }
}
class abc
{
    public static void main(String ab[])throws Exception
    {
        DataInputStream y=new DataInputStream(System.in);
        int N;
        N=Integer.parseInt(y.readLine());            //To input size of array
        Ring r=new Ring(N);
        r.getnum();
        r.print();
}
}





























5
-2,2,1,0,-1
Ring can be formed




























/*A class DeciTri has been defined to convert a decimal number to its equivalent trinary number. Where trinary numbers are number having base 3. Some of the members of the class are given below:
Class name:DeciTri
Data members/instance variables:
n: stores the decimal number
tri: stores the trinary equivalent number
Member functions:
DeciTri(): constructor to initialize the data members
void getnum(int nn): assign nn to n
void deci_tri(): calculates the trinary equivalent of ‘n’ and stores it in’tri’
void show(): displays the decimal number ‘n’ and its trinary equivalent.
Specify the class DecTri giving details of all the functions. Define the main() function to create an object and call the functions accordingly to enable the task.*/

Step1- DeciTri()
Step2- n=0;
Step3- tri=0
Step4- end DeciTri()
Step5- getnum(int nn)
Step6- n=nn
Step7- end getnum(int nn)
Step8- deci_tri()
Step9- D=""
Step10- b=n
Step11- while n!=0
Step12- s=n%3+s
Step13- n=n/3
Step14- end while
Step15- if(s.length()==0)then go to step-16 else go to step-17
Step16- s="0"+s
Step17- tri=Integer.parseInt(s)
Step18- n=b
Step19- end deci_tri()
Step20- show()
Step21- deci_tri()
Step22- print "Decimal number="+n
Step23- print "Trinary Equivalent="+tri
Step24- end show()
Step25- end
Step26- input nn
Step27- DeciTri d=new Decitri()
Step28- d.getnum(nn)
Step29- d.show()
Step30- end

















import java.io.*;
class DeciTri
{
    private int n;
    private int tri;
    public DeciTri()
    {
        n=0;                     //To initialize data members
        tri=0;
    }
    public void getnum(int nn)
    {
        n=nn;
    }
    public void deci_tri()   //decimal to trinary equivalent
    {
        String s="";
        int b=n;
        while(n!=0)
        {
            s=n%3+s;
            n=n/3;
        }
        if(s.length()==0)
            s="0"+s;
        tri=Integer.parseInt(s);             //To convert string to integer
        n=b;
    }
    public void show()
    {
        deci_tri();
        System.out.println("Decimal number= "+n);
        System.out.println("Trinary Equivalent= "+tri);
    }
}
class abc
{
    public static void main(String ab[])throws Exception
    {
        DataInputStream z=new DataInputStream(System.in);
        int nn;
        nn=Integer.parseInt(z.readLine());    //To input a decimal number
        DeciTri d=new DeciTri();
        d.getnum(nn);
        d.show();
    }
}















29
Decimal number= 29
Trinary Equivalent= 1002




























/*Write a program to create stack data structure using linked list*/

Step 1- Node(int value)
Step 2- data=value
Step 3- Next=null
Step 4- end Node(int value)
Step 5- end
Step 6- Stack()
Step 7- top=null
Step 8- end stack()
Step 9- isEmpty()
Step 10- if top==null then step 11 else step 13
Step 11- return true
Step 12- goto step 14
Step 13- return false
Step 14- end if
Step 15- end isEmpty ()
Step 16- push(int v)
Step 17- if(isEmpty()) then goto step 18 else goto step 20
Step 18- top=new Node(v)
Step 19- Node newSt=new Node(v)
Step 20- goto step 24
Step 21- newSt.Next=new Node(v)
Step 22- top=newSt
Step 23- Top=newSt
Step 24- end if
Step 25- end push(int v)
Step 26- pop()
Step 27- if(isEmpty()) then goto step 28 else goto step 30
Step 28- return 0
Step 29- goto step 34
Step 30- St=top
Step 31- v=top.data
Step 32- top=top.next
Step 33- return v
Step 34- end if
Step 35- end punch(int v)
Step 36- peek()
Step 37- if(isEmpty) then goto step 38 else goto step 40
Step 38- return p
Step 39- goto step 41
Step 40- return Top.data 
Step 41- end if
Step 42- end peek()
Step 43- print()
Step 44- if(isEmpty()) then goto step 45 else step 4
Step 45- print "empty stack"
Step 46- Node St=top
Step 47- while(St!=null)
Step 48- St=St.Next
Step 49- end while
Step 50- println()
Step 51- end if
Step 52- end
Step 53- x=new Stack()
Step 54- case 1
Step 55- print "element to push"
Step 56- input w
Step 57- x.push(w)
Step 58- break
Step 59- case 2
Step 60- w=x.pop
Step 61- if w==0 goto step 62 else step 64
Step 62- print underflow
Step 63- goto step 65
Step 64- print "element popped"
Step 65- end if
Step 66- break
Step 67- case 3
Step 68- w=x.peek()
Step 69- if(w==0) then step 70 else step 73
Step 71- print underflow
Step 72- goto step 24
Step 73- print "element peeked"
Step 74- break
Step 75- case 4
Step 76- default
Step 77- print "Invalid input"
Step 78- break
Step 79- end switch ()
Step 80- while(ch!=4)
Step 81- end do while
Step 82- class ends










1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
5
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
3
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
7
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
4
1.Push
2.Pop
3.Peek
4.Print
5.Exit
2
Elelment popped 4
1.Push
2.Pop
3.Peek
4.Print
5.Exit
3
Element peeked 7
1.Push
2.Pop
3.Peek
4.Print
5.Exit
4
7 3 5









/*Write a program to input numbers and find the lucky number using double linked list.*/

Step 1: node(int p)
Step 2: a=p 
Step 3: prev=next=null
Step 4: end node(int p)
Step 5: end
Step 6: add(int p)
Step 7: if l1==null then goto step 8 else step 10
Step 8: l1=new node(p)
Step 9: goto step 13
Step 10: l1.next=new node(p)
Step 11: (l1.next).prev=l1
Step 12: l1=l1.next
Step 13: end if
Step 14: end add(int p)
Step 15: sort()
Step 16: while l1.prev!=null
Step 17: l1=l1.prev
Step 18: node current=null
Step 19: l1=l1.next
Step 20: while l1!=null
Step 21: current = l1.prev
Step 22: while(current !=null && current.a>(current.next).a)
Step 23: d=current.a
Step 24: current.a=(current.next).a
Step 25: (current.next).a = d
Step 26: current=current.prev
Step 27: end while
Step 28: if l1.next==null then goto step 29 else step 30
Step 29: l2=l1
Step 30: l1=l1.next
Step 31: end while
Step 32: end sort()
Step 33: print ()
Step 34: while l2.prev!=null
Step 35: l2=l2.prev
Step 36: while l2!=null
Step 37: print l2.a +" " 
Step 38: l2=l2.next
Step 39: end while
Step 40: end print()
Step 41: end
Step 42: link k=new list()
Step 43: print "enter the numbers"
Step 44: input d
Step 45: StringTokenizer  st=new StringTokenizer(s)
Step 46: n=st.countTokens()
Step 47: for i=1 to n 
Step 48: s1=st.nextToken()
Step 49: n1= Integer.parseInt(s1)
Step 50: k.add(n1)
Step 51: end for
Step 52: k.sort()
Step 53: k.print()
Step 54: end






import java.io.*;
class node
{
    int data;
    node next;
    node prev;
    public node(int k)
    {
        data=k;
        next=null;
        prev=null;
    } 
}                                                               / /End of class node
class doublelucky
{
    public static void main(String ar[])throws Exception
    {
        DataInputStream z=new DataInputStream(System.in);
        int n,k,i,j;
        char ch;
        node l1,l2,l3,l4;
        l1=l2=l3=l4=null;
        System.out.println("Enter no. of numbers");
        n=Integer.parseInt(z.readLine());            //To input a number
        System.out.println("Enter numbers");
        for(i=1;i<=n;i=i+1)
        {
            k=Integer.parseInt(z.readLine());
            if(l1==null)
                l2=l1=new node(k);
            else
            {
                l1.next=new node(k);                 //Creating a node
                (l1.next).prev=l1;
                l1=l1.next;
            }
        }
        l1.next=l2;
        l2.prev=l1;
        System.out.println("Enter position");
        int g=Integer.parseInt(z.readLine());               //To input starting position
        l3=l1;
        for(i=1;i<=g;i=i+1)
            l3=l3.next;
        while(l3.next!=l3)
        {
            k=l3.data;
            l4=l3;
            while(l4.next!=l3)
                l4=l4.next;
            l4.next=l3.next;
            l3.next.prev=l4;
            l3.prev=null;
            l3.next=null;
            l3=l4.next;
            if(k>0)
            {
                for(j=1;j<k;j++)
                    l3=l3.next;                             //To move forward in linked list 
            }
            else
            {
                l3=l3.prev;
                for(j=1;j<(-1)*k;j++)
                    l3=l3.prev;                          //To move backward in linked list
            }
        }
        System.out.println("Lucky Number="+l3.data); //To print the lucky number 
    }
}























Enter no. of numbers
4
Enter numbers
1
2
4
6
Enter position
3
Lucky Number=1





















/*Program to depict merge sort technique*/

Step 1 - class mergesort
Step 2 - void mergeSort(int[] a, int n) 
Step 3 - if n < 2
Step 4 - return
Step 5 - endif
Step 6 - mid = n / 2;
Step 7 - l = new int[mid]
Step 8 - r = new int[n - mid]
Step 9 - for i = 0 to mid-1 inc 1 
Step 10 - l[i] = a[i]
Step 11 - endfor
Step 12 - for i = mid to n-1 inc 1
Step 13 - r[i - mid] = a[i]
Step 14 - endfor
Step 15 - mergeSort(l, mid)
Step 16 -mergeSort(r, n - mid)
Step 17 - merge(a, l, r, mid, n - mid)
Step 18 - endmergeSort(int[] a, int n)
Step 19 - void merge(int[] a, int[] l, int[] r, int left, int right) 
Step 20 - i = 0, j = 0, k = 0
Step 21 - while i < left && j < right
Step 22 - if l[i] <= r[j] goto step 23 else goto step 24
Step 23 - a[k++] = l[i++]
Step 24 - a[k++] = r[j++]
Step 25 - endif
Step 26 - endwhile
Step 27 - while i < left
Step 28 - a[k++] = l[i++]
Step 29 - endwhile
Step 30 - while j < right
Step 31 - a[k++] = r[j++]
Step 32 - endwhile(step )
Step 33 - endwhile(step )
Step 34 - endmerge(int[] a, int[] l, int[] r, int left, int right)
Step 35 - void main(String hj[])
Step 36 - Scanner s=new Scanner(System.in);
Step 37 - println "Enter value of n"
Step 38 - input n
Step 39 - println "Enter values..."
Step 40 - inputArray[]=new int[n]
Step 41 - for i=0 to n-1 inc 1
Step 42 - input inputArray[i]
Step 43 - endfor
Step 44 - mergeSort(inputArray,n)
Step 45 - for i=0 to n-1 inc 1
Step 46 - print inputArray[i]+","
Step 47 - endfor
Step 48 - endclassmergesort
Step 49 – end











import java.util.*;
class mergesort  //start of class
{
    public static void mergeSort(int[] a, int n) 
    {
        if (n < 2)
            return;
        int mid = n / 2;
        int[] l = new int[mid];
        int[] r = new int[n - mid];
        for (int i = 0; i < mid; i++) 
            l[i] = a[i];
        for (int i = mid; i < n; i++) 
            r[i - mid] = a[i];
        mergeSort(l, mid);
        mergeSort(r, n - mid);
        merge(a, l, r, mid, n - mid);
    }
    public static void merge(int[] a, int[] l, int[] r, int left, int right) 
    {
        int i = 0, j = 0, k = 0;
        while (i < left && j < right)
            if (l[i] <= r[j])
                a[k++] = l[i++];
            else
                a[k++] = r[j++];
        while (i < left)
            a[k++] = l[i++];
        while (j < right)
            a[k++] = r[j++];
    }
    public static void main(String hj[])
    {
        Scanner s=new Scanner(System.in);
        System.out.println("Enter value of n");
        int n=s.nextInt();
        System.out.println("Enter values...");
        int inputArray[]=new int[n];
        for(int i=0;i<n;i++)
            inputArray[i]=s.nextInt();
        mergeSort(inputArray,n);
        for(int i=0;i<n;i++)
            System.out.print(inputArray[i]+",");
    }
}

















Enter value of n(number of values)
5
Enter values...
11
2
4
14
15
2,4,11,14,15

Enter value of n(number of values)
9
Enter values...
12
1
25
24
23
22
21
78
75
1,12,21,22,23,24,25,75,78








/*Write a program to create queue data structure using linked list*/

Step 1- Node(int value)
Step 2- data=value
Step 3- Next=null
Step 4- end Node(int value)
Step 5- end
Step 6- Queue()
Step 7- First=null
Step 8- end Queue()
Step 9- isEmpty()
Step 10- if First==null then goto step 11 else goto step 13
Step 11- return true
Step 12- goto step 14
Step 13- return false
Step 14- end if
Step 15- end isEmpty()
Step 16- push(int v)
Step 17- if(isEmpty()) then goto step 18 else goto step 20
Step 18- First=new Node(v)
Step 19- goto step 26
Step 20- New Q=new Node(v)
Step 21- Node Current=First
Step 22- while(Current. Next!=null)
Step 23- Current=Current.Next
Step 24- end while
Step 25- Current. Next=new()
Step 26- end if
Step 27- pop
Step 28- if(isEmpty()) then goto step 29 else goto step 31
Step 29- return 0
Step 30- goto step 35
Step 31- v=First.data
Step 32- remove=First
Step 33- First=First.Next
Step 34- return v
Step 35- endif
Step 36- end pop()
Step 37- print()
Step 38- if (isEmpty()) then goto step 39 else goto step 41
Step 39- print "Queue is Empty"
Step 40- goto step 47
Step 41- Node NP=First
Step 42- while NP!=null
Step 43- print NP.data+" "
Step 44- NP=NP.Next
Step 45- end while
Step 46- println
Step 47- endif
Step 48- end
Step 49- x=new Queue()
Step 50- do
Step 51- println 1.push \n 2.pop \n 3.peek \n 4.print \n 5.exit
Step 52- input ch
Step 53- switch (ch)
Step 54- case 1
Step 55- print "element to push"
Step 56- input w
Step 57- x.push(w)
Step 58- break
Step 59- case 2
Step 60- w=x.pop()
Step 61- if w=0 then goto step 63 else goto step 64
Step 62- print "underflow"
Step 63- goto step 65
Step 64- print "element popped" +w
Step 65- end if
Step 66- break
Step 67- case 3
Step 68- w=x.peek()
Step 69- if w=0 then goto step 70 else goto step 72
Step 70- print underflow
Step 71- goto step 73
Step 72- print "element peeked" +w
Step 73- break
Step 74- case 4
Step 75- break
Step 76- default 
Step 77- print "invalid choice"
Step 78- end switch()
Step 79- end do while
Step 80- end











import java.util.*;
class Node
{
    public int data;
    public Node Next;
    public Node(int value)
    {
        data=value;
        Next=null;
    }
}                                                              //End of class Node
class Queue
{
    private Node First;
    public Queue()
    {
        First=null;
    }
   public boolean isEmpty()
    {
        if(First==null)                             //To check if First is null or not
            return true;
        else
            return false;
    }
    public void push(int v)
    {
        if(isEmpty())
            First=new Node(v);
        else
        {
            Node newQ=new Node(v);
            Node Current=First;
            while(Current.Next!=null)               //While loop
                Current=Current.Next;
            Current.Next=newQ;
        }
    }
    public int pop()
    {
        if(isEmpty())                           //To check if First is null or not
            return 0;
        else
        {
            int v=First.data;
            Node remove;
            remove=First;
            First=First.Next;
            return v;
        }
    }
    public int peek()
    {
        if(isEmpty())
            return 0;
        else
        {
            return First.data;
        }
    }                            
    public void print()            //To print the queue linked list
    {
        if(isEmpty())
            System.out.println("Queue is empty");
        else
        {
            Node NP=First;
            while(NP!=null)
            {
                System.out.print(NP.data+" ");
                NP=NP.Next;
            }
            System.out.println();
        }
    }                                               //End of class Queue
class abc
{
    public static void main(String ab[])throws Exception
    {
        Scanner sc=new Scanner(System.in);
        int w,ch;
        Queue x=new Queue();
        do
        {
            System.out.println("1.Push\n2.Pop\n3.Peek\n4.Print\n5.Exit");
            ch=sc.nextInt();                      //To input choice
            switch(ch)
            {
                case 1:
                    System.out.println("Element to push");
                    w=sc.nextInt();                 //To input value to be pushed
                    x.push(w);
                    break;
                case 2:
                    w=x.pop();                          //To assign value that is peeked
                    if(w==0)
                        System.out.println("Underflow");
                    else
                        System.out.println("Elelment popped "+w);
                    break;
                case 3:
                    w=x.peek();
                    if(w==0)
                        System.out.println("Underflow");
                    else
                        System.out.println("Element peeked "+w);
                    break;
                case 4:
                    x.print();                                  //To print the queue linked list
                    break;
                case 5:
                    break;
                default:
                    System.out.println("Invalid choice"); 
            }
        }while(ch!=4);
    }
}                                                          //End of class abc






1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
2
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
3
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
4
1.Push
2.Pop
3.Peek
4.Print
5.Exit
1
Element to push
5
1.Push
2.Pop
3.Peek
4.Print
5.Exit
3
Element peeked 2
1.Push
2.Pop
3.Peek
4.Print
5.Exit
2
Element popped 2
1.Push
2.Pop
3.Peek
4.Print
5.Exit
4
3 4 5









/*Circular Queue using Linked List*/

Step 1-  main
Step 2-  link l1=l2=null
Step 3-  int pos=1
Step 4-  do
Step 5-  print ("Enter a number ->")
Step 6-  input k
Step 7-  if(l1==null) then go to step 7 else go to step 12
Step 8-  l1=l2=new link()
Step 9-  l1.data=k
Step 10-  l1.next=null
Step 11-  go to step 16
Step 12-  l2.next=new link()
Step 13-  l2=l2.next
Step 14-  l2.data=k
Step 15-  l2.next=null
Step 16-  print ("Do you want to continue Y/N ->")
Step 17-  store the first letter of user's input in ch
Step 18-  convert ch into uppercase
Step 19-  end of do while if(ch=='n')
Step 20-  l2.next=l1
Step 21-  labelled do
Step 22-  print ("Enter choice->\n1)Insert\n2)Delete\n3)Search\n4)Print\n5)Exit")
Step 23-  input c1
Step 24-  switch(c1)
Step 25-  case 1
Step 26-  labelled do
Step 27-  leave a line
Step 28-  print ("Enter choice->\n1)Add at a position\n2)Add after a value\n3)Add before a value\n4)Exit")
Step 29-  input c
Step 30-  switch(c)
Step 31-  case 1
Step 32-  print ("Enter the number to inserted ->")
Step 33-  input k
Step 34-  print ("Enter the position at which the number is to be inserted->")
Step 35-  input n
Step 36-  pos=1
Step 37-  l3=new link()
Step 38-  l3.data=k
Step 39-  l3.next=null
Step 40-  for l2=l1 to l2.next!=l1;l2=l2.next
Step 41-  pos++
Step 42-  if(n<1) then go to step 43 else go to step 45
Step 43-  print ("Invalid position")
Step 44-  break
Step 45-  if(n==1) then go to step 46 else go to step 54
Step 46-  l4=l1
Step 47-  while(l4.next!=l1)
Step 48-  l4=l4.next
Step 49-  end while
Step 50-  l3.next=l1
Step 51-  l1=l3
Step 52-  l4.next=l1
Step 53-  break
Step 54-  if(pos==n) then go to step 55 else go to step 58
Step 55-  l3.next=l2.next
Step 56-  l2.next=l3
Step 57-  break
Step 58-  end for(step 40)
Step 59-  if(l2.next==l1&&n>pos) then go to step 60 else go to step 62
Step 60-  l2.next=l3
Step 61-  l3.next=l1
Step 62-  break (case 1)
Step 63-  case 2
Step 64-  print ("Enter number to be inserted ->")
Step 65-  input k
Step 66-  print ("Enter number after which you want to insert ->")
Step 67-  input h
Step 68-  l3=l1
Step 69-  l4=new link()
Step 70-  l4.data=k
Step 71-  l4.next=null
Step 72-  while(l3.data!=h)
Step 73-  l3=l3.next
Step 74-  end while
Step 75-  if(l3.next==l1) then go to step 76 else go to step 79
Step 76-  l3.next=l4
Step 77-  l4.next=l1
Step 78-  go to step 81
Step 79-  l4.next=l3.next
Step 80-  l3.next=l4
Step 81-  break (case 2)
Step 82-  case 3
Step 83-  print ("Enter number to be inserted ->")
Step 84-  input k
Step 85-  print ("Enter number before which you want to insert ->")
Step 86-  input h
Step 87-  l3=new link()
Step 88-  l4=new link()
Step 89-  l4.data=k
Step 90-  l4.next=null
Step 91-  l3=l1
Step 92-  if(l1.data!=h) then go to step 93 else go to step 99
Step 93-  while(l3.next.data!=h)
Step 94-  l3=l3.next
Step 95-  end while
Step 96-  l4.next=l3.next
Step 97-  l3.next=l4
Step 98-  go to step 106
Step 99-  link l5=l1
Step 100-  while(l5.next!=l1)
Step 101-  l5=l5.next
Step 102-  end while
Step 103-  l4.next=l1
Step 104-  l1=l4
Step 105-  l5.next=l1
Step 106-  break (case 3)
Step 107-  case 4
Step 108-  break the labelled do while (step 21)
Step 109-  default
Step 110-  print ("Wrong choice")
Step 111-  end switch
Step 112-  end do while if (c==4)
Step 113-  break (case 1)
Step 114-  case 2
Step 115-  labelled do
Step 116-  leave a line
Step 117-  print ("Enter choice->\n1)Delete at a position\n2)Delete a value\n3)Exit")
Step 118-  input c
Step 119-  switch(c)
Step 120-  case 1
Step 121-  print ("Enter the position at which the number is to be deleted ->")
Step 122-  input n
Step 123-  pos=1
Step 124-  l3=new link()
Step 125-  for l2=l1 till l2.next!=l1;l2=l2.next
Step 126-  pos++
Step 127-  if(n<1) then go to step 128 else go to step 130
Step 128-  print ("Invalid position")
Step 129-  break
Step 130-  if(n==1) then go to step 131 else go to step 137
Step 131-  while(l2.next!=l1)
Step 132-  l2=l2.next
Step 133-  end while
Step 134-  l1=l1.next
Step 135-  l2.next=l1
Step 136-  break
Step 137-  if(pos==n) then go to step 138 else go to step 143
Step 138-  l3=new link()
Step 139-  l3=l2.next
Step 140-  l2.next=l3.next
Step 141-  l3.next=null
Step 142-  break
Step 143-  end for 
Step 144-  break (case 1)
Step 145-  case 2
Step 146-  print ("Enter number which you want to delete :")
Step 147-  input h
Step 148-  l3=l1
Step 149-  while(l3.data!=h)
Step 150-  if(l3.next==l1) then go to step 151 else go to step 154
Step 151-  f=1
Step 152-  break
Step 153-  go to step 155
Step 154-  l3=l3.next
Step 155-  end of while
Step 156-  if(l3.data==h&&f!=1) then go to step 157 else go to step 177
Step 157-  l3=l1
Step 158-  l4=new link()
Step 159-  if(l1.data!=h) then go to step 160 else go to step 170
Step 160-  while(l3.next.data!=h)
Step 161-  if(l3.next==l1) then go to step 162 else go to step 164
Step 162-  g=1
Step 163-  break
Step 164-  l3=l3.next
Step 165-  end of while
Step 166-  l4=l3.next
Step 167-  l3.next=l4.next
Step 168-  l4.next=null
Step 169-  go to step 178
Step 170-  l3=l1
Step 171-  while(l3.next!=l1)
Step 172-  l3=l3.next
Step 173-  end while
Step 174-  l1=l1.next
Step 175-  l3.next=l1
Step 176-  go to step 178
Step 177-  print ("Not found")
Step 178-  break (case 2)
Step 179-  case 3
Step 180-  break labelled do while(step 115)
Step 181-  default
Step 182-  print ("Wrong choice")
Step 183-  end of switch
Step 184-  end do while if(c==3)
Step 185-  break (case 2)
Step 186-  case 3
Step 187-  print ("Enter the number to searched ->")
Step 188-  input k
Step 189-  l3=l1
Step 190-  while(l3.data!=k)
Step 191-  if(l3.next==l1) then go to step 192 else go to step 193
Step 192-  break
Step 193-  l3=l3.next
Step 194-  end of while
Step 195-  if(l3.data==k) then go to step 196 else go to step 198
Step 196-  print ("Found")
Step 197-  go to step 199
Step 198-  print ("Not found")
Step 199-  break (case 3)
Step 200-  case 4
Step 201-  l2=l1
Step 202-  do
Step 203-  print (l2.data+" ")
Step 204-  l2=l2.next
Step 205-  end do while if(l2==l1)
Step 206-  leave a line
Step 207-  break (case 4)
Step 208-  case 5
Step 209-  break labelled do while (step 21)
Step 210-  default 
Step 211-  print ("Wrong choice")
Step 212-  end do while if(c1==5)
Step 213-  end main  

import java.io.*;
class link
{
 int data;
 link next;
}
class circularlist
{
public static void main(String ar[])throws Exception
{
link l1,l2,l3,l4;
l1=l2=null;
char ch;
int k,n,x,pos=1,h,c,c1;
DataInputStream z=new DataInputStream(System.in);
do
{
System.out.println("Enter a number ->");
k=Integer.parseInt(z.readLine());
if(l1==null)
{
l1=l2=new link();
l1.data=k;
l1.next=null;
}
else
{
l2.next=new link();
l2=l2.next;
l2.data=k;
l2.next=null;
}
System.out.println("Do you want to continue Y/N ->");
ch=z.readLine().charAt(0);
ch=Character.toUpperCase(ch);
}while(ch!='N');
l2.next=l1;    
outer:do
{
System.out.println("Enter choice->\n1)Insert\n2)Delete\n3)Search\n4)Print\n5)Exit");
c1=Integer.parseInt(z.readLine());
switch(c1)
{
case 1:
abc:do
{
System.out.println();
System.out.println("Enter choice->\n1)Add at a position\n2)Add after a value\n3)Add before a value\n4)Exit");
c=Integer.parseInt(z.readLine());
switch(c)
{
case 1:
System.out.println("Enter the number to inserted ->");
k=Integer.parseInt(z.readLine());
System.out.println("Enter the position at which the number is to be inserted->");
n =Integer.parseInt(z.readLine());
pos=1;
l3=new link();
l3.data=k;
l3.next=null;
for(l2=l1;l2.next!=l1;l2=l2.next)
{
pos++;
if(n<1)
{
System.out.println("Invalid position");
break;
}
if(n==1)
{
l4=l1;
while(l4.next!=l1)
l4=l4.next;
l3.next=l1;
l1=l3;
l4.next=l1;
break;
}
if(pos==n)
{
l3.next=l2.next;
l2.next=l3;
break;
}
}//end of for
if(l2.next==l1&&n>pos)                        //if n>no.of elements entered
{
l2.next=l3;
l3.next=l1;
}
break;
case 2:
System.out.println("Enter number to be inserted ->");
k=Integer.parseInt(z.readLine());
System.out.println("Enter number after which you want to insert ->");
h=Integer.parseInt(z.readLine());
l3=l1;
l4=new link();
l4.data=k;
l4.next=null;
while(l3.data!=h)
l3=l3.next;
if(l3.next==l1)
{
l3.next=l4;
l4.next=l1;
}
else
{
l4.next=l3.next;
l3.next=l4;
}
break;
case 3:
System.out.println("Enter number to be inserted ->");
k=Integer.parseInt(z.readLine());
System.out.println("Enter number before which you want to insert ->");
h=Integer.parseInt(z.readLine());
l3=new link();
l4=new link();
l4.data=k;
l4.next=null;
l3=l1;
if(l1.data!=h)
{
while(l3.next.data!=h)              
l3=l3.next;
l4.next=l3.next;
l3.next=l4;
}
else
{
link l5=l1;
while(l5.next!=l1)
l5=l5.next;
l4.next=l1;
l1=l4;
l5.next=l1;
}
break;
case 4:
break abc;
default:
System.out.println("Wrong choice");
}//end of switch
}while(c!=4);
break;
case 2:
abc:do
{
System.out.println();
System.out.println("Enter choice->\n1)Delete at a position\n2)Delete a value\n3)Exit");
c=Integer.parseInt(z.readLine());
switch(c)
{
case 1:
System.out.println("Enter the position at which the number is to be deleted ->");
n =Integer.parseInt(z.readLine());
pos=1;
l3=new link();
for(l2=l1;l2.next!=l1;l2=l2.next)
{
pos++;
if(n<1)
{
System.out.println("Invalid postion");
break;
}
if(n==1)
{
while(l2.next!=l1)
l2=l2.next;
l1=l1.next;
l2.next=l1;
break;
}
if(pos==n)
{
l3=new link();
l3=l2.next;
l2.next=l3.next;
l3.next=null;
break;
}
}//end of for
break;
case 2:
System.out.println("Enter number which you want to delete :");
h=Integer.parseInt(z.readLine());
int f=0,g=0;
l3=l1;
while(l3.data!=h)
{
if(l3.next==l1)
{f=1;break;}
else
l3=l3.next;
}
if(l3.data==h && f!=1)
{
l3=l1;
l4=new link();
if(l1.data!=h)
{
while(l3.next.data!=h)              
{
if(l3.next==l1)
{
g=1;
break;
}
l3=l3.next;
}
l4=l3.next;
l3.next=l4.next;
l4.next=null;
}
else
{
l3=l1;
while(l3.next!=l1)
l3=l3.next;
l1=l1.next;
l3.next=l1;
}
}
else
System.out.println("Not found");
break;
case 3:
break abc;
default:
System.out.println("Wrong choice");
}//end of switch
}while(c!=3);
break;
case 3:
System.out.println("Enter the number to searched ->");
k=Integer.parseInt(z.readLine());
l3=l1;
while(l3.data!=k)
{
if(l3.next==l1)
break;
else
l3=l3.next;
}
if(l3.data==k)
System.out.println("Found");
else
System.out.println("Not found");
break;
case 4:
l2=l1;
do
{
System.out.print(l2.data+"  ");
l2=l2.next;
}while(l2!=l1);
System.out.println();
break;
case 5:
break outer;
default:
System.out.println("Wrong choice");
}
}while(c1!=5);
}
}









Enter a number ->
6
Do you want to continue Y/N ->
Y
Enter a number ->
3
Do you want to continue Y/N ->
Y
Enter a number ->
4
Do you want to continue Y/N ->
Y
Enter a number ->
2
Do you want to continue Y/N ->
Y
Enter a number ->
41
Do you want to continue Y/N ->
Y
Enter a number ->
21
Do you want to continue Y/N ->
Y
Enter a number ->
20
Do you want to continue Y/N ->
Y
Enter a number ->
65
Do you want to continue Y/N ->
N
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
1


Enter choice->
1)Add at a position
2)Add after a value
3)Add before a value
4)Exit
1
Enter the number to inserted ->
8
Enter the position at which the number is to be inserted->
4


Enter choice->
1)Add at a position
2)Add after a value
3)Add before a value
4)Exit
2
Enter number to be inserted ->
42
Enter number after which you want to insert ->
41


Enter choice->
1)Add at a position
2)Add after a value
3)Add before a value
4)Exit
3
Enter number to be inserted ->
27
Enter number before which you want to insert ->
41


Enter choice->
1)Add at a position
2)Add after a value
3)Add before a value
4)Exit
4
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
4
6  3  4  8  2  27  41  42  21  20  65
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
2


Enter choice->
1)Delete at a position
2)Delete a value
3)Exit
1
Enter the position at which the number is to be deleted ->
4


Enter choice->
1)Delete at a position
2)Delete a value
3)Exit
2
Enter number which you want to delete :
20


Enter choice->
1)Delete at a position
2)Delete a value
3)Exit
3
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
4
6  3  4  2  27  41  42  21  65
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
3
Enter the number to searched ->
25
Not found
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
3
Enter the number to searched ->
42
Found
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
4
6  3  4  2  27  41  42  21  65
Enter choice->
1)Insert
2)Delete
3)Search
4)Print
5)Exit
5


