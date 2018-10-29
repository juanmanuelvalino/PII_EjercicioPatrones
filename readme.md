# Ejercicios de DIP, ISP, SRP
## Ejercicio 1 
Sea el siguiente código:

```cs
//Objeto que representa un dato de la base de datos.
class DataBaseObject
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
    public DataBaseObject[] ListarDatos()
    {
//Devuelve un DataBaseObject[] con todos los datos almacenados en la base
    }
}
class AnlizadorDatos
{
    private BaseDeDatos baseDatos{get; set;};
    public void Analizar()
    {
        foreach (DataBaseObject DBObj in baseDatos.ListarDatos())
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
    public bool Cumplecondicion(DataBaseObject DBobj)
    {
        //Devuelve true si se cumple una cierta condición
    }
    public void MensajeUno()
    { /*Mensaje predeterminado*/ }
    public void MensajeDos()
    { /*Mensaje predeterminado*/ }
}

```
Critica el código de la clase `AnalizadorDatos` en base a:
- DIP
- ISP 
- SRP


## Ejercicio 2
Modifica el código del ejercicio 4 para que los tres principios se cumplan (si es que no se cumplían).

## Ejercicio 3 
En la clase `AnalizadorDatos`, se desea poder tener diversas condiciones y en base a estas emitir diferentes mensajes. 

**Por ejemplo**: si la condición evalúa si la descripción de un dato empieza con "f", cuando la misma se cumple deberá emitir un mensaje que diga esto por pantalla, y si la condición no se cumple, por pantalla se reportará que el dato no empieza con F. 

Reprograma la clase para cumplir con este nuevo requisito cumpliendo con los principios estudiados durante el curso.
