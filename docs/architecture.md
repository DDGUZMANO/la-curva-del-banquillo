# Arquitectura de La Curva del Banquillo

## Descripción General
La Curva del Banquillo es un proyecto de estadísticas y análisis de fútbol,
que integra una sección de trivia dinámica y predicción de lesiones basada en ML.

## Componentes Principales
- **Frontend**: HTML, CSS, JS, interacción con el usuario.
- **Backend**: PHP 8+, endpoints REST para jugadores, quiz y predicción.
- **Base de datos**: MySQL, almacena jugadores, lesiones, estadísticas.
- **ML Service**: Python + scikit-learn, Random Forest para predicción de lesiones.
- **Llama2 Integration**: Generación de preguntas dinámicas para el quiz.

## Flujo de Datos
1. Usuario accede al frontend.
2. Frontend consulta API del backend.
3. Backend obtiene datos de DB o llama al ML / Llama2.
4. Respuesta se devuelve al usuario.
