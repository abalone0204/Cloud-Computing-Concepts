##2.7 Membership: Which is the best failure detector

- Completeness -> Guarantee always

- Accuracy -> Probability PM(T) : Probability of mistake in time T

- Speed -> T time units(Time to detect the first failure)

- Scale -> N * L compare this to all the protocols( centralized, all-to-all, gossip...etc)

### Comparison

#### 1. All-to-all approach

- Every T units:
    
    - `L = N/T` -> The load per process is linear in N

#### 2. Gossip-based approach

- `T = log(N)*tg`

- `L = N/tg = N*log(N)/T`

- L(the load of messages per node) is higher than the all-to-all approach, but it's natural, because we get better accuracy by loading more messages per node.

### What's the best/optimal we can do?

- Practice the mathematical proof, it's hard but important.

- Conclusion is L is independent of N
