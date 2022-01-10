# How to integrate an custom contract and ABI using the ChainSafe Gaming SDK

## A brief overview of an ABI

In the last article we compiled a deployed a simple ERC20 token and integrated it into the ChainSafe Gaming SDK. Congratualtions to anyone that followed that tutorial and got that working. In this tutorial, we will integrate the ABI or Application Binary Interface. Which for us is the interface between Ethereum and our blockchain games. The EVM or (Ethereum Virtual Machine) is at the core of the Ethereum network, and our smart contracts are pieces of code stored on the Ethereum blockchain which are executed on EVM. 

As discussed in the previous tutorial, smart contracts are written Solidity and need to be compiled in EVM executable bytecode; when a smart contract is deployed, this bytecode is stored on the blockchain and is associated with an address. If you are coming from the Web 2 space this concept is very similar to an API. Although, the  ABI defines the methods and structures used to interact with the binary contract, just like the API does but on a lower-level. The ABI indicates the caller of the function to encode the needed information like function signatures and variable declarations in a format that the EVM can understand to call that function in bytecode; this is called ABI encoding.

## The elements of an ABI

* type: Defines the type of function. It can be one of the following, ‘function’, ‘constructor’, ‘receive' (for receive ether function), or ‘fallback’ (for default function).

* name: Defines the name of the function.

* inputs: It is an array of objects which defines parameters; each object has:

* name: Defines the name of the parameters.

* type: Defines the canonical types of the parameters. For example, uint256.

* components: Used to define tuple types, if a tuple type is reached, it is represented as type = tuple [other properties of tuple elements like name, type goes here].

* outputs: It is an array of output objects similar to inputs.

* stateMutability: Defines the mutability of a function. It can be one of the following values: ‘pure’ (specified not to read or write blockchain state), ‘view’ (specified when blockchain state is to be read, but no modification can be done), ‘nonpayable’ (this is the default mutability and doesn’t need to be mentioned while writing a function in code, this means a function does not accept Ether; using this we can read and write blockchain state), ‘payable’ (mentioning this means a function accepts Ether and can read/write blockchain state).


## How to generate the ABI and integrate it into the ChainSafe Gaming SDK?

In this part of the tutorial we are going to use Remix to compile and deploy an ERC20 smart contract. Then we will verify this smart contract on etherscan and add it to the ChainSafe gaming SDK. There we will properly format the ABI and incorporate it into the ChainSafe gaming SDK. Please follow the video for how this is works.


