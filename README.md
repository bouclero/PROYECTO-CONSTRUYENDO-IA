# PROYECTO-CONSTRUYENDO-IA
Soluciones actuales con IA para problemas de la vida real
# Proyecto de Domótica Inteligente

## Resumen

Este proyecto tiene como objetivo mejorar la domótica en el hogar mediante el uso de inteligencia artificial para crear un sistema de hogar inteligente. La IA gestionará diversas tareas domésticas, optimizará el uso de energía y mejorará la seguridad, haciendo la vida diaria más conveniente y eficiente.

## Antecedentes

El proyecto de domótica inteligente aborda varios problemas comunes en el hogar:
* Ineficiencia energética y altas facturas de servicios públicos
* Preocupaciones de seguridad y la necesidad de monitoreo constante
* La incomodidad de gestionar múltiples dispositivos manualmente

La motivación personal proviene del deseo de crear un entorno de vida más sostenible y seguro. Este tema es importante ya que utiliza la IA para mejorar la vida diaria, reducir el consumo de energía y mejorar la seguridad del hogar.

## ¿Cómo se usa?

El sistema de domótica inteligente está diseñado para usarse en entornos residenciales para automatizar y optimizar diversas funciones del hogar. Se puede usar en las siguientes situaciones:
* Automatización de sistemas de iluminación, calefacción y refrigeración según la ocupación y la hora del día
* Monitoreo de cámaras de seguridad y envío de alertas sobre actividades inusuales como aumento % humedad;aumento de temperatura o falta de suministro electrico
* Gestión de electrodomésticos inteligentes para reducir el consumo de energía

### Usuarios y Necesidades

Los usuarios principales de este sistema son propietarios y arrendatarios que buscan comodidad, eficiencia energética y seguridad mejorada. El sistema debe ser fácil de usar, personalizable y capaz de aprender las preferencias del usuario con el tiempo.

### Imágenes

![Hogar Inteligente](https://upload.wikimedia.org/wikipedia/commons/e/e4/Smart_Home_Technology.jpg)

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e4/Smart_Home_Technology.jpg" width="300">

### Ejemplo de Código

Aquí tienes un ejemplo sencillo de cómo la IA podría gestionar la iluminación inteligente:

```python
def main():
    habitaciones = ['Sala de estar', 'Cocina', 'Dormitorio', 'Baño']
    ocupacion = [True, False, True, False]  # Ejemplo de estado de ocupación
    estado_luz = [False, False, False, False]  # Estado inicial de la luz

    for i in range(len(habitaciones)):
        if ocupacion[i]:
            estado_luz[i] = True
            print(f"Encendiendo la luz en la {habitaciones[i]}.")
        else:
            estado_luz[i] = False
            print(f"Apagando la luz en la {habitaciones[i]}.")

main()
