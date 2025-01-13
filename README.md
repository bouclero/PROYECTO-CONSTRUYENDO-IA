##Resumen
# Proyecto de curso de creación de IA

# Iluminación Inteligente con IA

## Introducción
- La iluminación es un elemento clave para el confort y la eficiencia energética.
- La IA permite personalizar y automatizar la iluminación según hábitos y contexto.
- Uso de aprendizaje automático (ML) y procesamiento de lenguaje natural (PLN) para optimizar la experiencia.

## Objetivos
1. **Automatización**: Ajuste automático basado en condiciones ambientales y preferencias del usuario.
2. **Ahorro energético**: Reducción del consumo a través de optimización inteligente.
3. **Interacción natural**: Control mediante comandos de voz con PLN.

## Funcionalidades

### Sensores y Actuadores
- **Sensores utilizados**:
  - Movimiento: Detección de presencia en la habitación.
  - Luminosidad: Detectar niveles de luz natural.
  - Temperatura: Adaptación a climas fríos o cálidos.
- **Actuadores**:
  - Reguladores de intensidad de bombillas LED.
  - Control de colores RGB en luces inteligentes.
  - Interruptores inteligentes conectados.

### Aprendizaje Automático (ML)
1. **Análisis de patrones**:
   - Recopilación de datos sobre horarios y uso de habitaciones.
   - Modelos de clasificación (ej. árboles de decisión) para predecir uso.
2. **Modelos dinámicos**:
   - Entrenamiento continuo para adaptarse a cambios en los hábitos del usuario.
   - Ajustes según estaciones del año o las horas del dia
3. **Predicción de estados**:
   - Activar luces antes de la llegada del usuario (geolocalización via movil conectado al sistema)
   - Detectar si la persona está leyendo, descansando o trabajando para ajustar la luz.

### Procesamiento de Lenguaje Natural (PLN)
- **Comandos de voz**:
  - "Pon luz cálida en el salón."
  - "Apaga todas las luces de la casa."
  - "Cambia la luz del dormitorio a azul."
- **Implementación con herramientas**:
  - Uso de modelos como `Whisper` para transcripción.
  - Integración con asistentes de voz Google Assistant.
- **Conversaciones contextuales**:
  - Usuario: "¿Está encendida la luz del baño?"
  - Sistema: "No, pero puedo encenderla si quieres."

### Modos de Iluminación Inteligente
- **Automático**:
  - Basado en sensores y aprendizaje automático.
- **Manual**:
  - Control mediante app móvil o comandos de voz.
- **Escenas predefinidas**:
  - Modo lectura: Luz blanca cálida, intensidad media.
  - Modo fiesta: Iluminación RGB cambiante.

## Implementación Técnica

### Requisitos
1. Hardware:
   - Bombillas inteligentes compatibles (Philips Hue, Yeelight, etc.).
   - Sensores IoT (luminosidad, movimiento, temperatura).
   - Raspberry Pi para centralizar la automatización.
2. Software:
   - Biblioteca Python `phue` para control de luces.
   - Framework de PLN como `spaCy` o `transformers`.
   - Algoritmos de ML como `scikit-learn`.

### Ejemplo de Código: Aprendizaje Automático para Predicción de Uso
```python
import numpy as np
from sklearn.tree import DecisionTreeClassifier
from datetime import datetime

# Datos de ejemplo: Hora del día, día de la semana, estado (0: apagado, 1: encendido)
datos = [
    [8, 1, 1], [20, 1, 1], [23, 1, 0],  # Día laboral
    [9, 6, 1], [22, 6, 1], [1, 6, 0]   # Fin de semana
]

# Separar características y etiquetas
X = np.array([fila[:2] for fila in datos])
y = np.array([fila[2] for fila in datos])

# Modelo de decisión
modelo = DecisionTreeClassifier()
modelo.fit(X, y)

# Predicción: ¿Encender la luz un sábado a las 21:00?
hora = datetime.now().hour
dia_semana = datetime.now().weekday() + 1  # 1: lunes, 7: domingo
prediccion = modelo.predict([[hora, dia_semana]])

print("¿Encender luz?:", "Sí" if prediccion[0] == 1 else "No")

### Ejemplo de Código: Detector de intrusos
  def detect_intruder(sensor_data):
    if sensor_data == "motion_detected":
        print("Intruso detectado. Enviando alerta.")
        send_alert()

def send_alert():
    print("Alerta enviada al propietario y a las autoridades.")

# Simulación de datos del sensor
sensor_data = "motion_detected"
detect_intruder(sensor_data)

### Ejemplo de Código: Aplicacion uso en electrodomesticos
def optimize_appliances(usage_data):
    if usage_data["time"] > 22 or usage_data["time"] < 6:
        print("Reduciendo el consumo de energía en modo nocturno.")
        reduce_energy_usage()

def reduce_energy_usage():
    print("Electrodomésticos en modo de bajo consumo.")

# Simulación de datos de uso
usage_data = {"time": 23}
optimize_appliances(usage_data)


