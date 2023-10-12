```c#
// logikai operátorok:
// >, <, !=, ==, <=, >=
// logikai kapuk:
// NOT (negáció): ! (Shift + 4)
// OR (vagy): || (altgr + w)
// AND (és): && (altgr + c)

// vissztérési értékük: logikai típus: igaz/hamis
// bool--> true/false

bool valtozo = !(7 < 0) && !(6 > 7); // true

// Írjunk egy kif-t ami ellenőrzi hogy egy
// szám páros ÉS pozitív

Console.WriteLine( "Adj meg egy számot:" );
int a = Convert.ToInt32(Console.ReadLine());
if ((a % 2 == 0) && (a >= 0)) 
{
	// páros + pozitív
	Console.WriteLine("A szám páros és pozitív.");
}
if ( (a % 2 == 0) && !(a >= 0))
	
{
	Console.WriteLine("a szam paros es negativ dili");
	// páros +  negatív 
}
if (!(a % 2 == 0) && (a >= 0))
{
	// páratlan + pozitív
	Console.WriteLine("a szam paratlan es pozitiv");
}
if (!((a % 2 == 0) && (a >= 0))) 
{
	//páratlan és negatív
	Console.WriteLine();
}

/*
 Kérj be egy telószámot, 06 utánit, és ellenőrizd
hogy valid-e, ha igen nézd meg h milyen szolgáltatóhoz
tartozik
 */

Console.WriteLine("adj meg egy telefon számot 06 után");
string telefonszam = Console.ReadLine();

if (telefonszam.Length == 9)
{
	Console.WriteLine("valos telefon szám:");
	if (telefonszam[0] == '3') Console.WriteLine("Telekom");
	if (telefonszam[0] == '7') Console.WriteLine("vodafon");
	if (telefonszam[0] == '2') Console.WriteLine("yettel");
}
else Console.WriteLine("nem valós telefonszám");

switch (telefonszam.Length)
{
	case 9:
		Console.WriteLine("valós szám");
		switch(telefonszam[0])
		{
			case '3': Console.WriteLine("Telekom"); break;
			case '7': Console.WriteLine("vodafon");break;
			case '2': Console.WriteLine("yettel");break;
		}
		break;
	default: Console.WriteLine("nem valós telefonszám"); break;
}


// random

Random r = new Random();
int rand = r.Next(11); //[0, 10]
int rand2 = r.Next(9)+2; //[2, 10]
int rand3 = r.Next(53)-2; //[-2, 50]
int rand4 = r.Next(-29)-20; //[-20, -50]

/*
 generálj 6,10 között számot, 
majd a *,/, +, - végezzük el
 */

Random r1 = new Random();
int szam1 = r1.Next(5)+6; //6,10
int szam2 = r1.Next(5)+6;
Console.WriteLine($"{szam1}+{szam2}={szam1 + szam2}");
Console.WriteLine($"{szam1}-{szam2}={szam1 - szam2}");
Console.WriteLine($"{szam1}*{szam2}={szam1 * szam2}");
Console.WriteLine(
	(szam1 < szam2) 
	? $"{szam1}/{szam2}={szam1 / Convert.ToDouble(szam2)}" 
	: $"{szam2}/{szam1}={szam2 / Convert.ToDouble(szam1)}"
);

//RANDOM-------------------------

/*
 Számítsuk ki 5 véletlen [50,110] szám összegét, átlagát és írjuk ki a képernyőre
 */

Random r3 = new Random();
int sz1 = r3.Next(61) + 50;
int sz2 = r3.Next(61) + 50;
int sz3 = r3.Next(61) + 50;
int sz4 = r3.Next(61) + 50;
int sz5 = r3.Next(61) + 50;
double osszeg = sz1 + sz2 + sz3 + sz4 + sz5;
Console.WriteLine($"összeg: {osszeg}");
Console.WriteLine($"átlag: {osszeg / 5}");

/*
 Készítsünk egy kö/papír/olló programot
A gép [1,3] között generál
1-->kő
2-->papírt
3-->ollót
kérjen be egy számot a felhtól, 
if else legyen megoldva a logika
 */

Random random10 = new Random();
int gepSzam = random10.Next(3) + 1;
Console.WriteLine("Adj egy számot (1-3)[kő, papír, olló]");
int felhSzam = Convert.ToInt32(Console.ReadLine());
// kiíratom a gép mire gondolt
Console.Write("Gép: ");
switch (gepSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}
// kiíratom, hogy a felh. mire gondolt
Console.Write("Felh: ");
switch (felhSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}

if (gepSzam == felhSzam) Console.WriteLine("Döntetlen");
else if (gepSzam == 1 && felhSzam == 3
	|| gepSzam == 2 && felhSzam == 1
	|| gepSzam == 3 && felhSzam == 2
	) Console.WriteLine("gép győzött");
else Console.WriteLine("én nyertem");
```