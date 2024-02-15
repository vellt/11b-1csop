```c#
static void Main(string[] args)
{
	vektor();
	matrix();
	// PROGRAMOZÁSI TÉTELEK / NEVEZETES ALGORITMUSOK
	// gyakran használt algoritmusok a programozásban
	osszegzesTetele();
	megszamlalasTetele();
	eldontesTetele();
	komplex1();
	komplex2();
	Console.ReadKey();
}

private static void komplex2()
{
	int[] tomb = new int[] { 3, 8, -2, 5, 0, 10, -7, 4, 9 };
	int szamlalo = 0;
	// páratlan számok hány db
	// van-e páros szám
	// átlaguk
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i]%2!=0)
		{
			szamlalo++;
		}
	}
	Console.WriteLine($"ennyi páratlan van : {szamlalo}");
	// van-e páros szám
	bool vanE = false;
	int index = 0;
	while (vanE == false && index<tomb.Length)
	{
		if (tomb[index] % 2 == 0)
		{
			vanE = true;
		}
		index++;
	}
	if (vanE == true) Console.WriteLine("van páros");
	else Console.WriteLine("nincs");
}

private static void komplex1()
{
	// iskolai verseny
	// 2 10 fős iskolai csoport van
	// töltsük fel őket véltetlenszerűen [0,10] számokkal-->pontok
	// feladatok:
	// - melyik csoport szerzett több pontot
	// - mennyi tanuló szerzett az 1. csoportból 0 pontot
	// - volt-e a kettes csoportban aki 10 pontot szerzett
	Random random = new Random();
	int[] elsoCsoport = new int[10];
	int[] masodikCsoport = new int[10];
	for (int i = 0; i < 10; i++)
	{
		elsoCsoport[i] = random.Next(11); //[0,10]
		masodikCsoport[i] = random.Next(11); //[0,10]
	}
	// - melyik csoport szerzett több pontot
	int elsoOszeg = 0;
	int masodikOszeg = 0;
	for (int i = 0; i < 10; i++)
	{
		elsoOszeg += elsoCsoport[i];
		masodikOszeg += masodikCsoport[i];
	}
	if (elsoOszeg<masodikOszeg)  Console.WriteLine("masodik nyer");
	else if(elsoOszeg>masodikOszeg) Console.WriteLine("elsonyert");
	else Console.WriteLine("döntetlen");

	//  - mennyi tanuló szerzett az 1. csoportból 0 pontot
	int szamlalo = 0;
	for (int i = 0; i < elsoCsoport.Length; i++)
	{
		if (elsoCsoport[i]==0)
		{
			szamlalo++;
		}
	}
	Console.WriteLine($"{szamlalo} darab tanuló szerzett nulla pontot");

	// - volt-e a kettes csoportban aki 10 pontot szerzett
	bool vanE = false;
	int index = 0;
	while (vanE == false && index<masodikCsoport.Length)
	{
		if( masodikCsoport[index] == 10)
		{
			vanE = true;
		}

		index++;
	}
	if(vanE == true)
		Console.WriteLine("volt 10 pontot szerzo tanulo");
	else
		Console.WriteLine("nem volt 10 pontos tanulo");


}

/// <summary>
/// IGAZ/HAMIS  a tömbben olyan elem, ami a feltételnek megfelel
/// amint talál egyet ki kell lépnie a ciklusból
/// </summary>
private static void eldontesTetele()
{
	int[] tomb = new int[] { 12, 30, 10, 3, 12, 8, 11 };
	// van-e benne 30nál nagyobb szám
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i] > 30)
		{
			vanE = true;
		}
		i++;
	}
	if (vanE == true) Console.WriteLine("volt olyan eleme ami 30tól nagyobb");
	else Console.WriteLine("nem volt olyan");

}

/// <summary>
/// MENNYI olyan eleme van a tömbnek ami megfelel egy biz. feltételnek
/// </summary>
private static void megszamlalasTetele()
{
	// szamlalo=szamlalo+1;
	// szamlalo+=1;
	// szamlalo++;

	int[] tomb = new int[] { 3, 2, 3 };
	// mennyi páros van
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0)
		{
			szamlalo++;
		}
	}
	Console.WriteLine(szamlalo);
}

/// <summary>
/// tömb elemeinek az összege
/// </summary>
private static void osszegzesTetele()
{
	int[] tomb = new int[3];
	tomb[0] = 3;
	tomb[1] = 3;
	tomb[2] = 3;

	// osszeg=osszeg+tomb_akt_eleme
	// osszeg+=tomb_aktualis_eleme
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
		// osszeg = osszeg + tomb[i];
	}
	Console.WriteLine(osszeg); //9

	// konkatenáció/szöveg összefűzés------------------------------
	// ekkor a += folyamatosan bővíti a stringet egy újjabb karakterrel
	string osszeg1 = "";
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg1 += tomb[i];
		// osszeg = osszeg + tomb[i];
	}
	Console.WriteLine(osszeg1); //333
}

/// <summary>
/// mátrix az a 2 dimenziós tömb
/// </summary>
private static void matrix()
{
	int[,] matrix = new int[5, 4];
	Random r = new Random();
	// matrix.GetLength(0) --> 5 vektorból épül fel
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		// matrix.GetLength(1) --> 4 egy vektor hány elemből áll
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10); //[0,9]
		}
	}
	// kiíratni az elemeit
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.Write($"{matrix[i, j]} ");
		}
		Console.WriteLine();
	}
}

/// <summary>
/// vektor az az 1 dimenziós tömb
/// </summary>
private static void vektor()
{
	int[] tomb = new int[10];
	Random r = new Random();
	// feltöltés
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(10); //[0,9]
		// ha az a feladat, hogy konzolból
		//tomb[i] = Convert.ToInt32(Console.ReadLine()); 
	}
	// kiíratás
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.WriteLine(tomb[i]);
	}
}
```