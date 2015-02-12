## 2.1 Gossip: Multicast Problem 

- Multicast isn't `broadcast`, `broadcast` will send information to all nodes on network. Multicast focus on the particular **group** of nodes.

### Requirement

- Fault tolerance and scalability
    
    - Because the nodes may crash

    - Packet may be dropped

    - Thousands of nodes.

- Most in the application level.

### Implementation

#### 1. Centeralized

- It's the simplest implementation.

- Put receipients in the for or while loop, go though the group member and send the TCP or UDP packets

- Problems:
    
    - Fault tolerance

    - Latency, since the sender has to go through sequentially

    - Time complexity: `O(n)`(Suppose we have n nodes.)

#### 2. Tree-based

- If you build a balanced(or almost balanced) tree, the height of a n-nodes tree is log(n) => That means the time complexity to reach each node is `O(log(n))`. 

- Problems:
    
    - Needs to maintain the tree

- Solutions:

    - Build a spanning tree among the process of multicast group.

    - Use spanning tree to disemminate multicast

    - Use acknowledgements(ACKs) or negative acknowledgements(NAKs) to repair the nodes which do not receive message.([What is ACKs?](http://en.wikipedia.org/wiki/Acknowledgement_(data_networks)))
    
        - Issues: ACKs and NAKs might implode. For instance if the multicast wasn't sent successfully at the initial.

        - SRM (Scalable Reliable Multicast): 
            - Use NAKs but add random delays at the receiver. 

            - If the receiver need to send NAKs multiple time it should use exponential backoff to avoid NAK storms

        - RMTP (Reliable Multicast Transport Protocol)
    