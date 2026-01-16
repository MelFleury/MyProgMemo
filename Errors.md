### ValueError: 'index_left' cannot be a column name in the frames being joined
If either GeoDataFrame already contains a column named index_right, the join fails
**SOLUTION :** drop column