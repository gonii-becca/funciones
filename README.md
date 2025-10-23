# -*- coding: utf-8 -*-



proveedores = {}

while True:
    menu = input("ingrese que desea hacer[salir][lista][ingreso]: ").lower()
    if menu == "salir":
        break
    elif menu == "lista":
        print("\nLista de proveedores ingresados:")
        for cuit, datos in proveedores.items():
            print(f"CUIT: {cuit}")  
            print(f"Nombre: {datos['nombre']}")
            print(f"Apellido: {datos['apellido']}")
            print(f"Razón Social: {datos['razon_social']}")
            print(f"Tipo de Proveedor: {datos['tipo_proveedor']}")
            print(f"Email: {datos['email']}")
            print("-" * 30)
    elif menu == "ingreso":
        cuit = input("Ingrese el CUIT del proveedor: ")
        nombre = input("Ingrese el nombre: ")
        apellido = input("Ingrese el apellido: ")
        razon_social = input("Ingrese la razón social: ")
        tipo_proveedor = input("Ingrese el tipo de proveedor: ")
        email = input("Ingrese el email: ")
        proveedores[cuit] = {
        "nombre": nombre,
        "apellido": apellido,
        "razon_social": razon_social,
        "tipo_proveedor": tipo_proveedor,
        "email": email
        }
        print("Proveedor agregado correctamente.\n") 
    elif cuit in proveedores:
        print("¡Ese CUIT ya fue ingresado! Intente con otro.")
        break
