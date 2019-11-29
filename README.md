GuessTheWord 
==================================

Introduction
------------

This app is a two-player game, GuessTheWord. It is a word guessing app you can play with one or more friends. To play, hold the device in landscape, facing away from you with your thumbs on the **Skip** and **Got It** buttons. Your friends can then give you clues to help you guess the word. If you get the word right, press **Got It**. If you're stuck, press **Skip** or you can use the **End** button to end the game.

This application demostrates the Android Architecture components: MVVM(Model-View-ViewModel), LiveData and LiveData observer pattern.

When an application is not developed using MVVM Android Architecture, It wont be able to save data or restore the state of the app during configuration changes such as; when the app shuts down or restart, when the phone is tilted to the landscape mode. 
One can avoid this issue using the onSaveInstanceState() callback. However, using the onSaveInstanceState() method requires you to write extra code to save the state in a bundle, and to implement the logic to retrieve that state. Also, the amount of data that can be stored is minimal.

To resolve this issue finally, it is advisable to use android architecture(MVVM) when developing your app.

I also used android utility class called, CountDownTimer. The timer counts down until it reaches zero for a particular question. Once the count down reaches zero, the game is over, and your current score is viewed.

You must know how to work with fragments and layouts very well. I added the GameViewModel class for the GameFragment class that extends ViewModel.
I also added dependency in build.gradle(module:app) file to enable the ViewModel work.

I must explain some terms to make you understand better;

User Interface Controller
A UI controller is a UI-based class such as Activity or Fragment. A UI controller should only contain logic that handles UI and operating-system interactions such as displaying views and capturing user input. Don't put decision-making logic, such as logic that determines the text to display, into the UI controller.

In the GuessTheWord code, the UI controllers are the three fragments: GameFragment, ScoreFragment, and TitleFragment. Following the "separation of concerns" design principle, the GameFragment is only responsible for drawing game elements to the screen and knowing when the user taps the buttons, and nothing more. When the user taps a button, this information is passed to the GameViewModel.
ViewModel
A ViewModel holds data to be displayed in a fragment or activity associated with the ViewModel. A ViewModel can do simple calculations and transformations on data to prepare the data to be displayed by the UI controller. In this architecture, the ViewModel performs the decision-making.

The GameViewModel holds data like the score value, the list of words, and the current word, because this is the data to be displayed on the screen. The GameViewModel also contains the business logic to perform simple calculations to decide what the current state of the data is. 
ViewModelFactory
A ViewModelFactory instantiates ViewModel objects, with or without constructor parameters
 



