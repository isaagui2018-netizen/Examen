import random

def es_camaleon(numero):
    """
    Verifica si un numero cumple las condiciones para ser camaleon:
    1.La suma de sus digitos es par
    2.El numero invertido es divisible por 3
    """
    str_numero = str(numero)

    suma_digitos = sum(int(digito) for digito in str_numero) 
    condicion1 = suma_digitos % 2 == 0

    numero_invertido = int(str_numero [::-1])
    condicion2 = numero_invertido % 3 == 0

    return condicion1 and condicion2 
def generar_numeros(cantidad): 
    """
    Genera numeros aleatorios de 3 a 5 cifras
    """
    numeros = []
    for _ in range(cantidad): 

        numero = random.randint(100,99999)
        numeros.append(numero)
    return numeros
def main():
    try:
        cantidad = int(input("Cantidad de numeros a validar: "))
        if cantidad <= 0:
            print("la cantidad debe ser un numero positivo")
            return 
    except ValueError:
        print("Por favor, ingrese un numero valido")
        return

    numeros = generar_numeros(cantidad)
    print("Numeros generados:",",".join(map(str, numeros)))
    print()
    print("Resultados:")

    for numero in numeros: 
        if es_camaleon (numero):
            print(f"{numero} -> Si")
        else:
            print(f"{numero} -> No")
if __name__=="__main__":
    main()
