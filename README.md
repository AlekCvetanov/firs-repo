# firs-repo
My first repository
using System;
using System.Collections.Generic;
using System.Linq;

namespace Zadanie_10
{
    class Program
    {
        static void Main(string[] args)
        {
            List<string> items = Console.ReadLine().Split('!').ToList();
            string command = Console.ReadLine();
            while (command != "Go Shopping!")
            {
                string[] list = command.Split(" ");
                string command1 = list[0];
                string item = list[1];
                if (command1 == "Unnecessary")
                {
                    if (items.Contains(item))
                    {
                        items.Remove(item);
                    }
                }
                else if (command1 == "Urgent")
                {
                    if (!items.Contains(item))
                    {
                        items.Add(item);
                    }
                }
                else if (command1 == "Correct")
                {
                    string newItem = list[2];
                    int index = items.IndexOf(item);
                    if (items.Contains(item))
                    {
                        items.Add(newItem);
                        items.Remove(item);
                    }
                }
                else if (command1 == "Rearrange")
                {
                    if (items.Contains(item))
                    {
                        items.Remove(item);
                        items.Add(item);
                    }
                }
                command = Console.ReadLine();
            }
            Console.WriteLine(string.Join(", ", items));
        }
    }
}
