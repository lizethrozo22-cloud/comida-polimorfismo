# comida-polimorfismo
comida
"""
 Ejercicio 5: Comidas
Situación: Un restaurante sirve pizzas, hamburguesas, ensaladas y postres.
Tu tarea:
•	Piensa: ¿qué tiene en común cualquier comida?
•	¿Qué acciones se hacen con cualquier platillo?
•	Crea clase abstracta Comida con:
o	Atributos: nombre, precio, ingredientes, tiempo_preparacion
o	Métodos abstractos: preparar(), calcular_calorias()
•	Implementa Pizza e Hamburguesa
Pista: Toda comida se prepara y tiene cierto contenido calórico.

"""

from abc import ABC, abstractmethod


class Comida(ABC):
    def __init__(self, nombre, precio, ingredientes, tiempo_preparacion):
        self.nombre = nombre
        self.precio = precio
        self.ingredientes = ingredientes
        self.tiempo_preparacion = tiempo_preparacion

    @abstractmethod
    def preparar(self):
        pass

    @abstractmethod
    def calcular_calorias(self):
        pass


class Pizza(Comida):
    def __init__(self, nombre, precio, ingredientes, tiempo_preparacion, tipo_masa):
        super().__init__(nombre, precio, ingredientes, tiempo_preparacion)
        self.tipo_masa = tipo_masa

    def preparar(self):
        return (f"Preparando la pizza {self.nombre} con masa {self.tipo_masa}.")

    def calcular_calorias(self):
        calorias = 200 + len(self.ingredientes) * 50  # Ejemplo simple de cálculo
        return (f"La pizza {self.nombre} tiene aproximadamente {calorias} calorías.")


class Hamburguesa(Comida):
    def __init__(self, nombre, precio, ingredientes, tiempo_preparacion, tipo_pan):
        super().__init__(nombre, precio, ingredientes, tiempo_preparacion)
        self.tipo_pan = tipo_pan

    def preparar(self):
        return (f"Preparando la hamburguesa {self.nombre} con pan {self.tipo_pan}.")

    def calcular_calorias(self):
        calorias = 300 + len(self.ingredientes) * 40  # Ejemplo simple de cálculo
        return (f"La hamburguesa {self.nombre} tiene aproximadamente {calorias} calorías.")

class Ensalada(Comida):
        def __init__(self, nombre, precio, ingredientes, tiempo_preparacion,tipo_proteina):
            super().__init__(nombre, precio, ingredientes, tiempo_preparacion,)
            self.tipo_proteina = tipo_proteina

        def preparar(self):
            return (f"preparando la ensalada {self.nombre} con proteina {self.tipo_proteina}.")

        def calcular_calorias(self):
            calorias = 200 + len(self.ingredientes) * 50
            return (f"la ensalada {self.nombre} tiene aproximadamente {calorias} calorias.")

class Postre(Comida):
        def __init__(self, nombre, precio, ingredientes, tiempo_preparacion,tipo_lacteo):
           super().__init__(nombre, precio, ingredientes,tiempo_preparacion)
           self.tipo_lacteo = tipo_lacteo

        def preparar(self):
            return (f"preparando el postre {self.nombre} con lacteo {self.tipo_lacteo}.")

        def calcular_calorias(self):
            calorias = 300 + len(self.ingredientes) * 40
            return (f"el postre {self.nombre} tiene aproximadamente {calorias} calorias.")






h1 = Hamburguesa("Cheeseburger", 8.99, ["carne", "queso", "lechuga"], 10, "sesame")
p1 = Pizza("Margarita", 10.99, ["tomate", "queso", "albahaca"], 15, "delgada")
e1 = Ensalada("cesar",35000,["lechuga romana","aderezo","pollo","queso"],30,"pollo")
p1 = Postre("flan",20000,["leche","condensada","huevo","azucar","caramelo","vainilla"],5,"leche entera")
print("=== Hamburguesa ===")
print(h1.preparar())
print(h1.calcular_calorias())

print("")

print("=== Pizza ===")
print(p1.preparar())
print(p1.calcular_calorias())

print("")

print("=== Ensalada ===")
print(e1.preparar())
print(e1.calcular_calorias())

print("")
print("=== Postre ===")
print(p1.preparar())
print(p1.calcular_calorias())
