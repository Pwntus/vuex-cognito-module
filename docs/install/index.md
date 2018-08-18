# vuex-cognito-module

Vuex module to interface with AWS Cognito

Install:
```bash
yarn add @vuetify/vuex-cognito-module
```

Import into your project's entry point (main.js in most Vue projects)
```js
import attachCognitoModule from '@vuetify/vuex-cognito-module';
```

Attach cognito module to the store
```js
import store from './store';
attachCognitoModule(store, {
  UserPoolId: 'your-data-here',
  IdentityPoolId: 'your-data-here',
  ClientId: 'your-data-here',
  Region: 'your-data-here',
}, 'cognito')
```
