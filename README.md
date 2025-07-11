# <name function as on wiki>

## Documentation
See [<wiki page> on the wiki](<link to wiki page>) for more information.

## Functions
### <function 1>
<describe the purpose of the function>

#### Input
<describe the input of the function, with an input example if possible>

#### Output
<describe the output of the function, with an output example if appropriate>

# Setup for Developers
## Requirements
- Visual Studio Code
- NodeJS 18.x (use NVM)
- Access to Azure Artifacts for using IoT platform NPM libraries from Azure Artifacts.
  See the [wiki](https://dev.azure.com/enecomanagedcloud/IOT%20Platform/_wiki/wikis/Eneco%20IoT%20Platform%20Wiki/231/NodeJS-development?anchor=developing-npm-modules) for more details.
- For running locally: [Azure Functions Core Tool version 4.0](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v4%2Cwindows%2Cnode%2Cportal%2Cbash)

## Local environment setup
- Create file `.npmrc` as described in the above mentioned wiki page.
- Run `nvm use` to switch to correct node version.
- Create `.npmrc` file (see requirements)
- Run `npm ci` to install the dependencies.
- Run `npm run dev:prepare` to activate the conventional commit rules locally. 

## Unittests
<If a local database is needed to to the unittests, like PostgreSQL or SQL server, mention it here. Plus a reference to the approriate database wiki and the minimum schema version of the database which is required>
Run `npm test` in the project rootfolder.

# Setup for Deployment
## Environment variables
The following environment variables need to be set:
<list of required environment settings to be able to run the function on Azure>

Optional variables:
- DEBUG: any value if you want to have additional logging
- <plus other optional variables>

This environment variables should also be set in the `.env` for local testing and to `local.settings.json` for local running.
Get the correct values from Keyvault.

Example for local development

```env
```

## Environment setup for running locally
Create a `local.settings.json` file with the following contents when you want to run the function locally (not required):

```json
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "node",
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "WEBSITE_SITE_NAME":"<name function>-local"
  }
}
```
Start the local function by pressing F5 in vscode (this includes debug mode) or by running `func start` in the root of this folder.


## Version History

| Version | Date       | Notes |
|---------|------------|-------|
<version history>