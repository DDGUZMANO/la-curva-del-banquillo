# 🏗️ Arquitectura de *La Curva del Banquillo*

## 📌 Descripción General
*La Curva del Banquillo* es una plataforma de estadísticas y análisis de fútbol que integra:
- Un módulo de visualización de estadísticas de jugadores.
- Una sección de trivia dinámica con preguntas generadas por Llama2.
- Un sistema de predicción de lesiones basado en modelos de Machine Learning.

El proyecto combina backend en Python, base de datos relacional, un microservicio de ML y una capa frontend ligera.

---

## 🧩 Componentes Principales

### 🎨 **Frontend**
- HTML, CSS, JavaScript  
- Interfaz de usuario para:
  - Consultar estadísticas  
  - Jugar el quiz  
  - Ingresar datos para predicciones  
- Consume la API vía fetch/axios

---

### 🔧 **Backend (API REST en Python)**
- **FastAPI** (o Flask)  
- Expone endpoints para:
  - Gestión de jugadores  
  - Estadísticas  
  - Solicitudes del quiz  
  - Envío de datos al modelo de ML  
- Manejo de autenticación (en fases avanzadas)
- Conversión de datos entre capas (DTOs / Pydantic models)

---

### 💾 **Base de Datos (MySQL)**
Tablas principales:
- Jugadores  
- Estadísticas  
- Historial de lesiones  
- Resultados del quiz (opcional)  

El backend accede a la base de datos usando SQLAlchemy u otro ORM.

---

### 🤖 **ML Service (Microservicio de Machine Learning)**
- Implementado en Python con **scikit-learn**
- Modelo: **Random Forest** o Árboles de Decisión
- Funciones:
  - Recibe datos del jugador
  - Calcula:
    - Probabilidad de lesión en los próximos 3 meses
    - Número estimado de lesiones en la temporada
  - Devuelve los resultados al backend

Se despliega como un servicio independiente (`api_service.py`).

---

### 🧠 **Integración con Llama2**
- API externa que genera:
  - Preguntas dinámicas
  - 4 opciones de respuesta
  - La respuesta correcta
- El backend formatea las preguntas y las entrega al frontend para el juego.

---

## 🔄 Flujo de Datos (Paso a Paso)

1. **El usuario interactúa con el frontend**  
   Navega entre estadísticas, el quiz o el sistema de predicción.

2. **El frontend envía una solicitud a la API (backend)**  
   Ejemplos:  
   - `GET /players/123`  
   - `GET /quiz/generate`  
   - `POST /predict-injury`

3. **El backend procesa la solicitud**
   - Consulta MySQL  
   - Llama al microservicio de ML si es una predicción  
   - Llama a Llama2 para generar preguntas del quiz

4. **Procesamiento interno**
   - El ML service analiza los datos  
   - Llama2 genera pregunta + opciones  
   - El backend valida y arma la respuesta final

5. **La API responde al frontend**
   - JSON con la información solicitada

6. **El frontend muestra el resultado al usuario**
   - Tablas, gráficos, tarjetas, preguntas o predicciones

---

## 🧱 Diagrama

```text
                        ┌───────────────────────────┐
                        │         FRONTEND          │
                        │  HTML / CSS / JavaScript  │
                        │  - Trivia UI              │
                        │  - Stats dashboard        │
                        │  - Player profiles        │
                        └─────────────┬─────────────┘
                                      │
                                      ▼
                        ┌───────────────────────────┐
                        │          BACKEND          │
                        │        Laravel API        │
                        │ - /players                │
                        │ - /quiz                   │
                        │ - /predict-injury         │
                        └─────────────┬─────────────┘
                                      │
                 ┌────────────────────┼────────────────────┐
                 │                    │                    │
                 ▼                    ▼                    ▼
     ┌──────────────────┐   ┌──────────────────┐   ┌─────────────────────┐
     │      MySQL       │   │    ML SERVICE    │   │   Llama2 Service     │
     │ - jugadores      │   │  Python + SKLearn│   │  (local o nube)      │
     │ - lesiones       │   │  Random Forest   │   │ - genera preguntas   │
     │ - estadísticas   │   │ - predicción     │   │ - textos dinámicos   │
     └──────────────────┘   └──────────────────┘   └─────────────────────┘

                                      │
                                      ▼
                         ┌────────────────────────────┐
                         │         RESPUESTA          │
                         │ JSON → Frontend UI render  │
                         └────────────────────────────┘
