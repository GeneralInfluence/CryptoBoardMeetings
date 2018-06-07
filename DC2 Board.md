# DC2 Board Smart Contract Build-Out

<b>Assumptions:</b>
	`quorum` = 66%

<b>Variables:</b>
	Seed contract with 3 Keys (temporarily populate variables). This “Approved Caller List” (ACL) consists of officers of the board.

    president: [“0x5b2eC85Ea8706964E426f39caF39e31477050179”, “David Anderson”]
	vicePresident: [ wallet, “Sean Gonzalez”]
	treasurer: [ wallet, “Noah Lerman”]

These variables can be used to verify each function call after the contract is deployed. 
For instance, if the `msg.sender`’s address doesn’t match the `president` address, then the function call fails.

These roles will be able to be reset based on function calls to be developed.

<b>Functions</b>

*Call to Order*
Assuming only the President can call to order a board meeting, we need a function to determine if the message sender is, in fact, the president. This acts as all the authorization needed as the user verification takes place withing MetaMask (i.e. the president’s private password for the authorized wallet).

```
modifier onlyPresident() {
	if(!isPresident[msg.sender]) throw;
		_;
}
```

Yes, we need an isPresident() function.
***
*Quorum*

Assuming board members (and advisors) can authenticate they are present (likely an `attend()` function of some sort), the contract can determine if quorum is reached based on the count of active board members.
***
*Approve Minutes*

Coming.
