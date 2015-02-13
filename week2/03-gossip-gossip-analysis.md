##2.3. Gossip: The Gossip Protocol

### Analysis of push-based gossip protocol

#### Claim

1. It's lightweight in large groups

2. Spread multicast quickly

3. It's highly fault-tolerance

#### Analysis

##### Push-based

- From old mathematical branch of Epidemiology.

- We must define the symbol first:

    - Total pupulation `n+1`.

    - Contact rate is `beta`.

    - At any time , for uninfected number(`x`), and infected number(`y`), `x+y = n+1`

    - Protocol rounds `b` random targets per round -> `beta` = `b/n` (Since there are total n+1 nodes, we pick one infected node, and pick b nodes from the other n node to be the receivers)

- Advantages:

    - `clog(n)` runs -> **Low latency**

    - all but 1/(n^bc) nodes receive the multicast -> **Reliability**

    - each node has transmitted no more than cblog(n) gossip messages -> **Lightweight**

##But, `log(n)` is not a constant?

- Though it's not a constant, pragmaticaly, it's a very slowly growing number .

> Example(the base is two):
> - lg(1000) ~ 10
> - lg(1M) ~ 20
> - lg(1B) ~ 30
> - lg(all IPv4 address) ~32

- Fault tolerance:

    - Packet loss:

        - Suppose 50% packets loss

        - We analyze `b -> b/2`

        - To achieve the same reliability, takes twice as many rounds.(from clog(n) rounds to 2clog(n) rounds)

    - Node failure:
    
        - Suppose 50% nodes fail

        - We analyze `n -> n/2` and `b -> b/2`

        - The same as above

- With the fault tolerance, gossip possible die , but improbable.

- Once we get a few rounds and let few nodes get infected, it will be hard to kill gossip(Like the disease's spread out)

----

##### Pull-based

- In all form of gossips, it takes O(log(N)) rounds before about N/2 rounds.
    
    - Why?

    - Because in the spanning tree with constant number of degrees has O(log(N)) nodes

- Thereafter, pull-based gossip will get faster than push-based gossip.

- Seeing is believing:
    
    - After ith round, let `p_i` be the fraction of non-infected processes

    - `p_(i+1) = (p_i)^(k+1)` : k = b, it's the pull target per round per process

    - This is super exponential, finishing with the rate of O(log(log(n)))

##### Analysis



##### Summary

- So we can use the push-based in ther first half to spread quickly, and use the pull-based to finish the message spreading in the last-half.







