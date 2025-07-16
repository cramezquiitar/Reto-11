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
