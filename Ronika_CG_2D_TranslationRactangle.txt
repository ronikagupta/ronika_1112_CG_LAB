#include<stdio.h>
#include<conio.h>
#include<graphics.h>
#include<process.h>
#include<math.h>

void RectAngle(int x, int y, int Height, int Width);
void Translate(int x, int y, int Height, int Width);

void main() {
   int gd = DETECT, gm;
   int x, y, Height, Width;
   initgraph(&gd, &gm, " ");
   printf("Enter the First point for the Rectangle:");
   scanf("%d%d", &x, &y);
   printf("Enter the Height&Width for the Rectangle:");
   scanf("%d%d", &Height, &Width);
   RectAngle(x, y, Height, Width);
   getch();
   cleardevice();
   Translate(x, y, Height, Width);
   RectAngle(x, y, Height, Width);
   getch();
}

void RectAngle(int x, int y, int Height, int Width) {
   line(x, y, x + Width, y);
   line(x, y, x, y + Height);
   line(x + Width, y, x + Width, y + Height);
   line(x, y + Height, x + Width, y + Height);
}

void Translate(int x, int y, int Height, int Width) {
   int Newx, Newy, a, b;
   printf("Enter the Transaction coordinates");
   scanf("%d%d", &Newx, &Newy);
   cleardevice();
   a = x + Newx;
   b = y + Newy;
   RectAngle(a, b, Height, Width);
}