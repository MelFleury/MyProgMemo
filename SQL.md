## SQL
### Change column type
```sql
ALTER TABLE <table_name>
ALTER COLUMN <column_name> TYPE <type_name>
USING <column_name>::<type_name>;
```

### Create table from another existing table
```sql
CREATE TABLE <table_name> AS SELECT ...
```

### Change column already created
```sql
UPDATE <table_name>
SET <column_name> = <>ST_GeomFromText(geometry);
```

## PostGIS
### Install PostGIS
```sql
CREATE extension postgis;
```

### Differences between WKB and WKT
- WKB : Well-Known Binary - Efficient binary format for storage and transmission
- WKT : Well-Known Text - Human-readable text representation
--> GEOMETRY_TYPE(coordinate_list)

### Change column type from text to geometry
```sql
ST_GeomFromWKB(decode(geometry, 'hex'), 4326); --if WKB format
ST_GeomFromEWKT(geometry); --if WKT format

```

### Create spatial index
```sql
CREATE INDEX <index_name> -- ex. idx_geom
ON <table_name>
USING GIST (<geometry_column_name>) -- in general : "geom" or "geometry"
```

### Spatial join
```sql
ST_Intersects(table1.geometry, table2.geometry) -- if "intersects" predicate
ST_Contains(table1.geometry, table2.geometry) -- if "contains" predicate
```