# ARRAYS-STRINGBUILDER-CASTS
Derek Banas Youtube video of arrays, stringbuilder, casts
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Globalization;

namespace STRINGBUILDER
{
    class Program
    {
        static void Main(string[] args)
        {
            StringBuilder sb = new StringBuilder("Stringbuilder text");
            StringBuilder sb2 = new StringBuilder("More Stuff that is important", 256);//defines string of 256 length

            Console.WriteLine("sb Capacity: {0}", sb.Capacity);
            Console.WriteLine("sb2 Capacity: {0}", sb2.Capacity);

            Console.WriteLine("sb Length: {0}", sb.Length);
            Console.WriteLine("sb2 Length: {0}", sb2.Length);

            sb2.AppendLine("\n even more important text");

            CultureInfo enUS = CultureInfo.CreateSpecificCulture("en-US"); //need System.Globalization at top
            string bestCust = "Keith Scarlata";
            sb2.AppendFormat(enUS, "Best Customer: {0}", bestCust); //formats sb2 to US
            Console.WriteLine(sb2.ToString());
            Console.WriteLine("sb2 Length: {0}", sb2.Length);

            sb2.Replace("text", "characters"); //replaces 'text' with 'characters'
            Console.WriteLine(sb2.ToString());

            sb2.Append("Random Text");

            Console.WriteLine(sb.Equals(sb2)); //compares 2 strings (should return false)

            sb2.Insert(11, "that's great");

            Console.WriteLine(sb2.ToString());
            sb2.Remove(11, 7); //removes 7 characters beginning with 11th index
            Console.WriteLine(sb2.ToString());
            
            Console.ReadKey();
