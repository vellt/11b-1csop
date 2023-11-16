```c#
/*
 összetett logikai kifejezések
(>, <, >=, <=, ==, !=)-->(&&, ||)
 
 if struktúrák-->switch-ccsé alakítása

egyparaméteres random számokkal való műveletek

3, vagy több elem növekvő/csökkenő sorrendbe való cserélgetése

while, do while ciklusokkal feladatok
 */


// if-->switch----------------------------------
// szabályok:
// if feltételben "=="-t látunk
// de hogyha >, >=, !=, < , &&, || --> azok nem alakíthatóak át, 
// a switch csak ==-t tud kezelni
// ==-jel jobb oldalán különböző konstansnak kell lennie
// ==-jel bal oldalán változónak kell lenni, ha több feltétel
// van akkor mindegyikben egyforma változónak kell lennie
// if if if if if ---> az nem alakítható át swich-é
// ha if, else if, else if....else ---> átalakítható


int a = 7;
int b = 8;
int c = 10;
if (a == b) Console.WriteLine("a és b egyenlő");
else if (a == c) Console.WriteLine("a és c egyenlő");
else Console.WriteLine("a nem egyenlő b-vel és c-vel sem");
// nem alakítható át, mert az ==-jel jobb oldalán változó van,
// nem pedig konstans
switch (a)
{
	case b: Console.WriteLine("a és b egyenlő"); break;
	case c: Console.WriteLine("a és c egyenlő"); break;
	default: Console.WriteLine("a nem egyenlő b-vel és c-vel sem"); break;
}

int vegosszeg = 10_000;
string kedvezeny = "10%";
if (kedvezeny == "10%") Console.WriteLine(vegosszeg*0.9);
else if (kedvezeny == "30%") Console.WriteLine(vegosszeg*0.7);
else if (kedvezeny == "50%") Console.WriteLine(vegosszeg*0.5);
else Console.WriteLine("nállunk nincs ilyen kedvezmény");
// igen átalakítható
switch (kedvezeny)
{
	case "10%": Console.WriteLine(vegosszeg * 0.9); break;
	case "30%": Console.WriteLine(vegosszeg * 0.7); break;
	case "50%": Console.WriteLine(vegosszeg * 0.5); break;
	default: Console.WriteLine("nállunk nincs ilyen kedvezmény"); break;
}

// kövi

int ora = 12;
int perc = 30;
if(ora==10 && perc == 30)
{
	Console.WriteLine("Még van 2 órám kezdésig");
}else if (ora == 12)
{
	Console.WriteLine("Még van 2 órám");
}
else
{
	Console.WriteLine("Elkéstem");
}
// azért nem alakítható át, mert az első if-ben 
// AND operátor van (&&)

int eredmeny = 5;
if (eredmeny == 5) Console.WriteLine("jeles");
else if (eredmeny == 4) Console.WriteLine("jó");
else if (eredmeny == 3) Console.WriteLine("közepes");
else if (eredmeny == 2) Console.WriteLine("elégsége");
else if (eredmeny == 1) Console.WriteLine("elégtelen");
// ez igy átalakítható, bár ha csak else if helyett if lenne
// akk az már nem írható fel switchel egyazonos funkcionaliztással

switch (eredmeny)
{
	case 5: Console.WriteLine("jeles"); break;
	case 4: Console.WriteLine("jó"); break;
	case 3: Console.WriteLine("közepes"); break;
	case 2: Console.WriteLine("elégsége"); break;
	case 1: Console.WriteLine("elégtelen"); break;
}

// 3 random szám [-200,50]
// csökkenő

Random random = new Random();
int szam1 = random.Next(251)-200;
int szam2 = random.Next(251)-200;
int szam3 = random.Next(251)-200;
Console.WriteLine($"{szam1} {szam2} {szam3}");
if (szam1 < szam2)
{
	//csere
	int temp = szam2;
	szam2 = szam1;
	szam1 = temp;
}
if (szam1 < szam3)
{
	// csere
	int temp = szam3;
	szam3 = szam1;
	szam1 = temp;
}
if (szam2 < szam3)
{
	//csere
	int temp = szam3;
	szam3 = szam2;
	szam2 = temp;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");

// ciklusok
// while, do while

// 15 *-t írjunk ki
int szamlalo = 1;
while (szamlalo != 16)
{
	Console.WriteLine("*");
	szamlalo++;
}

// *
// **
// ***
// ****
// *
int szamlalo2 = 0;
while (szamlalo2!=4)
{
	szamlalo2++;
	int belsoSzamlalo = 0;
	while (belsoSzamlalo!=szamlalo2)
	{
		Console.Write("*");
		belsoSzamlalo++;
	}
	Console.WriteLine();
	if (szamlalo2 == 4) Console.WriteLine("*");
}

// kérj be egy x, és egy y-t
// (y legyen nagyobb mint az x)
// x-től y-ig, 
// az aktuális értéknek irja ki a négyzetét
// 1-->1, 2-->4, 3-->9

Console.WriteLine("Add meg az x értékét");
int x = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("Add meg az y értékét");
int y = Convert.ToInt32(Console.ReadLine());

while (x!=(y+1))
{
	Console.WriteLine($"{x}-->{x*x}");
	Console.WriteLine($"{x}-->{Math.Pow(x,2)}");
	x++;
}

// írassa ki 99-től 1-ig
// kiíratni az összes pozitív, 3al osztható egész
// számot

int szamlalo3 = 99;
while (szamlalo3!=0)
{
	if(szamlalo3 % 2==0 && szamlalo3 % 3==0)
		Console.WriteLine(szamlalo3);
	
	
	szamlalo3--;
}
```