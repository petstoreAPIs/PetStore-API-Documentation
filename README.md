# Contents:
- [PetStore API Release Notes](#petstore-api-release-notes)
- [Workflow to use Pet Endpoint Group](#workflow-to-use-pet-endpoint-group) 
- [Deprecated Endpoints in PetStore API](#deprecated-endpoints-in-petstore-API)

## PetStore API Release Notes
PetStore is a pet shop management solution. The PetStore API allows you to add, modify, or access data from the PetStore solution using API calls. 
The PetStore API has the following endpoint groups: 
- `pet`: This group contains endpoints required to manage the records of a pet. You can register, access, modify, and delete records of pets.
- `store`: This group contains endpoints required to manage store orders. You can create, update, and retrieve details of store orders.
- `user`: This group contains endpoints required to manage customer records.

For additional information on the tasks that you can do with PetStore API, see:
- [Managing the Details of a Pet](#managing-the-details-of-a-pet)
- [Managing the Store Records](#managing-the-store-records)
- [Managing the Customer Records](#managing-the-customer-records)
### Managing the Details of a Pet
The `pet` group contains the following endpoints that help you manage the records of a pet:
- `POST /pet`: Adds a new pet to the store. You can add the name of the pet, provide an ID to the pet, and add an image of the pet through an URL.
- `POST /pet/{petId}/uploadImage`: Uploads the image of the pet to the store. Provide the ID of the pet and upload the image of the pet.
- `PUT /pet`: Updates the details of an existing pet record in the store.
- `POST /pet/{petId}`: Updates the details of an existing pet record with form data.
- `GET /pet/{petId}`: Returns the details of a pet when you provide the pet ID.
- `GET /pet/findByStatus`: Returns the status of a pet; whether it is sold, available, or pending.
- `GET /pet/findByTags`: Returns the status of a pet through tags.
- `DELETE /pet/{petId}`: Deletes a pet record when you provide the pet ID.
### Managing the Store Records
The `store` group contains the following endpoints that help you manage store records:
- `POST /store/order`: Places an order for a pet. 
- `GET /store/order/{orderId}`: Returns the details of an order when you provide order ID. 
- `GET /store/inventory`: Returns pet inventories by status.
- `DELETE /store/order/{orderId}`: Deletes a store order when you provide the order ID.
### Managing Customer Records
The group contains the following endpoints that help you manage customer records and control user log in and log out: 
- `POST /user`: Creates a user with details such as contact information. This operation can only be done by a user already logged into the PetStore application.
- `POST /user/createWithArray`: Creates a list of users with given input array.
- `POST /user/createWithList`: Creates a list of users with given input array.
- `GET /user/login`: Logs user into the system.
- `GET /user/logout`: Logs out the user logged into the PetStore application.
- `PUT /user/{username}`: Updates user details. This operation can only be done by a user already logged into the PetStore application.
- `GET /user/{username}`: Returns user by user name.
- `DELETE /user/{username}`: Deletes the user. This operation can only be done by a user already logged into the PetStore application.

## Workflow to use Pet Endpoint Group
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. Example text blah. Example text blah. 
Example text blah. Example text blah. 

## Deprecated Endpoints in PetStore API
### Creating a Pet ID
