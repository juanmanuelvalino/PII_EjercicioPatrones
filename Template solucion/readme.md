# Ejercicios de DIP, ISP, SRP
## Ejercicio 1 

**DIP:** no se cumple debido a que se utiliza como parámetro datos de la clase "BaseDeDatos", lo que podría ocasionar que si algo cambiase en esa clase, el código de "AnalizadorDatos" dejaría de funcionar. A su vez, "BaseDeDatos" depende de "DataBaseObject".

**ISP:** no se cumple, dado que no hay implementadas interfaces en el código dado.

**SRP:** No se cumple pues la clase "AnalizadorDatos", no solo tiene la responsabilidad de analizar los datos, sino que también tiene la responsabilidad devolver de alguna manera ciertos mensajes.


## Ejercicio 2

```cs
//Insertar el código corregido
//Creo dos interfaces nuevas para aplicar DIP.
interface IDataBaseObject
{
    string Descripcion { get; }
}

interface IBaseDeDatos
{
    public void GrabarDato(string clave, IDataBaseObject dato);
    public String[] ListarClaves();
    public String[] ListarDescripcionDatos();
    public DataBaseObject[] ListarDatos();
}
//Objeto que representa un dato de la base de datos.
class DataBaseObject : IDataBaseObject
{
    public string Descripcion { get; }
}

//Base de datos.
class BaseDeDatos: IDataBaseObject, IBaseDeDatos
{
    public IDataBaseObject ObtenerDato(string clave)
    {
        //Devuelve el dato correspondiente a la clave
    }
    public void GrabarDato(string clave, DataBaseObject dato)
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
    public IDataBaseObject[] ListarDatos()
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
}
//Se separa la clase de análisis de la clase de devolución de datos para cumplir SRP
class ResultadoAnalisis
{
    public AnlizadorDatos analisis {get;}
    public void MensajeUno()
    { /*Mensaje predeterminado*/ }
    public void MensajeDos()
    { /*Mensaje predeterminado*/ }
}
```
## Ejercicio 3 

```cs
////Insertar el código corregido. El ejercicio 2 y 3 pueden ser resueltos de forma conjunta

```