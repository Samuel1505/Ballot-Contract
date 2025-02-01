# Ballot Smart Contract

## Overview
The `Ballot` smart contract implements a decentralized voting system that allows users to cast votes on predefined proposals. The contract also supports vote delegation, enabling voters to assign their voting rights to another address.

## Features Implemented
- **Granting Voting Rights**: Only the chairperson can grant voting rights.
- **Vote Delegation**: A voter can delegate their vote to another voter.
- **Voting Mechanism**: Voters can cast their vote for a proposal.
- **Winning Proposal Calculation**: Determines the proposal with the highest votes.
- **Retrieving the Winner's Name**: Returns the name of the winning proposal.

## Solidity Concepts Used
### 1. **Structs**
   - `Voter`: Holds voter information such as weight, voting status, delegate address, and chosen proposal.
   - `Proposal`: Stores proposal name and vote count.

### 2. **Mappings**
   - `voters`: Maps each address to its corresponding `Voter` struct.

### 3. **Arrays**
   - `proposals`: Stores the list of proposals available for voting.

### 4. **Functions**
   - `giveRightToVote()`: Grants a voter the right to vote.
   - `delegate()`: Allows a voter to delegate their vote.
   - `vote()`: Allows a voter to cast their vote.
   - `winningProposal()`: Determines the proposal with the most votes.
   - `winnerName()`: Retrieves the name of the winning proposal.

### 5. **Access Control**
   - Only the chairperson can assign voting rights.

### 6. **Error Handling**
   - Uses `require()` to enforce rules such as:
     - Only the chairperson can give voting rights.
     - Voters cannot delegate to themselves.
     - Prevents delegation loops.
     - Ensures a voter has not already voted.

## Security Considerations
- **Prevents Self-Delegation**: Ensures voters cannot delegate votes to themselves.
- **Detects Delegation Loops**: Prevents circular delegation.
- **Reverts Invalid Votes**: Ensures votes are cast within a valid range.
- **Access Control for Chairperson**: Restricts administrative actions to the contract creator.

This contract provides a secure and transparent voting process for decentralized decision-making. 🚀

