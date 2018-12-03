# Nutrition Value
.

----

# NEED to rename CLASSES TO CATEGORIES.
I WILL NEED TO REDO THE IMAGES ON THE FRONT PAGE.

----

*Milestone project for **Data Centric Development***  
*Developer: Anthony Bonello*

-------
**INDEX**

* [INTRODUCTION](#introduction)
* [UXD](#uxd)  
    * [Strategy](#strategy)
    * [Scope](#scope)
    * [Structure](#structure)
    * [Skeleton](#skeleton)
    * [Surface](#surface)
* [WIREFRAMES](#wireframes)
* [FEATURES](#features)
* [TECHNOLOGIES USED](#technologies-used)
* [TESTING](#testing)
* [DEPLOYMENT](#deployment)
* [CREDITS](#credits)
---
  
## INTRODUCTION
* [Back to TOP](#nutrition-value)

This app allows users to store information about the nutritional value of various food products. I chose to store the values per 100g (or 100ml). Users should be aware that this value on its own is not enough as some items which for the sake of this example, might be high in salt might be used in small quantities, while others which are low in salt might be used in larger quantitities. In any case products can be compared and filtered based on various parameters in the dashboard. (See features below.)

---

## UXD
* [Back to TOP](#nutrition-value)

This app allows the storage of information about food in a mongodb database and allows users to access, edit and delete that data in a variety of ways. Filtering is also allowed through d3.js graphs.

### **Strategy** 
* [Back to TOP](#nutrition-value)

**What do I want as the owner of the site?**

I was curious to find out what I eat. For this reason I planned this app to store the data about the food items I consume and display this data in some meaningful form.  
The values used are the typical nutrition values per 100g (or 100ml). Users should be aware that this value on its own is not enough as some items which for the sake of this example, might be high in salt might be used in small quantities, while others which are low in salt might be used in larger quantitities. In any case products can be compared and filtered based on various parameters in the dashboard. (See features below.)  
In any case, I found it interesting and somehow fascinating to see how various food products lay out on a graph when various food nutrions (parameters) are mapped against each other.

#### What does it do?
This data uses forms to collect the data and stores it in a mongodb database. Food items are categorised. Categories have their own form to create them. These categories keep track of the amount of food items I have in each category.

#### How does it work
A user can create food categories and enter data about food items. Both food categories and food items can be edited.
Categories keep track of the number of food items using it and if there are none, then it can be deleted.
There are two forms of data display, an accordion view and a dashboard built from d3.js graphs. Entries in a d3.js generated table in the dashboard acts as links which will open a modal with information about the food item displayed.

---

### **Scope** 
* [Back to TOP](#nutrition-value)

#### Features to implement

The app should allow the user to fullfill the following tasks:

* Categorize the foods according to food categories.
* Create, edit and delete categories. 
* A category can only be deleted if it is not being used by any food item.
* Editing a category will change the category name in all food items that are classified under that category.
* If editing a category name results in a name that is already in use, the food items from the old category will have their category renamed and the total food items using the current (new) category will be updated to reflect the total of the two separate categories. This is needed to keep track of the food items using a category to avoid deleting a category that is being used by food items.
* Functionality to see all the classes. Here there is also an indication of how many food items make use of each class.
* Creating a new category will check that the name is not already exist.
* Food Items can be viewed, added, edited and deleted.
* Confirmation required for deleting food items or categories.
* Contact form


#### User stories
A user wants to store data about a food item (Category already exists) 
1. User Clicks on `New Item`
2. Selects a Category (category exists)
3. Fill the rest of the form
4. Clicks `Add Food Item` button

A user wants to store data about a food item (Category does not exist) 
1. User Clicks on `New Item`
2. User Clicks on the `Category` field
3. Category does not exist. User clicks on the `here` button, part of the instruction just above teh coategory field.
4. User taken to the Add Category form.
5. User fills in the form
6. User enters a new category name. (The user can check the categories that already exist.)
7. If the category entered by the user already exist, the user will be alerted to this effect. A message is displayed. The user is prompted to use a different name.
8. If the category does not yet exist, a new category will be created, 0 will be assigned to the value of food items using this category (can be checked by visiting the `Food Categories` page) and the user will be automatically taken back to the `Add Food Item` page.
9. Fill the rest of the form
10. Clicks `Add Food Item` button

User wants to edit a food item

User wants to delete a food item

User wants to create a category

User wants to edit a category

User wants to delete a category

User wants to see details of food item (accordion view)

User wants to compare nutrition values



### **Structure**

Pages Navigation Header Footer

## Pages

1. I will have a home page with some description of the project and instructions for using the application.
2. I will have a page to add data [**C**]. This will be reached from a menu item.
3. I will have a page to display [**R**] the items. I will use an accordion structure. I can do one of two things:
    1. There will be a button to lead to a more details. Here there will be a button to delete the item.
    2. All the details will show once an accordion fold is open. There will be a button to delete the item on the accordion item header.
4. In any case the delete [**D**] button will either open a modal or take the user to another page for confirmation.
5. I will have an edit page [**U**]. It will be structured like the add page but will be prepopulated with the data for the particular item to be edited. There will be a button to save the changes or leave without saving changes.
6. There will be a **Dashboard** with DC.js graphs with filters and the possibility to select an item and go to the item's detail page. (Or the accordion fold of that particular item.)

-----------


### Skeleton
* [Back to TOP](#nutrition-value)


There are two ways of viewing the food items.

1. **The accordion view**  
    Here, each item is in an accordion panel. Opening a panel will display a card. I chose to display the info on a card which can rotate and show extra information at the back of the card. At the back, the user will also find buttons to edit or delete that particular food item.

    Apart from the button saying: "More info and Controls at the back", the curved arrow at the top right corner of the card is a visual indication pointing to the back of the card.  
    CAN I ADD A LINK TO THE ARROW TO FUNCTION AS A BUTTON?
    ---

2. **Dashboard**  
    In the dashboard view, the user is able to filter items based on categories, and a number of paramter combinations. At the bottom of the page there is a table which initially will show all products, currently up to 1000, but will be reduced depending on the filters applied. The name of the food item in the table is a button.
    # I would like to add pagination to the food table

    Clicking a food item in the table will open a modal which will display the data related to that food item.

    I experimented with styling the modal to make it appear as if it is a piece of paper on a desk. As soon as the user hovers over the modal, the paper-like background changes as if pressure or weight has been applied to it. I tried to achieve an organic effect.

    The user can close the modal in a number of ways.
    * Clicking on the close button.
    * Clicking on the X at the top right corner of the modal.
    * Clicking on the desk (the white border) around the modal.
    * Pressing the esc button on the computer keyboard.



* [wireframe](#wireframes) - follow this link for further reading

?????????
---
------
### Surface
* [Back to TOP](#nutrition-value)

#### Colors 

#### Typography

## WIREFRAMES
* [Back to TOP](#nutrition-value)  
* [Back to Skeleton](#skeleton)


## FEATURES
* [Back to TOP](#nutrition-value)

### Existing Features

### Features Left to Implement




## TECHNOLOGIES USED
* [Back to TOP](#nutrition-value)

- [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) - used to build the sctructure and the content of this project.
- [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3) - used for styling this project.
- [jQuery v3.3.1](https://jquery.com) - simplifies accessing the DOM.
- [Bootstrap v3.3.7](https://getbootstrap.com/docs/3.3/) - used for some of the styles (modified), as well as layout of the content.
- [Font Awesome v4.7.0](https://fontawesome.com/v4.7.0/) - used to display the GitHub and Linkedin Icons.
- [Google Fonts](https://fonts.google.com/) - Lobster and Roboto.
- [email.js](http://www.emailjs.com/) - used to enable the contact form to send emails to me.
- [jasmine v2.4.1](https://github.com/jasmine/jasmine) - behavior-driven development framework, used to unit test the functions related to form validation.
- [Compress JPEG ](compressjpeg.com) - I use GIMP to manipulate images. Once I export them as jpg, I use Compress Jpeg to minify them. Usually, I can gain between 25% and 50% reduction in file size.

## TESTING
* [Back to TOP](#nutrition-value)




The form is validated and it also has a try except to catch if the email address is not accepted by the server. In this case the user is returned to an error page.





~~If the user clicks on the delete button, a confirmation window will open. The user can confirm or reject the deletion. An item will be reduced from the class used by that item.~~

If a user selects to edit the food item, a window will open which will be prepopulated with the information of that item. The user can do the changes necessary and then click the "Update Food Item" button.

If the user chooses to reclassify a food item, then the necessary changes to the quantities of the category involved will be applied, (increase to the new category, decrease the old category).

The user can cancel the editing process and will be taken back to the accordion view.

There are three places that will take you to the route which allows for the adding a new category. The app keeps track of the calling place and will return there on cancelling or creating a new category. 
# Need to check this. 
Editing a food item and trying to create a new class from here will return to the add food item.

It is possible for the user to create a new food item. The form will have the category prepopulated. The user will have to select one. There is the option to create a new category which checks on whether it already exists.

















## Data

The data is the nutrional value per 100g (or 100ml for liquids).

* Energy (kJ)
* Energy (kcal)
* Fat
* Saturated Fat
* Carbohydrates
* Sugars
* Fibre
* Protein
* Salt
* Classification
* Shop
* Notes

Others might include:
B12 and Calcium.

I want to allow for data which in Not Available (**NA**) and values which are marked as less than (**<**).



## Deploy to Heroku

Name of app: **food-nutrition**  
URI: [https://food-nutrition.herokuapp.com/](https://food-nutrition.herokuapp.com/)

I am using ***gunicorn*** server. I found that I will have to set less settings myself.  
The differences include:
1. I do NOT need to run ```heroku ps:scale web=1```
2. I do NOT need to manually set the IP and PORT variables in *settings > Reveal Config Vars*.
3. I do NOT need to *Restart all Dynos* from *More*.

In all, using gunicorn makes deploying to Heroku much easier.

The commands needed are: (using this app as example)
1. Install gunicorn
~~~~
pip3 install gunicorn
~~~~

2. Create Procfile
~~~~
echo web: gunicorn run:app > Procfile
~~~~

3. Create/Update requirements.txt
~~~~
sudo pip3 freeze --local > requirements.txt
~~~~

4. Create the Heroku on the website (allows me to set Region to EU)

5. Log in to heroku (locally, need email and password) and check the apps
~~~~
heroku login
heroku apps
~~~~

6. Initialise git, if not already done and set a remote for heroku
~~~~
git init
heroku git:remote -a food-nutrition
~~~~

7. Push to Heroku
~~~~
git push heroku master
~~~~

DONE. -- Open the app at [https://food-nutrition.herokuapp.com/]()


### Addition

To access the files on Heroku, 
1. go to **More > Run console**.
2. run the command 
~~~~
heroku run bash
~~~~
3. Use normal bash commands.

.

------------

## Database

Create a MongoDB database on mLab.  
Database name: **food**  
MONGODB VERSION: **3.6.6 (MMAPv1)**

* add user
* add collection: **nutrition100**
* created 3 documents with some data.


I had to do some changes in the code I used in previous projects.  
MONGO_DBNAME and MONGO_URI had to be used as app.config:
~~~~
app.config["MONGO_DBNAME"] = getDbName()
app.config["MONGO_URI"] = getURI()
~~~~
The port argument complained about the int() method, so now it is:
~~~~
app.run(host=os.getenv('IP'), port=os.getenv('PORT'), debug=True)
~~~~

### Add Food Item

Implemented **add food item**.

Now updating Heroku.  
The following code:
~~~~
from connection import getDbName, getURI
.
.
.
.
app.config["MONGO_DBNAME"] = getDbName()
app.config["MONGO_URI"] = getURI()
~~~~

does not work in Heroku.

Instead, in Heroku set environment variables for **MONGO_DBNAME** and **MONGO_URI** with the correct information.

## Classification

I created another collection in the database that will hold the different classifications of food. This will help to give unity to the data.  

I implemented the code to populate the classification input field with classes to select from in the add food item page.

I implemented adding new classes. I also added the functionality of returning to the calling page if the process is cancelled.

Implemented editing a class.


## Backups

I implemented two routes that are used either to get a backup of the database, or replace the database from a backup file. This will help me in two cases. 
1. I mess up the data during testing where it is quicker to replace the lot rather than edit indivual entries
2. The data has been messed up by someone (possibly intentionally) - I am not currently implementing a log in system.

## Dashboard

Drafted a dsahboard with 2 scatter plots - fats vs sat, carbs vs sugar.

I plan to have 4 scatter plots and a bubble chart:
1. All Fat vs Saturated
2. All Carbohydrates vs Sugar
3. Energy vs Protein (have not decided which Energy value I will use)
4. Sugar vs Salt
5. All Fat vs Carbohydrates with the following additions:
    * size of bubble - Protein
    * color - changes with quantity of Sat fat
    * border color - changes with sugar content.

I want to be able to cancel each individual filter and all filters.
I would like to be able to transfer the filters to the get_food_items view, if it is possible, to display only the selected foods in the accordion.

There is something that need to be changed in the database. Currently, the values are stored in the database with the units attached. This is not what crossfilter etc wants. Numbers should be numbers. I can do the processing in javascript(jQuery) to remove the units before passing the data to crossfilter or I can store the numbers without the units. This is the way I am choosing to do. As a result, the display of data in the accordion view will show without units unless I change the code to add them for display. This is the next step. I also have to remove the code which was adding the units when adding a new food item.


## Resetting filters for Row Chart

I had a problem with resetting the classification row chart stopping working. I tried to see how I can force an svg group name to use with redrawAll(). This led to nowhere. After a long time of trying various things such as trying to use renderlet and on renderlet (both fail), I commented out some of the code that I had and suddenly the reset link worked.  
At this point I started uncommenting one line at a time and managed to narrow the error to 
~~~~javascript
 .xAxis().ticks(4) // DO NOT ADD: This will break the reset filters 
~~~~

Adding this line will stop the resetting of the filters.

By the way the above line of code will also stop
~~~~javascript
.controlsUseVisibility(true)
~~~~
from working. Otherwise it works fine.

Now I turned the reset link to a button to match that for the scatter plots.

## Testing
I already dealt with NA values in accordion not to show units. Now the same issue appears in the modal. I also realised that if a value had to be missing completely, the units will show on their own both in the accordion and the modal.

For the purpose of testing that these two issues are dealt with, I created two test food items, one having NA in all values that will take a unit and the other has all values empty. At the moment NA will not get a unit in the accordion but will do so in the modal (needs fixing). The food item with empty values will get units in both accordion and modal (both need fixing).

The code for the accordion is in the index.html (will be renamed later on) and that for the modal is in the dashboard3.html (This is the dashboard that I will use but will be renamed.)

I added two new test items, one for when I have a value for Energy 1 but not for energy 2, and the other one for vice versa. I want to hide the **/** in such cases ( as well as when both are missing).
Combinations tested: NA "", value "", NA value, NA NA, "" NA, "" value, "" "", value value, value "", value NA

Accordion Done.


## Confirm Delete

Implemented route to delete food item. Tested by creating a test items and deleting them.  
Implemented route to delete food class. Tested by creating a test items and deleting them.

Functionality includes the ability to cancel the delete process.

## Improving classification collection.

I want the classification collection to keep track of the number of food items that use a particular classification.

Also If I come to delete a class, it the confirmation page will tell me how many food items are currently using that class. If there are any food items that use a class, I will not be able to delete that class.

1. Start by taking a current backup of the data.
2. Then, manually add a count key to all documents in the classification collection.
3. Take new backup
4. When I look at the classes route, I see a count of how many Food Items make use of that class.
5. When I create a class, it will start with a default value of count = 0.
6. When I add a food Item, the count is increased by 1.
7. When I delete a food Item, the count is decreased by 1.
8. If I change the class of a food item, its old class will be reduced by 1 and the new class is increased by 1.
9. Deleting a food class is only allowed if that class is not used by any food item.


8. What will happen when I edit a class.
    1. I need to track all the food items that used the new class and have their class edited too.
    2. Having a count of the food items using that class should make sure that all items are edited.


    Breakdown:  
    1. Click edit button
    2. Go to edit page taking id  /edit_class/<class_id>
    3. Type the edit and press Edit Class button
    4. This will take you to the update class page, still carrying id, but now have the form data /update_class/<class_id>
    5. In the update route:
        1. classification = mongo.db.classification
        2. data = request.form.to_dict()
        3. del data["action"]
        4. Get old name of classification
        5. Check that it does not match the new Name (There was a change)
        6. If there was a change [ and count > 0] ie there are food items using this class:
            1. get food table
            2. Find all food items that make use of old class name - make a list of objects
            3. ~~Extra check if needed - decide later:~~
                * ~~Get class count and check that it matches the length of list of all food items using this class~~
            4. For each food item in list of food items:
                * Change the name of the class
        7. classification.update({"_id": ObjectId(class_id)}, data)
        8. return redirect(url_for('get_classification'))
    
    
    
    ## Bug - When I edit a class the count disappears

    Fixed

    ## Bug when editing class name to a name that already exist
    Fixed but want to add confirmation step.

    <h3>bug</h3>
    <p>When editing a class I need to make sure that the name is not already in use. I checked and at the moment I mess up the data with some classes being assigned to negative number of items and thus unable to deleted them, except from the database itself.</p>
        
    <h3>To do</h3>
    <p style="color: orange">When I edit the name, check if the name already exist. If yes, ask if the user wants to merge or create a new name. If it is a new name, enter the new name (check) and proceed as usual.</p>
    <p>If the user selects to merge, I need to find the items used by the class being edited and assing them to the new class, adding quantity of the new class and reducing from the edited class. Once the edited class reaches 0, I can delete that class</p>

    Want to add confirmation before merging.
    


Screen shots 

Edited with GIMP

Gif - first captured as .mov file using quickTime. Then turned into a gif using "Drop to Gif" App. 
This was further processed to reduce its size online at ezgif.com

