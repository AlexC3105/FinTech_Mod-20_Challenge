# Solidity Smart Contract

## Background

A fintech startup company has recently hired you. This company is disrupting the finance industry with its own cross-border, Ethereum-compatible blockchain that connects financial institutions. Currently, the team is building smart contracts to automate many of the institutions' financial processes and features, such as hosting joint savings accounts.

To automate the creation of joint savings accounts, you'll create a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. Your smart contract will use ether management functions to implement a financial institution's requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

## What You're Creating

- The completed JointSavings Solidity smart contract.
- A folder named Execution_Results that contains at least eight images. These images should confirm that the deposit and withdrawal transactions, which are designed to test the JointSavings functionality in the JavaScript VM, worked as expected.

## Files

Download the following files to help you get started:

- Module 20 Challenge files

## Instructions

The steps for this Challenge are divided into the following sections:

1. Create a Joint Savings Account Contract in Solidity
2. Compile and Deploy Your Contract in the JavaScript VM
3. Interact with Your Deployed Smart Contract

### Step 1: Create a Joint Savings Account Contract in Solidity

1. From the provided starter code, open the Solidity file named joint_savings.sol in the Remix IDE.
2. Define a new contract named JointSavings.
3. Define the following variables in the new contract:
   - Two variables of type address payable named accountOne and accountTwo
   - A variable of type address public named lastToWithdraw
   - Two variables of type uint public named lastWithdrawAmount and contractBalance
4. Define a function named withdraw that accepts two arguments: amount of type uint and recipient of type payable address. In this function, create code as follows:
   - Define a require statement that checks if recipient is equal to either accountOne or accountTwo. If it isn't, the require statement will return the "You don't own this account!" text.
   - Define a require statement that checks if balance is sufficient for accomplishing the withdrawal operation. If insufficient funds exist, it will return the "Insufficient funds!" text.
   - Add an if statement to check if lastToWithdraw is not equal to (!=) recipient. If it isn't equal, set it to the current value of recipient.
   - Call the transfer function of the recipient, and pass it the amount to transfer as an argument.
   - Set lastWithdrawAmount equal to amount.
   - Set the contractBalance variable equal to the balance of the contract by using address(this).balance to reflect the new balance of the contract.
5. Define a public payable function named deposit. In this function, create code as follows:
   - Set the contractBalance variable equal to the balance of the contract by using address(this).balance.
6. Define a public function named setAccounts that takes two address payable arguments, named account1 and account2. In the body of the function, set the values of accountOne and accountTwo to account1 and account2, respectively.
7. Add a fallback function so that your contract can store ether that's sent from outside the deposit function.

### Step 2: Compile and Deploy Your Contract in the JavaScript VM

1. Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.
2. In the Remix IDE, navigate to the "Deploy & Run Transactions" pane, and then make sure that "JavaScript VM" is selected as the environment.
3. Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

### Step 3: Interact with Your Deployed Smart Contract

Now that your contract is deployed, it's time to test its functionality. After each step, capture a screenshot of the execution, and then save it in a folder named Execution_Results. You'll share this folder with your final submission.

To interact with your deployed smart contract, complete the following steps:

1. Use the setAccounts function to define the authorized Ethereum address that will be able to withdraw funds from your contract.

   **Note**: You can either create dummy addresses on the [Vanity-ETH](https://vanity-eth.tk) website, which includes an Ethereum vanity address generator, or use the following Ethereum addresses:

   - Dummy account1 address: 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb
   - Dummy account2 address: 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0

2. Test the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the contractBalance function to verify that the funds were added to your contract:

   - Transaction 1: Send 1 ether as wei.
   - Transaction 2: Send 10 ether as wei.
   - Transaction 3: Send 5 ether.

   **Note**: Remembering how to convert ether to wei and vice versa can be challenging. So, you can use a website like [Ethereum Unit Converter](https://eth-converter.com) to ease doing the conversion.

3. Once you've successfully deposited funds into your contract, test the contract's withdrawal functionality by withdrawing 5 ether into accountOne and 10 ether into accountTwo. After each transaction, use the contractBalance function to verify that the funds were withdrawn from your contract. Also, use the lastToWithdraw and lastWithdrawAmount functions to verify that the address and amount were correct.

## Requirements

### Step 1: Create a Joint Savings Account Contract in Solidity (55 points)

To receive all points, you must:

- Create a new Solidity file named joint_savings.sol based on the starter code provided. (5 points)
- Define a new contract named JointSavings in the Solidity file. (5 points)
- Define all the required variables in the contract. (10 points)
- Define a withdraw function. (10 points)
- Define a deposit function. (10 points)
- Define the setAccounts function. (10 points)
- Define the fallback function. (5 points)

### Step 2: Compile and Deploy Your Contract in the JavaScript VM (15 points)

To receive all points, you must:

- Compile your smart contract without errors. (10 points)
- Deploy your smart contract in the JavaScript VM. (5 points)

### Step 3: Interact with Your Deployed Smart Contract (30 points)

To receive all points, you must:

- Use the setAccounts function as requested. Capture a screenshot of the execution, and share it in your final submission. (10 points)
- Test the deposit function. After each of the three transactions, capture a screenshot of the execution, and share it in your final submission. (10 points)
- Test the withdrawal functionality of the smart contract. After each of the two transactions, capture a screenshot of the execution, and share it in your final submission. Additionally, capture screenshots of the terminal output from the lastToWithdraw and lastWithdrawAmount functions, and share them in your final submission. (10 points)
