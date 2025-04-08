# Proyecto Geoespacial: Descarga de Imágenes Sentinel-2

Este proyecto contiene un script de Python (originalmente un notebook de Google Colab) para automatizar la búsqueda y descarga de imágenes satelitales **Sentinel-2 L2A** desde la plataforma **Planetary Computer**. Su propósito principal es facilitar la adquisición organizada de bandas espectrales para análisis geoespaciales, como el cálculo de NDVI o análisis de cobertura vegetal.

## 🚀 Funcionalidades

-   **Carga de polígonos GeoJSON:** Define zonas de interés para filtrar imágenes satelitales.
-   **Búsqueda con filtros:**
    -   Rango de fechas personalizable.
    -   Porcentaje máximo de nubosidad (`max_cloud_cover`).
-   **Descarga automática de bandas:** Descarga las principales bandas espectrales (`.tif`) disponibles del producto Sentinel-2 L2A seleccionado.
-   **Organización por carpeta:** Las bandas se guardan en una subcarpeta nombrada según el archivo GeoJSON de entrada y la fecha de la imagen (ej., `Cauca_1523_4567_Tecnicafe_20240115/B04.tif`).

## ⚙️ Parámetros Configurables en el Script

Dentro del script `Bajar_Sentinel.ipynb`, puedes ajustar:

-   `GEOJSON_PATH_MANUAL`: Ruta al archivo GeoJSON que define el área de interés.
-   `max_cloud_cover`: Porcentaje máximo de nubes aceptado (por defecto, 10%).
-   `date_range`: Rango de fechas para buscar imágenes (formato "YYYY-MM-DD/YYYY-MM-DD").
-   `SENTINEL_DIR`: Directorio base donde se guardarán las carpetas con las imágenes descargadas.

## 🧠 Requisitos

-   Python 3.x
-   Cuenta de acceso a [Planetary Computer](https://planetarycomputer.microsoft.com/) (generalmente abierta).
-   Un archivo GeoJSON que contenga al menos un polígono válido en EPSG:4326.
-   Dependencias de Python listadas en `requirements.txt`.

## 🛠️ Instalación

1.  Clona este repositorio:
    ```bash
    git clone https://github.com/TU_USUARIO/proyecto-geoespacial.git
    cd proyecto-geoespacial
    ```
2.  (Recomendado) Crea un entorno virtual:
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
    ```
3.  Instala las dependencias:
    ```bash
    pip install -r requirements.txt
    ```

## 🏃 Uso

1.  Asegúrate de tener tu archivo GeoJSON con el polígono de interés.
2.  Modifica las rutas y parámetros dentro del script `Bajar_Sentinel.ipynb` según sea necesario, especialmente `GEOJSON_PATH_MANUAL` y `SENTINEL_DIR`.
3.  Ejecuta el script (puedes convertir el notebook a un script `.py` o ejecutarlo celda por celda si tienes un entorno Jupyter).
4.  Las imágenes descargadas se guardarán en la carpeta especificada en `SENTINEL_DIR`.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## ⚠️ Nota sobre Datos

Las imágenes satelitales descargadas (`.tif`) pueden ocupar mucho espacio. Asegúrate de tener suficiente almacenamiento. Estos archivos `.tif` están excluidos del repositorio Git mediante el archivo `.gitignore`.
