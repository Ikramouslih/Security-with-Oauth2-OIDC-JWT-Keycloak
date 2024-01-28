# JEE-Activite-Pratique-7
 
L'objectif de cette activité pratique est de familiariser les participants avec l'utilisation de Keycloak, un système open-source de gestion des identités et des accès basé sur les standards OAuth 2.0 et OpenID Connect (OIDC). 

### Travail à faire ###

**Partie 1 :**
1. Télécharger Keycloak 23;
2. Démarrer Keycloak;
3. Créer un compte Admin;
4. Créer une Realm;
5. Créer un client à sécuriser;
6. Créer des utilisateurs;
7. Créer des rôles;
8. Affecter les rôles aux utilisateurs;
9. Avec PostMan :
    - Tester l'authentification avec le mot de passe;
    - Analyser les contenus des deux JWT Access Token et Refresh Token;
    - Tester l'authentification avec le Refresh Token;
    - Tester l'authentification avec Client ID et Client Secret;
    - Changer les paramètres des Tokens Access Token et Refresh Token.
- Vidéo à utiliser comme ressources (Les 49 premières minutes de la vidéo) : https://www.youtube.com/watch?v=vNKVm2vTL2Q 

**Partie 2 :**
Développer et sécuriser une application basée sur les micro-services en utilsant Oauth 2, OIDC, Keycloak :
- Invenroty-service;
- Frontend Tymeleaf;
- Frontend Angular.
- Vidéos à utiliser comme ressources :
  1. https://www.youtube.com/watch?v=zI0Xr-O3sqM&authuser=0
  2. https://www.youtube.com/watch?v=YbCooJDUtOM&authuser=0
  3. https://www.youtube.com/watch?v=aSPWnRSteTk&authuser=0
  4. https://www.youtube.com/watch?v=NnzoM08CvgA&authuser=0
  5. https://www.youtube.com/watch?v=LrqRjokK5dY&authuser=0

## OAuth (Open Authorization) ##
OAuth 2.0 est un protocole d'autorisation qui permet à une application tierce d'obtenir l'accès à des ressources au nom de l'utilisateur sans avoir besoin de ses identifiants. Il est couramment utilisé pour permettre l'authentification et l'autorisation sécurisées dans le contexte des applications web et mobiles. OAuth 2.0 fonctionne en émettant des jetons d'accès après qu'un utilisateur a autorisé l'application à accéder à ses données.

## OIDC (OpenID Connect) ##
OpenID Connect est une extension d'OAuth 2.0 qui ajoute une couche d'authentification à OAuth 2.0. Il fournit un moyen standard pour les applications de vérifier l'identité d'un utilisateur en utilisant des jetons d'identification. OIDC combine les fonctionnalités d'authentification et d'autorisation, offrant une solution complète pour la gestion des identités dans le cadre d'applications modernes.

## Keycloak ##
![Keycloak-logo](https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/7c8aa3e0-bc13-436b-a473-6aa2c4b6d598)

Keycloak est une solution open source de gestion des identités et des accès qui prend en charge OAuth 2.0 et OIDC. Il fournit des fonctionnalités telles que l'authentification unique (SSO), la gestion des utilisateurs, la gestion des rôles, la protection des ressources, et plus encore. Keycloak peut être utilisé pour sécuriser des applications web et des services, facilitant ainsi la mise en place de mécanismes d'authentification et d'autorisation robustes.

# Partie 1 #

Démarrer Keycloak en mode développement : `C:\tools\keycloak-23.0.4\bin>kc.bat start-dev`
<br><br>
<img width="960" alt="Screenshot 2024-01-11 002249" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/0777055e-3e7c-4649-9b49-76a88acacb66">
<img width="960" alt="Screenshot 2024-01-11 002047" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/d66d61cf-b8a8-4a41-8ec0-08ad065adf25">
<img width="958" alt="Screenshot 2024-01-11 002106" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/2581da27-0321-40c1-9d2b-c692f63d7e55">
<img width="960" alt="1" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/4f4e7d8c-dc99-492e-95fc-6969bb105c84">
<img width="958" alt="2" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/7d37ea6e-5c87-483e-a2e2-3409c90c007f">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/8072c325-9747-4587-b1a4-1ce1a7a2220a">
<img width="1190" alt="4" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/cb76e19a-b93d-4314-8801-3aea5f4530c1">
<img width="960" alt="5" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/8e9ab382-a359-4fbc-9733-f77df055f160">
<img width="1046" alt="6" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/2234ffd5-34fc-4162-850d-c35781ea141c">
<img width="960" alt="7" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/4f1146d7-e68c-4a5f-9033-b69dae882200">
<img width="890" alt="8" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/d3823a63-0272-4cb2-956d-0423ce907544">
<img width="960" alt="9" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/038d7714-ba18-4e20-9381-6694f45eea24">
<img width="960" alt="10" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/ebe6d9e1-fbbb-464d-a060-11d14d2b6fc6">
<img width="960" alt="11" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/dc679b49-4fe8-4389-8cf3-baedcdfc47bc">
<img width="960" alt="12" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/c9ca0369-417e-4921-98de-58e6f2b459de">
<img width="960" alt="13" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/bc0925d0-aace-4849-9f7c-db03e1c5bf63">
<img width="873" alt="14" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/5807e237-be68-495c-af86-a80054e775cc">
<img width="861" alt="15" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/56eab6ef-1450-41fa-b54a-da1c6ebfc933">
<img width="869" alt="16" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/c1fe473c-3d3a-42be-bb3c-241d3d1c3149">
<img width="960" alt="17" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/5216ff94-e9b9-4b4b-b4e9-23ff7ec92130">
<img width="868" alt="18" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/7e060e29-465e-45eb-b254-8f4fd77ab21e">
<img width="960" alt="19" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/c1268a7a-f139-4d82-8ff9-6b99537d71a2">
<img width="960" alt="20" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/4375d458-efe2-454f-8372-051cba366976">
<img width="960" alt="21" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/f04fbe85-fec5-4c4f-a9d6-e25adba079c8">
<img width="874" alt="22" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/5757c0d9-081b-47d2-8b53-27824355cc87">

# Partie 2 #

## Thymeleaf ##

### Authentification avec Google : ###
<img width="960" alt="Screenshot 2024-01-27 184443" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/34b82568-cb74-4709-a5e4-0ff188f196d7">
<img width="960" alt="Screenshot 2024-01-27 193650" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/189c69ff-648b-41ab-b8b1-385666e676be">
<img width="960" alt="Screenshot 2024-01-27 193501" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/b11989de-7bd5-4c4d-b58d-17561dee1872">
<img width="960" alt="Screenshot 2024-01-27 193520" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/c93e1076-7ab9-42fb-b7cf-8693ea213dae">

### Authentification avec Keycloak : ###
<img width="960" alt="Screenshot 2024-01-27 185440" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/3ef15b91-7de0-4465-b369-7cc2cabb37bc">
<img width="960" alt="screencapture-localhost-8080-admin-master-console-2024-01-27-18_50_56" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/bfdf164f-91b1-44c9-ac57-08bcba20de9e">
<img width="960" alt="Screenshot 2024-01-27 184543" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/076715fd-bbe1-45fc-88b5-7a9e777333da">
<img width="960" alt="Screenshot 2024-01-27 193642" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/f00ee975-1a4a-4d4d-a2bd-ec28c142786b">
<img width="960" alt="Screenshot 2024-01-27 193544" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/e42baebd-8503-45c1-8248-1334168e2295">
<img width="960" alt="Screenshot 2024-01-27 193601" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/06c30dcd-ef65-4ef4-97d5-e65db21007dd">

### Authentification avec Github : ###
![screencapture-github-settings-applications-2457777-2024-01-27-18_49_22](https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/2bed42dc-58c7-41ac-9157-7858da523915)
<img width="960" alt="Screenshot 2024-01-27 193618" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/a84a22c1-3a7a-448d-b481-40d9c8a10915">
<img width="960" alt="Screenshot 2024-01-27 171349" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/a2c20e29-ce00-4bc9-8449-45756597257a">
<img width="960" alt="Screenshot 2024-01-27 193627" src="https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/f1530943-f8d5-4ba9-8cda-5e079430b3f8">


## Angular ##

https://github.com/Ikramouslih/Security-with-Oauth2-OIDC-JWT-Keycloak/assets/60039200/18597f4e-8cf7-426d-8cc2-88edaa6607c7




