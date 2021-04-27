## ¡Hola, Mundo!

Ahora que has instalado Rust, vamos a escribir el primer programa en Rust.
Es tradicional cuando estás aprendiendo un nuevo lenguaje escribir un pequeño
programa que imprima el texto `¡Hola, mundo!` en la pantalla, ¡así que aquí
haremos lo mismo!

> Nota: Este libro asume que tienes conocimientos básicos con la línea de
> comandos. Rust no hace demandas específicas sobre su edición o herramientas
> o dónde vive su código, por lo que si prefiere usar su entorno de desarrollo
> integrado (IDE) en lugar de la línea de comandos, no dude en usar su IDE
> favorito. Muchos IDE ahora tienen cierto grado de compatibilidad con Rust;
> consulte la documentación del IDE para obtener más detalles. Recientemente,
> el equipo de Rust se ha centrado en permitir un gran soporte de IDE, ¡y se
> ha avanzado rápidamente en ese frente!

### Crear una Carpeta para el Proyecto

Comience por crear una carpeta para guardar tu código de Rust. A Rust no le
importa dónde está tu código, pero para los ejercicios y proyectos de este libro,
te sugerimos crear una carpeta llamada *proyectos* en tu carpeta personal y
mantenga todos sus proyectos allí.

Abre una consola e ingrese los siguientes comandos para crear una carpeta de
*proyectos* y otra para el proyecto “¡Hola, mundo!” dentro de la carpeta
*proyectos*.

Si usas Linux, macOS o PowerShell en Windows, ingresa lo siguiente:

```console
$ mkdir ~/proyectos
$ cd ~/proyectos
$ mkdir hola_mundo
$ cd hola_mundo
```

Si usas el CMD de Windows, ingresa lo siguiente:

```cmd
> mkdir "%USERPROFILE%\proyectos"
> cd /d "%USERPROFILE%\proyectos"
> mkdir hola_mundo
> cd hola_mundo
```

### Escribir y Ejecutar el Programa de Rust

A continuación, cree un nuevo archivo llamado *main.rs*. Los archivos de Rust
siempre terminan con la extensión *.rs*. Si usa má de una palabra en el nombre
de archivo, use un guión bajo para separarlas. Por ejemplo, use *hola_mundo.rs*
en lugar de *holamundo.rs*.

Ahora abre el archivo *main.rs* que acabas de crear e ingrese el código del Listado 1-1.

<span class="filename">Archivo: main.rs</span>

```rust
fn main() {
    println!("¡Hola, mundo!");
}
```

<span class="caption">Listado 1-1: Un programa que imprime `¡Hola, mundo!`</span>

Guarda el archivo y dirígite a la ventana de la consola. Si estás en Linux o
macOS, ingresa los siguientes comandos para compilar y ejecutar el archivo:

```console
$ rustc main.rs
$ ./main
¡Hola, mundo!
```

O si estás en Windows, ingresa el comando `.\main.exe` en lugar de `./main`:

```powershell
> rustc main.rs
> .\main.exe
¡Hola, mundo!
```

Independientemente de tu sistema operativo, el texto `¡Hola, mundo!` se debe mostrar
en la consola. Si no ve este resultado, consulte la parte de ["Solución de Problemas"]
[troubleshooting] de la sección Instalación para obtener ayuda.

Si `¡Hola, mundo!` se mostró, ¡felicitaciones! Oficialmente has escrito un programa de
Rust. Eso te convierte en un(a) programador(a) de Rust, ¡bienvenido(a)!

### Anatomía de un Programa de Rust

Repasemos en detalle lo que acaba de suceder en su programa “¡Hola, mundo!”.
Aquí está la primera pieza del rompecabezas:

```rust
fn main() {

}
```

Esas líneas definen una función en Rust. La función `main` es especial: Siempre
es el primer código que se ejecuta en cada programa ejecutable de Rust. La primera
línea declara una función llamada `main` que no tiene argumentos y no devuelve nada.
Si hubiera argumentos, irían dentro de los paréntesis `()`.

Además, puedes notar que el cuerpo de la función está envuelto entre corchetes `{}`.
Rust requiere de estos alrededor de todos los cuerpos de una función. Es un buen
estilo colocar el corchete de apertura en la misma línea que la declaración de la
función, agregando un espacio entre ellos.

Si desea usar un estilo estándar en todos los proyectos de Rust, puedes utilizar la
herramienta de formateo automático llamada `rustfmt` para formatear tu código en un
estilo particular. El equipo de Rust ha incluido esta herramienta con la distribución
estándar de Rust, como `rustc`, por lo que ya debería estar instalada en su computadora.
Consulte la documentación en línea para obtener más detalles.

Dentro de la función `main` encontrarás el siguiente código:

```rust
    println!("¡Hola, mundo!");
```

Esta línea hace todo el trabajo en este pequeño programa: imprime texto
en la pantalla. Hay cuatro detalles importatens a tener en cuenta aquí.

En primer lugar, el estilo de Rust es sangrar con cuatro espacios, no una tabulación.

En segudo lugar, `println!` llama una macro de Rust. Si en lugar de eso llamara
una función, tendría que ser escrito como `println` (sin el `!`). Hablaremos con
más detalle sobre las macros de Rust en el Capítulo 19. Por ahora, solo necesitas
saber que usando un `!` significa que estás llamando una macro en lugar de una
función normal.

En tercer lugar, verá el mensaje `"¡Hola, mundo!"`. Pasamos este texto como un
argumento a `println!`, y el texto se imprime en la pantalla.

Por último, terminamos la línea con un punto y coma (`;`), el cual indica que esta
expresión ha terminado y la siguiente está lista para comenzar. La mayoría de las
líneas de código de Rust terminan con un punto y coma.

### Compilar y Ejecutar Son Pasos Separados

Acabas de ejecutar un programa recién creado, así que miremos cada paso del proceso.

Antes de ejecutar un programa de Rust, debes compilarlo usando el compilador de Rust
ingresando el comando `rustc` y pasándole el nombre del archivo, algo como esto:

```console
$ rustc main.rs
```

Si tienes experiencia en C o C++, notarás que es muy similar a `gcc` o `clang`.
Después de compilar con éxito, Rust genera un ejecutable binario.

En Linux, macOS y PowerShell en Windows, puede ver el ejecutable ingresando el
comando `ls` en la consola. En Linux y macOS, verá dos archivos. Con PowerShell
en Windows, verá los mismos tres archivos que vería usando CMD.

```console
$ ls
main  main.rs
```

Con CMD en Windows, debes ingresar lo siguiente:

```cmd
> dir /B %= la opción /B dice que solo se muestren los nombres de archivo =%
main.exe
main.pdb
main.rs
```

Esto muestra el archivo de código fuente con la extensión *.rs*, el archivo
ejecutable (*main.exe* en Windows, pero *main* en las demás plataformas) y,
cuando se usa Windows, un archivo que contiene información de depuración con
extensión *.pdb*. Desde aquí, ejecuta el archivo *main* o *main.exe*, así:

```console
$ ./main # o .\main.exe en Windows
```

Si *main.rs* es su programa “¡Hola, mundo!”, esta línea imprimiría `¡Hola,
mundo!` en la consola.

Si estás más familiarizado con un lenguaje dinámico, como Ruby, Python o
JavaScript, posiblemente no estés acostumbrado a compilar y ejecutar un
programa con pasos separados. Rust es un lenguaje *compilado con anticipación*,
lo que significa que puede compilar un programa y darle el ejecutable a otra
persona, y ellos pueden ejecutarlo incluso sin tener Rust instalado. Si le da
a alguien un archivo *.rb*, *.py* o *.js*, debe tener instalada una implementación
de Ruby, Python o JavaScript (respectivamente). Pero en esos lenguajes, solo
necesita un comando para compilar y ejecutar su programa. Todo es una compensación
en el diseño del lenguaje.

Solo compilar con `rustc` está bien para programas simples, pero a medida
que su proyecto crezca, querrá administrar todas las opciones y facilitar el
intercambio de su código. A continuación, le presentaremos la herramienta Cargo,
que le ayudará a escribir programas de Rust en un entorno real.

[troubleshooting]: ch01-01-installation.html#solución-de-problemas
