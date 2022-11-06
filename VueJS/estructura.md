option api
```js
export default{
	name: 'ComponentName',
	props: {...}, //Props
	data() {...}, //Data variables
	computed: {...}, //Computed propr
	methods: {...}, //Functions
	mounted() {...} //Mounted hook (lifecycle)
}
```

composition
```js
export dafualt {
name:'ComponentName',
props: {...}, //Props
setup() {
	//Init logic, lifecycle hooks, etc...
		return {
			// Data, methods, computed, etc...
		}
	}
}
```
