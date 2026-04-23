# Generate JWT token

## Description

The **Generate JWT Token** action allows you to generate a JSON Web Token (JWT) in the context of OAuth authentication for server-to-server integration.

This action receives as input an RSA Private key and uses the hash algorithm RSA SHA-256 to generate the required signature for retrieving JWT access tokens for [DocuSign](https://developers.docusign.com/platform/auth/jwt/jwt-get-token/) and [Adobe Sign](https://developer.adobe.com/developer-console/docs/guides/authentication/JWT/) and any other third-party system with similar requirements.

## Usage

![Image 3: Generate JWT Token](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/generate-jwt-01.png)

The following must be configured:

*   _Claims id and value_: You can add multiple id and value pairs to adapt the tokens to the services you want to use.
*   _RSA Private Key_: The RSA private key in base64 format.
*   _Expiration time in minutes_: Sets the token expiration time. This field is optional. The defaullt time is 60 minutes (1 hour) and the maximum expiration time is 1440 minutes (24 hours).
