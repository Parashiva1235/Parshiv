// Cprogram to find voltage across given circuit
#include <stdio.h>
#include <math.h>
#define PI 3.142
int main() {
    char A,B,c,D,E,F;
    int n;
   float R,L,C,X1,X2,I,V,Z;
   printf("choose the type of circuit to calculate voltage by choosing their corresponding number\n");
   printf("Pure resistance-1\nPure capacitance-2\nPure inductance-3\nR-L Circuit-4\nR-C circuit-5\nR-L-C circuit-6\n");
   scanf("%d",&n);
   if(n==1)
   {
       printf("Enter the current through the circuit in Ampere and equivalent resistance of the circuit in Ohm respectively\n");
       scanf("%f%f",&I,&R);
       V=I*R;
       printf("voltage across the given circuit is:%fV\n",V);
   }
   else if(n==2)
   {
       printf("Enter the current through the circuit in Ampere and equivalent capacitance of the circuit in Faraday respectively\n");
       scanf("%f%f",&I,&C);
       X1=1/(2*3.142*50*C);
       V=I*X1;
       printf("voltage across the given circuit is:%fV\n",V);
   }
   else if(n==3)
   {
       printf("Enter the current through the circuit in Ampere and equivalent inductance of the circuit in Henry respectively\n");
       scanf("%f%f",&I,&L);
       X2=2*3.142*50*L;
       V=I*X2;
       printf("voltage across the given circuit is:%fV\n",V);
   }
   else if(n==4)
   {
       printf("Enter the current through the circuit in Ampere, equivalent inductance in Henry and equivalent resistance of the circuit in Ohm respectively\n");
       scanf("%f%f%f",&I,&L,&R);
       X2=2*PI*50*L;
       Z=sqrt((X2)*(X2)+R*R);
       V=I*Z;
       printf("voltage across the given circuit is:%fV\n",V);
   }
   else if(n==5)
   {
       printf("Enter the current through the circuit in Ampere, equivalent capacitance in Faraday and equivalent resistance of the circuit in Ohm respectively\n");
       scanf("%f%f%f",&I,&C,&R);
       X1=1/(2*PI*50*C);
       Z=sqrt((X1)*(X1)+R*R);
       V=I*Z;
       printf("voltage across the given circuit is:%fV\n",V);
   }
  else if(n==6)
   {
       printf("Enter the current through the circuit in Ampere, equivalent capacitance in Faraday, equivalent inductance in Henry and equivalent resistance of the circuit in Ohm respectively\n");
       scanf("%f%f%f%f",&I,&C,&L,&R);
       X1=1/(2*PI*50*C);
       X2=2*PI*50*L;
       Z=sqrt((X1-X2)*(X1-X2)+R*R);
       V=I*Z;
       printf("voltage across the given circuit is:%fV\n",V);
   }
   else
   printf("Error in choosing the ciruit\n");
    return 0;
}
