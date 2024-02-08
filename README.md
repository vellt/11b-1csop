```c#
static void Main(string[] args)
{
	ismetles();
	vektorIsm();
	matrixIsm();
	Console.ReadKey();
}

private static void matrixIsm()
{
	// 5x10-es mátrxix készítése
	// és elemeinek a kiíratása
	int[,] matrix = new int[5,10];
	for (int i = 0; i < matrix.GetLength(0); i++) // sor lehivatkozása
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.WriteLine(matrix[i,j]); // lehivatkozom az i. sor j. elemét (ami 0, sőt minden elem nulla alapból)
		}
	}
}

private static void vektorIsm()
{
	// 1 dim. tömbök/ vektorok készítése, feltölése és tartalmának kiíratása
	int[] tomb = new int[3];
	//[-50, 50]
	Random r = new Random();
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50;
		//Console.Write($"{tomb[i]}\t");
		Console.Write($"{tomb[i]} ");
		//Console.Write($"{tomb[i],5}");
	}
}

private static void ismetles()
{
	// tömbök előnye h nem kell 3 értékhez három változót léltre hoznom
	// hanem használhatok tömböt is, segít abban hogy egy változóban le tudjak
	// hivatkozni tetszőleges hosszúságú éréket
	int a = 6;
	int b = 7;
	int c = 5;

	int[] tomb = new int[3];
	// ha primitív típusú a tömb alapból a memóriában 0 értékekkel töltődik fel
	// primitív típsu: int, double, char, bool
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.WriteLine(tomb[i]);
	}

}
```