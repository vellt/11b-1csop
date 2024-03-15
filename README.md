```c#
static void Main(string[] args)
{
	Console.WriteLine("1. Pi értéke");
	Console.WriteLine("2. Pi kirajzolása");
	Console.WriteLine("3. Pi kirajzolása 2");
	Console.WriteLine("--------------------");
	Console.Write("Menu: ");
	switch (Convert.ToInt32(Console.ReadLine()))
	{
		case 1:
			piErteke();
			break;
		case 2:
			piKirajzol();
			break;
		case 3:
			piKirajzol2();
			break;
	}
	Console.ReadKey();
}

private static void piKirajzol2()
{
	Console.WriteLine("--------------------\n");
	string szoveg = File.ReadAllText("num3.txt");
	bool talalat = false;
	string ertek = "";
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == '{')
		{
			ertek = "";
			talalat = true;
		}else if (szoveg[i] == '}')
		{
			talalat = false;
			if (ertek == "B")
			{
				Console.Write(Math.Round(22/7.0,2));
			}
			else if(ertek=="0")
			{
				Console.WriteLine();
			}
			else
			{
				// szám
				int szam = Convert.ToInt32(ertek);
				for (int j = 0; j < szam; j++)
				{
					Console.Write(' ');
				}
			}
		}
		else if (talalat == true)
		{
			ertek += szoveg[i];
		}
		else
		{
			Console.Write(szoveg[i]);
		}
	}
}

private static void piKirajzol()
{
	Console.WriteLine("--------------------\n");
	string szoveg = File.ReadAllText("num1.txt");
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == 'K') Console.Write(" ");
		else if (szoveg[i] == 'B') Console.Write(Math.Round(22/7.0,2));
		else if (szoveg[i] == 'H') Console.Write("  ");
		else if (szoveg[i] == 'P') Console.Write("   ");
		else if (szoveg[i] >= '0' && szoveg[i] <= '9') Console.Write(szoveg[i]);
		else if (szoveg[i] == 'Q') Console.WriteLine();
	}
}

private static void piErteke()
{
	Console.WriteLine("--------------------\n");
	string szoveg = File.ReadAllText("num1.txt");
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == 'B') Console.Write(Math.Round(22 / 7.0, 2));
		else if (szoveg[i] > '0' && szoveg[i] < '9') Console.Write(szoveg[i]);
	}
}
```