# Transaction

[index.js:48-315](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L48-L315 "Source code on GitHub")

Creates a new transaction object.

**Parameters**

-   `data` **Buffer or Array or Object** a transaction can be initiailized with either a buffer containing the RLP serialized transaction or an array of buffers relating to each of the tx Properties, listed in order below in the exmple.Or lastly an Object containing the Properties of the transaction like in the Usage example.For Object and Arrays each of the elements can either be a Buffer, a hex-prefixed (0x) String , Number, or an object with a toBuffer method such as Bignum
    -   `data.chainId` **String** mainChain :"pchain",childChain 1 :"child_0"
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

[index.js:276-282](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L276-L282 "Source code on GitHub")

the minimum amount of gas the tx must have (DataFee + TxFee + Creation Fee)

Returns **BN** 

## getChainId

[index.js:181-183](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L181-L183 "Source code on GitHub")

returns chain ID

Returns **Buffer** 

## getDataFee

[index.js:263-270](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L263-L270 "Source code on GitHub")

The amount of gas paid for the data in this tx

Returns **BN** 

## getSenderAddress

[index.js:189-196](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L189-L196 "Source code on GitHub")

returns the sender's address

Returns **Buffer** 

## getSenderPublicKey

[index.js:202-207](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L202-L207 "Source code on GitHub")

returns the public key of the sender

Returns **Buffer** 

## getUpfrontCost

[index.js:288-292](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L288-L292 "Source code on GitHub")

the up front amount that an account must have for this transaction to be valid

Returns **BN** 

## hash

[index.js:149-175](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L149-L175 "Source code on GitHub")

Computes a sha3-256 hash of the serialized tx

**Parameters**

-   `includeSignature` **[Boolean]** whether or not to inculde the signature (optional, default `true`)

Returns **Buffer** 

## sign

[index.js:243-257](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L243-L257 "Source code on GitHub")

sign a transaction with a given private key

**Parameters**

-   `privateKey` **Buffer** 

## toCreationAddress

[index.js:140-142](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L140-L142 "Source code on GitHub")

If the tx's `to` is to the creation address

Returns **Boolean** 

## validate

[index.js:299-314](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L299-L314 "Source code on GitHub")

validates the signature and checks to see if it has enough gas

**Parameters**

-   `stringError` **[Boolean]** whether to return a string with a description of why the validation failed or return a Boolean (optional, default `false`)

Returns **Boolean or String** 

## verifySignature

[index.js:213-237](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L213-L237 "Source code on GitHub")

Determines if the signature is valid

Returns **Boolean** 

## from

[index.js:116-120](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L116-L120 "Source code on GitHub")

**Properties**

-   `from` **Buffer** (read only) sender address of this transaction, mathematically derived from other parameters.

## serialize

[index.js:109-109](https://github.com/PchainJS/pchainjs-tx/blob/eba1529794ee6a8d097e9e122d24fb7af961ef70/index.js#L109-L109 "Source code on GitHub")

Returns the rlp encoding of the transaction

Returns **Buffer** 
