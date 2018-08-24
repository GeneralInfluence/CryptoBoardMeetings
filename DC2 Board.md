# DC2 Board Smart Contract Build-Out

<b>Assumptions:</b>
```
	quorum = 66%
```

<b>Variables:</b>
Seed contract with 3 Keys (temporarily populate variables). This “Approved Caller List” (ACL) consists of officers of the board.

```
    president: [“0x5b2eC85Ea8706964E426f39caF39e31477050179”, “David Anderson”]
	vicePresident: [ wallet, “Sean Gonzalez”]
	treasurer: [ wallet, “Noah Lerman”]
```

These variables are used to verify each function call after the contract is deployed. 
For instance, if the `msg.sender`’s address doesn’t match the `president` address, then the function call fails.

*Roles will be able to be reset based on function calls to be developed.

<b>Functions</b>

*Schedule Board Meeting*
Creates a pending Board Meeting

*Call to Order*
Assuming only the President can call to order a board meeting, we need a function to determine if the message sender is, in fact, the president. This acts as all the authorization needed as the user verification takes place withing MetaMask (i.e. the president’s private password for the authorized wallet).

```
modifier onlyPresident() {
	if(!isPresident[msg.sender]) throw;
		_;
}
```

Yes, we need an isPresident() function.

*Quorum*

Assuming board members (and advisors) can authenticate they are present (likely an `attend()` function of some sort), the contract can determine if quorum is reached based on the count of active board members.

*Approve Minutes*

Approve the minutes from the previous board meeting (assuming there are previous minutes).



## Governance Data Fields

What data fields make up a board meeting? We break them into categories: Static, Ongoing, Event

###Static
		
_Board Members_


| Variable | Type | Storage Location |
| ------------- |:-------------:| -----:|
|`Election Date`	| |  Readable from Blockchain |
|`Name` | |	Readable from Blockchain |
|`Public Key `| | Readable from Blockchain |
		
Ratified Minutes

###Ongoing
Bylaws
? What are the legally required sections for ByLaws
			
		
###Goals
Active Goals for the Board	
		
###Policies
Active - Policies that have been voted into effect.
Consideration - Policies that are under consideration

Pending <b>Minutes</b>

<b>Events</b>:
	
<i>Call to Order</i>  -> Creates An Active Meeting
<i>Quorum</i> --> Iterates through an Agenda
Board Meeting <b>Agenda</b>:
General Information of Meeting
Actions
		

Instantiating a Board Contract:
<b>ByLaws</b>
Founding <b>Members</b>
	
Can our smart contract reference an Agenda JSON file and parse through.  


Scenarios:

1: <i>What if a board member loses their private key?</i> If there is no recovering the private key (perhaps there is an organization vault of seeds that requires some % vote?)
	
	
	
	


