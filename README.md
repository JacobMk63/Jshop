# Jshop
Ecommerce website/App
JSHOP “MVP specification”
Architecture

The minimum viable product (MVP) for the JShop ecommerce/App would typically include the essential features that allow users to create, manage, update and delete items in the shopping cart, it alway give the options for non register user to add, delete and make payment in the checkout page. There are various payments option for both users and guest users. Here are some key features that should be included in an MVP for the Ako Shop ecommerce/App:

Users should be able to create new account and login to have access to manage product, order and item order.
Non register users would have the ability to add items, delete items in the shopping cart and also make payment
Gives the option of continue shopping for both register and non register users at cart stage. The quantity of items can be added or removed by using the down and up arrows.
Provide section for shipping address for registered users and non registered user, but for digital products the shipping address is hiden.
##                                            STEPS FOR THE DEVELOPMENT IN DJANGO FRAMEWORK
###                                           SETUP THE APP AND INSTALL FRAMEWORK
####             Part 1 | Configure App
1. install the virtual enviroment and Django installed and created our first project using django-admin startproject “ecommerce”.
2. Create the first app files with python manage.py startapp “store".
3. Add app to settings.py
####              Part 2 | Templates
1. create a folder to store our templates. Our html files will be stored within our app inside a folder called "templates".
2. inside the templates folder create another folder with the same name as the app.
3. base.html → Template which all will inherit from
4. login.html → Home page/store front with all products
5. Cart.html → Users shopping cart
6. oders.html → order page
####              Part 3 | Views & URLs
1. Inside your apps views.py file created 3 views, store, cart, checkout. I created some "url paths" to call these views.
2. I Created a file called "urls.py" inside your app. Inside the app import “path” along with the “views” and create a urlpatterns list. Inside "urlpatterns " create 3 paths, one for each view and give them a name.
3. Base URLs Configuration. import "inlcude" just after "path" and add a path that points to the new urls.py we created inside "store". from django.contrib import admin, from django.urls import path, include
####              Part 4 | Static Files
Created a folder called "static" in the root directory.
Inside the new “static” folder, I created a folder called "CSS" and another called "Images". These files will hold all of our CSS and Images.
Inside the CSS folder, I created a file call main.css.
i configured things in settings.py and then add this link os.path.join(BASE_DIR, 'static') to our template.
##            DATA STRUCTURE and Algorithm
###           Part 1 | Models
## Database Models
### models
#[PICTURE HERE]

User- Built in Dango user model. An instance of this model will be created for each customer that registers with our website. This model will give us the ability to later use Djangos default authentication system without having to manually set this up ourselves.
Customer - Along with a User model each customer will contain a Customer model that holds a one to one relationship to each user. (OneToOneField).
Product - The product model represents products we have in store.
Order - The order model will represent a transaction that is placed or pending. The model will hold information such as the transaction ID, data completed and order status. This model will be a child or the customer model but a parent to Order Items.
OrderItem- An order Item is one item with an order. So for example a shopping cart may consist of many items but is all part of one order. Therefore the OrderItem model will be a child of the PRODUCT model AND the ORDER Model.

ShippingAddress- Not every order will need shipping information. For orders containing physical products that need to be shipping we will need to create an instance of the shipping model to know where to send the order. Shipping will simply be a child of the order model when necessary.

###             Part 2 | Render Products
1. Query Products- In our apps views.py file, I first imported all our models and then query the products within our store view. I added "products" into the context dictionary.
2. Render Products - Loop Through Products, Replace Fields for Product Price and Product Name
2. Product Image Field
3. ImageField()
4. User Cart- attach a customer to our user, and add some order items to go with the order which we will manually create from the admin panel.
#[PICTURE HERE]
