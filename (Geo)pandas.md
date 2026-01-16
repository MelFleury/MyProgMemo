## GEOPANDAS
### How calculate buffer with spheric coordinates ?
1. Map a local UTM (Universal Transverse Mercator) zone (metric projection) by longitude geometry : if linestring or polygon, use longitude centroids point
2. Reprojection into original projection ex. WGS 84 (EPSG:4326)

### Buffer
Creation of an extension of a geometric data (points, polylines or polygon) from a specific distance. For example, a 50 m buffer on polylines extends them from 50 m on **both side**.

### Spatial join
```python
sjoin(left_df, right_df, how='inner', predicate='intersects')
```

### Open an interactive leaflet map from gdf
```python
gdf.explore("Pop2012", cmap="Blues")
```

### Generate GeometryArray of shapely Point geometries from x, y(, z) coordinates
```python
points_from_xy(df.longitude, df.latitude, crs="EPSG:4326")
```

### Save GeoDataFrame into geojson file
```python
gdf.to_file('dataframe.geojson', driver='GeoJSON')
```

### Save GeoDataFrame into shp file
```python
gdf.to_file('dataframe.shp')
```

### Save GeoDataFrame into geopackage file
```python
gdf.to_file('dataframe.gpkg', driver='GPKG')
```

### Save GeoDataFrame into parquet file
```python
gdf.to_parquet('data.parquet')
```

### Convert WKB geometry into Shapely geometric object
```python
df["geometry"] = df["geometry"].apply(shapely.wkb.loads)
```

### Open GeoDataFrame from PostGIS table
```python
con, cur = ConnexionPostgreSQL() # see "### Connexion to a postgreSQL database"
query = "SELECT * FROM <table_name>"
gdf = gpd.GeoDataFrame.from_postgis(query, con, geom_col="<geometry_column_name>")
gdf #or gdf.head()
```

### Centroid of polygons
```python
gdf["centroid"] = gdf.<geometry_column_name>.centroid
```

## PANDAS
### Import
```python
import pandas as pd
```

### Get the elements of series that are not present in other series
```python
df[~df["attribute_name"].isin(another_df["attribute_name"])]
```

## NUMPY
### Import
```python
import numpy as np
```
### Return an array drawn from elements in choicelist, depending on conditions (condlist).
```python
condlist = [
    df["attribute_name"].between(325, 975, inclusive="left"),
    df["attribute_name"] >= 3250
    ]
choicelist = ["label_cond1", "label_cond2"]
np.select(condlist, choicelist, default = "inconnu") #or an integer
```

### Count NaN in specific row or column
```python
df["attribute_name"].isnull().sum() # change axis parameter in sum() for row or column
```

## PSYCOPG2
A python driver for PostGreSQL
### Import
```python
import psycopg2
```

### Connexion to a postgreSQL database
```python
def ConnexionPostgreSQL():
    conn = psycopg2.connect(
    dbname="ma_base",
    user="mon_user",
    password="postgres",
    host="localhost"
    )

    cur = conn.cursor()

    return conn, cur
```