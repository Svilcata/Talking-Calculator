using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Speech.Synthesis;
namespace Calculator
{
    class Program
    {
        private static SpeechSynthesizer synth = new SpeechSynthesizer();

        static void Main(string[] args)
        {
            double x = 0;
            double y = 0;
            bool quit = false;
            synth.SelectVoiceByHints(VoiceGender.Female);
            Console.WriteLine("Welcome to Speaking Calculator version 1.0!");
            Console.WriteLine("Created By Svilen Strahilov © Enjoy :)");
            synth.Speak("Welcome to Speaking Calculator version 1 point oh!,Please be patient with me as i am very slow in reading");

            while (!quit)
            {
            Start:
                Console.WriteLine("\nWhat would you like to do?");
                synth.Speak("What would you like to do?");
                Console.WriteLine("1 - Add");
                Console.WriteLine("2 - Subtract");
                Console.WriteLine("3 - Divide");
                Console.WriteLine("4 - Multiply");
                Console.WriteLine("5 - Modulus");
                Console.WriteLine("6 - Square number");
                Console.WriteLine("7 - Quit");
                Console.Write("Please enter your choice only in numbers: ");
                synth.Speak("Plese enter your choice only in numbers!");
                int action = int.Parse(Console.ReadLine());
                if (action != 1 && action != 2 && action != 3 && action != 4 && action != 5 && action != 6 && action != 7)
                {
                    Console.WriteLine("Can you read or listen ?! You had one JOB, ONE JOB ONLY");
                    synth.Speak("Can you read or listen ?! You had one JOB, ONE JOB ONLY");
                    Console.Write("If you want to continue, please Enter 1 for Yes, 2 for No:");
                    synth.Speak("If you want to continue, please Enter 1 for Yes, 2 for No");
                    x = int.Parse(Console.ReadLine());
                    if (x == 1)
                    {
                        Console.WriteLine("Perfect choice!");
                        synth.Speak("Perfect choice");
                        goto Start;
                    }
                    else if(x == 2)
                    {
                        Console.WriteLine("May the odds forever be in your favor, bye.");
                        synth.Speak("May the odds forever be in your favor, bye.");
                        break;
                    }
                }
                #region Switch
                switch (action)
                {
                    case 1:
                        Console.WriteLine("You have selected - ADD!");
                        synth.Speak("You have selected - ADDDDDD!");
                        Console.Write("Please enter x = ");
                        synth.Speak("Please enter x");
                        x = double.Parse(Console.ReadLine());
                        Console.Write("Please enter y = ");
                        synth.Speak("Please enter y");
                        y = double.Parse(Console.ReadLine());
                        decimal result = (int)x + (int)y;
                        Console.WriteLine("{0} + {1} = {2} ",x,y,result);
                        synth.Speak("Your result is shown below");
                        break;
                    case 2:
                        Console.WriteLine("You have selected - SUBTRACT!");
                        synth.Speak("You have selected - SUBTRACT!");
                        Console.Write("Please enter x = ");
                        synth.Speak("Please enter x");
                        x = double.Parse(Console.ReadLine());
                        Console.Write("Please enter y = ");
                        synth.Speak("Please enter y");
                        y = double.Parse(Console.ReadLine());
                        result = (int)x - (int)y;
                        Console.WriteLine("{0} - {1} = {2} ", x, y, result);
                        synth.Speak("Your result is shown below");
                        break;
                    case 3:
                        Console.WriteLine("You have selected - DIVIDE!");
                        synth.Speak("You have selected - DIVIDE!");
                        Console.Write("Please enter x = ");
                        synth.Speak("Please enter x");
                        x = double.Parse(Console.ReadLine());
                        Console.Write("Please enter y = ");
                        synth.Speak("Please enter y");
                        y = double.Parse(Console.ReadLine());
                        result = (int)x / (int)y;
                        Console.WriteLine("{0} / {1} = {2} ", x, y, result);
                        synth.Speak("Your result is shown below");
                        break;
                    case 4:
                        Console.WriteLine("You have selected - MULTIPLY!");
                        synth.Speak("You have selected - MULTIPLY!");
                        Console.Write("Please enter x = ");
                        synth.Speak("Please enter x");
                        x = double.Parse(Console.ReadLine());
                        Console.Write("Please enter y = ");
                        synth.Speak("Please enter y");
                        y = double.Parse(Console.ReadLine());
                        result = (int)x * (int)y;
                        Console.WriteLine("{0} * {1} = {2} ", x, y, result);
                        synth.Speak("Your result is shown below");
                        break;
                    case 5:
                        Console.WriteLine("You have selected - MODULUS!");
                        synth.Speak("You have selected - MODULUS!");
                        Console.Write("Please enter x = ");
                        synth.Speak("Please enter x");
                        x = double.Parse(Console.ReadLine());
                        Console.Write("Please enter y = ");
                        synth.Speak("Please enter y");
                        y = double.Parse(Console.ReadLine());
                        result = (int)x % (int)y    ;
                        Console.WriteLine("{0} % {1} = {2} ", x, y, result);
                        synth.Speak("Your result is shown below");
                        break;
                    case 6:
                        Console.WriteLine("You have selected - Square Number");
                        synth.Speak("You have selected - Square Number!");
                        Console.Write("Please enter square number = ");
                        double squareNumber = double.Parse(Console.ReadLine());
                        double result1 = Math.Sqrt(squareNumber);
                        Console.WriteLine("Square number of {0} is {1}",squareNumber,result1);
                        synth.Speak("Your result is shown below");
                        break;
                    case 7:
                        Console.WriteLine("Bye bye :)");
                        synth.Speak("I hope our paths do not cross again !");
                        quit = true;
                        break;

                }
                #endregion
            }
        }
    }
}
