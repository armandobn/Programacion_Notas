# NFTs
## Indice
1. [[#Crear NFTs]]
2. [[#Generar NFTs]]


## Crear NFTs
## Generar NFTs
Funcion para poder generar los NFTs y mandarlo a quien queramos
Documentacion: [https://hive-engine.github.io/engine-docs/actions#actions-nft-issueMultiple]
`Documentacion: JSON`
```json
// issue 3 tokens from contract -> a combination of users & contracts
{
   "contractName":"nft",
   "contractAction":"issueMultiple",
   "contractPayload":{
      "instances":[
         {
            "fromType":"contract",
            "symbol":"TSTNFT",
            "to":"aggroed",
            "feeSymbol":"ENG",
            "properties":{
               "level":0
            }
         },
         {
            "fromType":"contract",
            "symbol":"TSTNFT",
            "to":"dice",
            "toType":"contract",
            "feeSymbol":"ENG",
            "lockTokens":{
               "ENG":"5.75"
            }
         },
         {
            "fromType":"contract",
            "symbol":"TSTNFT",
            "to":"marc",
            "feeSymbol":"PAL"
         }
      ]
   }
}
```

`Mi funcion creada`
```js
async function createNfts(hive, user, quantity) { //max 10 nfts
	let instances = [];
	const properties = {
		LVL: 1,
		AGIL: 10,
		CREATIVE: 15,
	};
	const instance = {
		symbol: UTILITY_TOKEN_SYMBOL,
		to: user,
		feeSymbol: "BEE", //BEE o PAL (BEE es mas caro)
		properties,
	};
	for (let index = 0; index < quantity; index++) {
		instances.push(instance);
	}
	let json = {
		contractName: "nft",
		contractAction: "issueMultiple",
		contractPayload: {
		instances: instances,
		},
	};

	return new Promise((resolve, reject) => {
		hive.broadcast.customJson(
			ACTIVEKEY,
			[CONTRACT_CREATOR],
			[],
			HIVE_ENGINE_CHAIN_ID,
			JSON.stringify(json),
			function (err, result) {
				if (err) {
					console.log(err);
					reject(err);
				} else {
					console.log(result);
					resolve(result);
				}
			}
		);
	});
}

const HIVE_JS = hive;// hive es la api de HIVE-JS para poder llamarlo
const ACTIVEKEY = '';//CALVE ACTIVA/ACTIVE PRIVATE KEY(Se encunetra en HIVE KEYCHAIN)
const CONTRACT_CREATOR = "misticogama"; //AQUI TU CUENTA DE CREACION DEL TOKEN
const HIVE_ENGINE_CHAIN_ID = "ssc-testnet-hive"; //Hive-Engine Chain ID
const UTILITY_TOKEN_SYMBOL="RPT"; // EL SïMBOLO DE TU TOKEN
const USER = "misticogama";// LA CUENTA DE DESTINO
const QUANTITY = 2; //LA CANTIDAD A EVNIAR,CONDICION:(1.000)(Type:Texto)

createNfts(HIVE_JS,USER,QUANTITY);
```