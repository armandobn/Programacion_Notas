# Token
## Indice
1. [[#Crear Token]]
2. [[#Generar Token]]


## Crear Token
## Generar Token

Funcion para poder generar los tokens y mandarlo a quien queramos, debemos de utilizar de dos cosas:
- hive.broadcast.custom_json
-  Actions -> Tokens -> Action: **issue**

Documentacion: [[Documentacion#^765aa4|Hive-Js#hive.broadcast.custom_json]] 

```js
hive.broadcast.customJson(wif, requiredAuths, requiredPostingAuths, id, json, function(err, result) {
  console.log(err, result);
});
```

Action: **issue**
Emitir tokens a una cuenta (solo puede ser activado por la cuenta que creó el token)

Documentacion: [https://hive-engine.github.io/engine-docs/actions#actions-tokens-issue]
`Documentacion: JSON`
```
{
  "contractName": "tokens",
  "contractAction": "issue",
  "contractPayload": {
    "symbol": "YOUR_SYMBOL",
    "to": "alice",
    "quantity": "10000"
  }
}
```

`Estrutura`
```js
hive.broadcast.customJson(
	'ACTIVEKEY', //CLAVE ACTIVA/ACTIVE PRIVATE KEY(Se encunetra en HIVE KEYCHAIN)
	['CONTRACT_CREATOR'], //AQUI TU CUENTA DE CREACION DEL TOKEN
	[],
	"Hive-Engine Chain ID",//Hive-Engine Chain ID
	{contractName: "tokens",
	contractAction: "issue",
	contractPayload: {
		symbol: '', // EL SïMBOLO DE TU TOKEN
		to: '', // LA CUENTA DE DESTINO
		quantity: "1.000", // //LA CANTIDAD A EVNIAR,CONDICION:(1.000)(Type:Texto)
		},
	},
	async function (err, result) {
		if (err) {
			console.log(err, 'err')
		} else {
			console.log(result, 'result')
		}
	}
);
```

`Mi funcion creada`
```js
async function generateToken(hive, ACTIVEKEY, CONTRACT_CREATOR, HIVE_ENGINE_CHAIN_ID, token, user, quantity) {
	let json = {
		contractName: "tokens",
		contractAction: "issue",
		contractPayload: {
	    symbol: token, // EL SïMBOLO DE TU TOKEN
		to: user, // LA CUENTA DE DESTINO
		quantity: quantity, // CANTIDAD SIEMPRE CON AL MENOS TRES DECIMALES AUNQUE SEAN CEROS
		},
	};
	return new Promise((resolve, reject) => {
		hive.broadcast.customJson(
			ACTIVEKEY, //ACTIVEKEY
	        [CONTRACT_CREATOR], //CONTRACT_CREATOR
			[],
			HIVE_ENGINE_CHAIN_ID, //Hive-Engine Chain ID
			JSON.stringify(json),
			async function (err, result) {
	            if (err) {
					console.log(err);
					resolve(
					await generateToken(hive, token, quantity, user)
					);
				} else {
					console.log(result);
					resolve(result);
				}
			}
	);
	});
};

const HIVE_JS = hive;// hive es la api de HIVE-JS para poder llamarlo
const ACTIVEKEY = '';//CALVE ACTIVA/ACTIVE PRIVATE KEY(Se encunetra en HIVE KEYCHAIN)
const CONTRACT_CREATOR = ""; //AQUI TU CUENTA DE CREACION DEL TOKEN
const HIVE_ENGINE_CHAIN_ID = ""; //Hive-Engine Chain ID
const TOKEN = ""; // EL SïMBOLO DE TU TOKEN
const USER = "";// LA CUENTA DE DESTINO
const QUANTITY = "1.000"; //LA CANTIDAD A EVNIAR,CONDICION:(1.000)(Type:Texto)
generateToken(HIVE_JS, ACTIVEKEY, CONTRACT_CREATOR, HIVE_ENGINE_CHAIN_ID, TOKEN, USER, QUANTITY).then(v => { console.log(v) });
```

`Mi maestro lo escribio`
```
const generateToken = async (hive, token, quantity, user, transaction_id) => {
  let json = {
    contractName: "tokens",
    contractAction: "issue",
    contractPayload: {
      symbol: token,
      to: user,
      quantity: "" + quantity,
    },
  };

  return new Promise((resolve, reject) => {
    hive.broadcast.customJson(
      ACTIVEKEY,
      [CONTRACT_CREATOR],
      [],
      "ssc-mainnet-hive",
      JSON.stringify(json),
      async function (err, result) {
        if (err) {
          resolve(
            await generateToken(hive, token, quantity, user, transaction_id)
          );
        } else {
          resolve(result);
        }
      }
    );
  });
}; 
```