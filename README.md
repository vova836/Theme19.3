///Задача 1
using System;
using System.Collections.Generic;

namespace BookLibrary
{
    class Book : IComparable<Book>
    {
        public string Title { get; set; }
        public double Price { get; set; }

        public Book(string title, double price)
        {
            Title = title;
            Price = price;
        }

        public int CompareTo(Book other)
        {
            if (other == null) 
                return 1;
            return Title.CompareTo(other.Title);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            List<Book> library = new List<Book>();
            library.Add(new Book("Гарри Поттер", 20.50));
            library.Add(new Book("Великий Гэтсби", 15.80));
            library.Add(new Book("1984", 18.25));
            library.Add(new Book("Убить пересмешника", 12.99));
            library.Add(new Book("Происхождение земли", 17.75);

            library.Sort();

            foreach (Book book in library)
            {
                Console.WriteLine($"Title: {book.Title}, Price: {book.Price}");
            }
        }
    }
}
///Задача2
using System;
using System.Collections.Generic;

namespace PersonSorting
{
    class Person : IComparable<Person>
    {
        public string Name { get; set; }
        public int Age { get; set; }

        public Person(string name, int age)
        {
            Name = name;
            Age = age;
        }

        public int CompareTo(Person other)
        {
            if (other == null)
                return 1;
            return Name.CompareTo(other.Name);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            List<Person> people = new List<Person>();
            people.Add(new Person("Янишевский", 18));
            people.Add(new Person("Щеглов", 17));
            people.Add(new Person("Мустяца", 17));

            people.Sort();

            foreach (Person person in people)
            {
                Console.WriteLine($"Name: {person.Name}, Age: {person.Age}");
            }
        }
    }
}
///Задача3
using System;
using System.Collections.Generic;

namespace CarSorting
{
    class Car : IComparable<Car>
    {
        public int Id { get; set; }
        public string Brand { get; set; }
        public int MaxSpeed { get; set; }
        public double Price { get; set; }
        public double Discount { get; set; }

        public Car(int id, string brand, int maxSpeed, double price, double discount)
        {
            Id = id;
            Brand = brand;
            MaxSpeed = maxSpeed;
            Price = price;
            Discount = discount;
        }

        public double GetDiscountedPrice()
        {
            return Price - Price * Discount / 100;
        }

        public int CompareTo(Car other)
        {
            if (other == null)
                return 1;
            return Price.CompareTo(other.Price);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            List<Car> carDatabase = new List<Car>();
            carDatabase.Add(new Car(1, "Toyota", 200, 25000, 5));
            carDatabase.Add(new Car(2, "Honda", 190, 23000, 3));
            carDatabase.Add(new Car(3, "Ford", 180, 22000, 4));
            carDatabase.Add(new Car(4, "Chevrolet", 210, 27000, 6));
            carDatabase.Add(new Car(5, "BMW", 220, 35000, 8));

            carDatabase.Sort();

            foreach (Car car in carDatabase)
            {
                Console.WriteLine($"ID: {car.Id}, Brand: {car.Brand}, Price: {car.Price}, Discoun
///Задача4
using System;
using System.Collections.Generic;

namespace Figures
{
    // Абстрактный класс Фигура
    abstract class Figure : IComparable<Figure>
    {
        public abstract double GetArea();
        public abstract double GetPerimeter();

        public virtual void PrintInfo()
        {
            Console.WriteLine($"Figure. Area: {GetArea()}, Perimeter: {GetPerimeter()}");
        }

        public int CompareTo(Figure other)
        {
            if (other == null)
                return 1;
            return GetArea().CompareTo(other.GetArea());
        }
    }

    // Класс Прямоугольник
    class Rectangle : Figure
    {
        public double Width { get; set; }
        public double Height { get; set; }

        public Rectangle(double width, double height)
        {
            Width = width;
            Height = height;
        }

        public override double GetArea()
        {
            return Width * Height;
        }

        public override double GetPerimeter()
        {
            return 2 * (Width + Height);
        }

        public override void PrintInfo()
        {
            Console.WriteLine($"Rectangle. Width: {Width}, Height: {Height}. Area: {GetArea()}, Perimeter: {GetPerimeter()}");
        }
    }

    // Класс Круг
    class Circle : Figure
    {
        public double Radius { get; set; }

        public Circle(double radius)
        {
            Radius = radius;
        }

        public override double GetArea()
        {
        
