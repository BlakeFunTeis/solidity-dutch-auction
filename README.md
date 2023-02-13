# Dutch Auction Smart Contract

The Dutch Auction Smart Contract is an ERC721A compliant contract that allows users to mint NFTs using a Dutch auction mechanism. The contract implements the OpenZeppelin Ownable contract, the SafeMath library, and the ERC721A standard.

## Contract Details

### Variables

- `online`: a boolean variable that indicates whether the Dutch auction is currently online.
- `revealed`: a boolean variable that indicates whether the NFTs have been revealed.
- `baseURI`: a string variable that contains the base URI for the NFTs.
- `startTimestamp`: an integer variable that represents the start time of the Dutch auction.
- `endTimestamp`: an integer variable that represents the end time of the Dutch auction.
- `defaultPricePerToken`: an integer variable that represents the default price of each NFT.
- `priceDecayRate`: an integer variable that represents the decay rate of the price.
- `decayInterval`: an integer variable that represents the interval at which the price decays.
- `minimumPricePerToken`: an integer variable that represents the minimum price of each NFT.
- `supply`: an integer variable that represents the maximum supply of NFTs.
- `mintLimit`: an integer variable that represents the maximum number of NFTs that can be minted by a user.

### Structs

- `tokenBetchPrice`: a struct that contains the mint price and total number of NFTs minted by an address.

### Mappings

- `allMintData`: a mapping that maps an address to its corresponding `tokenBetchPrice` struct.

### Events

- `SetOnline`: an event that is emitted when the online status of the contract is set.
- `SetRevealed`: an event that is emitted when the revealed status of the contract is set.
- `SetStartTimestamp`: an event that is emitted when the start timestamp of the contract is set.
- `SetEndTimestamp`: an event that is emitted when the end timestamp of the contract is set.
- `SetPriceDecayRate`: an event that is emitted when the price decay rate of the contract is set.
- `SetDecayInterval`: an event that is emitted when the decay interval of the contract is set.
- `SetMinimumPricePerToken`: an event that is emitted when the minimum price per token of the contract is set.
- `SetSupply`: an event that is emitted when the total supply of the contract is set.
- `SetMintLimit`: an event that is emitted when the mint limit of the contract is set.

### Functions

- `DutchActionMint(uint _total)`: a function that allows a user to mint NFTs using the Dutch auction mechanism. The user must send enough ether to cover the current mint price of the NFTs. The function checks whether the conditions for minting NFTs are met and updates the `allMintData` mapping accordingly.
- `getCurrentMintPrice()`: a function that returns the current mint price of the NFTs, based on the current block time and the price decay rate.
- `setBaseURI(string memory _uri)`: a function that sets the base URI for the NFTs.
- `tokenURI(uint _tokenId)`: a function that returns the token URI for a specific token.
- `setOnline(bool _online)`: a function that sets the online status of the contract.
- `setRevealed(bool _revealed)`: a function that sets the revealed status of the contract.
- `setStartTimestamp(uint _startTimestamp)`: a function that sets the start timestamp of the contract.
- `setEndTimestamp(uint _endTimestamp)`: a function that sets the end timestamp of the contract.
- `setPriceDecayRate(uint _priceDecayRate)`: a function that sets the price decay rate of the contract.
- `setDecayInterval(uint _decayInterval)`: a function that sets the decay interval of the contract.
- `setMinimumPricePerToken(uint _minimumPricePerToken)`: a function that sets the minimum price per token of the contract.
- `setSupply(uint _supply)`: a function that sets the total supply of the contract.
- `setMintLimit(uint _mintLimit)`: a function that sets the mint limit of the contract.

## Modifiers
- `isNormalUser()`: a modifier that checks whether the caller is a normal user.

## Libraries
- `SafeMath`: a library that provides arithmetic operations with safety checks to prevent overflow and underflow.
- `Strings`: a library that provides string manipulation functions.

## Usage
The Dutch Auction Smart Contract allows users to mint NFTs using a Dutch auction mechanism. The current mint price of the NFTs is calculated based on the current block time and the price decay rate. The `DutchActionMint` function can be used to mint NFTs by sending enough ether to cover the current mint price.

The contract owner can set the base URI, online status, revealed status, start and end timestamps, price decay rate, decay interval, minimum price per token, total supply, and mint limit using the appropriate functions.

The `isNormalUser` modifier checks whether the caller is a normal user, i.e., not another contract.

The `SafeMath` library provides arithmetic operations with safety checks to prevent overflow and underflow.

The `Strings` library provides string manipulation functions.

## License
This code is licensed under the MIT License.