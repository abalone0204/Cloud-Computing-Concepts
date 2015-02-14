##2.6 Membership: Failure Detectors

- Suppose there are many processes in our group

- One of the processes which is p_i crashed.

- Then the failure detectors detect it and tell the others in our group.

### Desirable properties

- Completeness: Each of failures will be detected

- Accuracy: No mistaken detection 

- Speed: Time to first detection of a failure

- Scale: 
    
    - Equal load on each member

    - Network message load


- In spite of arbitrary simultaneous process failures


### Types of failure detectors

#### Centralized heartbeating

- Heartbeat sends periodically

- If heartbeat not received from `p_i` within timeout, mark `p_i` as failed.

- Disadvantage:

    - When the central point failed, there is no gurantee about who detect its failure

    - When there are large number of processes in the group, the central point might be overload with messages

#### Ring heartbeating

- It's a variant of centralize heartbeating.

- Where all processes are organized with a virtual ring. Every process has one connected to its neighbor process

- Avoid the hotspot like centralized heartbeating.

- Disadvantage:

    - Unpredictable on simultaneous multiple failures

#### All-to-all heartbeating

- Each process (p_i) sends heartbeat to all the ohter processes in the system

- Equal load per member

- Disadvantage:

    - If one of the process receiving message slow, it will mark all of other processes as failed, that cause low accuracy which we don't want to see.

