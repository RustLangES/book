## Instalación

El primer paso es instalar Rust. Lo descargaremos a través de `rustup`, una
herramienta en la línea de comandos para administrar las versiones de Rust y
herramientas asociadas. Necesitarás estar conectado a internet para la descarga.

> Nota: Si prefieres no usar `rustup` por alguna razón, por favor mira [la página
> de instalación de Rust](https://www.rust-lang.org/tools/install) para ver
> más alternativas.

Los siguientes pasos instalan la última versión estable del compilador de Rust.
Las garantías de estabilidad de Rust aseguran que todos los ejemplos del libro
que son compilados continuarán compilándose con las versiones más recientes de Rust.
El resultado puede ser ligeramente diferente entre versiones porque a menudo
Rust mejora los mensajes de error y advertencias. En otras palabras, cualquier
versión más nueva y estable de Rust que instale siguiendo estos pasos debería
funcionar como se esperaba en el contenido de este libro.

> ### Notas importantes de la Línea de Comandos
>
> En este capítulo y a lo largo del libro, estaremos mostrando algunos comandos
> usados en la consola. Todas las líneas que debes ingresar en una consola empezarán
> con `$`. No necesitas ingresar el caracter `$` en la consola; este solo indica el
> inicio de cada comando. Las líneas que no empiezan con `$` suelen mostrar el
> resultado de un comando ejecutado anteriormente. Adicional a esto, los ejemplos
> específicos para PowerShell usarán `>` en lugar de `$`.

### Instalando `rustup` en Linux o macOS

Si estás usando Linux o macOS, abre una consola e ingresa el siguiente comando:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

El comando descarga un script e inicia la instalación de la herramienta `rustup`,
que instala la última versión estable de Rust. Es posible que solicite su
contraseña. Si la instalación es exitosa, aparecerá la siguiente línea:

```text
Rust is installed now. Great!
```

Adicionalmente, necesitarás algún tipo de vinculador. Es probable que ya haya uno
instalado, pero cuando intentes compilar un programa de Rust y obtengas
errores que indiquen que no se pudo ejecutar un vinculador, significa que
no hay un vinculador instalador en tu sistema y tendrás que instalar uno
manualmente. Los compiladores de C generalmente vienen con el enlazador
correcto. Consulte la documentación de su plataforma para saber cómo instalar
un compilador de C. Además, algunos paquetes comunes de Rust dependen del
código de C y necesitarán un compilador de C. Por lo tanto, podría valer la
pena instalar uno ahora.

### Instalando `rustup` en Windows

En Windows, ve a [https://www.rust-lang.org/tools/install][install] y sigue las
instrucciones para instalar Rust. En algún punto de la instalación recibirás
un mensaje explicando que necesitarás las herramientas de compilación de C++
para Visual Studio 2013 o superior. La forma más fácil de adquirir las
herramientas de compilación es instalar [las Herramientas de Compilación
para Visual Studio 2019][visualstudio]. Cuando se le pregunte qué cargas de
trabajo instalar, asegúrese de seleccionar "Herramientas de compilación de C++"
y de que se incluyan el SDK de Windows 10 y los componentes del paquete del
idioma inglés.

[install]: https://www.rust-lang.org/tools/install
[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

El resto de este libro usa comandos que funcionan en *cmd.exe* y PowerShell.
Si hay una diferencia importante se explicará cuál usar.

### Actualización y Desinstalación

Después de haber instalado Rust a través de `rustup`, actualizar a la última
versión es fácil. En tu consola ejecuta el siguiente script:

```console
$ rustup update
```

Para desinstalar Rust y `rustup`, ejecute el siguiente comando de desinstalación:

```console
$ rustup self uninstall
```

### Solución de Problemas

Para verificar si tiene Rust instalado correctamente, abra la consola e ingrese
esta línea:

```console
$ rustc --version
```

Debería ver el número de versión, el hash de confirmación y la fecha de
confirmación de la última versión estable que se ha lanzado en el siguiente
formato:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Si ve esta información, ¡ha instalado Rust correctamente! Si no ve esta información
y está en Windows, verifique que Rust esté en su variable de sistema `%PATH%`. Si
todo es correcto y Rust aún no funciona, hay varios lugares en los que puede obtener
ayuda. El más fácil es el canal #beginners en [el Discord oficial de Rust][discord].
Allí, puedes hablar con otros rustáceos (un apodo con el que nos llamamos a nosotros
mismos) que pueden ayudarte. Otros recursos excelentes son [el foro de Usuarios][users]
y [Stack Overflow][stackoverflow].

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

### Documentación Local

La instalación de Rust también incluye una copia de la documentación de manera
local, entonces puedes leerla sin conexión a internet. Ejecuta `rustup doc` para
abrir la documentación local en tu buscador predeterminado.

Siempre que la librería estándar proporcione un tipo o función y no esté seguro
de qué hace o cómo usarlo, utilice la documentación de la interfaz de programación
de aplicaciones (API) para averiguarlo.
