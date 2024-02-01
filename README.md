```c#
// tömbök előnye, hogy nem kell rengeteg változót létrehoznom, hanem egy
// változóban letudok tárolni mindent, csak egy mutatóval [index] lehivatkozom
// az adott elemét. Ez a mutató/index 0-tól a tömb.Length-1ig tud lehivatkozni 
// tömbbéli elemeket
int sz1 = 12;
int sz2 = 33;
int sz4 = 12;

// int tömb létrehozása. KÖTELEZŐ megadni a tömb hosszát
int hossz = 3;
int[] tomb = new int[hossz];
// így tudunk egy-egy elemét lehivatkozni
tomb[0] = 12;
tomb[1] = 33;
tomb[2] = 12;

// az előző hivatkozást megtehetjük dimanikusabban is for ciklussal
// 0-tól meg 3ig, amit vagy a hossz változóval kapunk meg vagy a 
// tomb.Length-1el
for (int i = 0; i < hossz; i++)
{
	// dinamikusan feltöltjük a tömb minden elemét konzolból
	tomb[i] = Convert.ToInt32(Console.ReadLine()); 
}

// hozzunk létre egy 5 elemű string tömbböt és töltsük fel
// konzolból bekért ruhaneműkkel
int darab = 5;
string[] szekreny = new string[darab];
for (int i = 0; i < szekreny.Length; i++)
{
	Console.Write("ruha hozzáadása: ");
	szekreny[i] = Console.ReadLine();
}
// majd ha feltöltöttük kiíratjuk a ruhásszekrény tartalmát
Console.WriteLine("ruhás szekrény: ");
for (int i = 0; i < szekreny.Length; i++)
{
	Console.WriteLine($"- {szekreny[i]}");
}

// mátrix/két dimenziós tömb--------------------------------------------

int[,] matrix = new int[10, 5];
// GetLength(0)-->10, azaz mennyi vektorból/1dim tömbböl épül fel a mátrix
// GetLength(1)-->5, azaz mennyi elemű egy egy vektora/1dim tömbje
int szam = 1;
for (int i = 0; i < matrix.GetLength(0); i++) // a sorokat tudjuk vele végigjárni
{
	for (int j = 0; j < matrix.GetLength(1); j++) // egy egy sor összes emét tudjuk körbe járni
	{
		// feltöltjük a mátrix összes elemét szam változó aktuális értékével
		// majd növeljük, a következő ciklizálás során már egyel nagyobb értéket adunk hozzá
		matrix[i, j] = szam++; 
	}
}

// kiíratjuk a mátrix tartalmát ügyelve annak mátrixos nézetére
for (int i = 0; i < matrix.GetLength(0); i++)
{
	for (int j = 0; j < matrix.GetLength(1); j++)
	{
		Console.Write($"{matrix[i, j]}\t");
	}
	Console.WriteLine();
}

// 1. indexű sor 3. indexű elemét hivatkozom le (bal felső sarokban kezdem a számolást)
Console.WriteLine(matrix[1,3]); 


// 1dim tömb/ vektor-------------------------------------------------------------------------------
// hozzunk létre egy 5 elemű int tömbböt 
// majd töltsük fel [-10,10]-es intervallumban lévő számokkal
int[] tomb6 = new int[5];
Random r = new Random();
for (int i = 0; i < tomb6.Length; i++)
{
	tomb6[i] = r.Next(21)-10;
}
// majd írassuk ki egymás mellé az értékeket szóközzel elválasztva
for (int i = 0; i < tomb6.Length; i++)
{
	Console.Write($"{tomb6[i]} ");
}
Console.WriteLine();

// nézzük meg, hogy az előző feladatban feltöltött tömb elemei között
// mennyi (SZÁMOLJUK MEG!) negatív, pozitív, páros és páratlan szám van
int neg = 0;
int poz = 0;
int paros = 0;
int paratlan = 0;
for (int i = 0; i < tomb6.Length; i++)
{
	if (tomb6[i] < 0) neg++;
	else poz++;

	if (tomb6[i] % 2 == 0) paros++;
	else paratlan++;

}
Console.Write(neg);
Console.Write(poz);
Console.Write(paros);
Console.Write(paratlan);


Console.ReadKey();
```