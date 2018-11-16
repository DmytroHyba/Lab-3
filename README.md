#include "pch.h"
#include <iostream>
#include <math.h>
#include <stdio.h>
#define n 5
void bul(int a[n][n]);
void bul(int geom[n]);
int main(void)
{
	int i, j, sum, g, dob = 1, r, aref;
	int ge;
	static int a[n][n];
	static int geom[n];
	system("cls");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < n; j++)
		{
			printf("a[%d][%d] =", i + 1, j + 1);
			scanf_s("%d", &a[i][j]);
		}
	}
	printf("old array\n");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < n; j++)
			printf("%5d", a[i][j]);
		printf("\n");
	}
	bul(a);
	printf("\nnew array\n");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < n; j++)
		{
			printf("%5d", a[i][j]);
		}
		printf("\n");
	}



	for (r = 1, j = 0, g = 0; j < n; j++, g++, r++)
	{
		for (sum = 0, i = 0; i < n; i++)
		{

			sum = a[i][j] + sum;


		}
		aref = sum / n;
		printf("aref r%d=%d  ", r, aref);
		geom[g] = aref;



	}

	for (g = 0; g < n; g++)
	{

		dob = geom[g] * dob;

	}
	ge = pow(dob, 1.0 / 5.0);
	printf("  ge=%d", ge);


	for (int c = 0, i = 0; i < n; i++)
	{


		for (c = a[i][1], j = 0; j < n; j++)
		{
			if (c < a[i][j])
			{
				c = a[i][j];
			}

		}
		printf("max%d=%d ", i + 1, c);
		c = 0;
	}
}


void bul(int a[][n])
{
	int i, k, j, c;
	for (i = 0; i < n; i++)
	{
		for (k = n - 1; k >= 0; k--)
		{
			for (j = 0; j < k; j++)
			{
				if (a[i][j] > a[i][j + 1])
				{
					c = a[i][j];
					a[i][j] = a[i][j + 1];
					a[i][j + 1] = c;
				}
			}
		}
	}
}
