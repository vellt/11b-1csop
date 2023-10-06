```c#
// logikai operátorok: ==, !=, >, <, >=, <=
// true, vagy false-->bool típus
// logikai kapuk (logic gate):
// komplex logikai kifejezésekhez
// AND = && (AltGr + C)
// OR = || (AltGr + W)
// NOT = ! (Shift + 4)

bool and = (true && false);
Console.WriteLine(and);//false

bool or = (true || false);
Console.WriteLine(or);

bool not = !true;
Console.WriteLine(not); //false

/*
	Írjunk egy kifejezést, amely azt ellenőrzi, hogy egy adott
	szám osztható-e 3mal vagy 5-el
 */

Console.WriteLine("Add meg az x értékét");
int x = Convert.ToInt32(Console.ReadLine());

if ((x % 3 == 0) || (x % 5 == 0))
{
	Console.WriteLine($"Ez a(z) {x} szám olyan érték, ami vagy 3 és vagy 5-el osztható");
}

/*
 * && (AND) logikai kapuval kellene felírni
 */

Console.WriteLine("Add meg az o értékét");
int o = Convert.ToInt32(Console.ReadLine());
if (o > 0 && o < (((17 % 2) + (6 / 2)) / 4 + 1))  //1
{
	Console.WriteLine("FEJ");
}
else if (o > -1 && o < (Math.Pow(2, 3) - 7)) //o==0 
{
	Console.WriteLine("ÍRÁS");
}


/*
	Írjunk egy kifejezést, amely azt ellenőrzi, 
	hogy egy adott szám osztható-e 3mal vagy 5-el, 
	de nem mindkettővel!!
*/
Console.WriteLine("add meg az 'a' értékét");
int a = Convert.ToInt32(Console.ReadLine());
if (((a % 3 == 0) || (a % 5 == 0)) && !((a % 3 == 0) && (a % 5 == 0))) 
{
	// itt  minden lefut ha a feltétel igaz
}

/*
 * Írj egy kif, amely azt ellenőrzi, hogy egy adott 
 * szám páros és pozitív is egyben
 */
Console.WriteLine("add meg a l értékét");
int l = Convert.ToInt32(Console.ReadLine());
if ((l % 2 == 0) && (l >= 0)) 
{
	// páros és pozitív
}
else if(!((l % 2 == 0) && (l >= 0)))
{
	// páratlan és negatív
}else if ((l % 2 == 0) && !(l >= 0))
{
	// páros és negatív
}
else if (!(l % 2 == 0) && (l >= 0))
{
	// páratlan és pozitív
}


//----------------------------------------------
// RANDOM
Random r = new Random();
int random1 = r.Next(10); //[0,9]
int random2 = r.Next(7); //[0,6]
int random3 = r.Next(101); // [0,100]

// [-50, 50]
int random4 = r.Next(101)-50;
// [-100, 100]
int random5 = r.Next(201)-100;
// [1,60]
int random6 = r.Next(60)+1;
// [-15,-5]
int random7 = r.Next(11)-15;

// 2 paraméteres next
Random r2 = new Random();
// [-50, 50]
int random8 = r2.Next(-50, 51);
// [-100, 100]
int random9 = r2.Next(-100, 101);

/*
 Készítsen egy programot, amely generál egy random számot
[1,6] intervallumban. Majd kér egy tippet a felhasználótól
ha eltalálta a felh, írja ki hogy sikerült eltalálnia, ha nem
írja ki mire gondolta a gép.
 */

Random r4 = new Random();
int randomSzam = r4.Next(1, 7);
Console.WriteLine("Kérlek add meg a tipped");
int tipp = Convert.ToInt32(Console.ReadLine());
if (randomSzam == tipp)
{
	Console.WriteLine("Eltaláltad");
}
else
{
	Console.WriteLine($"Nem sikerült! Amire én gondoltam az a {randomSzam}");
}

/*
	2 random számot [1,10] készítsünk és 
	számoljuk ki az összegüket, kivonásukat, 
	szorzatukat, hányadosukat
 */
Random random = new Random();
int num1 = random.Next(10)+1; //vagy .Next(1,11);
int num2 = random.Next(10) + 1;
Console.WriteLine($"{num1}+{num2}={num1 + num2}");
Console.WriteLine($"{num1}-{num2}={num1 - num2}");
Console.WriteLine($"{num1}*{num2}={num1 * num2}");
Console.WriteLine($"{num1}/{num2}={num1 / Convert.ToDouble(num2)}");
```