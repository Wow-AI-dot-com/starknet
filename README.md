AIxBlock Cairo SmartContract
=

1. Adding Account

```
$ sncast account add --name <deployer> --address <account_address> --type argent --private-key <private_key> --add-profile sepolia
```

2. Declare Contracts

```
$ sncast -p sepolia declare --fee-token eth --contract-name AIxBlockToken
$ sncast -p sepolia declare --fee-token eth --contract-name AIxBlockReward
```

3. Deploy Contracts

```
$ sncast -p sepolia deploy --fee-token eth --class-hash <class_hash> -c <list_params>
```

### Deployment on Sepolia
- AIxBlockToken: [0x0422372C7eAE5Dc07398A517431447f343DFe19dc77Df4f4BCC30732465e57E1](https://sepolia.starkscan.co/token/0x0422372C7eAE5Dc07398A517431447f343DFe19dc77Df4f4BCC30732465e57E1)
- AIxBlockReward: [0x00fA9258877063c145B6B6BF30E28bB98fC10AFD318551aF958A01Df2F74d5bD](https://sepolia.starkscan.co/contract/0x00fA9258877063c145B6B6BF30E28bB98fC10AFD318551aF958A01Df2F74d5bD)

### User flow
- This contract applied [SNIP-12](https://github.com/starknet-io/SNIPs/blob/main/SNIPS/snip-12.md) for offchain message verification.
- Users can request the backend to generate a claim along with its signature, which is signed by the appropriate signer.
- The contract verifies the signature, and if it is valid, sends a reward token to the sender.