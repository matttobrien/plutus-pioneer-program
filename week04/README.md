## Overview
The homework for this week was to implement 'payTrace' in 'Homework.hs'. We were given an introduction to Haskell's Monads, the Contract Monad in Plutus, and how to use EmulatorTrace to run smart contracts locally without the Plutus Playground.

## Homework
The 'payContract' smart contract takes in the data PayParams, which contains a wallet address and an amount of lovelace, and then pays the amount of lovelace to the recipient wallet address. The goal of this homework was to work with EmulatorTrace to invoke the pay endpoint of payContract on Wallet 1 twice, each time with Wallet 2 as recipient, but with amounts given by the two arguments. This can be achieved by invoking activateContractWallet and passing it wallet1 and payContract. Next we have to call the pay endpoint using callEndpoint, here we can define the fields in PayParams. This was done twice, one call for each amount argument. The second part of the homework was to catch and log the exception thrown when the amount Ada in the ppLovelace field is greater than the amount in the user's wallet. This can be done in-line using the Contract.handleError function on the call to submitTx in the smart contract.