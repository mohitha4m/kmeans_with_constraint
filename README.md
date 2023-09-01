# kmeans clustering with size constraint
Kmeans clustering with cluster size constraints - min and max



Simple implementation of K-means algorithm with minimum and maximum cluster size constraint
This is done by reassigning points if the cluster size is not in the range of minimum and maximum cluster size, 
the reassignment is done by assigning to the next best cluster based distance metric
of each cluster

There are few limitations-
- Doesn't work well on sparse data
- Edge Cases: The code may encounter edge cases where it's not possible to meet the size constraints

## Example -

~~~
np.random.seed(0)
X = np.random.rand(300, 2)
k = 5
min_size = 30
max_size = 150

centers, labels = kmeans_with_constraints(X, k, min_size, max_size)
cluster_sizes = np.bincount(labels.astype(int))

# Print the cluster sizes
for cluster_idx, size in enumerate(cluster_sizes):
    print(f"Cluster {cluster_idx}: {size} data points")
~~~
