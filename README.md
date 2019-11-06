# Commercial Center Identification Using POI Data

## Objective

Identifying commercial centers in a city, Visakhapatnam here, given point of interest (POI) data. Point of Interest data is collected from Open Street Maps using `OverPy`, a python wrapper for `OverPass API` and interactive visualization is performed using `folium`.


## Data

Using OverPy, first collected amenities such as restaurants, complexes, malls, hospitals etc. and visualized these points on map.

<p align="center"> <img src="graphs/maps_with_markers.png"/> </p>

<p align="center"> <img src="graphs/maps_heatmap.png"/> </p>
From the graph above we can understand that the areas with dense-ly clustered points are more developed and has many amenities as compared to areas with far away points. There areas might be underdeveloped or there may be natural areas such as mountains or lakes.

## Clustering

To identify the commercial centers, clustering was performed.

### Density Based Spatial Clustering of Application with Noise (DBSCAN)

DBSCAN clusters the data points to separate the area of high density (having large no. of amenities) with the area of low density and hence, separating out commercial areas from other areas of the city. DBSCAN is used because: it is robust to outliers, and does not require number of clusters to be specified priorly.

<p align="center"> <img src="graphs/maps_dbscan.png"/> </p>
DBSCAN has identified 6 clusters from the entire data.

### K-Means Clustering

Clustering directly in K-Means can lead to improper clustering if we don't know the exact number of clusters. Therefore finding the correct number of clusters is important. This is done using `Elbow-method` and `Silhouette Score Analysis` (detailed analysis in `jupyter-notebook`). Following is the final result.

<p align="center"> <img src="graphs/maps_kmeans_clustering.png"/> </p>

## Understanding the Data

Achieving good clustering on a large data is not always possible and can lead to improper clusters. Therefore, we zoom into one of the larger clusters and repeat the process again and see if we can infer some insights and obtain better clusters.

### Density Based Spatial Clustering of Application with Noise (DBSCAN)

<p align="center"> <img src="graphs/maps_dbscan_smaller.png"/> </p>
DBSCAN has identified 7 clusters

### K-Means Clustering

<p align="center"> <img src="graphs/maps_kmeans_clustering_smaller.png"/> </p>
K-Means has identified 7 clusters
