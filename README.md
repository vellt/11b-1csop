```c#
static void Main(string[] args)
{
	// keresse meg a bekért szám legnagyobb és a legkissebb értékű karakter indexét.
	// Majd vonja ki a legnagyobból a legkisebbet. Ez a szám milyen karakternek felel meg.
	string bekertSzoveg = Console.ReadLine();
	int minIndex = 0;
	int maxIndex = 0;
	for (int i = 0; i < bekertSzoveg.Length; i++)
	{
		if (((int)bekertSzoveg[i]) < ((int)bekertSzoveg[minIndex]))
		{
			minIndex = i;
		}
		if (((int)bekertSzoveg[i]) > ((int)bekertSzoveg[maxIndex]))
		{
			maxIndex = i;
		}
	}
	// maximum ASCI kód értékű karakter
	Console.WriteLine(bekertSzoveg[maxIndex]);
	// minimum ASCI kód értékű karakter
	Console.WriteLine(bekertSzoveg[minIndex]);
	// a legnagyobból kivonjuk a legkisebbet, majd hogy látszódjon is valami, eltoljuk vagy 50-el
	int nagybolKisebb = (bekertSzoveg[maxIndex] - bekertSzoveg[minIndex])+50;
	Console.WriteLine(nagybolKisebb); // ASCII
	Console.WriteLine((char)nagybolKisebb); // karakter
	
	// kérjen be legalább egy három szavas mondatot, és csak a második szavát írassa ki
	string mondat = Console.ReadLine();
	int szokozSzamlalo = 0;
	int kezdoIndex = 0;
	int zaroIndex = 0;
	int index = 0; // ciklus változó
	// megkeressük, hogy melyik indextől kezdődik a maásodik szó, és melyik indexxel zárul
	while (szokozSzamlalo!=2)
	{
		if(mondat[index]==' ')
		{
			szokozSzamlalo++;
			if (szokozSzamlalo == 1) kezdoIndex = index + 1;
			if (szokozSzamlalo == 2) zaroIndex = index;
		}
		index++;
	}
	// ha megvannak a keresett értékek, akkor pont azt a szóösszetételt
	// tudjuk kiíratni, amit szerettünk volna, a mondat második szavát
	for (int i = kezdoIndex; i < zaroIndex; i++)
	{
		Console.Write(mondat[i]);
	}
	Console.WriteLine();
   
	// a bekért karakter szám-e? (SEGÍT az ASCII tábla)
	char karakter = Convert.ToChar(Console.ReadLine());
	if(karakter>=48 && karakter <= 57)
	{
		Console.WriteLine("A karakter egy szám");
	}
	else
	{
		Console.WriteLine("A karakter nem szám");
	}

	// kérjen be egy szöveget, majd írassa ki minden karakterértékének 
	// az ASCII kódbéli értékét egymás mellé szóközökkel elválasztva
	string szoveg = Console.ReadLine();
	for (int i = 0; i < szoveg.Length; i++)
	{
		Console.Write($"{(int)szoveg[i]} ");
	}
	Console.WriteLine();

	// kérjen be egy szöveget, és minden második karakterét
	// nagybetűsen írassa ki
	string bSzoveg = Console.ReadLine();
	for (int i = 1; i < bSzoveg.Length; i+=2)
	{
		Console.Write(bSzoveg[i]);
	}
	Console.WriteLine();

	// kérjünk be egy karaktert,
	// minden 'k'-->'m'-re cseréljünk kiíratáskor
	string sz = "ablak";
	for (int i = 0; i < sz.Length; i++)
	{
		if (sz[i] == 'k')
		{
			Console.Write('m');
		}
		else
		{
			Console.Write(sz[i]);
		}
	}
	Console.WriteLine();


	// új anyag rész! -----------------------------------------------------------------
	// számrendszerek

	// dec2bin: paraméterben egy 10-es számot adunk át a függvénynek
	// és visszatér a 2-es számrendszerbeli értékével
	string bin = dec2bin(40);
	// ezt kiíratjuk
	Console.WriteLine(bin);
	Console.ReadKey();
}

// dec2bin függvény:
// - van visszatérési értéke: string
// - van paramétere: int típust vár

private static string dec2bin(int dec)
{
	// megkeressük a kezdőhatványt
	int kezdohatvany = 0;
	while (dec > Math.Pow(2,kezdohatvany+1)) kezdohatvany++;
	int osszeg = 0;
	string bin = "";
	// ha megvan felépítjük karakterenként a 2-es számrendszerbeli értékét
	for (int i = kezdohatvany; i >= 0; i--)
	{
		if(osszeg+Math.Pow(2, i) <= dec)
		{
			osszeg += (int)Math.Pow(2, i);
			bin += "1";
		}
		else bin += "0";
	}
	// a függvény végén visszatérünk az elkészült kettes számrendszerbeli értékkel
	return bin;
}
```