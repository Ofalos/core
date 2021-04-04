# Ofaloso Core
Building UI components can be quite repititive and often require you deploying and redeploying changes which can be quite boring.
Ofalos core allow you to build your UI components from JSON. This opens doors for you to build UI quicker, and just work on unique business
logic. It also opens door for hosting your page definition elsewhere and updating the layout of your page, forms by non-technical persons.

## Table of contents
1. [Setup](#setup)
1. [Usage](#usage)


## Setup
To get started using @ofalos/core, first install it 
```bash
yarn add @ofalos/core

// or with npm
npm i @ofalos/core
```

then you can proceed to import it in your code as
```js
...
import OfalosCore from '@ofalos/core'

Vue.use(OfalosCore)
```

## Usage
To use ofalos core to build a page, you build a json with the following format

```js
const page = [
  {
    "tag": "h1",
    "content": "Ofalos demostration"
  },
  {
    "tag": "h3",
    "content": "This is the subheading"
  }
]
```

then in your vue code, you pass this page as a `content` attribute
```vue
<ofalos-core :content="page" />
```


