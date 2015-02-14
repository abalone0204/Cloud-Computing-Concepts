##2.5 Membership: What is group membership list?

- Server may have failure, and we need to implement the failure detectors.

- Process "group-based" system
    
    - Clouds/Datacenters

    - Replicated servers

    - Distributed databases

- Crash-stop/ Failure-stop process failures

- Each process in group of processes, we have a membership list which contains the process in your system and not-yet failed(non-faulty processes)

- Membership protocol:
    
    - Keep the membership list up to date

        - as the processes join the group

        - as the processes leave the group

        - as the processes failed silently

- Sub-protocols

    - Disseminations

    - Failue Detectors

