# CS360_MobileArchitect

# Briefly summarize the requirements and goals of the app you developed. What user needs was this app designed to address?

The inventory app required the use of separate database tables for user login/passwords and storing inventory items. The app needed to feature a screen for logging in and authenticating the user and displaying inventory items. It also needed mechanisms for updating inventory and sending SMS messages when inventory levels got low. 

The need for the app is to serve as a tool and justify transitioning the inventory system from traditional pen and paper to electronic. It needs to make the user’s daily operation easier and perform intuitively. 

# What screens and features were necessary to support user needs and produce a user-centered UI for the app? How did your UI designs keep users in mind? Why were your designs successful?

The first activity that opens when the app launches is the Login/Sign up screen. This featured TextViews to label the different EditTexts where users enter the information. It was important to have the Login/Sign Up buttons interact dynamically to let the user know which functions they are able to perform. With the EditTexts empty, both buttons would be disable to prevent accessing the database with empty queries. However, if username and password were entered, the Login button would enable and then disable again once the user typed first name and last name  which indicated a Sign Up action and would enable that button. 

To serve as home type of screen, the list of products in the database would be displayed by a RecyclerView that brings the most important details about a product the user. The current iteration of the app does not support adding images for the products, but the RecyclerView displayed a default image, name, sku, and inventory for each product. The user has an option to go to account details from the menu in the toolbar, a specific product’s detail screen, or a screen to add a new item.

The account detail screen has app and user information and lets the user grant permissions for the app to send SMS messages, and has an EditText to save the current user’s phone number to the user database. The UI includes a button for the user to grant permissions to send SMS messages. This gives clear indication of how to interact to achieve the desire result. The EditText for the phone number includes hint text to give clear direction of the desired format.

The product detail screen lays out the information from the database in an organized hierarchy. A menu is included in the tool bar to take actions for either deleting the product or continuing to the edit screen.

The edit product screen has the same layout as the previous detail screen, but with EditTexts that are initially set to the product’s values in the database. A clear save button is in the toolbar, as well as a Up button to return to the detail screen. 

Along the way, I made use of many Toasts to give helpful feedback for the status of actions, or details about the input validation.

# How did you approach the process of coding your app? What techniques or strategies did you use? How could those techniques or strategies be applied in the future?

The primary technique I used was the room persistence library. This simplified table creation by defining objects as entities. The room library also served as simple abstraction layer to SQLite so that future queries and functions can be implemented easily.

# How did you test to ensure your code was functional? Why is this process important, and what did it reveal?

Throughout the development process, I would consistently run the app on the emulator to validate functionality. For any unexpected behaviors, I would make use of the Android Studio debugger tool to identify logic errors. The logcat tool also provided helpful information any time the app would crash. 
# Consider the full app design and development process from initial planning to finalization. Where did you have to innovate to overcome a challenge?

I believe the greatest innovation during this process actually came from addition by subtraction. I was very ambitious during the design phase and wanted to include an activity to display transactions or changes that were made to the products. During the development phase, it became apparent that there was not an intuitive UI experience to implement this activity with my current knowledge. I weighed the options and decided the app would serve the user better now with a simplified UI, rather than adding features that could potentially make the app less appealing.

# In what specific component of your mobile app were you particularly successful in demonstrating your knowledge, skills, and experience?

In this process, I believe my best work was dynamically updating UI components depending on the context of the app. An example of this is the first login activity. The buttons and other views react intuitively. A “New user?” text view lets the user expand the necessary fields to create an account while simultaneously disabling the login button and enable the sign up button. Once the user account is inserted into the database, the extra fields collapse again and the user is prompted to sign in with the newly created credentials. 

A similar approach is in the user setting activity. If the user has previously, granted permissions for sending SMS messages, the button will be disabled to serve as a reminder.





