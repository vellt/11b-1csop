```c#
/* Intervallumok képzése a randommal */
Random r = new Random();
int sz1= r.Next(10); // [0,9]
// [10,60]
int sz2 = r.Next(51) + 10;
// [15,30]
int sz3 = r.Next(16) +15;
// [-1,20]
int sz4 = r.Next(22)-1;
// [-20,21]
int sz5 = r.Next(42)-20;
// [-20, -5]
int sz6 = r.Next(16)-20;
// [-5, -2]
int sz7 = r.Next(4)-5;

/*
 Állítsunk elő véletlen számot [0,10], a generált számot
írjuk ki, majd döntsük el hogy páros vagy páratlan
 */
Random r2 = new Random();
int x = r2.Next(11); // [0,10]
Console.Write($"a szám: {x} ");
if (x % 2 == 0)
{
	Console.WriteLine("páros");
}
else
{
	Console.WriteLine("páratlan");
}

/* Random generáljuk 2 számot [10,20], és írjuk ki
 * az értékeiket. Majd döntsük el
 * hogy melyik a nagyobb, ha egyenlő írjuk ki hogy a két
 szám az egyenlő. */

Random r4 = new Random();
int szam1 = r4.Next(11)+10;
int szam2 = r4.Next(11)+10;
Console.WriteLine($"szam1: {szam1}, szam2: {szam2}");
if (sz1 == sz2) Console.WriteLine("A kettő szám egyenlő");
else if (szam1 > szam2) Console.WriteLine("Az első szám a nagyobb");
else Console.WriteLine("A második szám a nagyobb");

// logikai kapuk
// AND (és): &&
// OR (vagy): ||
// NOT (negálás): !

/*
 * 3 random számot [15,30] kell generáléni és kiiírni, hogy lássuk mi generálódott!
 ellenőrízzük hogy a 3szög szerkeszthető-e. 
hogyan? akkor szerkeszthető, ha (a+b>c) és (a+c>b) és (b+c>a) 
 */
Random r5 = new Random();
int a = r5.Next(16)+15;
int b = r5.Next(16)+15;
int c = r5.Next(16)+15;

if ((a + b > c) && (a + c > b) && (b + c > a))
{
	Console.WriteLine("3szög szerkeszthető");
}
else
{
	Console.WriteLine("3szög nem szerkeszthető");
}

/*
 vizsgáljuk meg h egy szám osztható-e a másikkal, maradék
nélkül. intervallum= [1,10]
 */
Random r6 = new Random();
int x1 = r6.Next(10)+1;
int x2 = r6.Next(10)+1;
Console.WriteLine($"{x1} {x2}");
if (x1 % x2 == 0)
{
	Console.WriteLine($"{x1} osztható maradék nélkül {x2} számmal");
}
else
{
	Console.WriteLine($"{x1} NEM oszható m.n. {x2} számmal");
}

/*
 biztons. őr 3 dolgot állapít meg egy illetőröl:
alkohol szaga van, 1 vagy 0 érték 
bizonytalanul mozog, 1 vagy 0 érték
nincs-e fegyvere, 1 vagy 0 érték

ezekhez 3 akció társul:
--> ("kockázatos"): "alkohol szaga van" ÉS "bizonytalanul mozog"
	--> kidobja az illetőt
--> ("veszélyes"): "alk. szaga van" ÉS "Biz. mozog" ÉS "Fegyvere van"
	--> hivja a rendőrt
--> ("gyanus"):  "alk. szaga van" VAGY "Biz. mozog" VAGY "Fegyvere van"
	--> figyeli
 */
Random r7 = new Random();
int alkohol = r7.Next(2);
int mozg = r7.Next(2);
int fegyver = r7.Next(2);
switch (alkohol)
{
	case 1: Console.WriteLine("Nincs alkohol szaga"); break;
	default: Console.WriteLine("Alkholszaga van");break;
}
switch (mozg)
{
	case 1: Console.WriteLine("Bizonytalanul mozog"); break;
	default: Console.WriteLine("Nem mozog biz.nul"); break;
}
switch (fegyver)
{
	case 1: Console.WriteLine("van fegyvere"); break;
	default: Console.WriteLine("nincs fegyvere"); break;
}

if(alkohol==1  && mozg == 1)
{
	Console.WriteLine("kidobja az illetőt");
}
if(alkohol==1 && mozg==1 && fegyver == 1)
{
	Console.WriteLine("hivja a rendőrt");
}
if (alkohol == 1 || mozg == 1 || fegyver == 1)
{
	Console.WriteLine("figyeli");
}


/* random generáljunk 3 értéket [-5,10] 
 * végezzünk statisztikát a számokkal */
Random random = new Random();
int n1 = random.Next(16)-5;
int n2 = random.Next(16)-5;
int n3 = random.Next(16)-5;

// hány pozitív van 
int szamlalo = 0;
if (n1 >= 0) szamlalo++;
if (n2 >= 0) szamlalo++;
if (n3 >= 0) szamlalo++;
Console.WriteLine($"{szamlalo} enNyi pozitiv szám van.");

// hány negatív van
int nszamlalo = 0;
Console.WriteLine($"{n1} {n2} {n3}");
if (n1 < 0) nszamlalo = nszamlalo + 1;
if (n2 < 0) nszamlalo = nszamlalo + 1;
if (n3 < 0) nszamlalo = nszamlalo + 1;
Console.WriteLine($"Ennyi negatív szám van:{nszamlalo}");

// mennyi az átlaguk, 2 tizedesre kerekítve 
// osztásnál ügyelni, hogy egyik tag double legyen
double atlag = (n1 + n2 + n3) / 3.0;
Console.WriteLine($"{atlag:0.00}");

// mennyi páros van
int pszamlalo = 0;
if (n1 % 2 == 0) pszamlalo++;
if (n2 % 2 == 0) pszamlalo++;
if (n3 % 2 == 0) pszamlalo++;
Console.WriteLine($"ennyi van: {pszamlalo}");


Console.ReadKey();
```