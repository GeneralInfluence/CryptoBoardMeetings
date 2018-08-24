# DC2 Board Smart Contract Build-Out

__Assumptions:__
```
	quorum = 51%
```

_Variables:_
Seed contract with 3 Keys (populate variables / create first block). This “Approved Caller List” (ACL) consists of officers of the board.

```
    president: [“0x5b2eC85Ea8706964E426f39caF39e31477050179”, “David Anderson”]
	vicePresident: [ wallet, “Sean Gonzalez”]
	treasurer: [ wallet, “Noah Lerman”]
```

These variables are used to verify each function call after the contract is deployed. 
For instance, if the `msg.sender`’s address doesn’t match the `president` address, then the function call fails.

*Roles will be able to be reset based on function calls to be developed.

## Functions

__Schedule Board Meeting__
Only the President can schedule a board meeting
Creates a pending Board Meeting

__Call to Order__
Only the President can call to order a board meeting, which requires the following functions: 
* isPresident()
** only authorization required
** verification takes place within MetaMask (i.e. the president’s private password for the authorized wallet)
* meetingStart()

```
modifier onlyPresident() {
	if(!isPresident[msg.sender]) throw;
		_;
}
```

__Quorum__

Assuming board members (and advisors) can authenticate they are present (likely an `attend()` function of some sort), the contract can determine if quorum is reached based on the count of active board members.

__Approve Minutes__

Approve the minutes from the previous board meeting (assuming there are previous minutes).



## Governance Data Fields

What data fields make up a board meeting? We break them into categories: Static, Ongoing, Event

### Static
		
_Board Members_


| Variable | Type | Storage Location |
| ------------- |:-------------:| -----:|
|`Election Date`	| |  Readable from Blockchain |
|`Name` | |	Readable from Blockchain |
|`Public Key `| | Readable from Blockchain |
		
Ratified Minutes

### Ongoing
Bylaws
? What are the legally required sections for ByLaws
			
		
### Goals
Active Goals for the Board	
		
### Policies
Active - Policies that have been voted into effect.
Consideration - Policies that are under consideration

Pending <b>Minutes</b>

___Events__:
	
*Call to Order*  -> Creates An Active Meeting
*Quorum* --> Iterates through an Agenda
Board Meeting __Agenda__:
General Information of Meeting
Actions
		

Instantiating a Board Contract:
__ByLaws__
Founding __Members__
	
Can our smart contract reference an Agenda JSON file and parse through.  


Scenarios:

1: *What if a board member loses their private key?* If there is no recovering the private key (perhaps there is an organization vault of seeds that requires some % vote?)
	
	
	
	


