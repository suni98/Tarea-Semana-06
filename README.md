# Tarea-Semana-06
public class Vehiculo
{
    public string Placa { get; set; }
    public string Marca { get; set; }
    public string Modelo { get; set; }
    public int Año { get; set; }
    public double Precio { get; set; }
}

public class Nodo
{
    public Vehiculo Vehiculo { get; set; }
    public Nodo Siguiente { get; set; }
}

public class Estacionamiento
{
    private Nodo inicio;

    public void AgregarVehiculo(Vehiculo vehiculo)
    {
        Nodo nuevoNodo = new Nodo { Vehiculo = vehiculo, Siguiente = inicio };
        inicio = nuevoNodo;
    }

    public Vehiculo BuscarVehiculo(string placa)
    {
        Nodo actual = inicio;
        while (actual != null)
        {
            if (actual.Vehiculo.Placa == placa)
                return actual.Vehiculo;
            actual = actual.Siguiente;
        }
        return null;
    }

    public void VerVehiculosPorAño(int año)
    {
        Nodo actual = inicio;
        while (actual != null)
        {
            if (actual.Vehiculo.Año == año)
                Console.WriteLine($"Placa: {actual.Vehiculo.Placa}, Marca: {actual.Vehiculo.Marca}");
            actual = actual.Siguiente;
        }
    }

    // ... otros métodos
}
public class DataManager
{
    public List<double> List1 { get; set; }
    public List<double> List2 { get; set; }
    public List<double> LessThanAverage { get; set; }
    public List<double> GreaterThanAverage { get; set; }

    public void CalculateAndCompare()
    {
        // ... (código ya explicado anteriormente)
    }

    private double CalculateAverage()
    {
        double sum = 0;
        int count = 0;
        foreach (double num in List1.Concat(List2))
        {
            sum += num;
            count++;
        }
        return sum / count;
    }
}
