# Crowdfunding-smart-contract

# CrowdFunding Smart Contract

## Description

This project implements a decentralized crowdfunding platform using Solidity. The smart contract allows users to contribute Ether to a funding campaign with a specific target and deadline. The contract manager can create spending requests for the collected funds, which contributors can vote on. If the majority supports a request, the manager can execute the payment. The contract also includes functionality for contributors to get a refund if the funding target is not met by the deadline.

### Motivation

The primary motivation for this project was to explore and understand the development of decentralized applications on the Ethereum blockchain. It was inspired by the need for transparent and secure crowdfunding mechanisms where funds are handled in a decentralized manner without the need for intermediaries.

### Why This Project Was Built

This project was built to provide a practical solution to the problem of trust and transparency in crowdfunding. Traditional crowdfunding platforms often face issues related to the misuse of funds and lack of transparency. By leveraging blockchain technology, this project ensures that all transactions and fund allocations are transparent and governed by smart contract logic, reducing the potential for fraud and increasing trust among contributors.

### Problem Solved

The smart contract solves the problem of trust in crowdfunding by ensuring that:
- Contributions are securely stored and only accessible under predefined conditions.
- Spending requests are subject to approval by the majority of contributors, ensuring democratic control over fund usage.
- Contributors can get refunds if the funding target is not achieved by the deadline, mitigating the risk of losing money in unsuccessful campaigns.

### Lessons Learned

Developing this project provided insights into:
- The intricacies of writing secure and efficient smart contracts using Solidity.
- Implementing democratic voting mechanisms within smart contracts.
- Managing state and ensuring data persistence on the Ethereum blockchain.
- Handling Ether transactions and ensuring secure fund transfers.

## Smart Contract Details

### State Variables

- `contributors`: Mapping to track each contributor’s Ether contributions.
- `manager`: Address of the contract manager.
- `minimumContribution`: Minimum contribution amount required to participate.
- `deadline`: Timestamp after which contributions are no longer accepted.
- `target`: Funding goal to be achieved.
- `raisedAmount`: Total amount of Ether raised.
- `noOfContributors`: Number of unique contributors.
- `requests`: Mapping to store spending requests.
- `numRequests`: Counter for the total number of spending requests.

### Struct

**Request**:
- `description`: Description of the spending request.
- `recipient`: Address that will receive the funds if the request is approved.
- `value`: Amount of Ether requested.
- `completed`: Boolean indicating whether the request has been completed.
- `noOfVoters`: Number of contributors who have voted for the request.
- `voters`: Mapping to track who has voted for the request.

### Constructor

Initializes the contract with a target amount, a deadline, and sets the minimum contribution. The manager is set to the address that deploys the contract.

### Functions

- `sendEth()`: Allows users to contribute Ether.
- `getContractBalance()`: Returns the balance of the contract.
- `refund()`: Allows contributors to get a refund if the target is not met by the deadline.
- `createRequests(string memory _description, address payable _recipient, uint _value)`: Allows the manager to create a spending request.
- `voteRequest(uint _requestNo)`: Allows contributors to vote on a spending request.
- `makePayment(uint _requestNo)`: Allows the manager to execute a spending request if the majority approves and the target is met.

### Modifier

- `onlyManager()`: Ensures that only the manager can call certain functions.

## Usage

1. Deploy the contract with the desired target and deadline.
2. Contributors can send Ether to the contract using the `sendEth()` function.
3. The manager can create spending requests using the `createRequests()` function.
4. Contributors can vote on spending requests using the `voteRequest()` function.
5. If the majority supports a request, the manager can execute the payment using the `makePayment()` function.
6. If the target is not met by the deadline, contributors can get a refund using the `refund()` function.

## License

This project is unlicensed. 

## Contact

awaisali0313@gmail.com

