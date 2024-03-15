```c#
// egy teremben 10 pad van
// minden padban ül egy fiú vagy egy lány
// 0/1 fiú lány
int[,] terem = new int[10, 2];
Random r = new Random();
int lany = 0;
int fiu = 0;
for (int i = 0; i < terem.GetLength(0); i++)
{
	for (int j = 0; j < terem.GetLength(1); j++)
	{
		terem[i,j] = r.Next(2);
		if (terem[i, j] == 1) lany++;
		else fiu++;
		Console.Write($"{terem[i, j]} ");
	}

	Console.WriteLine();
}
// fiúból van lányból van több?
Console.WriteLine($"ennyi fiu van : {fiu}");
Console.WriteLine($"ennyi lany van : {lany}");
if (lany > fiu) Console.WriteLine("lányból több van");
else if (lany < fiu) Console.WriteLine("fiuból több van");
else Console.WriteLine("ugyan annyi");

// mennyi százaléka lány az teremben ülőknek?
Console.WriteLine($"{Math.Round(((double)lany/20)*100,2)}%");

// ez első padban 2 fiú ül?
int osszeg = 0;
for (int i = 0; i < terem.GetLength(1); i++) // 2 ember ül egy padban, 2x fut le
{
	osszeg += terem[0,i]; // 0. sor--> első pad.
}
// ha nulla maradt az összeg értéke akk két fiú ül ott
Console.WriteLine((osszeg==0)?"igen":"nem");

Console.ReadKey();
```