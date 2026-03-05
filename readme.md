# Solver Node Setup

Guide to setting up and running a Solver Node on the Qubetics Chain Abstraction network.

## Prerequisites

- `wget` is essential to download the binary from the release.

### Installing wget

**On Ubuntu 24:**
```bash
sudo apt update
sudo apt install wget -y
```

**On macOS Tahoe 26.3:**
Using [Homebrew](https://brew.sh/):
```bash
brew install wget
```

## Download the Binary

You can view the release details here: [v0.0.1 Release](https://github.com/Qubetics/solver-network-binary/releases/tag/v0.0.1)

Use `wget` to download the binary for your specific operating system:

**For Ubuntu 24:**
```bash
wget https://github.com/Qubetics/solver-network-binary/releases/download/v0.0.1/mpc-node
chmod +x mpc-node
```

**For macOS Tahoe 26.3:**
```bash
wget https://github.com/Qubetics/solver-network-binary/releases/download/v0.0.1/mpc-node-mac
chmod +x mpc-node-mac
```

## 1. Generate Peer ID

Each Solver Node needs a unique Peer ID to identify itself on the network. Generate one using:

**On Ubuntu 24:**
```bash
./mpc-node --generate
```

**On macOS Tahoe 26.3:**
```bash
./mpc-node-mac --generate
```

Save the generated Peer ID — you'll need it for the onboarding step.

## 2. Onboard & Fund the Node

Once your Peer ID is generated, it needs to be **onboarded** (registered) on the network. Use the onboarding portal to register:

👉 **[Onboarding Portal](<https://ticssolver.com/>)**

After onboarding, fund your node with the minimum required liquidity:

| Asset    | Minimum Required |
| -------- | ---------------- |
| **TICS** | 100000 TICS          |
| **BTC**  | 0.065 BTC     |

> *These amounts are examples and subject to change. Refer to the latest network parameters for confirmed values.*

Both balances must be met before the node connects. If the minimum requirements are not met, the node will be **banned from the network for 1 hour**.

## 3. Run the Node

Start your Solver Node:

**On Ubuntu 24:**
```bash
./mpc-node
```

**On macOS Tahoe 26.3:**
```bash
./mpc-node-mac
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
