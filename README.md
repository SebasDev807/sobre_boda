# Invitación de Boda Digital - Edwin & Vaneza 💍

Esta es una aplicación web interactiva desarrollada con **Astro** para la invitación digital de una boda. Diseñada con un enfoque moderno, elegante y "mobile-first", proporciona a los invitados toda la información necesaria para el gran día a través de una experiencia fluida e interactiva.

## 🌟 Características Principales

- **Invitaciones Personalizadas**: El enlace de la invitación puede recibir parámetros por URL para personalizar el saludo, los cupos y el número de mesa del invitado (ej: `?invitado=Familia%20Perez&cupos=3&mesa=4&g=M`).
- **Sobre Interactivo**: Al abrir la aplicación, los invitados son recibidos con una animación de un sobre sellado que se abre al hacer clic, desplegando el resto de las secciones.
- **Scroll Suave (Scroll Snap)**: Las distintas secciones de información están diseñadas para ajustarse perfectamente a la pantalla mediante CSS Scroll Snap, haciendo el desplazamiento mucho más cómodo y guiado en dispositivos móviles.
- **Cuenta Regresiva**: Un temporizador dinámico que muestra los días, horas, minutos y segundos restantes para el momento de la boda.
- **Detalles del Evento e Itinerario**:
  - Ubicación integrada con **Google Maps** (Villa del Carmen, Popayán) para una navegación directa mediante el botón de "Cómo Llegar".
  - Línea de tiempo (Itinerario) con los momentos clave de la celebración (ceremonia, cóctel, cena, hora loca, etc.).
  - Detalles de la fiesta (código de vestimenta y sugerencia de regalos).
- **Interacción Adicional**:
  - Sección para compartir fotografías del evento.
  - Formulario/Botón para confirmar asistencia (RSVP).

## 🛠️ Tecnologías Utilizadas

- **[Astro](https://astro.build/)**: Framework web para generar sitios rápidos y ligeros.
- **HTML, CSS, JavaScript (Vanilla)**: Construcción de componentes, animaciones e interacciones fluidas sin depender de librerías pesadas.
- **Google Fonts & Material Symbols**: Tipografía elegante (Cormorant Garamond, Montserrat) e íconos modernos.

## 🚀 Cómo ejecutar el proyecto localmente

Este proyecto utiliza Node.js y tu gestor de paquetes preferido (`npm`, `pnpm` o `yarn`).

1. **Instalar dependencias:**
   ```bash
   npm install
   ```
2. **Iniciar el servidor de desarrollo:**
   ```bash
   npm run dev
   ```
   *El servidor local estará disponible en `http://localhost:4321`.*

3. **Construir para producción:**
   ```bash
   npm run build
   ```

## 🔗 Parámetros de URL admitidos

Puedes probar la personalización de la invitación agregando los siguientes query parameters a la URL (por ejemplo: `http://localhost:4321/?invitado=Daniela&g=F&cupos=2&mesa=5`):

- `invitado` (**obligatorio**): Nombre del invitado o familia (ej. "Daniela", "Familia López"). Si este parámetro falta, se muestra un error amigable y el sobre queda bloqueado.
- `g`: Tratamiento. Acepta `M` (Sr.), `F` (Sra.) o `FM` (Familia). **Por defecto es `M` (Sr.)** si no se especifica.
- `cupos`: Cantidad de puestos reservados para ese invitado.
- `mesa`: Número de la mesa asignada en la recepción.

