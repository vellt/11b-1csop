```c#
static void Main(string[] args)
{
	// egy 'a' karakterből kinyerni az ASCII beli értékét
	char karakter = 'a';
	Console.WriteLine((int)karakter);

	// egy ASCII beli számból kinyerni a karakteres értékét
	int ASCII = 97;
	Console.WriteLine((char)ASCII);

	// hogyan alakítjuk át a kisbetűket nagybetűkké
	// 1. lépés: meghatározom az 'a' értékét, és az 'A'
	//           értékét, majd megnézem a kettő közötti
	//           differenciát.
	// 2. lépés: ha már tudom hogy -32-t kell elvonnom a kisbetűből
	//           hogy nagy betűt kapjak, megtudom határozni,
	//           hogy x-->X legyen
	Console.WriteLine((int)'a');
	Console.WriteLine((int)'A');
	char x = 'x';
	Console.WriteLine((char)(x-32));

	// hogyan tudom a kert első indexelhető elemét lehivatkozni?
	string sz = "kert";
	Console.WriteLine(sz[0]); // k
	// hogyan tudom kert első indexelhető elemét lehivathozni?
	Console.WriteLine(sz[sz.Length-1]); // t

	// minden második karakter legyen nagybetűs
	// pl: aztalon-->aZtAlOn
	for (int i = 0; i < sz.Length; i++)
	{
		if (i % 2 != 0) 
			Console.Write((char)(sz[i]-32));
		else
			Console.Write(sz[i]);
	}
	Console.WriteLine();

	// (a-z) karaktereket egymás alá
	//      (ha egymás mellé kiíratás lenne a feladat akkor 
	//      Console.Write()-ot használunk)
	for (int i = 'z'; i >= 'a'; i--)
	{
		Console.WriteLine((char)(i-32));
	}

	// kérj be egy nevet (vezeteknev keresztnev),
	// majd képezz belőlle monogrammot, pl:
	// kiss pista --> K.P.
	Console.WriteLine("Add meg a neved");
	string nev = Console.ReadLine();
	Console.Write($"{(char)(nev[0] - 32)}.");
	for (int i = 0; i < nev.Length; i++)
	{
		if (nev[i] == ' ')
		{
			Console.WriteLine($"{(char)(nev[i + 1] - 32)}.");
		}
	}

	// keressük meg, hogy van-e a szövegben 'b' betű, 
	// amennyiben van írjuk ki, hogy hanyadik indexen található a stringben
	// ha nincs írjuk ki, hogy nem található benne 'b' betű
	Console.WriteLine("szöveg:");
	string szoveg = Console.ReadLine();
	int index = -1;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == 'b')
		{
			index = i;
		}
	}
	if (index == -1)
	{
		Console.WriteLine("nem volt benne b betű");
	}
	else
	{
		Console.WriteLine($"Van benne {szoveg[index]}, méghozzá: {index} indexen");
	}

	// kérjünk be egy tetszőleges szöveget, majd minden karakterének nyerjük ki
	// az ASCII kódbeli értékét, ezeket az értékeket írassuk egymás mellé,
	// szóközökkel elválasztva
	Console.WriteLine("Adjon meg egy szöveget:");
	string a = Console.ReadLine();
	for (int i = 0; i < a.Length; i++)
	{
		Console.Write($"{(int)a[i]} ");
	}

	// adott egy MAC cím vagy Physical Address. Minden kötőjelét
	// cserélje ':'-ra. Azaz: '-' --> ':'
	string physicalAddress = "6C-6A-77-44-C8-E3";
	for (int i = 0; i < physicalAddress.Length; i++)
	{
		if (physicalAddress[i] == '-')
		{
			Console.Write(":");
		}
		else
		{
			Console.Write(physicalAddress[i]);
		}
	}
	Console.WriteLine();
	
	// kérj be egy nevet, majd fordított sorrendbe egymás mellé
	// írassa ki a karakterekeit, ahól szóköz van,
	// ott alkalmazzon sortörést
	Console.WriteLine("Add meg a neved:");
	string nev2 = Console.ReadLine();
	for (int i = nev2.Length-1; i > -1; i--)
	{
		Console.Write(nev2[i]);
		if (nev2[i]==' ')
		{
			Console.WriteLine();
		}
	}
	Console.WriteLine();


	// üzenet tikosító, és visszafejtő program
	Console.WriteLine("adj meg egy szöveget");
	// bekérünk egy szöveget a konzolról
	string uzenet = Console.ReadLine(); 
	// a megírt függvénynek átadjuk paraméterül a bekért
	// szöveget, amelynek a feladatköre, az hogy abból
	// titkosított szöveges adatot gyártson
	string titkositott = Titkositas(uzenet);
	// ezt a titkosított szöveget egyben kiíratom,
	// de akár egy for ciklussal is körbe járhatnám
	// az elemeit, és karakterenként történő kiíratással
	// is ugyan ezt el tudnám érni
	Console.WriteLine(titkositott);
	// majd visszafejtjük a titkosított üzenetet,
	// az arra megírt 'Visszafejtes' függvénnyel,
	// és amint ezt a visszafejett üzenetet vissza
	// adta a függvény, kiíratjuk a Console.WriteLine-al
	Console.WriteLine(Visszafejtes(titkositott));
	Console.ReadKey();
}

// titkosító függvény, vár egy szöveget paraméterként,
// amit majd titkosít, és visszatér ezzel az új (titkosított)
// üzenettel
static string Titkositas(string uzenet)
{
	string titkositottUzenet = "";
	for (int i = 0; i < uzenet.Length; i++)
	{
		titkositottUzenet += (char)(uzenet[i] - 45);
	}
	return titkositottUzenet;
}

// vár paraméterül egy titkosított üzenetet, visszafejti,
// és visszatér vele
static string Visszafejtes(string titkositottUzenet)
{
	string uzenet = "";
	for (int i = 0; i < titkositottUzenet.Length; i++)
	{
		 uzenet+= (char)(titkositottUzenet[i] + 45);
	}
	return uzenet;
}
```