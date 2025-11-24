# Integración de Llama2 para Trivia

## Propósito
Generar preguntas dinámicas de trivia sobre fútbol y deporte.

## Flujo
1. Frontend envía request al backend.
2. Backend llama a Llama2 con prompt específico.
3. Llama2 devuelve pregunta + 4 opciones.
4. Backend envía la respuesta al frontend.

## Tecnologías
- FastAPI (o Flask) para backend
- API / servicio local Llama2 (Ollama / LM Studio)
- JSON como formato de comunicación
