Para crear token y NFTs es en [Trivaldex](https://tribaldex.com/nfts/manage)
## Requisitos
	- Pagar una comision de 100 BEE


## Token


```js
let propAccount = "AQUI TU CUENTA DE CREACION DEL TOKEN";
let actPrivKey = "AQUI VA LA ACTIVE PRIVATE KEY";
let json = {
    contractName: "tokens",
    contractAction: "issue",
    contractPayload: {
        symbol: 'HKLEARN', // EL SïMBOLO DE TU TOKEN
        to: 'apzyx', // LA CUENTA DE DESTINO
        quantity: "1.000", // CANTIDAD SIEMPRE CON AL MENOS TRES DECIMALES AUNQUE SEAN CEROS
    },
};

console.log('2')
return new Promise((resolve, reject) => {
    hive.broadcast.customJson(
        actPrivKey, //ACTIVEKEY
        [propAccount], //CONTRACT_CREATOR
        [],
        "ssc-mainnet-hive",
        JSON.stringify(json),
        async function (err, result) {
            if (err) {
                console.log(err, 'err')
                reject(err);
            } else {
                console.log(result, 'result')
                resolve(result);
            }
        });

});
```

### d 
```
setProperties:
Edits one or more data properties on one or more instances of an NFT.

requires active key: no

can be called by: Steem account or smart contract on the authorized list of editing accounts/contracts for the data properties in question

parameters:

symbol (string): symbol of the token (uppercase letters only, max length of 10)
(optional) fromType (string): indicates whether this action is being called by a Steem account or a smart contract. Can be set to user or contract. If not specified, defaults to user. Note that a smart contract can still set this to user in order to execute the action on behalf of a Steem account rather than the calling contract itself.
nfts (array of object): the data properties to set and their corresponding NFT instance ID. Should be formatted as follows: [ {"id":"1", "properties": {"name1":"value1","name2":"value2",...}}, {"id":"2", "properties": {"name1":"value1","name2":"value2",...}, ...} ]
A maximum of 50 tokens can be edited in a single call of this action.

examples:
{
    "contractName": "nft",
    "contractAction": "setProperties",
    "contractPayload": {
        "symbol": "TESTNFT",
        "nfts": [
            { "id":"573", "properties": {
                "color": "red",
                "level": "2"       // a number property can be set using either a string or number
               }
            },
            { "id":"301", "properties": {
                "level": 3         // a number property can be set using either a string or number
               }
            }
        ]
    }
}

{
    "contractName": "nft",
    "contractAction": "setProperties",
    "contractPayload": {
        "symbol": "TESTNFT",
        "fromType":"contract",
        "nfts": [
            { "id":"1284", "properties": {
                "isFrozen": true
               }
            }
        ]
    }
} 
```

## NFTs
Nota:
- Tribaldex solo ofrece 3 propiedades gratis en los NFTs, a partir de esto habrá que pagar por cada propiedad añadida. Lo que recomendamos es añadir propiedades al backend que les dará más control y verstailidad sobre los NFTs.
- Las propiedades deberán colocarlas en READ:ONLY “NO”, si colocan el sí lo que va a pasar es que no van a poder modificar las propiedades del NFT y probablemente tengan que gastar 100 BEE más en otro contrat