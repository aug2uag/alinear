<img src="./alinear.jpg">

# alinear

> HR time-lock bounty hunting smart contract

This smart contract is intended to interface with the alinear dApp that handles much of the logic off-chain. For example, the smart contract doesn't maintain the schedule of payouts-- this would need additional struct and storage params that currently seem to be unnecessary.

In its place, the token is designed to represent a discrete unit of function pertaining to a task managed by the dApp. A token creator will bind the token to an operation for their internal Human Resource hiring affairs, all the details of which are handled off-chain. __The purpose and value of this system is to ensure the bounty is paid contingent to the bounty hunter having reported and contributed to an employee who remains with the company long enough for the bounty hunter to be awarded in full__. Therefore, the purpose of the time-lock mechanism is to ensure a business doesn't have to assume risks of paying others for employees that turn out to be unqualified or who do not stay.

<img src="./overview.png">

The system operates as a Distributed Autonomous Organization (DAO) whereby rules are established by the "Benefactor", including the bounty reward and specifications. The "Bounty Hunter" acts autonomously to claim the reward, at which time the time-lock series is initiated for the benefit of delivering the reward in a minimum risk and transparent scenario.

YouTube video explainer available at: https://youtu.be/bKy8vFSxIfI



TODO:
- add `Ownable` and lock `total_approvals` after first set (only once; mutex) by the owner
- ensure amount and transfer with `pay_bounty_hunter` and `nft_is_approved`
- remove `pay_bounty_hunter` and handle payouts on approval (`nft_is_approved` only)
- improve test coverage to include full transfer schedule
- harden revoke, ensure no deposit and balance is lost
- audit (static and dynamic analysis), publish on mainet