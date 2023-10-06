<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 4


<!-- Su documentación aquí -->
nombre_usuario = input("Hola, ingresa tu nombre: ")
def saludar(nombre):
    print("Hola,", nombre, "comencemos los ejercicios")
saludar(nombre_usuario)

#EJERCICIO 1
def calculadora(num1, num2, operacion):
    if operacion == '+':
         resultado= num1 + num2
    elif operacion == '-':
         resultado= num1 - num2
    elif operacion == '*':
         resultado= num1 * num2
    elif operacion == '/':
        if num2 != 0:
            resultado= num1 / num2
        else:
            resultado = "Error: División por cero"
    else:
        resultado = "Operador no válido"
    
    return resultado

resultado_suma = calculadora(5, 3, '+')
resultado_resta = calculadora(10, 2, '-')
resultado_multiplicacion = calculadora(4, 6, '*')
resultado_division = calculadora(8, 0, '/')

print("Suma:", resultado_suma)
print("Resta:", resultado_resta)
print("Multiplicación:", resultado_multiplicacion)
print("División:", resultado_division)

#EJERCICIO 2

def contar_vocales(cadena):
    contador = 0
    cadena = cadena.lower()
    for caracter in cadena:
        if caracter in 'aeiou':
            contador += 1
    return contador


texto = "ejemplo"
cantidad_vocales = contar_vocales(texto)

print("Número de vocales en el texto:", cantidad_vocales)

#EJERCICIO 3

def es_primo(numero):
    if numero <= 1:
        return False
    for i in range(2, int(numero**0.5) + 1):
        if numero % i == 0:
            return False
    return True

# Ejemplos de uso:
numero1 = 23
numero2 = 67
resultado1 = es_primo(numero1)
resultado2 = es_primo(numero2)

print(numero1, "es primo:", resultado1)
print(numero2, "es primo:", resultado2)


#EJERCICIO 4

def contar_palabras(cadena):
    palabras = cadena.split()
    cantidad_palabras = len(palabras)
    return cantidad_palabras

# Ejemplo de uso:
texto = "hagamos un ejemplo"
resultado = contar_palabras(texto)

print("Número de palabras en el texto:", resultado)

def potencia(base, exponente):
    resultado = base ** exponente
    return resultado
# Ejemplo de uso:
base = 13
exponente = 3
resultado = potencia(base, exponente)
print(f"{base} elevado a la {exponente} es igual a {resultado}")

#EJERCICIO 5
def potencia(base, exponente):
    resultado = 1
    for _ in range(exponente):
        resultado *= base
    return resultado
# Ejemplo de uso:
resultado = potencia(56, 3)
print(resultado)  







