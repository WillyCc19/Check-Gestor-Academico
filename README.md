<div align="center">

# ✅ Check! — Gestor Académico

### Organiza tus tareas y lleva el control de tus calificaciones en un solo lugar.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Proyecto académico de desarrollo web con Python y Flask.**

</div>

---

## 📖 Descripción

**Check!** es una aplicación web orientada a la organización académica. Permite **registrar cursos y tareas**, consultar o eliminar pendientes y **llevar un control de las calificaciones mediante una calculadora de promedio ponderado**. Su interfaz integra páginas HTML con estilos CSS y un backend desarrollado con Flask.

El proyecto permite aplicar conceptos de programación en Python, manejo de formularios, rutas web, plantillas dinámicas y comunicación entre cliente y servidor.

## ✨ Funcionalidades principales

| Módulo | ¿Qué permite hacer? |
| --- | --- |
| 📚 **Cursos y tareas** | Registrar el nombre de un curso junto con la descripción de una tarea. |
| 📝 **Lista de pendientes** | Visualizar las tareas registradas y eliminarlas. |
| 🔎 **Consulta dinámica** | Recuperar las descripciones de tareas a través de un endpoint JSON. |
| 🧮 **Calculadora de notas** | Ingresar calificaciones sobre 20 y sus respectivos porcentajes de evaluación. |
| 📊 **Promedio ponderado** | Calcular y mostrar automáticamente la suma ponderada de las notas registradas. |
| 🗑️ **Edición de notas** | Eliminar una calificación y actualizar el promedio mostrado. |
| 🏠 **Página de inicio** | Presentar el proyecto y acceder a sus distintos módulos. |

## 🛠️ Tecnologías utilizadas

| Tecnología | Uso en el proyecto |
| --- | --- |
| **Python** | Lógica del servidor, registro de datos y cálculos. |
| **Flask** | Rutas HTTP, procesamiento de formularios y respuestas JSON. |
| **HTML5** | Estructura de las páginas y formularios. |
| **CSS3** | Estilos y presentación visual. |
| **JavaScript** | Peticiones `fetch()` para consultar tareas. |
| **Jinja2** | Renderización de las listas y valores desde Flask. |
| **Gunicorn** | Servidor WSGI previsto en la configuración de despliegue (`Procfile`). |

## 🖥️ Vista del proyecto

La aplicación cuenta con una **página de bienvenida**, un **módulo de cursos y tareas** y una **calculadora de promedio ponderado**.

> 📸 **Para añadir capturas reales:** crea la carpeta `capturas/` en el repositorio y descomenta las siguientes líneas después de subir las imágenes con esos nombres.

<!--
### Página de inicio
![Página de inicio](capturas/inicio.png)

### Gestión de tareas
![Gestión de tareas](capturas/tareas.png)

### Calculadora de notas
![Calculadora de notas](capturas/calculadora.png)
-->

## 📁 Estructura del proyecto

```text
ProyectoFundamentos/
├── main.py                         # Aplicación Flask y rutas
├── requirements.txt                # Dependencias Python
├── Procfile                        # Comando para despliegue con Gunicorn
├── runtime.txt                     # Versión de Python declarada
├── templates/
│   ├── pagina1.html                # Página principal
│   ├── pagina2.html                # Gestión de cursos y tareas
│   └── calculadora_notas.html      # Calculadora de promedio
└── static/
    ├── css/                        # Hojas de estilo
    └── imagenes/                   # Recursos gráficos de la web
```

## 🚀 Instalación y ejecución local

**Requisitos:** Python y `pip` instalados.

1. Clona el repositorio y entra a la carpeta del proyecto:

   ```bash
   git clone https://github.com/TU-USUARIO/Check-Gestor-Academico.git
   cd Check-Gestor-Academico
   ```

   > Sustituye `TU-USUARIO` por tu usuario real de GitHub y ajusta el nombre de la carpeta si tu repositorio tiene otro nombre.

2. Crea y activa un entorno virtual:

   **Windows (PowerShell):**
   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   **Linux / macOS:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

4. Inicia la aplicación:

   ```bash
   python main.py
   ```

5. Abre en tu navegador: **http://127.0.0.1:5000/**

## 🌐 Rutas principales

| Método | Ruta | Descripción |
| --- | --- | --- |
| `GET` | `/` | Página de inicio. |
| `GET / POST` | `/pagina2` | Consulta y registro de tareas. |
| `GET` | `/obtener_tareas` | Devuelve las descripciones de tareas en JSON. |
| `POST` | `/eliminar_tarea` | Elimina tareas según su descripción. |
| `GET / POST` | `/calculadora_notas` | Consulta, registro y cálculo de notas. |
| `POST` | `/eliminar_nota` | Elimina una nota por identificador. |
| `GET` | `/obtener_notas` | Devuelve las notas y porcentajes en JSON. |

## 🧮 ¿Cómo funciona el cálculo del promedio?

Cada nota se multiplica por su porcentaje de evaluación. Luego se suman los resultados:

\[
\text{Promedio ponderado} = \sum_{i=1}^{n}\left(\text{Nota}_i \times \frac{\text{Porcentaje}_i}{100}\right)
\]

**Ejemplo:**

| Evaluación | Nota | Peso | Aporte |
| --- | ---: | ---: | ---: |
| Práctica 1 | 16 | 30 % | 4.80 |
| Examen parcial | 14 | 30 % | 4.20 |
| Examen final | 18 | 40 % | 7.20 |
| **Total** | | **100 %** | **16.20** |

**Resultado: 16.20/20**. El programa muestra el cálculo con dos decimales. Si los pesos no suman el 100 %, el código muestra la suma ponderada de los pesos ingresados, sin normalizarlos al 100 %.

## ⚠️ Alcance actual y posibles mejoras

- **Almacenamiento temporal:** las tareas y notas se guardan en listas de Python en memoria; al reiniciar el servidor se pierden los registros.
- **Gestión básica de tareas:** se pueden añadir y eliminar tareas, pero el código aún no incorpora fechas límite ni estados de tarea completada.
- **Validaciones:** existe una validación básica para notas de 0 a 20 y porcentajes de 0 a 100. Se pueden reforzar las validaciones del lado del servidor.
- **Próximas mejoras posibles:** persistencia con una base de datos, edición de tareas, autenticación de usuarios y seguimiento de tareas completadas.

## 🎓 Aprendizajes aplicados

Este proyecto permitió poner en práctica el uso de **rutas y métodos HTTP**, procesamiento de **formularios**, representación dinámica de información con **Jinja2**, manejo de **listas y diccionarios en Python**, generación de **respuestas JSON** y diseño básico de una aplicación web con **Flask**.

---

<div align="center">

**Check! — Organización académica y control de notas en una sola aplicación.** ✅

</div>
