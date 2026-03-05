# Solver Node Setup

Guide to setting up and running a Solver Node on the Qubetics Chain Abstraction network.

## 1. Generate Peer ID

Each Solver Node needs a unique Peer ID to identify itself on the network. Generate one using:

```bash
./mpc-node --generate
```

Save the generated Peer ID — you'll need it for the onboarding step.

## 2. Onboard & Fund the Node

Once your Peer ID is generated, it needs to be **onboarded** (registered) on the network. Use the onboarding portal to register:

👉 **[Onboarding Portal](<PASTE_LINK_HERE>)**

After onboarding, fund your node with the minimum required liquidity:

| Asset    | Minimum Required |
| -------- | ---------------- |
| **TICS** | 100000 TICS          |
| **BTC**  | 0.065 BTC     |

> *These amounts are examples and subject to change. Refer to the latest network parameters for confirmed values.*

Both balances must be met before the node connects. If the minimum requirements are not met, the node will be **banned from the network for 1 hour**.

## 3. Run the Node

Start your Solver Node:

```bash
./mpc-node
```

If everything is funded and onboarded correctly, your node will join the network and start participating in DKG rounds, threshold signing, and intent resolution.

## Rewards

Solver Nodes earn rewards for processing cross-chain transactions. The reward rate depends on whether the node has been validated:

| Status        | Reward |
| ------------- | ------ |
| Unvalidated   | 75%    |
| Validated     | 100%   |

> *These percentages are examples and subject to change. Refer to the latest network parameters for confirmed values.*

New nodes start at **75% rewards**. To unlock the full **100%**, the node must go through the validation process — this requires consistent uptime, successful participation in DKG rounds, and maintaining the minimum liquidity at all times.
