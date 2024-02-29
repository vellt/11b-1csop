```c#
static void Main(string[] args)
{
	feladatBefejezese();
	programozasiTetelek();
	matrixGyak();
	matrixFeladat();
	Console.ReadKey();
}

private static void matrixFeladat()
{
	// egy 14 fős csoportban AAF-ből röpdolgozatot írat a tanár minden hónapban
	// Eltelt 4 hónap. Mindenki kapott 1-1 jegyet [1,5]-ban minden dogára.
	int[,] csoport = new int[14, 4];
	Random random = new Random();
	for (int i = 0; i < csoport.GetLength(0); i++)
	{
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			csoport[i, j] = random.Next(5) + 1;
		}
	}

	// - melyik tanulónak mennyi az átlaga
	for (int i = 0; i < csoport.GetLength(0); i++)
	{
		int szum = 0;
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			szum += csoport[i, j];
		}
		Console.WriteLine($"{i+1}. tanulónak az átlaga: {(szum/4.0):0.00}");
	}
	// - mennyi az osztályátlag
	double tanulokSzum = 0;
	for (int i = 0; i < csoport.GetLength(0); i++)
	{
		int szum = 0;
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			szum += csoport[i, j];
		}
		tanulokSzum+= szum / 4.0;
	}
	double osztalyatlag = tanulokSzum / 14;
	Console.WriteLine($"osztályátlag: {osztalyatlag:0.00}");

	// - mennyi tanuló áll bulásra (1.6 alatt)
	int bukasraAlloTanulokSzama = 0;
	for (int i = 0; i < csoport.GetLength(0); i++)
	{
		int szum = 0;
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			szum += csoport[i, j];
		}
		double atlag = szum / 4.0;
		if (atlag < 1.6) bukasraAlloTanulokSzama++;
	}
	Console.WriteLine(bukasraAlloTanulokSzama);

	// - mennyi tanuló van az osztályátlag alatt
	int osztalyatlagAlattiTanulokSzama = 0;
	for (int i = 0; i < csoport.GetLength(0); i++)
	{
		int szum = 0;
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			szum += csoport[i, j];
		}
		double atlag = szum / 4.0;
		if (atlag < osztalyatlag) osztalyatlagAlattiTanulokSzama++;
	}
	Console.WriteLine(osztalyatlagAlattiTanulokSzama);
	// - van-e olyan tanuló aki bukásra áll? (1.6 alatt)
	bool  vanE = false;
	for (int i = 0; vanE==false && i < csoport.GetLength(0); i++)
	{
		int szum = 0;
		for (int j = 0; j < csoport.GetLength(1); j++)
		{
			szum += csoport[i, j];
		}
		double atlag = szum / 4.0;
		if (atlag <1.6) vanE=true;
	}
	Console.WriteLine(vanE ? "van" : "nincs");
	// - van-e olyan tanuló aki csak egyest szerzett a 4 hónap alatt
	// - van-e olyan tanuló akinek az első jegye és az utolsó jegye megegyezik
}

private static void matrixGyak()
{
	int[,] matrix = new int[2,4];
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++) // sorok lekérése
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10) + 1; //[1,10]
			Console.Write($"{matrix[i, j]}\t");
		}
		Console.WriteLine();
	}
}

private static void programozasiTetelek()
{
	// összegzes: összeadja az elemeket, vagy összefűz
	// megszámlálás: FELTÉTELnek mennyi elem passzol, db
	// eldöntés: FELTÉTEL mentén eldöntjük van-e benne olyan elem, avagy nincs

	int[] tomb = new int[] { 1, 2, 3, 4, 5 };
	// összegzes
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	Console.WriteLine(osszeg);
	// az összegzés tétele összefűzésre (konkatenáció) is alkalmas
	string[] mondoka = new string[] { "beka", "ül", "a", "fűben" };
	string osszefuzott = "";
	for (int i = 0; i < mondoka.Length; i++)
	{
		osszefuzott += mondoka[i]+" ";
	}
	Console.WriteLine(osszefuzott);

	// megszámlálás
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) szamlalo++;

	}
	Console.WriteLine(szamlalo);

	// eldöntés
	bool vanE = false;
	for (int i = 0; vanE==false && i < tomb.Length; i++)
	{
		if (tomb[i] == 2) vanE = true;
	}
	Console.WriteLine(vanE ? "van" : "nincs");
}

private static void feladatBefejezese()
{
	string[] gyumolcsok = new string[]
	{
		"alma",
		"korte",
		"banan",
		"narancs",
		"szilva",
		"Mandarin"
	};
	// melyik a legtöbb magánhangzót tartalmazó szó
	string legtobbMaganhangzo = gyumolcsok[0];
	int maxMaganhangzo = 0;
	for (int i = 0; i < gyumolcsok.Length; i++)
	{
		string gyumolcs = gyumolcsok[i];
		int maganhangzo = 0;
		for (int j = 0; j < gyumolcs.Length; j++)
		{
			if( gyumolcs[j] == 'a' ||
				gyumolcs[j] == 'e' ||
				gyumolcs[j] == 'i' ||
				gyumolcs[j] == 'o' ||
				gyumolcs[j] == 'u')
			{
				maganhangzo++;
			}
		}
		if (maxMaganhangzo < maganhangzo)
		{
			maxMaganhangzo = maganhangzo;
			legtobbMaganhangzo = gyumolcs;
		}
	}
	Console.WriteLine(legtobbMaganhangzo);

	// van-e szilva a tömbben.
	bool vanE = false;
	int index = 0;
	while (vanE==false && index<gyumolcsok.Length)
	{
		if (gyumolcsok[index] == "szilva") vanE = true;

		index++;
	}
	Console.WriteLine((vanE ? "van" : "nincs") + " benne szilva");
}
```