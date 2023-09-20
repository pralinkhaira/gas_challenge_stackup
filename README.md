# Gas Optimization Bounty by StackUp

![12 July - Gas Optimisation Challenge](https://github.com/clement-stackup/gas_challenge/assets/120361535/21c826fb-8776-4837-a8fe-b7040426eafa)

## Overview of Bounty

Gas is the unit of measurement for the computational work required to execute a transaction or deploy a smart contract on the Ethereum blockchain. Gas optimization techniques are important because they can significantly reduce the cost of deploying and executing smart contracts, making them more affordable for users.

This bounty challenges you to optimize a smart contract by applying the various listed gas optimization techniques. To complete this bounty, you must apply the techniques described below to the provided smart contract and write a simple unit test. Once you are done, upload your working files to your GitHub repository and submit the GitHub URL to successfully complete the bounty.

## Overview of Gas Optimization Techniques

To successfully complete this bounty, you will need to apply the following gas optimization techniques:

1. **Fixed Size over Dynamic Arrays**: Using fixed-size arrays instead of dynamic arrays can reduce gas consumption because Solidity has to perform less work to manage the memory allocation of arrays in the smart contract

2. **Caching State Variable**: Caching frequently accessed state variable can reduce gas consumption by reducing the number of storage reads required

3. **Implement Uncheck Block**: Using the `unchecked` block can reduce gas consumption by skipping certain checks such as integer overflows

4. **For Loop Increment Syntax**: Using a different for loop increment syntax can help reduce gas consumption

## Getting Started

To get started, clone this repository to your local machine and navigate to the project directory. Next, install the required dependencies.

```bash
git clone https://github.com/clement-stackup/gas_challenge.git
cd gas_challenge && npm install
```

Once you have cloned the repository and installed the necessary dependencies, open the `contracts/gasChallenge.sol` file to view the smart contract and apply the following gas optimization techniques above.

## Test Smart Contract

Next, head over to `test/test_gasChallenge.js`. You are required to write a unit test under the describe block to check that after running the gas optimized function, the sum of array is 0. Once you have implemented the test block, proceed the run the following command to test your smart contract.

```bash
npx hardhat test
```

This command will test the smart contract and compute the estimated gas cost. This is computed using the [hardhat-gas-reporter](https://www.npmjs.com/package/hardhat-gas-reporter) library.

The library has been configured to output the estimated gas costs to a new `gas-report.txt` file on your root directory. You can then view the estimated gas consumption for each of the smart contract functions in this file. The `optimizedFunction()` should output a lower gas consumption to the `notOptimizedFunction()` as shown below.

![Screenshot 2023-07-11 at 2 34 24 PM](https://github.com/clement-stackup/gas_challenge/assets/120361535/99e33517-5974-40a1-aa87-279051e58e42)

This command will also check if the sum of the array returns 0. You can refer below to view the terminal console when all tests have passed!

![image](https://github.com/clement-stackup/gas_challenge/assets/120361535/760df9a2-c9f5-4c0f-af50-7a88093bdbda)

## Bounty Submission

Upload all your working files to your GitHub Repository and submit your GitHub Repository URL to the StackUp Gas Optimization Challenge Bounty Page to successfully complete this challenge!

## Reward Update

- Just completed the Gas Optimisation Bounty Challenge by StackUp Dev and received a fantastic `$10` reward for my efforts! 
- I'm thrilled to share that I've successfully completed the Gas Optimisation Challenge! This challenge was all about enhancing a smart contract's efficiency by applying various gas optimisation techniques. These techniques are essential to reduce the costs associated with deploying and running smart contracts, ultimately making them more accessible to users.
- Screenshots :
- 1. **Rewarded Page:**

![image](https://media.licdn.com/dms/image/D4D22AQEtB_BypnJ4yQ/feedshare-shrink_2048_1536/0/1691751431331?e=1698278400&v=beta&t=B-D3Bfp5AsNtjZDKbupkahyR4FUJsqbZhia-tbY49IQ)

- 2. **Github Repo Screenshot:**

![image](https://media.licdn.com/dms/image/D4D22AQG7Yep3j8gAGA/feedshare-shrink_2048_1536/0/1691751431234?e=1698278400&v=beta&t=1YL_3qKnZrMGZZXlyE_mz1hkEtkx3xncdRmF4BqvhYs)

- 3. **Total Reward:**

![image](https://media.licdn.com/dms/image/D4D22AQG-tgC8V_Ig5g/feedshare-shrink_800/0/1691751430844?e=1698278400&v=beta&t=a1pxuGKDSOE_PtQdSapQuP5RO-S3TCqKX2KneWYOY3I)

- 4. **Amouth Credited:**

![image](https://media.licdn.com/dms/image/D4D22AQGjzrIn3D0ahQ/feedshare-shrink_800/0/1691751430962?e=1698278400&v=beta&t=FG7dYx0T962I7c9l6C4LkUWJUL0Yh5JDx2BcGmVQyaA)
