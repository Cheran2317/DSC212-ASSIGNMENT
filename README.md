# Karate Club Modularity - Assignment

Done by Cheran Ela (IMS24072)

This project performs recursive spectral community detection on the Karate Club graph.  
After each split, the updated community structure and the modularity score are shown.  
Once all splits are complete, the program allows interactive inspection of any node’s metrics  
and how those metrics evolve across the recursive partitions.

---

## What the code does

- Performs **recursive spectral modularity partitioning**:
  - Uses the leading eigenvector of the modularity matrix
  - Splits a community only if the top eigenvalue is positive
  - Continues recursively on each subcommunity

- Shows **visualizations after each split**:
  - Communities are colored differently
  - Modularity score (Q) is displayed at every split

- Computes **node-level metrics**:
  - Degree centrality  
  - Betweenness centrality  
  - Closeness centrality  
  - Clustering coefficient  

- Tracks **how these metrics change** across the sequence of splits  
  (metrics are computed within each node’s community at each step)

- Allows **interactive exploration**:
  - User enters a node ID  
  - Displays a bar chart of the node’s metrics on the full graph  
  - Displays a line plot of how the node’s metrics evolve across splits  

---

## Key findings (short discussion)

- **Nodes 0 and 33** remain the most central throughout the process.  
  They occupy hub-like positions, so even when the graph splits, they stay important inside their new communities.

- **Betweenness centrality changes the most** across splits.  
  Nodes that act as bridges between groups lose betweenness when the graph is partitioned and those connections disappear.

- **Closeness centrality often increases** for nodes that end up in small, tightly connected communities  
  since distances between nodes decrease.

- **Degree centrality is mostly stable**, because it depends only on immediate neighbors  
  and does not change much across the splits.

- Community structure has a strong impact on how we interpret node importance.  
  A node may look central in the full graph but lose influence after separation,  
  or may become more central inside its own smaller, cohesive subcommunity.

---

## Files included

- `karate_glub_graph.ipynb` — the main script containing the whole code

- `README.md` — this document

---

## Dependencies

- networkx  
- numpy  
- matplotlib  

