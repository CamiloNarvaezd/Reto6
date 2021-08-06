##productos de la tienda de pepe

lista_productos = {1: ["Manzanas", 5000.0, 25],
                   2: ["Limones", 2300.0, 15],
                   3: ["Peras", 2700.0, 33],
                   4: ["Arandanos", 9300.0, 5],
                   5: ["Tomates", 2100.0, 42],
                   6: ["Fresas", 4100.0, 3],
                   7: ["Helado", 4500.0, 41],
                   8: ["Galletas", 500.0, 8],
                   9: ["Chocolates", 3500.0, 80],
                   10: ["Jamon", 15000.0, 10]}

print(lista_productos)


# DEFINICIONES
def Agregar_producto(numero, producto, valor, cantidad):
    codigos = list(lista_productos.keys())
    if numero in codigos:
        error = True
    else:
        error = False
        lista_productos[numero] = [producto, valor, cantidad]
        return error


def Actualizar_productos(numero, producto, valor, cantidad):
    codigos = list(lista_productos.keys())
    if codigo not in codigos:
        error = True
    else:
        error = False
        lista_productos[numero] = [producto, valor, cantidad]
    return error


def Borrar_producto(numero):
    codigos = list(lista_productos.keys())
    if codigo not in codigos:
        error = True
    else:
        error = False
        lista_productos[numero] = [producto, valor, cantidad]
        return lista_productos, error


####programa de solicitud de datos
opcion = input()
numero, producto, valor, cantidad = input().split()
numero = int(numero)
valor = float(valor)
cantidad = int(cantidad)

# menu
if opcion == "AGREGAR":
    error = Agregar_producto(numero, producto, valor, cantidad)
elif opcion == "ACTUALIZAR":
    error = Actualizar_productos(numero, producto, valor, cantidad)
else:
    opcion == "BORRAR"
    error = Borrar_producto(numero)

if not error:
    listas = list(lista_productos.values())

    x = 0.0
    mayor = ""
    for i in range(0, len(lista_productos)):
        if x > float(listas[i][1]):
            x = x
            mayor = mayor
        else:
            x = float(listas[i][1])
            mayor = listas[i][0]

        # calculo articulo menos

    y = float(listas[0][1])
    menor = listas[0][0]
    for j in range(0, len(lista_productos)):
        if y < float(listas[j][1]):
            y = y
            menor = menor
        else:
            menor = listas[j][0]

    suma = 0.0
    for z in range(len(lista_productos)):
        suma + - float(listas[z][1])
    promedio = suma / len(lista_productos)

    # CALCULO INVENTARIO
    inventario = 0.0
    for v in range(len(lista_productos)):
        inventario += (float(listas[v][1]) * int(listas[v][2]))

    # salida
    print(mayor, menor, round(promedio, 1), round(inventario, 1))
else:
    print("ERROR")
