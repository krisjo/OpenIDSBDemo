# OpenIDSBDemo
## Open ID Connect with OAuth 2.0 using Spring Boot

### Initial setup
#### Google Oauth2
To use Google's OAuth 2.0 authentication system for login, you must set up a project in the Google API Console to obtain OAuth 2.0 credentials.

NOTE: https://developers.google.com/identity/protocols/OpenIDConnect[Google's OAuth 2.0 implementation] for authentication conforms to the
https://openid.net/connect/[OpenID Connect 1.0] specification and is https://openid.net/certification/[OpenID Certified].

Follow the instructions on the https://developers.google.com/identity/protocols/OpenIDConnect[OpenID Connect] page, starting in the section, "Setting up OAuth 2.0".
In the "Authorized redirect URIs" sub-section, set a URI field to `http://localhost:8080/login/oauth2/code/google`.

After completing the "Obtain OAuth 2.0 credentials" instructions, you should have a new OAuth Client with credentials consisting of a Client ID and a Client Secret.

#### Svipe iD
To use Svipe's authentication system for login, you must first install the Svipe ID app on your device.
Then you must set up an application in the Svipe iD Developer Portal to obtain OAuth 2.0 credentials.
Login trough https://developer.svipe.com/home using your Svipe ID app and create an application, filling the Name, Login redirect URI and Logout redirect URI fields.
Set the "Login redirect URI" field to `http://localhost:8080/login/oauth2/code/svipe`.

### Adding the Client Registration

Then, you need to configure the application authorizations in application.yaml to point to your Google and Svipe client configurations by specifying their respective client id and client secret.

### Build and Run
```
$ cd two-providers
$ mvn clean package
$ java -jar target/*.jar
```
