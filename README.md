# SPECTRAL BIPARTITION AND MODULARITY ANALYSIS OF KARATE CLUB SET 
This code does the recursive spectral bipartition algorithm which finds  the best possible set of communities within the karate club set which maximises the modularity score . This is done by checking the the eigen value of modularity matrix 'B' and finding its leading eigen vector.

# CODE
 # Spectral bipartition Function
  The first part of the code defines a recursive spectral bipartition function which splits the graph.                                                               
  The function checks the leading eigenvalue of Modularity Matrix , if its  positive this implies  it can be split.                                                  
  Then if it can be split it assigns the nodes to 2 different communities based on the signs of elements of leading eigenvectors.                                           
  Then if sign of all elements in eigen vector is same this means that all nodes belong to same community so it can't be split no more.                                     
  So code checks if one of communities are empty list and if so it exits while loop and splits no more.                                                                                                         
  Finally the function returns a  community history list which is a nested list of communities present at each iteration of the split.                               
# Visualisation
  The code iterates through the community history list and plots communities present in every iteration as graph with every community having different colour.
  The code creates a metric history dictionary which contains each node and each of its centrality scores at every iteration.
  Then iterating through this dictionary , each metric score V/s node ID is  plotted for every iteration as a bar plot.
  
# SHORT DISCUSSION
The Nodes  0,5,33 consistently remains central across the 3 iterations.They have high value of degree centrality ,betweenness centrality and closeness centrality   relative to all other nodes in all iteration indicating that even after splitting into separate communities it remains relatively important.But however the  clustering scores for these nodes are relatively low as it connects separate communities and so fraction neighbours of these nodes which are connected between
themselves will be low.
The structure of community structures affect these metrics very much such as Node 8 which had high betweenness centrality in iteration 0 but after iter 1 and iter 2 this became zero showing that it had acted as a bridge connecting 2 communities but however after splitting it got destroyed.The community structure concentrates betweenness centrality in a few bridging nodes, while most others have very low values because they operate only within tightly knit groups.

The community structure prevents nodes from having globally high closeness values, because most are only close to nodes inside their own cluster, not the whole network.This is reason why many nodes have low value for closeness score at iteration no. zero but as iterations increase more dense community is formed which increases the closeness score of nodes within that community.

Community structure makes degree centrality high within each community but not across the whole graph, because most links are present locally within the community rather than global graph.


