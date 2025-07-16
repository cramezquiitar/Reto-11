# Reto-11

1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.
 * **endswith:** Devuelve ```True``` si la cadena Verifica que finaliza con un texto específico. dado, de lo contrario, devuelve ```False```.
 ```python
cadena = "programacion.py"
print(cadena.endswith(".py"))  # True
```

 * **startswith:** Devuelve ```True``` Verifica si una cadena inicia con un texto determinado. dado, de lo contrario, ```False```.
```python
cadena = "programacion.py"
print(cadena.startswith("pro"))  # True
```

 * **isalpha:** Devuelve ```True``` si todos los caracteres de la cadena son letras del alfabeto (y la cadena no está vacía).
```python
texto = "Python"
print(texto.isalpha())  # True
```

**isalnum:** Devuelve ```True``` si la cadena contiene solo letras y números, sin símbolos ni espacios., y la cadena no está vacía.
    ```python
    usuario = "user123"
print(usuario.isalnum())  # True
     ```
     
**isdigit:** Devuelve ```True``` si todos los caracteres son dígitos numéricos, y hay al menos un carácter.
```python
numero = "2025"
print(numero.isdigit())  # True
 ```

**isspace:** Devuelve ```True``` si la cadena contiene solo espacios (sin letras ni números).
```python
titulo = "Curso De Python"
print(titulo.istitle())  # True
```

**istitle:** Devuelve ```True``Verifica si cada palabra en la cadena comienza con mayúscula y el resto en minúscula.
```python
titulo = "Curso De Python"
print(titulo.istitle())  # True
```

**islower:** Devuelve ```True``` si si todos los caracteres son minúsculas.
```python
texto = "python"
print(texto.islower())  # True
```

**isupper:** Devuelve ```True``` si todos los caracteres son mayúsculas.
```python
texto = "PYTHON"
print(texto.isupper())  # True
```

2. Procesar el <a href="https://www.py4e.com/code3/mbox.txt">archivo</a> y extraer:
 - Cantidad de vocales
 - Cantidad de consonantes
 - Listado de las 50 palabras que más se repiten
```python
# Importamos las librerías necesarias
import urllib.request  # Sirve para leer archivos directamente desde internet
from collections import Counter  # Sirve para contar cuántas veces se repite cada palabra

# PASO 1: Leer el archivo desde internet
# Guardamos la dirección del archivo de texto
url = 'https://www.py4e.com/code3/mbox.txt'
# Abrimos la dirección usando urllib y guardamos la respuesta
respuesta = urllib.request.urlopen(url)
# Leemos todo el contenido del archivo y lo pasamos de bytes a texto
texto_completo = respuesta.read().decode('utf-8')

# PASO 2: Contar vocales y consonantes
# Creamos dos contadores, uno para las vocales y otro para las consonantes
cantidad_vocales = 0
cantidad_consonantes = 0
# Recorremos cada carácter del texto completo
for letra in texto_completo:
    # Verificamos si el carácter es una letra del alfabeto
    if letra.isalpha():
        # Convertimos la letra a minúscula para facilitar la comparación
        letra = letra.lower()
        # Si la letra está en el grupo de vocales, sumamos 1 al contador de vocales
        if letra in 'aeiou':
            cantidad_vocales += 1
        else:
            # Si no es vocal, entonces es consonante
            cantidad_consonantes += 1

# PASO 3: Preparar el texto para contar palabras
# Convertimos todo el texto a minúsculas para que no distinga entre mayúsculas y minúsculas
texto_minusculas = texto_completo.lower()
# Reemplazamos signos de puntuación por espacios para que no afecten el conteo de palabras
# Por ejemplo, si no quitamos los puntos, "correo." y "correo" se contarían como diferentes
texto_minusculas = texto_minusculas.replace('.', ' ')
texto_minusculas = texto_minusculas.replace(',', ' ')
texto_minusculas = texto_minusculas.replace(':', ' ')
texto_minusculas = texto_minusculas.replace(';', ' ')
texto_minusculas = texto_minusculas.replace('!', ' ')
texto_minusculas = texto_minusculas.replace('?', ' ')
texto_minusculas = texto_minusculas.replace('"', ' ')
texto_minusculas = texto_minusculas.replace("'", ' ')
texto_minusculas = texto_minusculas.replace('(', ' ')
texto_minusculas = texto_minusculas.replace(')', ' ')
texto_minusculas = texto_minusculas.replace('[', ' ')
texto_minusculas = texto_minusculas.replace(']', ' ')

# PASO 4: Contar palabras más repetidas
# Dividimos el texto en palabras, separando por espacios
lista_de_palabras = texto_minusculas.split()
# Usamos Counter para contar cuántas veces aparece cada palabra
conteo_palabras = Counter(lista_de_palabras)
# Obtenemos las 50 palabras más repetidas
palabras_mas_repetidas = conteo_palabras.most_common(50)

# Mostrar los resultados
# Imprimimos la cantidad total de vocales encontradas en el texto
print("Cantidad de vocales:", cantidad_vocales)
# Imprimimos la cantidad total de consonantes encontradas en el texto
print("Cantidad de consonantes:", cantidad_consonantes)
# Imprimimos las 50 palabras más repetidas y cuántas veces aparece cada una
print("\nLas 50 palabras más repetidas son:")
for palabra, cantidad in palabras_mas_repetidas:
    print(palabra, ":", cantidad)
```
