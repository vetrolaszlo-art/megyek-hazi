using System;
using System.CodeDom;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace házi
{
    class Program
    {
        static void Main()
        {
            
            
            Console.Write("Hány megyét szeretnél megadni? ");
            int megyekSzama = int.Parse(Console.ReadLine());

            List<string> megyekNevei = new List<string>();
            List<int> lakossagok = new List<int>();

            int osszesLakos = 0;

            for (int i = 0; i < megyekSzama; i++)
            {
                Console.WriteLine();
                Console.WriteLine((i + 1) + ". megye:");

                Console.Write("Megye neve: ");
                string megyeNev = Console.ReadLine();

                Console.Write("Lakosok száma: ");
                int lakossag = int.Parse(Console.ReadLine());

                megyekNevei.Add(megyeNev);
                lakossagok.Add(lakossag);

                osszesLakos = osszesLakos + lakossag;
            }

            int legtobbLakos = lakossagok[0];
            int legtobbLakosuMegyeIndexe = 0;

            for (int i = 1; i < lakossagok.Count; i++)
            {
                if (lakossagok[i] > legtobbLakos)
                {
                    legtobbLakos = lakossagok[i];
                    legtobbLakosuMegyeIndexe = i;
                }
            }

            double atlag = (double)osszesLakos / megyekSzama;

            Console.WriteLine();
            Console.WriteLine("Legtöbb lakosú megye: " + megyekNevei[legtobbLakosuMegyeIndexe]);
            Console.WriteLine("Lakossága: " + legtobbLakos);

            Console.WriteLine();
            Console.WriteLine("A megyék átlagos lakossága: " + atlag.ToString("N0") + " fő");

            Console.WriteLine();
            Console.WriteLine("A megyék átlagos lakossága: " + atlag.ToString("N0") + " fő");

            for (int i = 0; i < lakossagok.Count; i++)
            {
                if (lakossagok[i] < atlag)
                {
                    Console.WriteLine(megyekNevei[i] + " - " + lakossagok[i] + " fő");
                }
            }
        }
    }
}   
