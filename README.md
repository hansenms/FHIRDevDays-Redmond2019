# FHIR DevDays - Redmond 2019

This repository contains an example application for [FHIR DevDays 2019 on the Microsoft Redmond Campus](https://www.devdays.com/us/schedule/).

The setup includes:

1. [Azure API for FHIR](https://azure.microsoft.com/en-us/services/azure-api-for-fhir/)
1. A single page JavaScript app that accesses the FHIR API.

The Web App uses [Azure App Service Authentication](https://docs.microsoft.com/en-us/azure/app-service/overview-authentication-authorization) for authentication/authorization.

To deploy the example, you will need an [Azure Active Directory client application registration](https://docs.microsoft.com/en-us/azure/healthcare-apis/register-confidential-azure-ad-client-app) with permissions to access the "Azure Healthcare APIs" application (identifier URI: `https://azurehealthcareapis.com`) and you need to know the [identity object id](https://docs.microsoft.com/en-us/azure/healthcare-apis/find-identity-object-ids) of your user. Please collect the following information:

1. Azure AD client application ID.
1. Azure AD client application secret.
1. Your identity object id.

Then hit the button below to deploy to Azure:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhansenms%2FFHIRDevDays-Redmond2019%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="https://azuredeploy.net/deploybutton.png"/>
</a>

During the deployment, you will be asked to provide a `siteName`. The web application will be available at `https://siteName.azurewebsites.net`. You must ensure that the Azure AD client application has `https://siteName.azurewebsites.net/.auth/login/aad/callback` as an allowed reply URL.

A more advanced sandbox can be found at: [https://github.com/Microsoft/fhir-server-samples](https://github.com/Microsoft/fhir-server-samples).