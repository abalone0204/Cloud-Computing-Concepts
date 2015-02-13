##2.2. Gossip: The Gossip Protocol

- Concept of gossip: Periodically sending message to random nodes which are infected. And after node receivied the message, it will become infected node, and it will start sending message during next period.

### Push gossip v.s Pull gossip

- Push: Once you have message, start gossiping about it.

- Pull: Periodically poll a few randomly selected processes for new multicast message which didn't receive.

- Hybrid: Mix both.