# Transaction

[index.js:48-307](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L48-L307 "Source code on GitHub")

Creates a new transaction object.

**Parameters**

-   `data` **Buffer or Array or Object** a transaction can be initiailized with either a buffer containing the RLP serialized transaction or an array of buffers relating to each of the tx Properties, listed in order below in the exmple.Or lastly an Object containing the Properties of the transaction like in the Usage example.For Object and Arrays each of the elements can either be a Buffer, a hex-prefixed (0x) String , Number, or an object with a toBuffer method such as Bignum
    -   `data.chainId` **Number** EIP 155 chainId - mainnet: 1, ropsten: 3
    -   `data.gasLimit` **Buffer** transaction gas limit
    -   `data.gasPrice` **Buffer** transaction gas price
    -   `data.to` **Buffer** to the to address
    -   `data.nonce` **Buffer** nonce number
    -   `data.data` **Buffer** this will contain the data of the message or the init of a contract
    -   `data.v` **Buffer** EC recovery ID
    -   `data.r` **Buffer** EC signature parameter
    -   `data.s` **Buffer** EC signature parameter
    -   `data.value` **Buffer** the amount of ether sent

**Properties**

-   `raw` **Buffer** The raw rlp encoded transaction

**Examples**

```javascript
var rawTx = {
  nonce: '0x00',
  gasPrice: '0x09184e72a000',
  gasLimit: '0x2710',
  to: '0x0000000000000000000000000000000000000000',
  value: '0x00',
  data: '0x7f7465737432000000000000000000000000000000000000000000000000000000600057',
  v: '0x1c',
  r: '0x5e1d3a76fbf824220eafc8c79ad578ad2b67d01b0c2425eb1f1347e8f50882ab',
  s: '0x5bd428537f05f9830e93792f90ea6a3e2d1e 0e84952dd96edbae9f658f831ab13'
};
var tx = new Transaction(rawTx);
```

## getBaseFee

[index.js:268-274](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L268-L274 "Source code on GitHub")

the minimum amount of gas the tx must have (DataFee + TxFee + Creation Fee)

Returns **BN** 

## getChainId

[index.js:179-181](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L179-L181 "Source code on GitHub")

returns chain ID

Returns **Buffer** 

## getDataFee

[index.js:255-262](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L255-L262 "Source code on GitHub")

The amount of gas paid for the data in this tx

Returns **BN** 

## getSenderAddress

[index.js:187-194](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L187-L194 "Source code on GitHub")

returns the sender's address

Returns **Buffer** 

## getSenderPublicKey

[index.js:200-205](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L200-L205 "Source code on GitHub")

returns the public key of the sender

Returns **Buffer** 

## getUpfrontCost

[index.js:280-284](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L280-L284 "Source code on GitHub")

the up front amount that an account must have for this transaction to be valid

Returns **BN** 

## hash

[index.js:147-173](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L147-L173 "Source code on GitHub")

Computes a sha3-256 hash of the serialized tx

**Parameters**

-   `includeSignature` **[Boolean]** whether or not to inculde the signature (optional, default `true`)

Returns **Buffer** 

## sign

[index.js:235-249](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L235-L249 "Source code on GitHub")

sign a transaction with a given private key

**Parameters**

-   `privateKey` **Buffer** 

## toCreationAddress

[index.js:138-140](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L138-L140 "Source code on GitHub")

If the tx's `to` is to the creation address

Returns **Boolean** 

## validate

[index.js:291-306](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L291-L306 "Source code on GitHub")

validates the signature and checks to see if it has enough gas

**Parameters**

-   `stringError` **[Boolean]** whether to return a string with a description of why the validation failed or return a Boolean (optional, default `false`)

Returns **Boolean or String** 

## verifySignature

[index.js:211-229](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L211-L229 "Source code on GitHub")

Determines if the signature is valid

Returns **Boolean** 

## from

[index.js:116-120](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L116-L120 "Source code on GitHub")

**Properties**

-   `from` **Buffer** (read only) sender address of this transaction, mathematically derived from other parameters.

## serialize

[index.js:109-109](https://github.com/PchainJS/pchainjs-tx/blob/81be6d085af8ea7efc8af96be44598c29adaac77/index.js#L109-L109 "Source code on GitHub")

Returns the rlp encoding of the transaction

Returns **Buffer** 
