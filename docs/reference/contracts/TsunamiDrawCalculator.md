

## Functions
### initialize
```solidity
  function initialize(
    contract ITicket _ticket,
    address _drawSettingsManager,
    contract ClaimableDraw _claimableDraw
  ) public
```
Initializer sets the initial parameters


#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_ticket` | contract ITicket | Ticket associated with this DrawCalculator
|`_drawSettingsManager` | address | Address of the DrawSettingsManager. Can be different from the contract owner.
|`_claimableDraw` | contract ClaimableDraw | ClaimableDraw associated with this DrawCalculator

### calculate
```solidity
  function calculate(
    address _user,
    struct DrawLib.Draw[] _draws,
    bytes _pickIndicesForDraws
  ) external returns (uint96[])
```
Calulates the prize amount for a user for Multiple Draws. Typically called by a ClaimableDraw.


#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_user` | address | User for which to calcualte prize amount
|`_draws` | struct DrawLib.Draw[] | draw array for which to calculate prize amounts for
|`_pickIndicesForDraws` | bytes | The encoded pick indices for all Draws. Expected to be just indices of winning claims. Populated values must be less than totalUserPicks.

#### Return Values:
| Name                           | Type          | Description                                                                  |
| :----------------------------- | :------------ | :--------------------------------------------------------------------------- |
|`An`| address | array of amount of prizes awardable
### setDrawSettings
```solidity
  function setDrawSettings(
    uint32 _drawId,
    struct DrawLib.DrawSettings _drawSettings
  ) external returns (bool success)
```
Sets DrawSettings for a draw id. only callable by the owner or manager


#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_drawId` | uint32 | The id of the Draw
|`_drawSettings` | struct DrawLib.DrawSettings | The DrawSettings to set

### setClaimableDraw
```solidity
  function setClaimableDraw(
    contract ClaimableDraw _claimableDraw
  ) external returns (contract ClaimableDraw)
```
Sets DrawSettings for a draw id. only callable by the owner or manager


#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_claimableDraw` | contract ClaimableDraw | The address of the ClaimableDraw to update with the updated DrawSettings

### getDrawSettings
```solidity
  function getDrawSettings(
    uint32 _drawId
  ) external returns (struct DrawLib.DrawSettings)
```
Gets the DrawSettings for a draw id


#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_drawId` | uint32 | The id of the Draw

### manager
```solidity
  function manager(
  ) public returns (address)
```
Gets current _manager.

Returns current _manager address.1


#### Return Values:
| Name                           | Type          | Description                                                                  |
| :----------------------------- | :------------ | :--------------------------------------------------------------------------- |
|`Current`|  | _manager address.
### setManager
```solidity
  function setManager(
    address _newManager
  ) public returns (bool)
```
Set or change of manager.

Throws if called by any account other than the owner.

#### Parameters:
| Name | Type | Description                                                          |
| :--- | :--- | :------------------------------------------------------------------- |
|`_newManager` | address | New _manager address.

#### Return Values:
| Name                           | Type          | Description                                                                  |
| :----------------------------- | :------------ | :--------------------------------------------------------------------------- |
|`Boolean`| address | to indicate if the operation was successful or not.
### owner
```solidity
  function owner(
  ) public returns (address)
```

Returns the address of the current owner.


### renounceOwnership
```solidity
  function renounceOwnership(
  ) public
```

Leaves the contract without owner. It will not be possible to call
`onlyOwner` functions anymore. Can only be called by the current owner.
NOTE: Renouncing ownership will leave the contract without an owner,
thereby removing any functionality that is only available to the owner.


### transferOwnership
```solidity
  function transferOwnership(
  ) public
```

Transfers ownership of the contract to a new account (`newOwner`).
Can only be called by the current owner.


## Events
### ManagerTransferred
```solidity
  event ManagerTransferred(
    address newManager
  )
```

Emitted when _manager has been changed.

#### Parameters:
| Name                           | Type          | Description                                    |
| :----------------------------- | :------------ | :--------------------------------------------- |
|`newManager`| address | new _manager address.
### OwnershipTransferred
```solidity
  event OwnershipTransferred(
  )
```



### DrawSettingsSet
```solidity
  event DrawSettingsSet(
  )
```
Emitted when the DrawParams are set/updated


### Initialized
```solidity
  event Initialized(
  )
```
Emitted when the contract is initialized


### ClaimableDrawSet
```solidity
  event ClaimableDrawSet(
  )
```
Emitted when the claimableDraw is set/updated

