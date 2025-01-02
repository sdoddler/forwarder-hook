<img width="575" alt="forwarderhook" src="https://github.com/user-attachments/assets/56a8e15e-388e-47a1-ab93-8b9fa0893764" />

## Forwarder Hook for Xahau Network
This is a small example to demonstrate the use of a working hook in Xahau. The hook is programmed in C. It is recommended for educational purposes only. The creator is not responsible for any problems it may cause.

## What does the hook forwarder do?

The hook is installed on an account. Once installed, every time the account receives a payment through a Payment or URITokenBuy transaction type, it will be distributed among the accounts stored in the account namespace. If there are no accounts in the namespace, it will do nothing.

## How to add addresses?

The hook allows up to 10 addresses to which the amounts received can be distributed in equal parts. They will be registered with an identifier from 00 to 09. The addresses must be converted to Account ID. To do this you can use the following services:

- https://hooks.services/tools/raddress-to-accountid 
- https://transia-rnd.github.io/xrpl-hex-visualizer

To check if you are doing it right, address: rBnGX5KRERL2vMtZU2hDpF4osbhvichmvn will be translated to 6E7FE292948037180F3646CC248FAF2BCACD59893C

To add an account we must create an Invoke transaction from the hook account and add the following Hook parameters:

ADD with the AccountID
NUM with the position we want between 00 to 09

Example:

ADD: 6E7FE2948037180F3646CC248FAF2BCACD59893C
NUM: 00

## How to delete addresses?

To delete you have to create an Invoke transaction from the hook account and use as parameter DEL and the position between 00 to 09. In case there is any address registered with that identifier, it will delete it.

DEL with the position we want to delete between 00 to 09

Example:

NUM: 01

## Attention

This hook or other installed hooks could change the expected result. So it is important to pre-test this and other hooks on Testnet before using it on Mainnet.
