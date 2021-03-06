
# Basic Code

Here I demonstrate a some basic usage of RCy3 package with building a network using igraph which helps in accurately understanding the data through networks.
```
install.packages("igraph")
library(igraph)
cytoscapePing()

personalities <- data.frame(name=c("Sam", "Bobby", "Lily", "Rahul",
                            "Monica", "Sunny"),
                     age=c(24,28,45,32,20, 36),
                     gender=c("M", "M", "F", "M", "F", "M"),
                     acceptance=c(10,10,10,10,10,8))
 ```
 A dataframe is made with columns as name, age, gender and acceptance and stored in personality variable.
 
 ```
 family_relations <- data.frame(from=c("Bobby", "Lily", "Lily", "Sam",
                               "Rahul", "Monica"),
                        to=c("Sam", "Monica", "Bobby", "Sunny", "Lily", "Bobby"),
                        same_dept=c(FALSE,FALSE,TRUE,FALSE,FALSE,TRUE),
                        closeness=c(6,8,10,4,2,1), suggestion=c(8,2,6,4,8,2))
```                        
A dataframe is made with columns from, to, same_dept, closeness, suggestion and stored in family_relations variable.

```
ig <- graph_from_data_frame(family_relations, directed=TRUE, vertices=personalities)
```
A directed igraph is made from dataframe family_realtions and vertices as personalities.

```
createNetworkFromIgraph(ig,"SampleIgraph")
```
A network is created from igraph with the name SampleIgraph.

The network created is as shown:

![network](https://github.com/dA505819/Uses_of_RCy3/blob/master/images/Capture.JPG)


