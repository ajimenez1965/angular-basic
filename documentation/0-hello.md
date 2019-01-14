title: 0-Hello
class: animation-fade
layout: true

.bottom-bar[
{{title}}
]

---

class: impact

# {{title}}

## Hola Angular CLI

---

# 1. Angular y el CLI

# 2. Estructura de una aplicación Angular

# 3. Configuración

# 4. Angular y su ecosistema

---

class: impact

# 1 Angular y el CLI

## Instalación de Angular CLI 7

## Crear y ejecutar aplicaciones Angular

---

## 1.1 Instalación de Angular CLI 7

> Angular es una plataforma de desarrollo dogmática y llave en mano.

Necesitarás [NodeJS](https://nodejs.org/en/) y su manejador de de paquetes _npm_.

```console
node -v
```

Instrucciones para instalar angular cli.

```console
*$ npm i -g @angular/cli@latest
$ ng version
$ ng help
$ ng new --help
```

---

## 1.2. Crear y ejecutar aplicaciones Angular

-   Configuración que viene por defecto,

-   Soluciones a medida.

> Para más información mira la documentación del comando [ng new](https://angular.io/cli/new).

---

### 1.2.1 Normal

```console
ng new normal
```

--

### 1.2.2 Minimalista

```console
ng new minimalista -s -S -t
```

--

### 1.2.3 Profesional

```console
ng new profesional -p acme --routing true
```

---

### 1.2.4 Empresarial

```console
ng new empresarial --create-application false
cd empresarial
ng generate application compras -p acme --routing true
```

--

### 1.2.5 Angular Board

La aplicación que sirve de ejemplo a este tutorial fue creada con este comando:

```console
ng new angular-board --routing true -s -S
```

---

> Recap:

# 1 Angular y el CLI

## Instalación de Angular CLI 7

## Crear y ejecutar aplicaciones Angular

---

class: impact

# 2. Estructura de una aplicación Angular

## Ficheros y carpetas principales

## Edición de un Hola Mundo

---

## 2.1 Ficheros y carpetas principales

-   **angular.json** _: configuración del propio CLI. La madre de todos los configuradores_
-   **package.json** _: dependencias de librerías y scripts_
-   **src/** _: la carpeta donde están los archivos fuentes_
    -   **index.html** _: un fichero HTML índice estándar_
    -   **main.ts** _: fichero TypeScript de arranque de la aplicación_
    -   **app/** _: la carpeta con el código específico de tu aplicación_
        -   **app.module.ts** _: la aplicación es un árbol de módulos, y este es su raíz_
        -   **app.component.ts** _: la página es un árbol de componentes, y este es su raíz_
        -   **app.component.html** _: el componente tiene una parte visual, esta es su vista_

---

## 2.2. Edición

### 2.2.1 `npm start`

1. `npm start`
2. `ng serve`
3. **webpack** server en http://localhost:4270
    1. vigilancia de cambios sobre la carpeta `src/`
    2. _live reload_
    3. compilado de la aplicación
    4. recarga del navegador

---

### 2.2.2 Edición de un Hola Mundo

**cambiar un fichero de código y comprobar el resultado** en el navegador.

1. Abre el fichero `app.component.ts`
2. Busca dentro de él una clase llamada `AppComponent`.
3. Asígnale el saludo de rigor: `title = 'actibot: hello world ;-)';`.
4. Guarda y comprueba cómo tu navegador **se habrá actualizado automáticamente**.

---

> Recap:

# 2. Estructura de una aplicación Angular

## Ficheros y carpetas principales

## Edición de un Hola Mundo

---

class: impact

# 3. Configuración

## Configurar el CLI

## Configurar el Workflow

## Configurar la aplicación

---

## 3.1 Angular.json

-   Configuración Multi proyecto propia de angular.
-   Rutas y configuraciones básicas para entornos de compilación y despliegue

## 3.2 Package.json

-   Dependencias en ejecución y para desarrollo
-   Scripts de ayuda

## 3.3 Environment

-   Usadas en tiempo de ejecución
-   Valores distintos por entorno

---

### Ejemplo Angular.json

Instalación de un producto de terceros

```console
npm install mini.css --save
```

Configuración en `angular.json`

```json
{
    "styles": [
        "src/styles.css",
*       "./node_modules/mini.css/dist/mini-default.min.css"
    ]
}
```

---

### Ejemplo Package.json

```json
{
    "scripts": {
    "build:doc": "cd ./documentation/ && bs e -o ../docs/readme",
    "build:prod": "ng build --prod",
    "build:pub": "ng build --prod --output-path docs --base-href https://academiabinaria.github.io/ActiBot/",
    "e2e": "ng e2e",
    "http-server": "http-server ./dist/actibot/ -c-1 -p4271 -a localhost -o",
    "lint": "ng lint",
    "ng": "ng",
    "pub:doc": "npm run build:doc && npm run push",
    "pub": "npm run build:pub && npm run build:doc && npm run push",
    "push": "git add * && git commit -m 'pub' && git push",
    "start:doc": "cd ./documentation/ && bs s",
    "start:prod": "npm run build:prod && npm run http-server",
*   "start": "ng serve --aot -o --port 4270",
    "test": "ng test"
  }
}
```

---

### Ejemplo Environments

```typescript
export const environment = {
    appName: 'Actibot',
    production: false
};
```

```typescript
title = environment.appName + 'hello world ;-)';
```

--

### Ejemplo Assets

```html
<img width="100" src="./assets/logo.png" />
```

---

> Recap:

# 3. Configuración

## Configurar el CLI

## Configurar el Workflow

## Configurar la aplicación

---

class: impact

# 4. Angular y su ecosistema

## Extensiones de Visual Studio

## Configurar Prettier

## Ecosistema de terceros

---

## 4.1. Extensiones de Visual Studio

-   [Extensiones Esenciales](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials)
-   [Prettier](https://prettier.io/)

---

## 4.2 Configurar Prettier

### Prettier.config.js

```js
module.exports = {
    printWidth: 100,
    tabWidth: 2,
    useTabs: false,
    semi: true,
    singleQuote: true,
    trailingComma: 'none',
    bracketSpacing: true,
    jsxBracketSameLine: false,
    arrowParens: 'avoid',
    rangeStart: 0,
    rangeEnd: Infinity,
    requirePragma: false,
    insertPragma: false,
    proseWrap: 'preserve'
};
```

---

## 4.3 Ecosistema de terceros

-   [Angular Console](https://angularconsole.com/)
-   [Angular Material](https://material.angular.io/)

---

> Recap:

# 4. Angular 7, el CLI 7 y su ecosistema

## Extensiones de Visual Studio

## Configurar Prettier

## Ecosistema de terceros