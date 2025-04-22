# Operaciones Morfológicas en Imágenes Binarias

Este programa implementa operaciones morfológicas básicas (erosión y dilatación) para procesamiento de imágenes binarias.

## Funcionalidades principales

El programa ofrece dos operaciones morfológicas fundamentales:

1. **Erosión**: Elimina píxeles en los bordes de los objetos
2. **Dilatación**: Añade píxeles a los bordes de los objetos

## Estructura del código

### Funciones principales

1. **erosion(cantSelec, imgVec, h, w)**:
   - Aplica la operación de erosión a una imagen binaria
   - Utiliza un elemento estructurante de 3x3 (8-vecindad)
   - Un píxel permanece solo si todos sus vecinos están activos
   - Permite aplicar la operación múltiples veces (iteraciones)
   - Muestra comparación entre imagen original y resultado

2. **dilatacion(cantSelec, imgVec, h, w)**:
   - Aplica la operación de dilatación a una imagen binaria
   - Utiliza un elemento estructurante de 3x3 (8-vecindad)
   - Un píxel activo expande su valor a todos sus vecinos
   - Permite aplicar la operación múltiples veces (iteraciones)
   - Muestra comparación entre imagen original y resultado

### Flujo del programa

1. Carga una imagen binaria de un conjunto predefinido
2. Convierte la imagen a una matriz binaria (1 para objeto, 0 para fondo)
3. Solicita al usuario:
   - Número de iteraciones para la operación
   - Tipo de operación morfológica (1: erosión, 2: dilatación)
4. Aplica la operación seleccionada
5. Muestra los resultados usando matplotlib:
   - Imagen original
   - Imagen procesada

## Uso

1. Ejecutar el programa
2. Seleccionar una imagen (0-9)
3. Especificar número de iteraciones
4. Elegir tipo de operación (1-2)
5. El programa mostrará los resultados en una ventana gráfica

## Requisitos

- Python 3.x
- Bibliotecas:
  - Pillow/PIL (`Image`)
  - OpenCV (`cv2`)
  - NumPy (`numpy`)
  - Matplotlib (`matplotlib.pyplot`)

## Parámetros importantes

- **cantSelec**: Número de veces que se aplicará la operación
- **imgVec**: Matriz binaria que representa la imagen
- **h, w**: Altura y anchura de la imagen
- **Elemento estructurante**: Vecindad de 8 píxeles (3x3)

## Visualización

El programa muestra una comparación lado a lado:
- Para erosión: Imagen original vs. imagen erosionada
- Para dilatación: Imagen original vs. imagen dilatada

Las imágenes se muestran con:
- Blanco (255,255,255): Objeto
- Negro (0,0,0): Fondo

## Notas

- Las imágenes deben ser binarias (blanco y negro)
- El programa está configurado para trabajar con imágenes en la carpeta `bilevel_images`
- Las operaciones morfológicas son sensibles al número de iteraciones
- Se recomienda usar valores pequeños (1-5) para cantSelec
