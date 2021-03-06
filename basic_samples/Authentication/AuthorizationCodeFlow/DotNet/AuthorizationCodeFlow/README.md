# Authorization Code Flow + PKCE Sample and Test

This client uses the OAuth2/OIDC Authorization Code Flow + PKCE to obtain an access token. See the root folder [README](../../../README.md) for more information about this flow.

## Requirements

- .Net Core 2.2.1 or later
- Web Browser with Javascript enabled
  - You will need Google Chrome if you want to run the automated test

## Running the sample client

### Prerequisites

- Register an AuthorizationCode client in OCS and ensure that the registered client in OCS contains `http://localhost:5004/callback.html`, and `http://localhost:5004/silent-refresh.html` in the list of RedirectUris.
- Replace the placeholders in the [config](./wwwroot/config.js) file with your TenantID and ClientID obtained from registration.

You can learn more about the config options [here](https://github.com/IdentityModel/oidc-client-js/wiki#other-optional-settings).

### Using Visual Studio

- Load the .csproj in this directory
- Rebuild project
- Click Start to run it
- Pres the *login* button in the browser
- Follow the prompts in the web browser to log in
  - Keep in mind that if you are already logged in with the same account in the browser, you will not have to log in again.

### Using Command Line

- Make sure you have the install location of dotnet added to your path
- Run the following command from the location of this project:

```shell
dotnet run
```

- Follow the prompts in the web browser to log in
- Return to the application after having been authenticated in the browser

## Running the automated test

### Prerequisites

- Make sure the sample client in the previous section above is running.
- Make sure Google Chrome is the default browser on your test system.
- Download the ChromeDriver version from `http://chromedriver.storage.googleapis.com/index.html` corresponding to the version of Google Chrome that is installed. Set the environmental variable ChromeWebDriver to the directory containing the Chrome Driver executable).  
- Update the [appsettings.json](../AuthorizationCodeFlowTest/appsettings.json) with the username and password for the Microsoft account that will be used to log in. The test is only written to work with a personal Microsoft account and must only prompt for only username followed by password (no Two-Factor authentication or other consent or informational prompts). Also if the location of the sample application has been modified then change the url location.

### Using Visual Studio 

- Load the .csproj from the AuthorizationCodeFlowTest directory above this in Visual Studio
- Update the appsettings.json to the appropriate url for the location the AuthorizationCodeFlow app will run, as well as username and password for the Microsoft account that will be used to log in.
- Rebuild project
- Open Test Explorer and make sure there is one test called Test1 showing
- Run the test

### Using Command Line

- Make sure you have the install location of dotnet added to your path
- Run the following command from the location of the AuthorizationCodeFlowTest project (you may need to run as Administrator for the test to use the Chrome Driver):

```shell
dotnet test
```

&nbsp;

[![Build Status](https://osisoft.visualstudio.com/Engineering%20Incubation/_apis/build/status/All_Test/Auth_PKCE_DotNet?branchName=master)](https://osisoft.visualstudio.com/Engineering%20Incubation/_build/latest?definitionId=4920&branchName=master)

For the general steps or switch languages see the Task  [ReadMe](../../../)<br />
For the main OCS page [ReadMe](https://github.com/osisoft/OSI-Samples-OCS)<br />
For the main samples page on master [ReadMe](https://github.com/osisoft/OSI-Samples)