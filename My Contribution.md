# Changes Made

Here's the summary containing all the changes done to the `gasChallenge.sol` and `test_gasChallenge.js` files, as well as the addition of the `gas-report.txt` file:

## gasChallenge.sol

- Applied Fixed-Size Array Technique: Changed the `numbers` array from dynamic to fixed-size with length 10.

```solidity
// Before
uint[] numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// After
uint[10] numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```

- Applied Caching of State Variable: In the `optimizedFunction`, cached the `numbers` array to reduce state variable reads.

```solidity
// Before
function optimizedFunction() public {
    // Original code here
}

// After
function optimizedFunction() public {
    uint[10] memory cachedNumbers = numbers; // Cached the numbers array
    // Original code here using cachedNumbers instead of numbers
}
```

- Applied Unchecked Block: Used the `unchecked` block to modify the `cachedNumbers` array without bounds checking.

```solidity
// Before
function optimizedFunction() public {
    // Original code here
}

// After
function optimizedFunction() public {
    uint[10] memory cachedNumbers = numbers; // Cached the numbers array
    unchecked {
        // Original code here using unchecked block for array modification
    }
}
```

- Applied Different For Loop Increment Syntax: Used `++i` instead of `i++` in the for loop for gas optimization.

```solidity
// Before
function optimizedFunction() public {
    // Original code here
}

// After
function optimizedFunction() public {
    uint[10] memory cachedNumbers = numbers; // Cached the numbers array
    unchecked {
        for (uint i = 0; i < cachedNumbers.length; ++i) {
            // Original code here
        }
    }
}
```

## test_gasChallenge.js

- Added Unit Test for "Check Sum Of Array": Implemented a unit test to check if the sum of the array is 0 after running the `optimizedFunction()`.

```javascript
describe("Check Sum Of Array", () => {
    it("Should return 0", async () => {
        const sumOfArray = await gas_contract.getSumOfArray();
        expect(sumOfArray).to.equal(0);
    });
});
```

## Added gas-report.txt

- Created a new file named `gas-report.txt` to capture gas consumption statistics after running the tests.

```
·-----------------------------------------|----------------------------|-------------|-----------------------------·
|          Solc version: 0.8.18           ·  Optimizer enabled: false  ·  Runs: 200  ·  Block limit: 30000000 gas  │
··········································|····························|·············|······························
|  Methods                                                                                                         │
·················|························|··············|·············|·············|···············|··············
|  Contract      ·  Method                ·  Min         ·  Max        ·  Avg        ·  # calls      ·  usd (avg)  │
·················|························|··············|·············|·············|···············|··············
|  gasChallenge  ·  notOptimizedFunction  ·           -  ·          -  ·      58727  ·            1  ·          -  │
·················|························|··············|·············|·············|···············|··············
|  gasChallenge  ·  optimizedFunction     ·       44193  ·      57755  ·      50974  ·            2  ·          -  │
·················|························|··············|·············|·············|···············|··············
|  Deployments                            ·                                          ·  % of limit   ·             │
··········································|··············|·············|·············|···············|··············
|  gasChallenge                           ·           -  ·          -  ·     417076  ·        1.4 %  ·          -  │
·-----------------------------------------|--------------|-------------|-------------|---------------|-------------·
```
