# Sistemas Informáticos Industriales

![UPM](https://img.shields.io/badge/UPM-ETSIDI-red)
![Curso](https://img.shields.io/badge/Curso-2026--2027-blue)
![Lenguaje](https://img.shields.io/badge/C-Programming-00599C?logo=c)
![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?logo=ubuntu)
![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?logo=git)

Material docente de la asignatura **Sistemas Informáticos Industriales** de la **Escuela Técnica Superior de Ingeniería y Diseño Industrial (ETSIDI)** de la **Universidad Politécnica de Madrid (UPM)**.

---

## 📖 Descripción

Este repositorio contiene el material utilizado en las prácticas de la asignatura **Sistemas Informáticos Industriales**, incluyendo los guiones y el código de inicio.

El objetivo de la asignatura es introducir en el desarrollo de aplicaciones para sistemas informáticos industriales, haciendo especial énfasis en el uso del lenguaje C y del sistema operativo Linux.

---

## 📚 Wiki

La documentación detallada de cada una de las prácticas se encuentra en la Wiki del repositorio.

➡️ **Acceso a la Wiki:**  
https://github.com/raquelcedazo/sistemas-informaticos-industriales/wiki

---

## 🎓 Profesorado

Asignatura impartida por el **Departamento de Ingeniería Eléctrica, Electrónica, Automática y Física Aplicada** de la **Universidad Politécnica de Madrid**:

- **Raquel Cedazo** *(coordinadora de las prácticas)*
- **David Álvarez**
- **Imanol Izcara**

---

## 🤝 Contribuciones

Este repositorio tiene finalidad exclusivamente docente.

Si detectas algún error o tienes alguna sugerencia de mejora, puedes comunicarlo al profesorado de la asignatura.


# Práctica 1.sii-57552

Juego de tenis para dos jugadores en C++.
Proyecto de la asignatura Sistemas Informáticos Industriales.


## Descripción
Aplicación gráfica de un juego de tenis en modo local para dos jugadores
que comparten teclado y pantalla. El proyecto se irá ampliando a lo largo
de las prácticas de la asignatura.

## Funcionalidades
- Práctica 1: movimiento de la esfera y de las raquetas.
  Se han implementado los métodos Mueve de las clases Esfera y Raqueta.

## Compilación y ejecución
    cd workspace
    mkdir build
    cd build
    cmake ..
    make
    ./tenis
    
# Práctica 2.sii-57552

Primeramente, he creado una nueva rama que se llama práctica 2.

Luego, he completado el archivo logger.cpp para que actúe como el proceso receptor de la información.

El logger se encarga de crear la tubería con nombre (mkfifo), abrirla en modo lectura (open), entrar en un bucle infinito para recibir los datos (read), mostrarlos por la salida estándar y destruirla adecuadamente al terminar (close y unlink). Para que funcione correctamente, debo ejecutarlo siempre antes que el juego.

En Mundo.cpp, he añadido el identificador de la tubería como atributo dentro de la clase Mundo, he configurado la apertura de la tubería en modo escritura dentro de la función Init(), y he programado el envío de datos mediante write en el método OnTimer(), de modo que cada vez que un jugador anota un punto, se transmite su nombre y su puntuación total.

He modificado el archivo CMakeLists.txt incluyendo la directiva add_executable(logger logger.cpp) para compilar el nuevo programa.

Por último, he subido los cambios a Bitbucket desde la rama practica2, y he creado la etiqueta correspondiente al finalizar y fusionado la rama con la principal (master).
