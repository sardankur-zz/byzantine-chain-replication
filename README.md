# byzantine-chain-replication

Dist Algo limitation on size of message


To run on multiple nodes
1. add to config file "multi_node=ClientNode"
2. Run two nodes for (olympus, replica) and client
    a. Olympus and replica : python3 -m da -n MainNode main.da config.txt
    b. Client : python3 -m da -n ClientNode -D main.da config.txt
