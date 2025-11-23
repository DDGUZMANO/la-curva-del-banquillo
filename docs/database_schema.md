# Esquema de Base de Datos

## Tablas principales

### players
- id (PK)
- nombre
- edad
- peso
- altura
- nacionalidad
- posición

### injuries
- id (PK)
- player_id (FK)
- tipo_lesion
- fecha_inicio
- fecha_fin
- gravedad

### performance
- id (PK)
- player_id (FK)
- partido
- minutos_jugados
- goles
- asistencias
