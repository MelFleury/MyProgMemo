## Install packages
```r
install.packages("<package_name>")
```

## Import R library
```r
library(<package_name>)
```

## Visulize map in viewer tab
VS Code settings (File > Preferences > Settings) > Search "R:Plot Use Httpgd" (je n'ai plus réussis à le retrouver une fois activé) > Activate it

## "leaflet" library
### Import
```r
library(leaflet)
```

## "sf" library
### Import
```r
library(sf)
```

### Read geopackage file
```r
<table_name> <- st_read("<gpkg_file_name>.gpkg")
```

## "dplyr" library
### Import
```r
library(dplyr)
```

### Select specific columns from table
```r
<table_name> %>% select (colname1, colname2)
```

### Exclude specific column from table
```r
<table_name> %>% select (-colname1)
```

