### Contents:
- [Swagger PetStore API Release Notes](#swagger-petstore-api-release-notes)
- [Basic Workflow to use PetStore API](#basic-workflow-to-use-petstore-api) 
- [Deprecated Endpoints in PetStore API](#deprecated-endpoints-in-petstore-api)

## Swagger PetStore API Release Notes
PetStore is a web-based pet shop management application. 

The [Swagger Petstore API](https://petstore.swagger.io/) allows you to add, modify, or access data from the PetStore application using API calls. 

The PetStore API has the following endpoint groups: 
- `pet`: This group contains endpoints required to manage the records of a pet. You can register, access, modify, and delete records of pets.
- `store`: This group contains endpoints required to manage store orders. You can create, update, and find details of store orders.
- `user`: This group contains endpoints required to manage customer records.

For additional information on the tasks that you can do with PetStore API, see:
- [Managing Pet Details](#managing-pet-details)
- [Managing Store Records](#managing-store-records)
- [Managing Customer Records](#managing-customer-records)

### Testing Swagger PetStore API
To test the endpoints, use the api key `special-key` to test the authorization filters.
#### Authorization
Your application must obtain user authorization before it can execute an endpoint call. PetStore API uses OAuth 2.0 Implicit Grant to obtain the consent of a user to perform an API request. The Authorization URL is https://petstore.swagger.io/oauth/authorize.
#### Scopes
Scopes grant access to data on an application on behalf of the user. Each endpoint might declare one or more scopes.

The following scopes are available:

| Scope Name  | Description                     |
| ----------- | ------------------------------- |
| `read:pets` | reads details of the pets       |
| `write:pets`| modifies the details of the pets|

For information about planned deprecation of endpoints, see [Deprecated Endpoints in PetStore API](#deprecated-endpoints-in-petstore-API).

### Managing Pet Details 

The `pet` group contains the following endpoints that help you manage the records of a pet:
- `POST /pet`: Adds a new pet to the store. You can add the name of the pet, provide an ID to the pet, and add an image of the pet through an URL.
- `POST /pet/{petId}/uploadImage`: Uploads the image of the pet to the store. Provide the ID of the pet and upload the image of the pet.
- `PUT /pet`: Updates the details of an existing pet record in the store.
- `POST /pet/{petId}`: Updates the details of an existing pet record with form data.
- `GET /pet/{petId}`: Returns the details of a pet when you provide the pet ID.
- `GET /pet/findByStatus`: Returns the status of a pet; whether the pet is still available, sold, or the sale is pending.
- `GET /pet/findByTags`: Returns the status of a pet through tags.
- `DELETE /pet/{petId}`: Deletes a pet record when you provide the pet ID.

### Managing Store Records

The `store` group contains the following endpoints that help you manage store records:
- `POST /store/order`: Places an order for a pet. 
- `GET /store/order/{orderId}`: Returns the details of an order when you provide order ID. 
- `GET /store/inventory`: Returns pet inventories by status.
- `DELETE /store/order/{orderId}`: Deletes a store order when you provide the order ID.

### Managing Customer Records

The `user` group contains the following endpoints that help you manage customer records: 
- `POST /user`: Creates a user with details such as contact information. This operation can only be done by a user already logged into the PetStore application.
- `POST /user/createWithArray`: Creates a list of users with given input array.
- `POST /user/createWithList`: Creates a list of users with given input array.
- `GET /user/login`: Logs user into the system.
- `GET /user/logout`: Logs out the user logged into the PetStore application.
- `PUT /user/{username}`: Updates user details. This operation can only be done by a user already logged into the PetStore application.
- `GET /user/{username}`: Returns user by user name.
- `DELETE /user/{username}`: Deletes the user. This operation can only be done by a user already logged into the PetStore application.

### Models

#### API Response

| Name        | Description |
| ----------- | ----------- |
| code        | Number      |
| type        | String      |
| message     | String      |

#### Category

| Name        | Description |
| ----------- | ----------- |
| id          | Long        |
| name        | String      |

#### Pet

| Name        | Description   |
| ----------- | --------------|
| id          | Long          |
| Category    | Category      |
| name        | String        |
| photoUrls   | array<String> |
| tags        | array<Tag>    |
| status      | Status        |

#### Tag
  
| Name        | Description   |
| ----------- | --------------|
| id          | Long          |
| name        | String        |

#### Order

| Name        | Description   |
| ----------- | --------------|
| id          | Long          |
| petId       | Long          |
| quantity    | Number        |
| shipDate    | DateTime      |
| tags        | array<Tag>    |
| status      | Status1       |
| complete    | Boolean       |

#### User

| Name         | Description   |
| ------------ | --------------|
| id           | Long          |
| username     | String        |
| firstName    | String        |
| lastName     | String        |
| email        | String        |
| password     | String        |
| phone        | String        |
| userStatus   | Number        |

## Basic Workflow to use PetStore API

The following flowchart shows a basic workflow using some of the PetStore API endpoints:
![Workflow](https://user-images.githubusercontent.com/115869494/196049932-e74b3b7b-88b4-400b-9cbc-8382db52c808.png)


## Deprecated Endpoints in PetStore API

This section lists endpoints that are deprecated currently or those that will no longer be in use in future. If available, the endpoints that replace the deprecated endpoints are also mentioned in this section.

#### GET /pet/findByTags

The `GET /pet/findByTags` helps users to find pets using multiple tags with comma separated strings. Effective 17th April 2023, the `GET /pet/findByTags` endpoint is deprecated, and will no longer be available for use. To find pets, you must migrate to using `GET /pet/{petId}` or (`GET /pet/findByStatus`). You can no longer use multiple strings to find a specific pet.
  
**Warning!** `Continuing to use GET /pet/findByTags will break your code from 17th April 2023.` 
