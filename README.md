```c#
while (true)
{
	Console.WriteLine("Add meg a százalékot!");
	int szazalek = Convert.ToInt32(Console.ReadLine());
	int erdemjegy = 1;
	if (szazalek >= 86) erdemjegy = 5;
	else if (szazalek >= 71) erdemjegy = 4;
	else if (szazalek >= 56) erdemjegy = 3;
	else if (szazalek >= 40) erdemjegy = 2;
	else erdemjegy = 1;
	switch (erdemjegy)
	{
		case 5: Console.WriteLine("jeles (5)"); break;
		case 4: Console.WriteLine("jó (4)"); break;
		case 3: Console.WriteLine("közepes (3)"); break;
		case 2: Console.WriteLine("elégséges (2)"); break;
		default: Console.WriteLine("elégtelen (1)"); break;
	}
}

// dolgozat feladatok -----------------------------------------
//1. feladat
Console.WriteLine("Add meg az x értét");
int x = Convert.ToInt32(Console.ReadLine());
if (x == 1) Console.WriteLine("hétfő");
else if (x == 2) Console.WriteLine("kedd");
else if (x == 3) Console.WriteLine("szerda");
else if (x == 4) Console.WriteLine("csütörtök");
else if (x == 5) Console.WriteLine("péntek");
else if (x == 6) Console.WriteLine("szombat");
else if (x == 7) Console.WriteLine("vasárnap");

//2. feladat
Console.WriteLine("add meg a 1. számot");
int szam1 = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("add meg a 2. számot");
int szam2 = Convert.ToInt32(Console.ReadLine());
if (szam1 < szam2)
{
	Console.WriteLine($"osztás eredménye: {(Convert.ToDouble(szam1)/szam2):0.0000}");
}
else
{
	Console.WriteLine($"osztás eredménye: {(Convert.ToDouble(szam2)/szam1):0.0000}");
}

// 3. feladat
Console.WriteLine("Add meg a szám értékét és kiszámolom a 21. gyökét");
int szam = Convert.ToInt32(Console.ReadLine());
double gyokvonas = Math.Pow(szam, (1 / Convert.ToDouble(21)));
Console.WriteLine($"A {szam} 21. gyöke: {gyokvonas:0.000}");

// 4. feladat
Console.WriteLine("add meg a rombusz hosszát");
double a = Convert.ToDouble(Console.ReadLine());
Console.WriteLine("add meg a rombusz hosszához tartozó magasságát");
double m = Convert.ToDouble(Console.ReadLine());
double T = a * m;
double K = 4 * a;
Console.WriteLine($"terület: {T:0.00}");
Console.WriteLine($"kerület: {K:0.00}");
```
