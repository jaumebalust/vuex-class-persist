# vuex-class-persist

Note: this project is a wrapper around Vuex-Persist and is not intended to steal any of ChampionSwimmer's code.

## Usage

The usage and creation is all the same as vuex-persist, with one added parameter when calling the 

### Steps

Import it
```js
import VuexClassPersistence from 'vuex-class-persist'
```

Create an object

```js
// You will need to be able to supply an array of your classes
// to ensure they get restored from storage.
const classes = [
  class User { /* Omitted */ },
  class Profile { /* Omitted */ },
  class Example { /* Omitted */ },
  ...
]

const vuexLocal = new VuexClassPersistence({
    storage: window.localStorage
}, classes)
```

Use it as Vue plugin. (in typescript)

```typescript
const store = new Vuex.Store<State>({
  state: { ... },
  mutations: { ... },
  actions: { ... },
  plugins: [vuexLocal.plugin]
})
```

(or in Javascript)
```js
const store = {
  state: { ... },
  mutations: { ... },
  actions: { ... },
  plugins: [vuexLocal.plugin]
}
```

