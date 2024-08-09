# GCNCODE
Use STK to create a three-layer Walker satellite constellation, including 100 LEO satellites at an altitude of 550 kilometers, 25 MEO satellites at an altitude of 2500 kilometers, and 3 MEO satellites at an altitude of 8000 kilometers, as shown in the figure below. Export 4000 csv files from STK, that is, the satellite visibility distance matrix of 4000 time slots. Based on these visibility matrices, calculate the delay matrix and visibility matrix from the controller to the switch. Randomly generate the load of 100 switches. Use the above data as the input of GCN, and use the simulated annealing algorithm to calculate the optimal allocation strategy as the GCN true label.

![image](https://github.com/user-attachments/assets/9dfb8161-702e-4e2f-996b-80d1e6dc9472)

The visibility_distance_matrix file stores the visibility distance matrix between the controller and the switch for each time slot. The 0 element in the matrix indicates that the controller and the switch are not visible, and the non-0 element indicates the distance between the controller and the switch. This matrix is ​​used to calculate the visibility matrix and the delay matrix.

The visibility_matrix file stores the visibility matrix between the controller and the switch for each time slot. The 0 element in the matrix indicates that the controller and the switch are not visible, so communication cannot be established. The 1 element indicates that the controller and the switch are visible and communication can be established. This matrix represents the weight of the edge in the graph.

The delay_matrix file stores the delay matrix between the controller and the switch for each time slot. The 0 element in the matrix indicates that the controller and the switch are not visible, which means that the delay is infinite. The non-0 element indicates the delay between the controller and the switch. This matrix represents the weight of the edge in the graph.

The loads.json file stores the switch load of each time slot in the form of a dictionary. The keyword indicates the current time slot, and the value indicates the load of all switches. These load information are node features of the graph and are used to represent the attributes of each node.

The strategy.json file stores the optimal allocation strategy matrix of the controller and the switch for each time slot in the form of a dictionary. The key represents the current time slot and the value represents the optimal allocation strategy matrix. These allocation strategies are used as the true labels of GCN.
