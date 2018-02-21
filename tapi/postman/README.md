![](./logo.png)

# Postman

## Overview

This guide helps developers get started with the WhereIsMyTransport platform by querying the API using Postman.

At the end of this guide you will have completed the following:

- Setup Postman.
- Created a client for the WhereIsMyTransport platform.
- Requested a token using this new client.
- Performed API requests to the WhereIsMyTransport platform with your token.

## Setup Postman

1. Download [**Postman**](https://www.getpostman.com/)
2. Download the **WhereIsMyTransport** [Postman **Collection**](PlatformCollection.json)
3. Open Postman and add the above **Collection** and **Environment** as follows:

    3.1 **Adding the collection**
    
    Click the import button, and select the collection file from your download location.

    ![](postman_1_import_collection.png)

    Once your collection has been imported, you should see it in the left pane. This is a collection of REST API calls for the **WhereIsMyTransport** platform.

    ![](postman_2_import_done.png)

    To test it, select the first API call in the collection: **POST** token, and send the request. 
    
    You should see the response: `error: invalid_client`. Don't worry, this means that Postman has been setup correctly. 
    
    The reason for this is that the **ClientId** and **ClientSecret** fields in the Postman Environment are blank.
    
    In the next step we will create client credentials with which you will use to authenticate on the **WhereIsMyTransport** platform.
     
     
## Connect to our API

You need to be authenticated in order to make an API request to the WhereIsMyTransport platform. 

To do this you need to do the following:

1. Create a client on the **WhereIsMyTransport** [Developer Portal](https://developer.whereismytransport.com/).
    ![](devportal_client_create.png)

2. Copy the *ClientId* and *ClientSecret* into the respective fields of the Postman environment.
    ![](devportal_client.png)

3. The first API call in the collection allows you to retrieve an access token. When using the updated credentials, you should see a `200` `OK` response. The response body contains the a field named `access_token` whose value will be used in the `BearerToken` header when making requests to the API. But don't worry - this is done for you. At this point you are authenticated and can access our platform until the bearer token expires. Upon expiry, you will need to request another token.
    ![](postman_5_token.png)

4. To use the token for the other API calls, specify the token as a header with `Authorization: Bearer {token}`. For a complete set of the API's endpoints, please see the full [documentation](https://developer.whereismytransport.com/documentation). Below is an example of how to retrieve a list of agencies using the bearer token.
    ![](postman_6_agencies.png)

And that's it. You can use the Postman collection from here on, and use our [documentation](https://developer.whereismytransport.com/documentation) to explore of the capabilities of our API. 

Happy coding! 
