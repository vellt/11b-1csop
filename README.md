```c#
// printeljük ki, mit látunk?
int sz1 = 65;
int sz2 = 76;
int sz3 = 77;
int sz4 = 65;
Console.WriteLine($"{sz1} {sz2} {sz3} {sz4}");

// és most?
Console.WriteLine($"{(char)sz1} {(char)sz2} {(char)sz3} {(char)sz4}");

// az 'a' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
Console.WriteLine((int)'a');
// az 'z' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
Console.WriteLine((int)'z');

//A-->a
Console.WriteLine((char)(65+32));
//b-->B
Console.WriteLine((char)(98-32));

// alakítsuk nagybetűssé az "x, y, z"-t pl--> X, Y, Z
Console.WriteLine($"{'x' - 32} {'y' - 32} {'z' - 32}");

// A kisbetűs angolszász abc kiíratása, ehhez meg kell keresni
// az 'a' és a 'z' azonosítóját, amit korábban megtettünk
for (int i = 97; i <= 122; i++)
{
	Console.WriteLine((char)i);
}

// A nagybetűs angolszász abc kiíratása (32-vel eltolva kisbetűsöket kapunk)
for (int i = 97 - 32; i <= 122 - 32; i++)
{
	Console.WriteLine((char)i);
}

// szöveg mint tömb ------------------------------------------------------------
string beka = "beka";
Console.WriteLine(beka.Length); // 4 <--szöveg hossza
Console.WriteLine(beka[0]);// 'b' <--- az 1. indexet adja vissza
Console.WriteLine((int)beka[0]);// 98-as indexű ASCII kód

// Kérd be a neved kisbetűsen, és alakítsd át nagybetűssé
Console.WriteLine("Add meg a neved");
string nev = Console.ReadLine();
for (int i = 0; i < nev.Length; i=i+1)
{
	Console.Write((char)(nev[i]-32)); // -32-el eltolva nagybetűset kapunk
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést



// keressük meg, hogy a nevünkben van-e 'e' betű
int szamlalo = 0;
for (int i = 0; i < nev.Length; i = i + 1)
{
	if (nev[i] == 'e')
	{
		szamlalo++;
	}
}
if (szamlalo > 0) 
{
	Console.WriteLine($"Van benne 'e' betű. Méghozzá: {szamlalo} db");
}

// hány db magánhangzó van a bekért szövegben?
Console.WriteLine("Adj meg egy szöveget");
string szoveg = Console.ReadLine();
int darabszam = 0;
for (int i = 0; i < szoveg.Length; i++)
{
	
	if(
		szoveg[i]=='a'      || 
		szoveg[i] == 'e'    || 
		szoveg[i] == 'i'    || 
		szoveg[i] == 'u'    || 
		szoveg[i] == 'o'
		)
	{
		darabszam++;
	}
}
Console.WriteLine($"Ennyi db magánhangzó volt: {darabszam}");

// az előző feladatban lévő bekért szöveg összes magánhangzóját alakítsuk át i-betűvé
for (int i = 0; i < szoveg.Length; i++)
{

	if (
		szoveg[i] == 'a'    || 
		szoveg[i] == 'e'    || 
		szoveg[i] == 'u'    || 
		szoveg[i] == 'o'
		)
	{
		Console.Write('i'); // az magánhangzók helyére i-betűt
	}
	else
	{
		Console.Write(szoveg[i]); // minden másra az eredeti betűt íratjuk ki
	}
}

// alakítsuk át a nevünket nagybetűssé
string nev2 = "benjamin";
for (int i = 0; i < nev2.Length; i++)
{
	Console.WriteLine((char)(nev2[i]-32)); // kisbtű-->NAGYBETŰ -32vel eltolom
}

// nem mindegy a konstanst hogyan írjuk, meglehet nézni, hogy mi van akkor ha a szám körül
// "" van vagy '' vagy pedig nincs semmi vagy pedig a szám után egy .0 van, ezek mind mást típust eredményeznek
Console.WriteLine("6".GetType()); //string
Console.WriteLine('6'.GetType()); // char
Console.WriteLine(6.GetType()); // int
Console.WriteLine(6.0.GetType()); // double


Console.ReadKey();
```