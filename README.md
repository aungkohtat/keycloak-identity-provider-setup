# keycloak-identity-provider-setup

## Getting Started with Keycloak for Identity and Access Control


Today, many websites and apps need secure login and user access control. Instead of creating your own login system, you can use a tool like Keycloak.

Keycloak is a free and open-source tool made by Red Hat. It was first released in 2014. Keycloak helps developers add login, logout, and user management features to their apps without writing a lot of extra code.

It supports modern login systems like Single Sign-On (SSO), OAuth2, and OpenID Connect. You can also connect it with other systems like LDAP or Active Directory.

In this guide, you will learn how to use Keycloak for managing users and protecting your app. We will start with a basic setup and go step by step.

## Setup
To set up Keycloak, ensure you have Docker installed. We’ll pull a Keycloak image to our local Docker Desktop application.

Keycloak offers multiple setup and installation methods. Check them out here

Installing Keycloak

Open a terminal window and enter the following command to pull and run a Keycloak image:

```
docker run -p 8080:8080 -e KC_BOOTSTRAP_ADMIN_USERNAME=admin -e KC_BOOTSTRAP_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:26.1.4 start-dev
```

- open Docker and verify that both an image and a container have been created.
![](./img/Screenshot%202025-04-07%20at%2012.42.36 PM.png)

- and than access Keycloak by visiting http://localhost:8080 


  ![](./img/Screenshot%202025-04-07%20at%2012.44.54 PM.png)


- Login with User: admin, Password:admin
 
    ![](./img/Screenshot%202025-04-07%20at%2012.46.21 PM.png)


## Setting up a Realm
- A realm in Keycloak is like a tenant. It lets admins create separate groups of applications and users. By default, Keycloak has a "master" realm, but it's only for managing Keycloak itself, not applications.

    ![](./img/Screenshot%202025-04-07%20at%2012.48.11 PM.png)

- Create Realm
    ![](./img/Screenshot%202025-04-07%20at%2012.51.09 PM.png)

    ![](./img/Screenshot%202025-04-07%20at%2012.51.21 PM.png)

## Creating a User
- In the left navigation, select “Users” and click “Create New User”. Input the username and any additional details you wish to include.

    ![](./img/Screenshot%202025-04-07%20at%2012.53.00 PM.png)

    ![](./img/Screenshot%202025-04-07%20at%2012.55.07 PM.png)

- Credential add Password
    ![](./img/Screenshot%202025-04-07%20at%2012.58.40 PM.png)

## Testing Login

- In my case, the URL will be http://localhost:8080/realms/akhtech/account



## Create a Client
- In Keycloak, an application is a Client. To secure an application, we must add it as a client

    ![](./img/Screenshot%202025-04-07%20at%201.01.07 PM.png)


    ![](./img/Screenshot%202025-04-07%20at%201.08.44 PM.png)

    ![](./img/Screenshot%202025-04-07%20at%201.09.24 PM.png)
    ![](./img/Screenshot%202025-04-07%20at%201.10.29 PM.png)
    ![](./img/Screenshot%202025-04-07%20at%201.11.39 PM.png)
    ![](./img/Screenshot%202025-04-07%20at%201.13.47 PM.png)
    ![](./img/Screenshot%202025-04-07%20at%201.16.02 PM.png)

## Create another Client
   ![](./img/Screenshot%202025-04-07%20at%201.48.31 PM.png)
   ![](./img/Screenshot%202025-04-07%20at%201.49.14 PM.png)
   ![](./img/Screenshot%202025-04-07%20at%201.50.14 PM.png)

## Test Token Using Podman
   ![](./img/Screenshot%202025-04-07%20at%202.45.28 PM.png)

## Using JWT Decodded
  ![](./img/Screenshot%202025-04-07%20at%202.47.50 PM.png)




That's it! We set up Keycloak on our machine, made a realm, added a user, and set up a client. Now it's ready to use for login and access control.

### Happy Using Keycloak...!!!