# tucan-extension
Chrome/Firefox extesnion to improve user TU Darmstadts TUCaN user interface

## WIP
### Chrome:
We can just load an unpacked extension without issues.

### Firefox:
Extensions need to be packaged into an .xpi and signed using your dev credentials before it can be installed in firefox.

#### Signing process:

Get the web-ext tool.
`$ npm install -g web-ext`

Testing: `web-ext run`

Pack the extension into a zip:
`$ web-ext build`

To be able to sign an extension, we need to create an account on the [Mozilla developer hub](https://addons.mozilla.org/en-US/developers/). Once the account is created we go to [this page](https://addons.mozilla.org/en-US/developers/addon/api/key/) and generate our API keys by clicking on the “Generate new credentials” button. Two credentials will be created: `JWT issuer` and `JWT secret`. To sign our package we must use them both and launch the following command from inside the extension directory:

`$ web-ext sign --channel=unlisted --api-key=$AMO_JWT_ISSUER --api-secret=$AMO_JWT_SECRET`

The `web-ext-artifacts` directory will be created: inside of it we will find the signed .xpi file that we can install by visiting the `about:addons` firefox page. The command will also upload our extension to our firefox developer account.

## Credits 
[JonasEmrich/Better-TUCaN](https://github.com/JonasEmrich/Better-TUCaN)
