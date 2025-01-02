## Forwarder Hook for Xahau Network
This is a small example to demonstrate the use of a working hook in Xahau. The hook is programmed in C. It is recommended for educational purposes only. The creator is not responsible for any problems it may cause.

## What does the hook forwarder do?

The hook is installed on an account. Once installed, every time the account receives a payment through a Payment or URITokenBuy transaction type, it will be distributed among the accounts stored in the account namespace. If there are no accounts in the namespace, it will do nothing.

## How to add addresses?

The hook allows up to 10 addresses to which the amounts received can be distributed in equal parts. They will be registered with an identifier from 00 to 09. The addresses must be converted to Account ID. To do this you can use the following services:

- https://hooks.services/tools/raddress-to-accountid 
- https://transia-rnd.github.io/xrpl-hex-visualizer

To check if you are doing it right, address: rBnGX5KRERL2vMtZU2hDpF4osbhvichmvn will be translated to 6E7FE292948037180F3646CC248FAF2BCACD59893C
