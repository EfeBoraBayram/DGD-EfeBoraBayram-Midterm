# DGD203-EfeBoraBayram-Midterm
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Welcome to the Action Adventure Game!");
        
        
        Console.Write("What is your name? ");
        string playerName = Console.ReadLine();

        Console.WriteLine($"Great to meet you, {playerName}! Prepare for an action-packed adventure!");

        
        string[] questions = {
            "You spot a treasure chest guarded by a fierce dragon. Do you (a: Fight the dragon, b: Sneak past it)?",
            "You find a mysterious potion on the ground. Do you (a: Drink it, b: Throw it away)?",
            "You encounter a group of bandits blocking your path. Do you (a: Negotiate with them, b: Charge in and fight)?",
            "You hear a loud explosion nearby. Do you (a: Investigate the noise, b: Run away to safety)?",
            "You discover a hidden cave. Do you (a: Enter cautiously, b: Shout to see if anyone is inside)?",
            "You find a magical sword on the ground. Do you (a: Take it, b: Leave it for someone else)?",
            "You see an ally in trouble. Do you (a: Rush to help, b: Stay hidden and observe)?",
            "You have to choose a vehicle for your escape. Do you (a: Take a horse, b: Steal a motorcycle)?"
        };

        
        char[] answers = new char[questions.Length];

       
        for (int i = 0; i < questions.Length; i++)
        {
            Console.WriteLine(questions[i]);
            Console.Write("Your answer: ");
            answers[i] = Console.ReadKey().KeyChar;
            Console.WriteLine(); 
        }

       
        ProvideFeedback(answers, playerName);
    }

    static void ProvideFeedback(char[] answers, string playerName)
    {
        Console.WriteLine($"\nThank you for playing, {playerName}!");
        Console.WriteLine("Based on your choices:");

        foreach (char answer in answers)
        {
            switch (answer)
            {
                case 'a':
                    Console.WriteLine("- You are bold and fearless, ready to take on any challenge!");
                    break;
                case 'b':
                    Console.WriteLine("- You prefer to think strategically and avoid unnecessary risks!");
                    break;
                default:
                    Console.WriteLine("- You have a unique perspective; keep it up!");
                    break;
            }
        }

        
        if (answers[0] == 'a' && answers[6] == 'a')
        {
            Console.WriteLine("Your courage knows no bounds! You battle dragons and save your friends!");
        }
        else if (answers[1] == 'b' && answers[4] == 'a')
        {
            Console.WriteLine("You are cautious but also adventurous, ready to face the unknown!");
        }
        else if (answers[3] == 'a' && answers[5] == 'a')
        {
            Console.WriteLine("You are curious and brave, ready to explore the mystical and magical!");
        }
        else if (answers[2] == 'b' && answers[7] == 'b')
        {
            Console.WriteLine("You are a true strategist, always thinking two steps ahead in any situation!");
        }
        else
        {
            Console.WriteLine("Your choices reflect a balanced approach to adventure, combining bravery with wisdom.");
        }
    }
}
