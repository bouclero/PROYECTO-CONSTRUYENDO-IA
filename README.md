# Proyecto: Mejora de la Domótica en Casa con IA

## Introducción
- Implementar IA para optimizar la experiencia en casa.
- Áreas principales:
  - Iluminación inteligente.
  - Música personalizada.
  - Seguridad avanzada.
  - Control de electrodomésticos.

## Iluminación Inteligente
- Detectar la presencia de personas en una habitación.
- Ajustar la intensidad de luz según la hora del día.
- Modos predefinidos:
  - Relajación.
  - Trabajo.
  - Fiesta.
- Integración con asistentes de voz (ej. Alexa, Google Assistant).
- Ejemplo de código en Python:
  ```python
  import time
  from phue import Bridge
  
  # Conexión al puente de Philips Hue
  bridge = Bridge('IP_DEL_BRIDGE')
  bridge.connect()
  
  # Función para ajustar la iluminación
  def ajustar_luz(habitacion, intensidad, color):
      luces = bridge.get_light_objects('name')
      if habitacion in luces:
          luces[habitacion].brightness = intensidad
          luces[habitacion].xy = color  # Coordenadas para color
          print(f"Luz en {habitacion} ajustada a intensidad {intensidad} y color {color}.")
      else:
          print("Habitación no encontrada.")

  # Ejemplo de uso
  ajustar_luz('Sala', 200, [0.5, 0.4])  # Intensidad y color
