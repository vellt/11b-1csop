```c#
Random random = new Random();
int sz = random.Next(10); //[0,9]
//[2,10]
int sz1 = random.Next(9)+2;
//[5,10]
int sz2 = random.Next(6)+5;
//[-5,10]
int sz3 = random.Next(16)-5;
// [-2,2]
int sz4 = random.Next(5)-2;
// [-10,-5]
int sz5 = random.Next(6)-10;
// [-30, -20]
int sz6 = random.Next(11)-30;

// generáljunk le 3 random számot [-100, 50]
// írjuk ki az értéküket
Random random1 = new Random();
int szam1 = random1.Next(151) - 100;
int szam2 = random1.Next(151) - 100;
int szam3 = random1.Next(151) - 100;
Console.WriteLine($"{szam1} {szam2} {szam3}");

// 1. mennyi páros ebből és mennyi a páratlan
int parosDarab = 0;
int paratlanDarab = 0;
if (szam1 % 2 == 0)
{
	// páros
	parosDarab++;
	//parosDarab=parosDarab+1;
	//parosDarab+=1;
}else
{
	// páratlan
	paratlanDarab++;
}

if (szam2 % 2 == 0) parosDarab++;
else paratlanDarab++;

if (szam3 % 2 == 0) parosDarab++;
else paratlanDarab++;

Console.WriteLine($"páros: {parosDarab},\npáratlan: {paratlanDarab}");

// mennyi a pozitív és mennyi a negatív ebből
int pozitivDarab = 0;
int negativDarab = 0;
if (szam1 >= 0) pozitivDarab++;
else negativDarab++;
if (szam2 >= 0) pozitivDarab++;
else negativDarab++;
if (szam3 >= 0) pozitivDarab++;
else negativDarab++;
Console.WriteLine($"poz: {pozitivDarab},\nneg: {negativDarab}");

// átlag, kerekítés 4 tizedre
double atlag = Convert.ToDouble(szam1 + szam2 + szam3) / 3.0;
Console.WriteLine($"átlaguk: {atlag:0.0000}");
Console.WriteLine($"átlaguk: {Math.Round(atlag,4)}");


string korso = "viz";
string pohar = "cola";
Console.WriteLine($"korso {korso}, pohar {pohar}");
string urespohar = korso;
korso = pohar;
pohar = urespohar;
Console.WriteLine($"korso {korso}, pohar {pohar}");

int x = 10;
int y = 5;
Console.WriteLine($"{x} {y}");
//csere
int temp = x;
x = y;
y = temp;
Console.WriteLine($"{x} {y}");

// hogyan lehet, (ugye van 3 változónk), a random
// számainknak az értékét megcserélni, szam1 csere szam2-vel
int temp2 = szam1;
szam1 = szam2;
szam2 = temp2;
Console.WriteLine($"{szam1} {szam2} {szam3}");

// növekvő sorrendbe tenni a 3 random számot

//szam1, szam2, szam3
Random random2 = new Random();
int num1 = random2.Next(151) - 100;
int num2 = random2.Next(151) - 100;
int num3 = random2.Next(151) - 100;
Console.WriteLine($"{num1} {num2} {num3}");
if (num1 > num2)
{
	int temp1 = num1;
	num1 = num2;
	num2 = temp1;
}
if (num1 > num3)
{
	int temp1 = num1;
	num1 = num3;
	num3 = temp1;
}
if (num2 > num3)
{
	int temp1 = num2;
	num2 = num3;
	num3 = temp1;
}
Console.WriteLine($"{num1} {num2} {num3}");

// while, do-while ciklus
// elöltesztelős ciklus: while
// hátultesztelős: do-while
// elöltesztelő ciklus (while): egy olyan ciklus, ami ellenörzi a fetételt, és
// addig fut, ismétli a ciklus magot, AMÍG a feltétel igaz

// hátlultesztelős (do while): mindenféleképpen 1x lefut, és első lefutás után
// ellenőrzi, hogy igaz-e a feltétel, és
// addig fut, ismétli a ciklus magot, AMÍG a feltétel igaz

int szam = 6;
while (szam>4)
{
	Console.WriteLine("while");
	Console.WriteLine("igen kisebb mint 4");
}

do
{
	Console.WriteLine("do while");
	Console.WriteLine("igen kisebb mint 4");
} while (szam < 4);

// kisebb feladatok:
// 6-10ig szám kiiratása while ciklussal
int szamlalo = 6;
while (szamlalo<=10)
{
	Console.WriteLine(szamlalo);
	szamlalo++;
	
}

//írjuk ki a páros számokat 2-10 között
int szamlslo2 = 2;
while (szamlslo2<=10)
{
	if (szamlslo2 % 2 == 0) Console.WriteLine(szamlslo2);
	szamlslo2++;
}

// írjuk ki 10től 1ig a számokat csökkenő sorrendben

int szamlalo3 = 10;
while (szamlalo3 >= 1) 
{
	Console.WriteLine(szamlalo3);
	szamlalo3--;
}

Console.ReadKey();
```