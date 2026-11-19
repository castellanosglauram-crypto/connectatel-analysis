# Análisis de clientes ConnectaTel

Proyecto del Sprint 7 del bootcamp de Análisis de Datos de TripleTen.

## 🎯 Objetivo del proyecto

Evaluar el comportamiento de los clientes de **ConnectaTel**, una empresa de telecomunicaciones en Latinoamérica, con información registrada hasta 2024. El análisis busca:

- Construir un perfil estadístico de los clientes.
- Detectar comportamientos atípicos (outliers).
- Crear segmentos de clientes por edad y nivel de uso.
- Proponer estrategias de retención y mejoras a los planes ofrecidos.

## 📂 Datasets utilizados

| Archivo | Descripción |
|---|---|
| `plans.csv` | Planes actuales (Básico y Premium): precio mensual, minutos, mensajes y GB incluidos, y costo por excedente. |
| `users_latam.csv` | 4.000 clientes: edad, ciudad, fecha de registro, plan y fecha de cancelación (churn). |
| `usage.csv` | 40.000 registros de uso de 2024: llamadas (duración) y mensajes (longitud). |

## 🧩 Etapas del análisis

1. **Carga y exploración:** estructura, tipos de datos y primeras filas de cada dataset.
2. **Calidad de datos:** valores nulos, sentinels (`-999` en edad, `"?"` en ciudad) y fechas fuera de rango (registros en 2026).
3. **Limpieza:** imputación de la edad con la mediana, conversión de sentinels y fechas imposibles a nulos, y verificación de nulos MAR en `duration` y `length`.
4. **Resumen por usuario:** agregación de mensajes, llamadas y minutos por cliente y unión con la tabla de usuarios (`user_profile`).
5. **Distribuciones y outliers:** histogramas por plan, boxplots y límites con el método IQR.
6. **Segmentación:** grupos por nivel de uso (Bajo, Medio, Alto) y por edad (Joven, Adulto, Adulto Mayor).
7. **Insight ejecutivo:** conclusiones y recomendaciones para el negocio.

## 💡 Principales hallazgos

- El 73,6 % de los clientes es de **uso medio**. El segmento de **alto uso** (7 %) tiene la mayor tasa de cancelación (14 %).
- La **edad no cambia el comportamiento** de uso, y los planes Básico y Premium tienen un consumo casi idéntico.
- El consumo real está muy por debajo de lo que incluyen los planes. Esto abre la oportunidad de rediseñarlos y crear un plan de entrada para clientes de bajo uso.

## ▶️ Cómo ejecutar el notebook

**Opción 1: Google Colab**
1. Abre [Google Colab](https://colab.research.google.com/) → *File → Open notebook → GitHub*.
2. Pega la URL de este repositorio y selecciona el notebook.
3. Sube los archivos `plans.csv`, `users_latam.csv` y `usage.csv` a la sesión y ajusta las rutas en la celda de carga (por ejemplo, `pd.read_csv('plans.csv')`).

**Opción 2: Local**
1. Clona el repositorio: `git clone https://github.com/castellanosglauram-crypto/connectatel-analysis.git`
2. Instala las dependencias: `pip install pandas seaborn matplotlib jupyter`
3. Abre el notebook con `jupyter notebook` y ajusta las rutas de los CSV.

## 🔁 Guía de reproducción

1. Ten los tres archivos CSV disponibles y actualiza las rutas en la celda **"cargar archivos"**.
2. Ejecuta el notebook de principio a fin con **Kernel → Restart & Run All** (o *Runtime → Run all* en Colab). Las celdas dependen unas de otras, así que deben correr en orden.
3. Los resultados (tablas, gráficos e insights) se generan en el mismo notebook.

## 🛠️ Herramientas

Python 3 · pandas · seaborn · matplotlib · Jupyter Notebook
