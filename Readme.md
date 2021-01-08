                                          07.01.2021
                                        f(x) = cosh (x/2)
                                 Teilora rindas - kods, versija 1

#include<stdio.h>
#include<math.h>
void main(){
 double x=-1,y,a0,a1,a2,a3,S0,S1,S2,S3;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a0 = pow(x,2*0)/(1.);
 S0 = a0;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a0,S0);

 a1 = pow(x,2*1)/(1.*1*2*8);
 S1 = a0 + a1;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a1,S1);

 a2 = pow(x,2*2)/(1.*1*2*3*4*64);
 S2 = a0 + a1 + a2;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a2,S2);

 a3 = pow(x,2*3)/(1.*1*2*3*4*5*6*512);
 S3 = a0 + a1 + a2 + a3;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a3,S3);
}

                                Teilora rindas - kods, versija 2
                                
// S0 , S1 , S2 , S3 −> S
#include<stdio.h>
#include<math.h>
void main(){
 double x=-1,y,a0,a1,a2,a3,S;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a0 = pow(x,2*0)/(1.);
 S = a0; //S0 = a0;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a0,S);

 a1 = pow(x,2*1)/(1.*1*2*8);
 S = S + a1; //S1 = a0 + a1; // S += a1;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a1,S);

 a2 = pow(x,2*2)/(1.*1*2*3*4*64);
 S = S + a2; //S2 = a0 + a1 + a2; // S += a2;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a2,S);

 a3 = pow(x,2*3)/(1.*1*2*3*4*5*6*512);
 S = S + a3; //S3 = a0 + a1 + a2 + a3; // S += a3;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a3,S);
}

                                     Teilora rindas - kods, versija 3

// a0 , a1 , a2 , a3 −> a
#include<stdio.h>
#include<math.h>
void main(){
 double x=-1,y,a,S;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a = pow(x,2*0)/(1.); //a0 = pow(x,2*0)/(1.);
 S = a; //S = a0;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);

 a = a*(x,2*1)/(2*8); //a1 = pow(x,2*1)/(1.*1*2*8);
 S = S + a; //S = S + a1;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);

 a = a*(x,2*2)/(3*4*8); //a2 = pow(x,2*2)/(1.*1*2*3*4*64);
 S = S + a; //S = S + a2;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);

 a = a*(x,2*3)/(5*6*64); //a3 = pow(x,2*3)/(1.*1*2*3*4*5*6*512);
 S = S + a; //S = S + a3;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
}

                                   Teilora rindas - kods, versija 4
#include<stdio.h>
#include<math.h>
void main(){
 double x=-1,y,a,S;
 int k=0;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a = pow(x,2*0)/(1.);
 S = a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 k++;
 a = a*(x,2*1)/(x); //a = a*(x,2*1)/(2*8);
 S = S + a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);;
 k++;
 a = a*(x,2*2)/(x); //a = a*(x,2*2)/(3*4*8);
 S = S + a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 k++;
 a = a*(x,2*3)/(x); //a = a*(x,2*3)/(5*6*64);
 S = S + a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
}

                            Teilora rindas - kods, versija 5

#include<stdio.h>
#include<math.h>
void main(){
 double x=-1,y,a,S;
 int k=0;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a = pow(x,2*0)/(1.);
 S = a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 
 while(k<3)
 {
 k++;
 a = a*(x,2*k)/(x);
 S = S + a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 }
}

                          Teilora rindas - kods, gala versija

#include<stdio.h>
#include<math.h>
double mans_cosh (double x){
double a, S;
int k=0;

 a = pow(x,2*0)/(1.);
 S = a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 
 while(k<3)
 {
 k++;
 a = a*(x,2*k)/(x);
 S = S + a;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a,S);
 }
 return S;
}
void main ()
    {
double x=-1, y, yy;
y = cosh(x/2);
 printf ("hiperboliskā funkcija cosh − y =cosh(%.1f)=%.1f\n",x,y);

yy = mans_cosh(x/2);
 printf ("lietotāja funkcija − y = mans_cosh(%.1f )=%.1f\n",x,yy);
    }

                 (k=499; k=500)

#include<stdio.h>
#include<math.h>
void main(){
 double x=30,y,a0,a499,a500,S0,S499,S500;
 y = cosh(x/2);
 printf("y=cosh(%.1f)=%.1f\n",x,y);

 a0 = pow(x,2*0)/(1.);
 S0 = a0;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a0,S0);

 a499 = pow(x,2*499)/(1.*998*2,1497);
 S499 = a0 + a499;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a499,S499);

 a500 = pow(x,2*500)/(1.*1000*2,1500);
 S500 = a0 + a499 + a500;
 printf("%.1f\t%8.1f\t%8.1f\n",x,a500,S500);
}
