```c#
static void Main(string[] args)
{
	feladat1();
	feladat2();
	feladat3();
	Console.ReadKey();
}

private static void feladat3()
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

	// mennyi legalabb 5 karakteres szó van benne
	Console.WriteLine();
	int szamlalo = 0;
	for (int i = 0; i < gyumolcsok.Length; i++)
	{
		if (gyumolcsok[i].Length >= 5) szamlalo++;
	}
	Console.WriteLine($"ennyi legalább 5 karakteres: {szamlalo}");

	// van-e páros karakterhosszú szó
	int index = 0;
	bool VANe = false;
	while (VANe == false && index<gyumolcsok.Length)
	{
		if (gyumolcsok[index].Length % 2 == 0) VANe = true;
		index++;
		
	}
	Console.WriteLine((VANe?"van":"nincs")+" páros karakter hossz");

	// van-e olyan szó, amely nagybetűvel kezdődik
	int index2 = 0;
	bool Vane = false;
	while(Vane == false && index2<gyumolcsok.Length)
	{
		string gyumolcs = gyumolcsok[index2];
		if (gyumolcs[0]>='A' && gyumolcs[0] <= 'Z')
		{
			Vane = true;
		}
	}
	Console.WriteLine((Vane ? "van":"nincs")+ " amely nagybetűvel kezdődik");

	// van-e olyan szó, amely tartalmaz 'd' betűt
	int index3 = 0;
	bool VanE = false;
	while(VanE==false && index3<gyumolcsok.Length)
	{
		string gyumolcs = gyumolcsok[index3];
		int index4 = 0;
		while (VanE == false && index4 < gyumolcs.Length) 
		{
			if (gyumolcs[index4] == 'd') VanE = true;
			index4++;
		}
		index3++;
	}
	Console.WriteLine((VanE?"van":"nincs")+ "olyan szó amely tartalmaz d betut");

	// melyik a legtöbb magánhangzót tartalmazó szó
	// van-e szilva a tömbben.

}

private static void feladat2()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a vasutipar rekordjait. Keszul az 1000km/h-s vonat.";
	// mennyi db betű (kisbetű/nagybetű) van benne
	int betuszamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if ((szoveg[i] >= 'a' && szoveg[i] <= 'z') || (szoveg[i] >= 'A' && szoveg[i] <= 'Z')) 
			betuszamlalo++;
	}
	Console.WriteLine(betuszamlalo);
	
	// mennyi db maganhangzo van benne
	int maganhangzoszamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (
			szoveg[i] == 'a' || 
			szoveg[i] == 'e' || 
			szoveg[i] == 'i' || 
			szoveg[i] == 'u' || 
			szoveg[i] == 'o')
		{
			maganhangzoszamlalo++;
		}
	}
	Console.WriteLine(maganhangzoszamlalo);

	// mennyi db mondatbol all
	int mondatszamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == '.') mondatszamlalo++;
	}
	Console.WriteLine(mondatszamlalo);

	// mennyi db szam van benne
	int szamszamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= '0' && szoveg[i] <= '9') szamszamlalo++;
	   
	}
	Console.WriteLine(szamszamlalo);

	// hány %-a szám a teljes szövegnek, 2 tizedes
	double szamszazalek = szamszamlalo / (double)szoveg.Length;
	Console.WriteLine($"{(szamszazalek*100):0.00}");
	// van-e benne kisbetű
	bool vanE = false;
	int index = 0;
	while(vanE==false && index < szoveg.Length)
	{
		if(szoveg[index]>='a' && szoveg[index] <= 'z')
		{
			vanE = true;
		}
		index++;
	}
	Console.WriteLine((vanE ? "van" : "nincs") + " benne kis betű");

	// van-e benne /-jel
	bool vanE2 = false;
	int index2 = 0;
	while (vanE2 == false && index2 < szoveg.Length)
	{
		if (szoveg[index2] == '/') vanE2 = true;

		index2++;
	}

	Console.WriteLine((vanE2 ? "van" : "nincs") + " benne / jel");

	// írassa ki a szöveget. Viszont, ha van benne nagybetű, azt írassa ki kisbetűsen.
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i]>='A' && szoveg[i]<='Z')
		{
			Console.Write((char)(szoveg[i]+32));
		}
		else Console.Write(szoveg[i]);
	}

}

private static void feladat1()
{
	int[] tomb = new int[10];
	Random r = new Random();
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(21)-10; //[-10,10]
		Console.Write($"{tomb[i]} ");
	}
	Console.WriteLine();

	// mennyi páratlan szám van benne (megszámlálás)
	int paratlanDb = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 != 0) paratlanDb++;
	}
	Console.WriteLine(paratlanDb);

	// mennyi 0-nél kisebb (megszámlálás)
	int tiznelKisebb = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] < 0) tiznelKisebb++;
	}
	Console.WriteLine(tiznelKisebb);

	// mennyi az átlaguk 2 tizedes pontosan (összegzés)
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
		// osszeg = osszeg + tomb[i];
	}
	double atlag = osszeg / (double)tomb.Length;
	Console.WriteLine($"átlaguk: {atlag:0.00}");
	Console.WriteLine($"átlaguk: {Math.Round(atlag,2)}");

	// van-e benne negatív szám (eldöntés)
	bool vanE = false;
	int index = 0;
	while (vanE==false && index<tomb.Length)
	{
		if (tomb[index] < 0) vanE = true;
		index++;
	}
	// ugyan az mint a while ciklus csak forral
	for(int i=0; vanE == false && i < tomb.Length; i++)
	{
		if (tomb[i] < 0) vanE = true;
	}
	Console.WriteLine((vanE? "van":"nincs")+" benne negatív szám");

	// van-e az átlagtól nagyobb szám (eldöntés)
	bool vanE2 = false;
	for (int i = 0; vanE2 == false && i < tomb.Length; i++) if (tomb[i] > atlag) vanE2 = true;
	Console.WriteLine((vanE2 ? "van" : "nincs") + " az átlagtól nagyobb szám benne.");
}
```