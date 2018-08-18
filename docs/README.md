# vuex-cognito-module
* [Install](/install/index.md)
* [Configure Cognito](/aws/cognito-setup.md)

## Exposed Getters

`isLoggedIn`: Boolean indicating logged in state

## Actions
### `fetchSession()`
Sets current user and session state

### `signInUser({ username: String, password: String })`
Signs in an already created user and sets user obj in localstorage with `USER` key

### `registerUser({ username: String, password: String, attributes: Object })`
Creates a new user and sets user obj in localstorage with `USER` key
* `attributes` obj should be attributes required by User Pool
```js
{
    email: 'test@test.com',
    phone_number: '+13335557777' // E.164 number convention
}
```
###### [See AWS Amplify Docs for more info](https://aws-amplify.github.io/amplify-js/media/authentication_guide#sign-up)

### `confirmUser({username: String, code: String})`
MFA verify user during registration. Used for custom registration flows.

### `resendConfirmation({ username: String })`
Resends confirmation email/code

### `forgotPassword({ username: String })`
Begins forgot password flow, and sends reset code to user

### `changePassword({username:String, code:String, newPassword: String})`
Changes `username`s password to `newPassword` given the `code` sent by `forgotPassword`

### `signOut()`
Signs out user and removes `USER` key from localstorage
