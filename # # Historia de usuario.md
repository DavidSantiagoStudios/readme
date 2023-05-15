# # Historia de usuario 



# # Descripción caso de uso 


### Objetivo

El objetivo de este sistema es permitir el registro de las ventas de cinturones en una tienda de moda y proporcionar información sobre el modelo más vendido y el total de ventas.

### Requerimientos

**Interfaz de usuario:**

- El sistema debe solicitar al usuario la cantidad vendida para cada modelo de cinturón.
- Se debe utilizar una instancia de la clase `Scanner` para leer las entradas del usuario.

**Registro de ventas:**

- El sistema debe almacenar la cantidad vendida para cada modelo de cinturón en un arreglo de enteros.
- Debe existir un arreglo de cadenas para almacenar los nombres de los modelos de cinturones.

**Cálculo del modelo más vendido:**

- El sistema debe determinar automáticamente el modelo más vendido comparando las cantidades vendidas.
- Se debe mantener un registro de la cantidad máxima vendida y el nombre del modelo correspondiente.

**Cálculo del total de ventas:**

- El sistema debe calcular el total de ventas sumando todas las cantidades vendidas registradas.

**Salida de resultados:**

- El sistema debe mostrar el nombre del modelo más vendido y la cantidad vendida correspondiente.
- Debe mostrar el total de ventas de la tienda.

**Manejo de errores:**

- El sistema debe manejar adecuadamente cualquier error de entrada, como entradas no numéricas o negativas.

**Modularidad:**

- El sistema debe estar organizado en una clase llamada "VentasCinturones".
- Se debe implementar un método adicional llamado "sumarElementos" para calcular la suma de elementos de un arreglo.

**Restricciones técnicas:**

- El sistema debe implementarse en Java.

- Se debe utilizar el paquete `java.util.Scanner` para la interacción con el usuario.
- Se debe utilizar arreglos para almacenar las cantidades vendidas y los nombres de los modelos de cinturones.

- Se debe asegurar el cierre adecuado del objeto `Scanner` al finalizar la interacción con el usuario.


# # Diagrama de Caso de Uso 


# # Detalle del caso de uso 

### Caso de Uso: 

Registro de ventas de cinturones en una tienda de moda

###Objetivo

El objetivo de este caso de uso es permitir el registro de las ventas de cinturones en una tienda de moda y proporcionar información sobre el modelo más vendido y el total de ventas.

###Actores
- Vendedor: Persona encargada de registrar las ventas de cinturones.

###Precondiciones

- El vendedor debe tener acceso al sistema de registro de ventas.

###Flujo Principal

1. El vendedor inicia el proceso de registro de ventas.

2. El sistema muestra al vendedor una lista de modelos de cinturones disponibles.

3. Para cada modelo de cinturón:

1. El vendedor ingresa la cantidad vendida del modelo seleccionado.

2. El sistema verifica que la cantidad ingresada sea válida (mayor o igual a cero).

3. El sistema registra la cantidad vendida para el modelo de cinturón.

4. El sistema compara la cantidad vendida con la cantidad máxima vendida hasta el momento.

5. Si la cantidad vendida es mayor que la cantidad máxima vendida:

- El sistema actualiza la cantidad máxima vendida con la cantidad ingresada.

- El sistema registra el modelo de cinturón como el modelo más vendido hasta el momento.

4. El sistema calcula el total de ventas sumando todas las cantidades vendidas registradas.

5. El sistema muestra al vendedor el modelo de cinturón más vendido y la cantidad vendida correspondiente.

6. El sistema muestra al vendedor el total de ventas de la tienda.

### Postcondiciones

- Se registran las ventas de cinturones en el sistema.

- Se obtiene información sobre el modelo más vendido y el total de ventas
















# # DFD










# #  Pseudocodigo

Inicio
   Declarar y asignar variables
      cantidadCinturones: arreglo de enteros de tamaño 5
      cinturones: arreglo de cadenas con los nombres de los cinturones
      maxCantidadVendida: entero
      cinturonMasVendido: cadena

   Crear una instancia de Scanner
   Para cada elemento i en el rango de 0 a 4

      Mostrar mensaje "Ingrese la cantidad vendida para " + cinturones[i] + ": "
      Leer cantidadCinturones[i] desde la entrada del usuario

   Si cantidadCinturones[i] es mayor que maxCantidadVendida
         Asignar cantidadCinturones[i] a maxCantidadVendida
         Asignar cinturones[i] a cinturonMasVendido

Calcular el totalVentas llamando a la función sumarElementos con cantidadCinturones como argumento

   Mostrar "El cinturón más vendido fue: " + cinturonMasVendido
   Mostrar "Cantidad vendida del cinturón más vendido: " + maxCantidadVendida
   Mostrar "Total de ventas de la tienda: " + totalVentas

Cerrar la instancia de Scanner
Fin

Función sumarElementos (array: arreglo de enteros)
   Declarar e inicializar la variable sum como 0

Para cada elemento i en array
      Sumar i a sum

Retornar sum 

















# # Codigo de programacion estructurada 



int[] cantidadCinturones = new int[5];
String[] cinturones = {"Cinturón Prada", "Cinturón Diesel", "Cinturón Versache", "Cinturón Armani", "Cinturón WhiteSpice"};
int maxCantidadVendida = 0;
String cinturonMasVendido = "";

for (int i = 0; i < 5; i++) {
    System.out.print("Ingrese la cantidad vendida para " + cinturones[i] + ": ");
    cantidadCinturones[i] = leerEnteroDesdeConsola();

    if (cantidadCinturones[i] > maxCantidadVendida) {
        maxCantidadVendida = cantidadCinturones[i];
        cinturonMasVendido = cinturones[i];
    }
}

int totalVentas = sumarElementos(cantidadCinturones);

System.out.println("El cinturón más vendido fue: " + cinturonMasVendido);
System.out.println("Cantidad vendida del cinturón más vendido: " + maxCantidadVendida);
System.out.println("Total de ventas de la tienda: " + totalVentas);




# # Codigo de programacion Orientada a Objetos 


import java.util.Scanner;

public class VentasCinturones {
    private int[] cantidadCinturones;
    private String[] cinturones;
    private int maxCantidadVendida;
    private String cinturonMasVendido;
    private Scanner scanner;

    public VentasCinturones() {
        cantidadCinturones = new int[5];
        cinturones = new String[]{"Cinturón Prada", "Cinturón Diesel", "Cinturón Versache", "Cinturón Armani", "Cinturón WhiteSpice"};
        maxCantidadVendida = 0;
        cinturonMasVendido = "";
        scanner = new Scanner(System.in);
    }

    public void ingresarCantidadVendida() {
        for (int i = 0; i < 5; i++) {
            System.out.print("Ingrese la cantidad vendida para " + cinturones[i] + ": ");
            cantidadCinturones[i] = scanner.nextInt();

            if (cantidadCinturones[i] > maxCantidadVendida) {
                maxCantidadVendida = cantidadCinturones[i];
                cinturonMasVendido = cinturones[i];
            }
        }
    }

    public int calcularTotalVentas() {
        int totalVentas = 0;
        for (int cantidad : cantidadCinturones) {
            totalVentas += cantidad;
        }
        return totalVentas;
    }

    public void mostrarResultados() {
        System.out.println("El cinturón más vendido fue: " + cinturonMasVendido);
        System.out.println("Cantidad vendida del cinturón más vendido: " + maxCantidadVendida);
        System.out.println("Total de ventas de la tienda: " + calcularTotalVentas());
    }

    public void cerrarScanner() {
        scanner.close();
    }

    public static void main(String[] args) {
        VentasCinturones ventas = new VentasCinturones();
        ventas.ingresarCantidadVendida();
        ventas.mostrarResultados();
        ventas.cerrarScanner();
    }
}


