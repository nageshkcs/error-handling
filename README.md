# Alcohol Detection 

## Overview

The **AlcoholDetection** smart contract is designed to manage alcohol detection in a controlled environment, such as events or establishments. The contract allows the organizer to control participant access and detect alcohol consumption. It includes functions to calculate fines and determine whether a participant should be sent to jail based on predefined conditions.

## Contract Details

### Organizer

- The `organizer` variable stores the address of the contract organizer, ensuring only authorized individuals can interact with specific functions.

### Participant Management

- The `isParticipantAllowed` mapping tracks whether a participant is allowed based on their address.

### Events

1. **ParticipantAllowed**: Emitted when a participant is allowed by the organizer.
2. **AlcoholDetected**: Emitted when alcohol consumption is detected in a participant.

### Functions

1. **calculateFine(uint256 number)**
    - External function to calculate a fine based on a given numerical value.
    - Utilizes `assert()` to set the acceptable range from 1 to 15.
    - Utilizes `require()` to set the applicable range from 4 to 8, with a custom error message for cases outside the range.
    - Returns the calculated fine.

2. **isImprisonment(uint256 number)**
    - External function to determine whether a participant should be sent to jail.
    - Uses `revert()` to handle an exceptional case if the input number is equal to or greater than 9.
    - Returns a boolean indicating whether the participant should be sent to jail.

### Getting Started

To deploy and interact with the AlcoholDetection smart contract, follow these steps:

1. Ensure you have a compatible Ethereum development environment (e.g., Remix, Truffle).
2. Deploy the contract to the desired Ethereum network.
3. Set the organizer's address after deployment.

### Functionality

#### Participant Management

- The organizer can allow or disallow participants using the `isParticipantAllowed` mapping.

#### Fine Calculation

- Use the `calculateFine` function to determine the fine amount based on a given numerical value.
- Ensure the provided number is within the accepted range (1 to 15) using `assert()` and (4 to 8) using `require()`.

#### Imprisonment Check

- Utilize the `isImprisonment` function to check whether a participant should be sent to jail based on a numerical input.
- A `revert()` statement handles an exceptional case if the input number is 9 or greater.

### Events

- The smart contract emits events (`ParticipantAllowed` and `AlcoholDetected`) for transparency and monitoring purposes.

### Security Considerations

- Ensure only authorized addresses are granted the role of the organizer.
- Be cautious with the predefined ranges in the `calculateFine` function to avoid unintended outcomes.

## Auhtor

Nagesh  K C

nageshkc02@gmail.com

### License

This smart contract is released under the MIT License. See the [License File](LICENSE) for more details.
