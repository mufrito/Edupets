# PROYECTO COMPLETO: EDUPETS

Actúa como un desarrollador Senior Full Stack especializado en FastAPI, Jinja2, autenticación, arquitectura limpia y despliegue en Vercel.

Debes construir desde cero una aplicación web llamada "Edupets", siguiendo estándares profesionales de desarrollo, organización de carpetas, separación de responsabilidades y buenas prácticas.

## Tecnologías obligatorias

* Python 3.12+
* FastAPI[standard]
* Jinja2 Templates
* HTML5
* CSS3
* JavaScript Vanilla
* JWT Authentication
* Google Sheets API como base de datos provisional
* Diseño responsive
* Preparado para despliegue en Vercel

## Objetivo del proyecto

Edupets es una plataforma educativa de matemáticas inspirada en Duolingo donde el estudiante tiene una mascota virtual que debe cuidar mientras avanza en actividades matemáticas.

La mascota tiene estadísticas que disminuyen con el tiempo y el usuario debe completar actividades para ganar monedas y comprar objetos en una tienda.

## Estructura profesional requerida

Genera todo el proyecto organizado así:

edupets/

├── app/
│   ├── main.py
│   ├── config.py
│   ├── dependencies.py
│   │
│   ├── routers/
│   │   ├── auth.py
│   │   ├── pet.py
│   │   ├── activities.py
│   │   ├── shop.py
│   │
│   ├── services/
│   │   ├── google_sheets.py
│   │   ├── auth_service.py
│   │   ├── pet_service.py
│   │   ├── activities_service.py
│   │
│   ├── models/
│   │   ├── user.py
│   │
│   ├── static/
│   │   ├── css/
│   │   │   └── style.css
│   │   │
│   │   ├── js/
│   │   │   ├── app.js
│   │   │   ├── pet.js
│   │   │   ├── activities.js
│   │   │
│   │   └── images/
│   │       ├── comida.png
│   │       ├── felicidad.png
│   │       ├── logo.png
│   │       ├── pet.png
│   │       ├── sueno.png
│   │       ├── vida.png
│   │       └── vidamenos.png
│   │
│   ├── templates/
│   │   ├── base.html
│   │   ├── index.html
│   │   ├── login.html
│   │   ├── register.html
│   │   ├── pet.html
│   │   ├── activities.html
│   │   ├── shop.html
│   │
│   └── utils/
│       ├── security.py
│
├── requirements.txt
├── vercel.json
├── README.md
├── .env.example

## Base de datos provisional

Utilizar Google Sheets como almacenamiento.

URL:

https://docs.google.com/spreadsheets/d/1bRR_985w1aFByMg1GDAAaKnYPOWbqajbYD8btE7zC1k/edit

Columnas:

A = Usuario

B = Contraseña

C = Monedas

D = Felicidad

E = Comida

F = Sueño

G = Nombre

La conexión debe realizarse mediante Google Sheets API.

NO usar scraping.

Explica claramente:

* Cómo obtener credenciales
* Cómo generar service account
* Cómo compartir la hoja con el correo de la cuenta de servicio
* Cómo configurar variables de entorno

## Pantalla inicial

Ruta "/"

Mostrar:

* Logo
* Texto:

"Bienvenido a Edupets"

Dos botones:

* Iniciar sesión
* Registrarse

Diseño moderno inspirado en Duolingo.

## Registro

Campos:

* Usuario
* Contraseña

Al crear una cuenta:

Monedas = 0

Felicidad = 100

Comida = 100

Sueño = 100

Nombre = "Mi Mascota"

Guardar en Google Sheets.

## Inicio de sesión

Implementar:

* JWT
* Cookies seguras
* Middleware de autenticación

Tras iniciar sesión:

Redirigir a la mascota.

## Pantalla principal de mascota

La mascota debe ser el elemento central.

Mostrar:

Imagen:

pet.png

Encima:

Tres esferas circulares.

Felicidad:

* felicidad.png
* porcentaje

Comida:

* comida.png
* porcentaje

Sueño:

* sueno.png
* porcentaje

Las esferas deben tener:

* Animaciones suaves
* Efecto de vaciado
* Actualización visual en tiempo real

Debajo de la mascota:

Nombre editable.

Al modificarlo:

Guardar en la base de datos.

## Degradación de estadísticas

Las estadísticas deben disminuir con el tiempo.

Ejemplo:

Cada minuto:

* Felicidad -1
* Comida -1
* Sueño -1

IMPORTANTE:

NO actualizar Google Sheets constantemente.

Mantener cambios en memoria/localStorage.

Guardar en Google Sheets:

* al cerrar sesión
* al cerrar pestaña
* al salir del sitio

Implementar eventos beforeunload o solución equivalente.

## Lista de tareas

Panel plegable.

Mostrar objetivos.

Ejemplos:

* Completa 5 sumas
* Completa 5 restas
* Completa 5 multiplicaciones

Mostrar progreso.

Al completar objetivos:

Dar monedas.

## Tienda

Crear vista independiente.

Mostrar dos productos:

Pollo

Imagen:

comida.png

Precio:

20 monedas

Efecto:

+20 comida

Juguete

Imagen:

felicidad.png

Precio:

30 monedas

Efecto:

+20 felicidad

Verificar monedas disponibles.

Actualizar mascota.

## Actividades

Debe ser la característica principal.

Inspiración:

Duolingo.

Crear mapa de progreso con niveles.

Módulos:

1. Sumas
2. Restas
3. Multiplicación
4. División

Cada nivel debe:

Generar ejercicios aleatorios.

Mostrar:

Pregunta.

Ejemplo:

7 + 4 = ?

Tres respuestas.

Solo una correcta.

Las otras dos incorrectas.

Orden aleatorio.

## Sistema de vidas

Cada nivel tiene:

3 vidas.

Mostrar usando:

vida.png

Cuando se pierde una:

Reemplazar por:

vidamenos.png

Si vidas = 0:

Regresar automáticamente a la mascota.

## Recompensas

Al completar niveles:

* monedas
* progreso
* tareas

Guardar progreso.

## Diseño

Inspiración visual:

Duolingo.

Color principal:

Azul claro.

Fondos:

Blancos.

Características:

* Sombras suaves
* Bordes redondeados
* Microanimaciones
* Transiciones fluidas
* Responsive
* Sin exceso de efectos
* Estilo profesional

## Seguridad

Implementar:

* Hash de contraseñas
* JWT
* Variables de entorno
* Validaciones
* Protección CSRF cuando aplique

## Despliegue

Generar:

requirements.txt

vercel.json

README.md

Incluir instrucciones completas para desplegar en Vercel.

Explicar:

* Variables de entorno
* Instalación
* Ejecución local
* Producción

## Entrega esperada

Genera el código COMPLETO de todos los archivos.

No generes ejemplos ni pseudocódigo.

Genera una implementación funcional lista para ejecutar.
