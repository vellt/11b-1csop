```c#
static void Main(string[] args)
{
	VektorosFeladat();
	matrixosFeladat();
	Console.ReadKey();
}

private static void matrixosFeladat()
{
	// DOLGOZATBAN VÁRHATÓ MÁTRIXOS FELADATOK
	int[,] honapok = new int[12, 30];
	Random r = new Random();
	for (int i = 0; i < honapok.GetLength(0); i++)
	{
		for (int j = 0; j < honapok.GetLength(1); j++)
		{
			honapok[i, j] = r.Next(21)-10; //[-10,10]
		}
	}
	// Melyik hónapban van mennyi az átlaghőmérsékelt
	double honapokAtlaghomersekletei = 0; // a harmadik részfeladathoz kell
	for (int i = 0; i < honapok.GetLength(0); i++)
	{
		int egyHonapOsszHomerseklete = 0;
		for (int j = 0; j < honapok.GetLength(1); j++)
		{
			egyHonapOsszHomerseklete += honapok[i, j];
		}
		int honapNapjai = honapok.GetLength(1);
		double egyHonapAtlagHomerseklete = egyHonapOsszHomerseklete / (double)honapNapjai;
		honapokAtlaghomersekletei += egyHonapAtlagHomerseklete; // a harmadik részfeladathoz kell
		Console.WriteLine($"{i+1}. hó: {egyHonapAtlagHomerseklete:0.00} az átlaghőmérséklete");
	}
	// Mennyi az éves átlaghőmérséklet
	double evesAtlag = honapokAtlaghomersekletei / (double)honapok.GetLength(0);
	Console.WriteLine(Math.Round(evesAtlag, 2));
}

private static void VektorosFeladat()
{
	// 12 napig megmértük a napi csapadék mennyiséget. Határozzuk meg
	// mennyi eső esett összesen.

	int[] csapadekok = new int[12];
	Random r = new Random();
	int osszes = 0;
	for (int i = 0; i < csapadekok.Length; i++)
	{
		csapadekok[i] = r.Next(21) + 10;
		osszes += csapadekok[i];
		//osszes =osszes+ csapadekok[i];
	}
	Console.WriteLine(osszes);


	// ismerjuk 9 auto fogyasztasat, dontsuk el,
	// hogy minden auto 10 liter alatt fogyasztott_e
	int szamlalo = 0;
	int[] fogyasztasok = new int[9];
	for (int i = 0; i < fogyasztasok.Length; i++)
	{
		fogyasztasok[i] = r.Next(12)+4;
		if(fogyasztasok[i] < 10)
		{
			szamlalo++;
		}
	}
	Console.WriteLine(((szamlalo==fogyasztasok.Length)?"":"nem")+" minden autó fogyasztott 10liter alatt");

	//ismerjuk 11 ember magassagat van e olyan ember amely alacsonyabb mint a mogotte allo ember
	int[] magassag = new int[11];
	bool vanE = false;
	for (int i = 0; i < magassag.Length; i++)
	{
		magassag[i] = r.Next(31)+160;
	}

	for (int i = 1; vanE==false && i < magassag.Length; i++)
	{
		if (magassag[i] < magassag[i - 1]) vanE = true;
	}
	if (vanE == true)  Console.WriteLine("van olyan ember amely alacsonyabb");
	else Console.WriteLine("Nincs benne alacsonyabb");


	// határozzuk meg hogy egy adott hónap melyik évszakba esik

	int honap = Convert.ToInt32(Console.ReadLine());
	switch (honap)
	{
		case 12:
		case 1:
		case 2:
			Console.WriteLine("Tél");
			break;
		case 3:
		case 4:
		case 5:
			Console.WriteLine("Tavasz");
			break;
		case 6:
		case 7:
		case 8:
			Console.WriteLine("Nyár");
			break;
		case 9:
		case 10:
		case 11:
			Console.WriteLine("Ősz");
			break;
	}

	if (honap >= 9 && honap <= 11) Console.WriteLine("Ősz");
	else if (honap >= 6 && honap <= 8) Console.WriteLine("Nyár"); 
	else if (honap >=3  && honap <=5 ) Console.WriteLine("Tavasz");
	else Console.WriteLine("Tél");

	// olvassunk be adig ami nem irunk be ket azonos nevet
	string kezdetlegi = "";
	string bekert = "";
	bool bentmaradasiFeltetel = true;
	while (bentmaradasiFeltetel) 
	{
		bekert = Console.ReadLine();
		if (bekert == kezdetlegi) bentmaradasiFeltetel = false;
		kezdetlegi = bekert;
	}
	Console.WriteLine("kilép");

	// -----------------------------------------------------
	// DOLGOZATBAN VÁRHATÓ VEKTOROS FELADATOK
	// allitson elo veletlenszeruen 28 szamot -10;10-es intervallumban

	int[] veletlen = new int[28];
	for (int i = 0; i < veletlen.Length; i++)
	{
		veletlen[i] = r.Next(21)-10;
	}

	// pozitiv vagy a negativ szambol van tobb
	int negativ = 0;
	int pozitiv = 0;
	for (int i = 0; i < veletlen.Length; i++)
	{
		if (veletlen[i] >= 0) pozitiv++;
		else negativ++;
	}
	if (negativ < pozitiv) Console.WriteLine("pozitivbol tobb van");
	else if (pozitiv < negativ) Console.WriteLine("negativbol tobb van");
	else Console.WriteLine("egyforma");

	// Hányszor fordul elő a 7-es szám
	int het = 0;
	for (int i = 0; i < veletlen.Length; i++)
	{
		if (veletlen[i] == 7) het++;
	}
	Console.WriteLine(het);

	// van-e a számok között nulla
	bool van = false;
	for (int i = 0; van==false && i < veletlen.Length; i++)
	{
		if (veletlen[i] == 0) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");

	// negatív számok átlaga
	int negativDB = 0;
	for (int i = 0; i < veletlen.Length; i++)
	{
		if (veletlen[i] < 0) negativDB++;
	}
	double atlag = negativDB / (double)veletlen.Length;
	Console.WriteLine(Math.Round(atlag,2));
}
```