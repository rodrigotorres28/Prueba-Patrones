# Ejercicios de DIP, ISP, SRP
## Ejercicio 1 

**DIP:** No se cumple debido a que no se implementan abstracciones de clases, cumplecondición dentro de la clase AnalizadorDatos utiliza directamente objetos de la clase DataBaseObject cuando en su lugar se podria implementar una abtracción de dicha clase

**ISP:** No se cumple debido a que no existen interfaces las cuales tengan operaciones que de ser utilizadas por alguna clase solo afecten a dicha clase y no interfieran con el resto

**SRP:** No secumple debido a que hay clases que poseen más de 1 responsabilidad, la clase base de datos tiene tanto la responsabilidad de obtener datos como la de grabarlos, listar claves, listar descripciones y listar instancias de DataBaseObject


## Ejercicio 2

```cs

class IDataBaseObject
{
    public string Descripcion {get; }
}

class DataBaseObject : IDataBaseObject
{
    public string Descripcion { get; }
}

//Base de datos.
class BaseDeDatos
{
    public DataBaseObject ObtenerDato(string clave)
    {
        //Devuelve el dato correspondiente a la clave
    }
    public void GrabarDato(string clave, IDataBaseObject dato)
    {
        //Graba el dato en la base de datos, bajo la clave dada
    }
    public String[] ListarClaves()
    {
        //Devuelve un String[] con todas las claves
    }
    public String[] ListarDescripcionDatos()
    {
        //Devuelve un String[] con la descripción de todas los 
        //datos almacenados en  la base
    }
    public DataBaseObject[] ListarDatos()
    {
//Devuelve un DataBaseObject[] con todos los datos almacenados en la base
    }
}
class AnlizadorDatos
{
    private IBaseDeDatos baseDatos{get; set;};
    public void Analizar()
    {
        foreach (IDataBaseObject DBObj in baseDatos.ListarDatos())
        {
            if (CumpleCondicion(DBObj))
            {
                MensajeUno();
            }
            else
            {
                MensajeDos();
            }
        }
    }
    public bool Cumplecondicion(IDataBaseObject DBobj)
    {
        //Devuelve true si se cumple una cierta condición
    }
    public void MensajeUno()
    { /*Mensaje predeterminado*/ }
    public void MensajeDos()
    { /*Mensaje predeterminado*/ }
}

```
## Ejercicio 3 

```cs
class AnlizadorDatos
{
    mensajeCondicion = "" //Acá va el string que cumplecondición asigna dependiendo de que condición se                         cumplió
    private IBaseDeDatos baseDatos{get; set;};
    public void Analizar()
    {
        foreach (IDataBaseObject DBObj in baseDatos.ListarDatos())
        {
            if (CumpleCondicion(DBObj))
            {
                MensajeUno();
            }
            else
            {
                MensajeDos();
            }
        }
    }
    public bool Cumplecondicion(IDataBaseObject DBobj)
    {
        //Devuelve true si se cumple una cierta condición
        //Asigna a la variable mensajeCondicion un string dependiendo de que condición se cumplió
    }
    public void MensajeUno()
    { /*Mensaje obtenido de la variable mensajeCondicion*/ }
    public void MensajeDos()
    { /*Mensaje predeterminado si no cumple condición*/ }
}

```
