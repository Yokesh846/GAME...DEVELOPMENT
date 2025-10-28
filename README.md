# EX 8 : THREE DIMENSIONAL IMAGE PROJECTIONS

## AIM :
    
  To implement the projections in three dimensional image using a C coding.


## ALGORITHM :

   Step 1 : start.

   Step 2 : Draw any image in the three dimensional plane.

   Step 3 : Get the choice of axis as input from the user.

   Step 4 : Perform the projection about the desired axis.

   Step 5 : Display the projected image.

   Step 6 : Stop.

## Program :

Name: Dharshini S

Reg no: 212224040074

```
#include<stdio.h> 
#include<math.h> 
#include<conio.h> 
#include<stdlib.h> 
#include<graphics.h> 
int gd=DETECT,gm;     
double x1,x2,y1,y2; 
void draw_cube(double edge[20][3]) 
{ 
int i; 
initgraph(&gd,&gm,"..\bgi"); 
clearviewport(); 
for(i=0;i<19;i++) 
{ 
x1=edge[i][0]+edge[i][2]*(cos(2.3562)); 
y1=edge[i][1]-edge[i][2]*(sin(2.3562)); 
x2=edge[i+1][0]+edge[i+1][2]*(cos(2.3562));     
y2=edge[i+1][1]-edge[i+1][2]*(sin(2.3562)); 
line(x1+320,240-y1,x2+320,240-y2);     
} 
line(320,240,320,25); 
line(320,240,550,240); 
line(320,240,150,410); 
getch(); 
closegraph();     
} 
void perspect(double edge[20][3]) 


 { 
 int ch; 
 int i; 
 float p,q,r; 
 clrscr(); 
 printf("\n -=[ Perspective Projection About ]=-"); 
 printf("\n 1:==>X-Axis "); 
 printf("\n 2:==>Y-Axis "); 
 printf("\n 3:==>Z-Axis "); 
 printf("\n Enter Your Choice :="); 
 scanf("%d",&ch); 
 switch(ch) 
  { 
  case 1: 
   printf("\n Enter P :="); 
   scanf("%f",&p); 
   for(i=0;i<20;i++) 
{ 
edge[i][0]=edge[i][0]/(p*edge[i][0]+1); 
edge[i][1]=edge[i][1]/(p*edge[i][0]+1); 
edge[i][2]=edge[i][2]/(p*edge[i][0]+1); 
} 
   draw_cube(edge); 
      break; 
  case 2: 
   printf("\n Enter Q :="); 
   scanf("%f",&q); 
   for(i=0;i<20;i++) 


{ 
edge[i][1]=edge[i][1]/(edge[i][1]*q+1); 
edge[i][0]=edge[i][0]/(edge[i][1]*q+1); 
edge[i][2]=edge[i][2]/(edge[i][1]*q+1); 
} 
   draw_cube(edge); 
   break; 
  case 3: 
   printf("\n Enter R :="); 
   scanf("%f",&r); 
   for(i=0;i<20;i++) 
{ 
edge[i][2]=edge[i][2]/(edge[i][2]*r+1); 
edge[i][0]=edge[i][0]/(edge[i][2]*r+1); 
edge[i][1]=edge[i][1]/(edge[i][2]*r+1); 
} 
   draw_cube(edge); 
   break; 
  } 
 closegraph(); 
 } 
 void main() { 
 int choice; 
 double edge[20][3]= { 
   100,0,0,100,100,0,0,100,0,0,100,100,0,0,100,0,0,0, 
   100,0,0,100,0,100,100,75,100,75,100,100,100,100,75, 
   100,100,0,100,100,75,100,75,100,75,100,100,0,100,100, 
   0,100,0,0,0,0,0,0,100,100,0,100 
}; 
clrscr(); 
draw_cube(edge); 
perspect(edge); 
closegraph(); 
}


```

## Output :
<img width="633" height="468" alt="Screenshot 2025-10-06 112452" src="https://github.com/user-attachments/assets/d054b613-566a-47cd-83ec-50e3cce1ae5e" />



<img width="635" height="392" alt="Screenshot 2025-10-06 112515" src="https://github.com/user-attachments/assets/b316e1cd-303a-4eeb-ada6-0881be4c8a5a" />

<img width="619" height="467" alt="Screenshot 2025-10-06 112521" src="https://github.com/user-attachments/assets/42eda2c9-2b8a-4fd5-aab8-a4a60ffcb610" />

<img width="646" height="395" alt="Screenshot 2025-10-06 112547" src="https://github.com/user-attachments/assets/15d30b15-8bbc-409f-b43b-9c90710c1845" />

<img width="622" height="453" alt="Screenshot 2025-10-06 112559" src="https://github.com/user-attachments/assets/e606db51-f7bb-460c-8516-608876385852" />

<img width="634" height="403" alt="Screenshot 2025-10-06 112614" src="https://github.com/user-attachments/assets/5b634373-6956-4753-981d-a3bc5f5dbfb4" />

<img width="624" height="475" alt="Screenshot 2025-10-06 112620" src="https://github.com/user-attachments/assets/4f2ff9bf-09d5-4583-9900-1dbb53df4d4a" />

## Result :

Thus, the C program for performing perspective projections of a 3D object along the X, Y, and Z axes was successfully implemented. The output images demonstrate the effect of projecting the 3D object onto different planes based on user input.
