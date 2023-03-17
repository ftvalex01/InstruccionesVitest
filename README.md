# InstruccionesVitest

Instrucciones para instalar Vitest:

1- Crea una carpeta para tu proyecto.

2- Abre Visual Studio Code y arrastra la carpeta dentro del editor o ábrela desde la opción de "Open Folder" para asegurarte de estar en la ruta correcta.

3- En la barra superior, selecciona "Terminal" y luego "New Terminal".

En la terminal que se abre, copia y pega el siguiente comando:

4- npm init -y

Una vez que termine el proceso anterior, copia y pega el siguiente comando:

5- npm install -D vitest

Ahora instala Standard JS con el siguiente comando:

6- npm install standard -D

Una vez hecho esto, en la carpeta de tu proyecto deberías tener la siguiente estructura:

- node_modules (una carpeta)
- package-lock.json (un archivo)
- package.json (otro archivo)

Abre el archivo package.json y busca la sección "scripts". Reemplaza el contenido actual por lo siguiente:
8--------------------

"scripts": {
  "test": "vitest",
  "coverage": "vitest run --coverage"
},

--------------------
Justo debajo de donde se encuentra "devDependencies", agrega lo siguiente:
9---------------------

"eslintConfig": {
  "extends": "./node_modules/standard/eslintrc.json"
},

--------------------

Asegúrate de colocar la coma al final de "devDependencies", de lo contrario te dará un error.


--------------------
Si necesitas utilizar Vitest con React, sigue los siguientes pasos:
--------------------

Instala las dependencias necesarias:

1- npm install react react-dom -E
2- npm install @vitejs/plugin-react -D
3- npm install @testing--library/react happy-dom -D

-----------------------

4- Crea un archivo llamado vite.config.js y pega el siguiente contenido:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  test: {
    environment: 'happy-dom'
  }
})

--------------------

Finalmente, actualiza la sección "scripts" del archivo package.json con lo siguiente:

--------------------

"scripts": {
  "dev": "vite",
  "test": "vitest",
  "coverage": "vitest run --coverage"
}

--------------------
¡Listo! Ahora estás listo para utilizar Vitest en tu proyecto.
