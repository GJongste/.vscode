# Ketenstandaard Api REST Client

[https://bitbucket.org/3xt/ketenstandaard-api-rest-client](https://bitbucket.org/3xt/ketenstandaard-api-rest-client)

This Ketenstandaard Api REST Client can be used to see the Ketenstandaard Api REST services in action.

## v1.0

* Initial version.

## Prerequisites

* client_id/client_secret from Ketenstandaard
* Ketenstandaard account credentials (username/password)
* Installation of git
* Installation of Visual Studio Code
* Installation of the REST Client extension

## Getting Started

* Get a client_id/client_secret at [https://www.ketenstandaard.nl/](https://www.ketenstandaard.nl/)
* Download and install git [git](https://git-scm.com/downloads)
* Download and install Visual Studio Code. [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
* Start Visual Studio Code. Search for and install extension [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
* Open a command prompt and clone this repository with git
* Open the newly created directory with Visual Studio Code

## Settings
Some variables are used from the settings file. 
* Create a settings.json file in the directory .vscode --> ".vscode/settings.json"
* Copy this into the setting.json file:

```json
{
"rest-client.environmentVariables": {
	"production": {
		"authUrl": "https://authorize.ketenstandaard.nl",
		"baseUrl": "https://api.ketenstandaard.nl/api/v1",
		"client_id": "",
		"client_secret": ""
	}
}
}
```
* Fill in the client_id/client_secret you received from Ketenstandaard

## Start you first request
* Open one of the .http files in Visual Studio Code
* Switch the environment in the Status bar to "production"
* Click on "Send Request" in the "ClientCredentialsGrant". Or place your cursor between ### and ### and use the keyboard shortcut ctrl-alt-r. This service will fetch an access-token that will be used in subsequential requests.
* Systematic.http implements the Authorization Code Flow. This is a two step proces. 1. Click on "Send Request" in the "login" to login as an end user (opens external web browser). 2. Copy/paste the authorization code value in the return URL, replacing [INSERT_CODE_FROM_RETURNURL] under the "AuthorizationCode" segment en click on "Send Request". For the Systematic API the ClientCredentialsGrant is only available on request for development/testing.
* Next click on "Send Request" above one of the service calls.

