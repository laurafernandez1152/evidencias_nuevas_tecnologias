<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 10 


<!-- Su documentación aquí -->
...
import pandas as pd
import streamlit as st
data = pd.read_csv('resultados_pruebas_saber_3_5_y_9.csv', delimiter=";")

#limpieza
data = data.dropna()

#esta por cuestiones de conflicto con los filtros
data

#filtro 1
st.header("Filtro 1")
st.write ("Mostrar todos los promedios de matematicas")
filtro1 = data[data["area"] == "matemáticas"]
st.dataframe(filtro1)

#filtro 2
st.header("Filtro 2")
st.write ("Mostrar todos los promedios de lenguaje")
filtro2 = data[data["area"] == "lenguaje"]
st.dataframe(filtro2)

#filtro 3
def prom(promedio):
    return promedio < 250
st.header("Filtro 3")
st.write ("Mostrar todos los promedios de lenguaje menores a 250")
filtro3 = data[(data["area"] == "lenguaje") & (data["promedio"] <250)]
st.dataframe(filtro3)

#filtro4
def prom(promedio):
    return promedio > 250
st.header("Filtro 4")
st.write ("Mostrar todos los promedios de lenguaje mayores a 250")
filtro4 = data[(data["area"] == "lenguaje") & (data["promedio"] >250)]
st.dataframe(filtro4)

#filtro5
st.header("Filtro 5")
st.write ("Mostrar todas las pruebas de 9°")
filtro5 = data[data["grado"] == 9 ]
st.dataframe(filtro5)

#filtro6
st.header("Filtro 6")
st.write ("Mostrar todas las pruebas de 3°")
filtro6 = data[data["grado"] == 3 ]
st.dataframe(filtro6)

#filtro7
st.header("Filtro 7")
st.write ("Mostrar todas las pruebas de 5°")
filtro7 = data[data["grado"] == 5 ]
st.dataframe(filtro7)

#filtro 8
def niv(nivel_superior):
    return nivel_superior > 65
st.header("filtro 8")
st.write ("Mostrar la comuna 8 con nivel superior a 65 en matematicas")
filtro8 = data[(data["area"] == "matemáticas") & (data["nivel_superior"] >65) & (data["comuna"]==8) ]
st.dataframe(filtro8)

#filtro 9
#def prom(promedio):
    #return promedio > 400
#st.header("filtro 9")
#st.write ("Mostrar el sector educativo con un promedio mayor a 400")
#filtro9 = data[(data["sector_educativo"]) & (data["promedio" >400 ])]
#st.dataframe(filtro9)

def prom(promedio):
    return promedio > 400

st.header("Filtro 9")
st.write("Mostrar el sector educativo con un promedio mayor a 400")
filtro9 = data[data["sector_educativo"] & (data["promedio"] > 400)]
st.dataframe(filtro9)

#filtro 10
st.header("Filtro 10")
st.write ("Mostrar todos los registros con base en el colegio que registre el usuario")
institucion = st.text_input("Ingresa la institucion educativa que quieras filtrar")
institucionLista = []
institucionLista.append(institucion)
filtro10 = data[data["establecimiento_educativo"].isin(institucionLista)]
if st.button("filtrar Institucion educativa"):
   st.dataframe(filtro10)
else:
    st.write('escribe correctamente el nombre de la Institucion educativa')

st.dataframe(filtro10)

...




