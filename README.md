# Kk
// Базовый класс
public abstract class Animal
{
    public string Name { get; set; }

    public Animal(string name)
    {
        Name = name;
    }

    public abstract void MakeSound();
    public abstract void Eat(string food);
    public abstract void Sleep(int time); // время во времени в условных единицах
}

// Подкласс Lion
public class Lion : Animal
{
    public Lion(string name) : base(name) { }

    public override void MakeSound()
    {
        Console.WriteLine($"{Name} рычит: " +
                          "Roaaar!");
    }

    public override void Eat(string food)
    {
        Console.WriteLine($"{Name} ест {food} с достоинством.");
    }

    public override void Sleep(int time)
    {
        Console.WriteLine($"{Name} спит {time} часов.");
    }
}

// Подкласс Monkey
public class Monkey : Animal
{
    public Monkey(string name) : base(name) { }

    public override void MakeSound()
    {
        Console.WriteLine($"{Name} кричит: уа-у-у!");
    }

    public override void Eat(string food)
    {
        Console.WriteLine($"{Name} ест {food} очень активно.");
    }

    public override void Sleep(int time)
    {
        Console.WriteLine($"{Name} спит {time} часов.");
    }
}

// Подкласс Dog
public class Dog : Animal
{
    public Dog(string name) : base(name) { }

    public override void MakeSound()
    {
        Console.WriteLine($"{Name} лает: гав-гав!");
    }

    public override void Eat(string food)
    {
        Console.WriteLine($"{Name} кушает {food} и виляет хвостом.");
    }

    public override void Sleep(int time)
    {
        Console.WriteLine($"{Name} спит {time} часов.");
    }
}

// Класс Zoo
public class Zoo
{
    private List<Animal> animals = new List<Animal>();

    public void AddAnimal(Animal a)
    {
        animals.Add(a);
    }

    public void ShowAllAnimals()
    {
        foreach (var a in animals)
        {
            Console.WriteLine(a.GetType().Name + ": " + a.Name);
        }
    }
}
