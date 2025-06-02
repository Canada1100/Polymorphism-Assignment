# Polymorphism-Assignment

public string FirstName { get; set; }


public string LastName { get; set; }


public static bool operator ==(Employee e1, Employee e2)
{
    if (ReferenceEquals(e1, e2))
        return true;

    if ((object)e1 == null || (object)e2 == null)
        return false;

    return e1.Id == e2.Id;
}

/
public static bool operator !=(Employee e1, Employee e2)
{
    return !(e1 == e2);
}


public override bool Equals(object obj)
{
    var other = obj as Employee;
    if (other == null) return false;
    return this.Id == other.Id;
}


public override int GetHashCode()
{
    return this.Id.GetHashCode();
}


public void Quit()
{
    
    Console.WriteLine($"Employee {FirstName} {LastName} with ID {Id} has quit.");
}
