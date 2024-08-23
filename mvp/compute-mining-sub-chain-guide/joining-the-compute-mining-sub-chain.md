# Joining the Compute Mining Sub-chain

### After Installation

Providers must supply a 'public\_address' in the blockchain. This address will be associated with the provider's peer address in Gintonic to receive rewards for computation work. To keep track of rewards, use the same address at each launch. Using a new address will create a new entry in the database.

Upon server launch, it receives a unique 'peer\_id', which is paired with the provided 'peer\_public\_address' and sent to the Gintonic backend for storage in the Rewards module.

### Joining the Swarm

To join the swarm, the following parameters are required. These parameters are hardcoded for this version:

* 'initial\_peer': The address of the initial swarm peer, necessary to join the network. In MVP 1.0, there is one swarm and one 'initial\_peer' address, provided during the installation script execution. This poses a security risk, as the 'initial\_peer' address is sensitive information. This issue should be addressed in upcoming releases.
* GPU resource allocation: Set to the default value of N blocks (70% of total GPU capacity)

### Gintonic client termination

The Gintonic client process can be terminated in the following ways:

* Killing the process manually
* Restarting or shutting down the machine
* Using the CTRL+C keyboard shortcut

To rejoin the swarm after termination, follow Step 2 in the "Setting Up Your Environment: Before Starting" section.
