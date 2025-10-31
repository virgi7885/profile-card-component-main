# 🌟 Tarjeta de Perfil - Solución con Tailwind CSS

Esta es una solución al desafío "Tarjeta de Perfil" del Desafío de Frontend Mentor.

## 🔗 Enlaces

* **URL de la Solución Live:** https://virgi7885.github.io/profile-card-component-main/
* **Repositorio GitHub:** (https://github.com/virgi7885)
* **Página del Desafío:** https://www.frontendmentor.io/challenges/profile-card-component-cfArpWshJ

---

## 💻 El Desafío

El objetivo era construir la maquetación y lograr que se viera lo más parecido posible al diseño original.

### 🛠️ Herramientas Usadas

* **HTML5**
* **Tailwind CSS v4** (Adaptación)
* **PostCSS** (Para procesar Tailwind)
* **[Otras herramientas, ej. Git, VS Code]**

---

## 🎨 Proceso de Adaptación a Tailwind CSS

El diseño original estaba destinado a ser completado usando CSS nativo. Mi enfoque fue adaptarlo completamente a un flujo de trabajo moderno utilizando Tailwind CSS, lo cual mejoró la velocidad y la mantenibilidad del código.

### 1. Configuración Inicial y Colores

Adapté la guía de estilo de Frontend Mentor usando la directiva **`@theme`** (para Tailwind v4) en mi archivo `app.css`.

* **Colores Personalizados:** Definí los tokens para el color de fondo principal y los colores de texto y *hover* directamente en el `@theme`.
    ```css
    @theme {
      --color-primary-blue: #19a7ae;
      --color-primary-gray: #6b7280; 
      /* ... otros colores ... */
    }
    ```

### 2. El Desafío del Fondo (Background)

El principal reto fue lograr que las dos burbujas gigantes de fondo se mantuvieran fijas en las esquinas y se ajustaran al tamaño del dispositivo sin usar elementos `<img>`.

**❌ Intento Fallido (Solución Pura CSS):** Inicialmente intenté definir las imágenes de fondo en el `<main>` usando `background-image` y `background-position`. El control de la posición compleja (`top -500px, left -250px`) fue difícil de manejar y ajustar a diferentes tamaños.

**✅ Solución Exitosa (Adaptación con Elementos `<img>` y Posicionamiento Absoluto):**

Decidí usar etiquetas `<img>` simples para las burbujas y las posicioné de forma absoluta con respecto al contenedor principal (`<main>`).

* **Contenedor de Anclaje:** El elemento `<main>` se configuró como **`relative`** (`class="relative w-full h-screen..."`) para establecer un contexto.
* **Posicionamiento de Burbujas:** Las imágenes se colocaron con la clase **`absolute`** y valores fijos grandes y negativos para empujarlas fuera del `main`, creando la ilusión de que provienen de la esquina.
    ```html
    <img class="absolute left-[-250px] top-[-500px] w-[970px] h-[970px]" ...>
    ```

### 3. Maquetación y Centrado de la Tarjeta

* **Centrado de la Página:** Usé las utilidades de Flexbox en el `<body>` y `<main>` para centrar la tarjeta vertical y horizontalmente: `min-h-screen flex items-center justify-center`.
* **Diseño de la Tarjeta:** La estructura interna de la tarjeta (`<article>`) se manejó con las utilidades estándar de Tailwind (bordes redondeados, sombras, *padding*). La fila de estadísticas se construyó fácilmente con `flex place-content-around`.

---

## 🚀 Lo que Aprendí

* **Dominio de `position: absolute` vs. `background-image`:** Reforcé que para un control total y un posicionamiento independiente, la mejor práctica es usar elementos HTML posicionados de forma absoluta en lugar de propiedades de `background-image` complejas.
* **Aprovechamiento de los Tokens de Tailwind v4:** La capacidad de definir estilos complejos como las coordenadas del fondo con `@theme` acelera el desarrollo, manteniendo el CSS base limpio y listo para ser utilizado en cualquier parte del HTML.

---

## ✍️ Autor

* **Virgi7885** - (https://www.frontendmentor.io/profile/virgi7885)