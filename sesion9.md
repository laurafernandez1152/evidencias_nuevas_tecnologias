<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 9 


<!-- Su documentación aquí -->
...

import pandas as pd
import streamlit as st
import matplotlib.pyplot as plt 
data = pd.read_csv('ventas_vehiculos .csv')

st.header("Tabla antes de la limpieza de datos")
data
#datos vacios
data = data.dropna()

#datos atipicos
plt.hist(data["Color"])
st.pyplot()

plt.boxplot(data["Kilometraje"])
st.pyplot()

data.plot.scatter(x="Marca", y="Año")
st.pyplot()

data = data[~((data["Modelo"] == "Sedán") & (data["Precio"] > 35000))]
data = data[data["Año"]>2000]

#datos duplicados
duplicates = data[data.duplicated(keep=False)]
st.write(duplicates)

#formato de datos
st.write(data.dtypes)
data["Fecha"] = pd.to_datetime(data["Fecha"])
st.write(data.dtypes)

st.header("Tabla despues de la limpieza de datos")
data
...






