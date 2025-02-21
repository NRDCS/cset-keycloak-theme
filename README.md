# cset-keycloak-theme
Customized theme for keycloak

Purpose: to add cusotmizable theme for keycloak, were main parameter can be added to the theme.properties configuration file.

Two main usecases are supported:
- IdP discovery page. Having Idp without users, just with references to two external IdPs: CSIRT IdP and Constituent's IdP. No login-password dialog should be provided, just buttons to choose between two IdPs.
- IdP login screen with login and password.

Theme properties files (theme/theme.porperties) can have the following options:

| Parameter | Example value | Description |
| ------------- | ------------- |-------------|
|logoURL|https://www.nrdcs.eu/_nuxt/image/62906c.webp|Add logo at the top|
|logoHeight|97px|Logo height|
|logoWidth|236px|Logo width|
|BoxWidth|700px|Authentication box width|
|backgroundColor|#3d475a|Background color of the page|
|buttonColor|#242578|Signin button color|
|hideLoginPassword|true|Should we hide login-password dialog (for IdP discovery page)|
|showTitle|true|Should we show title on the page (we can skip it if we have logo)|
|CSIRTButtonBackground|#242578|Button color for CSIRT IdP (IdP should have alias CSIRT in the keycloak config)|
|CSIRTButtonText|white|Button text color for CSIRT IdP (IdP should have alias CSIRT in the keycloak config)|
|ConstituentButtonBackground|#6365f3|Button color for Constituent IdP (IdP should have alias Constituents in the keycloak config)|
|ConstituentButtonText|white|Button text color for Constituent IdP (IdP should have alias Constituents in the keycloak config)|
|TitleColor|black|Page title text color|

# Usage
1. Clone repository
1. Edit theme/theme.properties, adjust colors, other settings.
1. In the docker-compose.yml add volume: mount folder theme/ to the container destination folder /opt/keycloak/themes/SomeName
1. In the Keycloak webui select the Realm, go to Realm setting page, Themes tab. In the Login theme dropdown select SomeName. Save configuration.