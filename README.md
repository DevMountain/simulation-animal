<img src="https://devmounta.in/img/logowhiteblue.png" width="250" align="right">

# Project Summary

This project is designed to replicate what you might receive on the job. There won't be any guided instruction on what you'll need to do. We will only provide you with design specifications and technical requirements. Your mentors have also been asked to provide only minimal guidance. They can point you in the right direction, but cannot help you code. This project is a chance for you to combine and showcase the skills you've learned so far.

With this specification/requirement only structure, we believe this project will showcase what you can do at this point of the program. Because of this, we feel this project will be worth putting in your portfolio.

Good luck and work hard!

# Color Palette & Font

<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/assets/color-palette.png" />

<b><a href="https://fonts.google.com/specimen/Open+Sans?selection.family=Open+Sans">Google Font - Open Sans</a></b>
<br/>

### The icons are included in the assets folder of this repository
There are a few versions of the orange logo, and there is also an SVG if you prefer to work with that.


# Application Design

## Auth View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/login.png" />

## Browsing View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/all.png" />

## Details View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/details.png" />

## Cart View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/cart.png" />

## Orders View

<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/orders.png" />

## Add Pet View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/add-pet.png" />

## Edit Pet View
<img src="https://raw.githubusercontent.com/Alan-Miller/animal-simulation/master/views/edit-pet.png" />

# Technical Requirements - Front-end

## Auth View
* User can log in into their account.
* User can register for an account.
* User should be navigated to the All Animals view on a successful login or successful registration.

## All Animals View
* User can view all animals available for checkout
* User can filter animals by name / availability
* User can reset an applied filter to see a list of all animals again
* User can navigate to Details view by clicking on an animal    in the list
* User can navigate to Add Animal view through link in top corner
* User can log out and be redirected back to the Auth View

## Details View
* User is able to add animal to cart from here
* User is able to navigate to Edit Animal view 
* User is able to delete an animal from the database
    * This should redirect the user back to the All Animals View
* User is able to navigate to previous view
* User should be redirected to the All Animals view after adding the animal to the cart

## Checkout / Cart View
* User is able to remove an animal from cart and cart is updated in header and component
* User can checkout
  * Should add the animals in the cart to an order on the past orders page
  * Should clear the cart
  * Should update animals from in stock to out of stock
* User should be redirected to the All Animals view on checkout

## Past Orders View
* User can see past orders grouped by order with order number

## Add Animal View
* User can add an animal to the All Animals view with all the appropriate values
  * Name, image url (The animal should start in stock by default)
  * User can see a preview of the image
    * The image cannot break out of the preview container if the image is bigger
    * The preview container's size should remain static
* User is able to navigate to previous view, canceling the addition of a new animal
* User should be redirected to the All Animals view on completion

## Edit Animal View
* User populates an editable section based on the selected animal's details to update and change information about the animal 
* User is able to navigate to previous view, canceling the edit
* User should be redirected to the All Animals view on completion

# Technical Requirements - Back-end
* The back-end should be created using express.
* Massive will be used to establish a connection to your database and manipulate/retrieve data with SQL files
* Student will create tables using the supplied data

## Endpoints

### Authorization Endpoints

* POST - /api/auth/login - Sets the user information on the session.
  * On success return a status of 200 and the user object.
  * A user object should have the following properties:
    * id - This is the UserId you are using for your database.
    * username - This is the username associated with the UserId.
  * The database should store the password, but you should not send this information to the front end as part of the user object
  * On failure return a status of 500.
* POST - /api/auth/register - Registers a user to the database. Sets the user information on the session.
  * On success return a status of 200 and the user object.
  * A user object should have the following properties:
    * id - This is the UserId you are using for your database.
    * username - This is the username associated with the UserId.
  * The database should store the password, but you should not send this information to the front end as part of the user object
  * On failure return a status of 500.
* POST - /api/auth/logout - Destroys the session. Sends a status of 200.

#### NOTE: This is in no way a secure or effective way of storing user credentials. This is required for you to demonstrate your knowledge of data transfer and correspondence between the user and your server using sessions. Do not ever rely on this method in anything bound for production.
