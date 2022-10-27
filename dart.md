# *UNIVERSIDAD DE COLIMA*
## *FACULTAD DE INGENIERIA MECANICA Y ELECTRICA*
#### *CARRERA: INGENIERIA EN COMPUTACION INTELIGENTE*
#### *ANDREA KETZABEL MADRIGAL RODRIGUEZ*
#### *PROFESOR: WALTER MATA LOPEZ 
----

_HOLA SOY ANDREA ESTUDIANTE DE ICI Y EN ESTE TRABAHO PRESENTARE LOS EJERCICIOS QUE HICE 
EN SEGUNDA PARCIAL_

---
### TIPADO ESTATICO 
    import 'dart:io';
    import 'dart:js_util';
    void main() {
    print("Hola mundo");
    //tipado explicito
    int miEntero = 10; 
    //Para declarar variables la primer letra es minuscula
    double miDouble = 3.1416;
    print(miDouble is int);
    print(miEntero is double);
    num miNumero = 10;
    num miNumero2 = 3.1416;
    print(miNumero is int);
    print(miNumero2 is int);
 
    String miCadena = "hola";
    print(miCadena is String);

    dynamic miDinamico = "Hola";
    print(miDinamico);
    miDinamico = 3.1416;
    print(miDinamico);

    bool miBool = true;
    print(!miBool);
---
### CLASES
    
    void main() {
    User usuario = User("ANDREA", 15);
    print(usuario);
    usuario.reporteUser();
    print(usuario.nombre);
    print(usuario.edad);
    usuario.nombre = "andrea";
    usuario.edad = 18;

    User usuario2 = User();
    usuario2._nombre = "julian";
    usuario2.edad = 19;
    usuario2.reporteUser();
   }
    
    //Clase que reperesenta un usueario
    class User {
    //Siempre la primera letra del nombre de la clase es en mayuscula
    ///Propiedad de nombre de tipo string
    String? _nombre;

    ///Propiedad edad de tipo int
    int? _edad;

    ///metodo que imprime un usuario
    void reporteUser() {
      print(_nombre);
      print(_edad);
    }

    User(String nombre, int edad) {
      this._nombre = nombre;
      this._edad = edad;
    }

    void set nombre(String nombre) => _nombre = nombre;
    String get nombre => _nombre!;
    void set nombre(String nombre) {
      _nombre = nombre;
    }

    void set edad(int edad) {
      _edad = edad;
    }
    void set edad(int edad) => _edad = edad; //=> ES UN FAT ARROW
    int get edad => _edad!;
    String get nombre {
      return _nombre!; // "!" ES PARA OBLIGAR A RETORNAR UN VALOR.
        }
     }
---
### CLASE CON METODOS GET 
    void main() {
    User usuario = User(nombre: "ANDREA", edad: 15);
    print(usuario.getNombre);
    print(usuario.getEdad);
     }

    class User {
    String? nombre;
    int? edad;
    void reporteUser() {
    print(nombre);
    print(edad);
    }

    User({this.nombre, this.edad});

    void set setnombre(String nombre) => nombre = nombre;
    void set setedad(int edad) => edad = edad; //=> ES UN FAT ARROW
    String get getNombre => nombre!;
    int get getEdad => edad!;
    }
---
### RUNTYME
    void main(List<String> args) {
    //declaracion de constante con tipo explicito
    //Tiempo de compilacion
    const double miPi =
      3.1416; // las constantes se asignan en tiempo de compilacion
    const double miGravedad = 9.81;
    //Asignando un valor en tiempo de ejecucion
    final double miPi;
    miPi = setPi();
    print(miPi);
    print(miGravedad);
    }

    double setPi() {
    //tiempo de ejecucion
    return 3.1416;
    }

    void main(List<String> args) {
    num miNumero;
    // Dynamic es un tipo de dato es para que le puedas asignar cualquier tipo de dato
    miNumero = 3.1416;

    print(miNumero.runtimeType); // Runtyme es el tiempo de ejecucion.
    //esto me regresara un dato tipo double.
    }

    void main() {
    var minumero1 = 100;
    var minumero2 = 9.81;
    var nombre = "kurt";
    print(minumero1.runtimeType);
    print(nombre.runtimeType);
    }

    void main() {
    var numero1 = 100;
    var numero2 = 9.81;

    var resultado; //no asigne ningun tipo de dato,
    //y al poner var me lo pone de tipo dinamico.

    resultado = numero1 + numero2;

    print(resultado.runtimeType); //Aqui nos damos cuenta que
    //que al poner runtime por
    //tiempo de ejecucion nos
    //retorna un valor double
    }

    void main() {
    const numero1 = 19.5;
    const numero2 = 10;
    //Final es para declarar una variable como entero.
    final total = numero1 * numero2;
    print(total);
    }

    void main() {
    //Impresion de numeros hexadecimales
    int nhex1 = 0xf;
    int nhex2 = 0xf;

    print(nhex1 * nhex2);
    var nOcatal = 125.toRadixString(8);
    print(nOcatal.runtimeType);

    var nh = 125.toRadixString(16);
    print(nh.runtimeType);
    } 
---
### INTERPOLACION DE CADENAS
    void main() {
    String nombreCurso = "Programacion Funcional";  
    var num = 4;
    String carrera = "ici";
    //contetacion de cadenas
    print(carrera + " " + nombreCurso);
    //interpolaciond e cadenas
    print("$carrera $nombreCurso");
    // de esta forma es para funciones u operaciones aritmeticas
    print("${getCarrera}${nombreCurso}");
    print("el cuadrado de $num es ${num * num}");
    print("el cuadrado de $num es ${cuadrado(num)}");
    }

    String getCarrera() {
    return "ici";
    }

    int cuadrado(int num) {
    return num * num;
    }

      void main() {
     // de esta manera podemos imprimir  sin
    //necesidad de poner "," y si queremos hacerlo
    // en varios renglones "\n".
    print("En un lugar de la "
      "de la mancha de cuyo"
      "nombre no quiero acordarme");
     }

     void main() {
     print("Dame tu nombre");
    // Aqui obtenemos un dato a traves
    // del teclado.
     final nombre = stdin.readLineSync();
    print("Tu nombre es $nombre");
    }
---
### CORDINALES SI
    void main() {
    int n1 = 5, n2 = 3;     
    if (n1 > n2) {
    print("$n1>$n2");
    } else if (n1 == n2) {
    print("$n1=$n2");
    } else {
    print("$n1<$n2");  
    }
    }
---
### INTERRUPTOR SENTENCIA 
    void main() {
    var dia;
    dia = 1;
     switch (dia) {
    case 1:
      print("el dia es ${getDay(dia)}");
      break;
    case "martes":
      print("hoy es martes");
      break;
    default:
      print("Dia no conocido");
     }
    }

    String getDay(int num) {
     if (num == 1) {
    return "lunes";
    } else {
    return " ";
    }
    }
---
### INCREMENTOS  Y DECREMENTOS

    void main(List<String> args) {

      var contador=0;

    contador=contador+1;
     print(contador);
     contador+=1;
     print(contador);
    contador++;
    print(contador);
    ++contador;
    print(contador);

    var c=10;
     print(++c);//11
    c=10;
    print(c++); //10
    print(c);
    }
    // DECREMENTOS
    void main(List<String> args) {

    var contador = 0;

    contador = contador - 1;
      print(contador);
     contador -= 1;
    print(contador);
    contador--;
      print(contador);
     --contador;
     print(contador);

     var c = 10;
    print(--c); //11
    c = 10;
    print(c--); //10
    print(c);
    }
