# sDoddler's Remix

<img width="575" alt="forwarderhook" src="https://github.com/user-attachments/assets/56a8e15e-388e-47a1-ab93-8b9fa0893764" />

## Percentage based Forwarder Hook for Xahau Network
This hook resends a percentage of the amount from a payment received or a URI buy to a specific destination. It also specifies a minimum amount of XAH received in drops.

 It could easily be expanded to add other accounts & differing percentages. 
 Be careful - if your percentages go over 1.0 then you will be spending **EXTRA** XAH

 This is my first hook - exercise caution while using though it has been tested.

 This hook was heavily inspired by the tutorial here:
[SimplePayment](https://github.com/technotip/HookTutorials/blob/main/SimplePayment.c) &  [Ekiserrepe's Forwarder hook](https://github.com/Ekiserrepe/forwarder-hook)

 This is being used in tandem with the Xah Elementals Game - more info can be found via:
[TheShillverse on X](x.com/theshillverse)
[Elementals on TheShillverse](theshillverse.com/elementals)
**Please use new accounts to test this hook and test everything beforehand on Testnet just in case. I am not responsible for any losses. Create your own code if you are not sure.**

## What does the Forwarder Hook do?

The hook is installed on an account. Once installed, every time the account receives a payment through a Payment or URITokenBuy transaction type, it will be distribute the set percentage to the account provided. 

## Attention

This hook or other installed hooks could change the expected result. So it is important to pre-test this and other hooks on Testnet before using it on Mainnet.

## How to install the Forwarder Hook on Testnet?

Do not install this hook via it's Hook Hash - it needs to be recompiled so the account can be changed. Compiling is made easy via the [Hooks Builder](https://hooks-builder.xrpl.org/)

Once compiled you can install it via:

1. [XRPLWin Hook Install Tool](https://xahau-testnet.xrplwin.com/tools/hook/from-hash)

2. Or you can do it sending the transaction below:

`

    {  
    "Account": "rU3BHbWv4XknyNbDYnPtcv4XUiRUQ8pUst",
        "TransactionType": "SetHook",
        "Flags": 0,
        "NetworkID":21338, // Testnet
        "Hooks": [
            {
                "Hook": {
                    "CreateCode": "0061736D01000000012C0760..... {COMPILED HEX CODE HERE}",
                    "Flags": 1,
                    "HookOn": "FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF7FFFFFFFFFFFF7FFFFFBFFFFE",
                    "HookNamespace": "08BDF258525D0852D6BEE2849D8DACC2A08F1C74911C56EE97AE31CBE0FC75B8", // shillverseForwarder namespace
                    "HookApiVersion": 0
                }
            }
        ]
    }`

## How to uninstall the Forwarder Hook on Mainnet/Testnet?

    const prepared = {
      "TransactionType": "SetHook",
      "Account": your_account_address,
      "Flags": 0,
      Hooks:
    [        
        {                        
            Hook: {
                CreateCode: "",
                Flags: 1,
            }
        }
    ],
      ...networkInfo.txValues,
    };

## How to change addresses / percentages / minimum drops?

You can replace the master account variable at the top of the script - using the tools below to gather the correct data- 

- https://hooks.services/tools/raddress-to-accountid 
- https://transia-rnd.github.io/xrpl-hex-visualizer

Verification Example:
rPNKEiCGzPd53MhqjkQJrtJKLLVWi6bav1 becomes
{ 0xF3U, 0xD7U, 0x6AU, 0x09U, 0x64U, 0x7CU, 0x81U, 0x3DU, 0x03U, 0x63U, 0xE6U, 0xF8U, 0x20U, 0xBBU, 0x7CU, 0x79U, 0x7DU, 0x2EU, 0xB7U, 0x04U }

Changing percentages and minimum drops is as easy as changing the variables `percentage01` `minimum_drops`

## Last Thoughts
Created by @[TheShillverse](https://x.com/theShillverse) you can find out more about The Shillverse @ [TheShillverse.com](https://theshillverse.com)
Credit to @[ekiserrepe](https://x.com/ekiserrepe). You can find more of his projects on [ekiserrepe.com](https://www.ekiserrepe.com)
