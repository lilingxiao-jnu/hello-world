# hello-world
pre
#include<iostream>
#include<iomanip>
#include<cmath>
using namespace std;
double f(double x)
{
	return 2 + sin(2 * sqrt(x));
}
/*double fun(double a, double b, int c)
{
	double x, h = (b - a) /( 2.0 * c);
	double s1 =0, s2=0; 
	for (int i = 0; i < c; i++)
	{
		x = a + h * (2.0 * i + 1);
		s1+=  f(x);
	}
	for (int i = 1; i <c; i++)
	{
		x = a + h * (2.0 * i);
		s2 += f(x);
	}
	return h * (f(a) + f(b) + 4.0 * s1 + 2.0 * s2) / 3;
}*/
double fun(double a, double b, int c)
{
	double s=0, x, h = (b - a) / c;
	for (int i = 0; i < c; i++)
	{
		x = a + h * i;
		s += f(x)+f(x+h);
	}
	return h * s / 2;
}
int main()
{
	int c;
	double a, b;
	cin >> a >> b >> c;
	cout<<setprecision(6)<<fun(a, b, c);	
}
