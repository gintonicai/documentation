---
description: >-
  Provider receives GIN token reward for contribution to the Gintonic network.
  This section describes how awards are calculated and how a provider can
  receive them.
---

# Earning Rewards

## Essential Parameters

* _system\_public\_address_ - system blockchain account, assigned manually in Rewarding module, receives system fee and rewards of unauthorized peers.
* _init\_peer public address_ - system blockchain account, assigned manually in Rewarding module, receives rewards for the work done by init\_peer.
* _unauth\_peer public address_ - system blockchain account, assigned manually in Rewarding module, receives rewards unauthorized peers, who have no associated public address.

## Charging for an Inference Job

Initiating a model inference triggers the billing module to calculate the token charge:

1. The developer account is charged per message (no actual token transfers occur; only backend balance calculations).
2. The charged amount is added to the system balance.

## Reward Calculation

Rewards are based on the computational work each node performs. The reward for each 'peer\_id' is calculated as follows:

`reward (peer_id) = {( job_price - system_fee ) * block_amount } / { job_size}`

, where &#x20;

_'job\_price'_ = 1 GIN, rewards distributed per message. Constant for MVP.

_'sysetm\_fee'_ = 0.001 GIN (0.1%), accrued to system\_public\_address.

_'block\_amount'_ = received from Petals Master Node API, selected by 'peer\_id' from peers\_contribution.

_'job\_size'_ = received from Petals Master Node API.

## Rewards distribution

System defines which public address accrues each calculated reward:

| Condition                                                                                                                  | To which account reward goes        |
| -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| _peer\_id = initial\_peer_                                                                                                 | to _initial\_peer\_public\_address_ |
| <p><em>peer_id != initial_peer AND</em></p><p><em>peer_id <strong>has</strong> a peer_public_address</em> in Rewards.</p>  | to _peer\_public\_address_          |
| <p><em>peer_id != initial_peer AND</em></p><p><em>peer_id <strong>hasn’t</strong> peer_public_address</em> in Rewards.</p> | to _unauth\_peer\_public\_address_  |

Then transfers peer\_id reward to corresponding address from the system balance to which GIN was charged in “Charging for an inference job”

## Check Reward Balance

To check available rewards:

1. Click option "Check available rewards."
2. Gintonic verifies if the address exists in the Rewarding service and returns its status (address found or not) and the available rewards balance for withdrawal (if the address is found).

## Withdraw Rewards

To receive rewards:

1. Click option "Withdraw."
2. The Gintonic backend confirms the rewards balance and creates a unique transaction signature (recipient, amount, GIN-SC address, nonce) for you to sign.
3. Sign the transaction on the frontend via Metamask. \
   This action triggers a call to the GIN smart contract's _'withdraw_' endpoint to transfer all available rewards to yours public address.
