# Seasonal-Message-ReactApp
A React App that detects latitude of the user as well as the month, and based on that info they are greeted with a seasonally relevant message.

index.js

The project functions by using a class component that initializes its state outside of the constructor method, as the project didn't call for a unique constructor. The method componentDidMount is then used to load the initial data, which gets the latitude of a user using geolocation, as well as setting the state as an error message for if the latitude is not found, or for if the user doesn't have location services enabled. Next the render method has two if statements, and then an implied else statement. This makes it so that if there's an error, and no latitude found, the user is notified with an error message. If there isn't an error, and if a latitude is found, then the class component named SeasonDisplay is returned. In all other cases, the else statement of 'Loading!' is given to the user. The component of index.js is able to communicate the latitude to the SeasonDisplay class component by utilizing props, which have a prop value of the state '{this.state.lat},' which is one of the two values created when the state initializes.

SeasonDisplay.js

SeasonDisplay.js file contains a class component, and two functions. The first function named getSeason determines the correct season using the latitude of the user and getMonth. The class component named SeasonDisplay works with the remaining function named seasonConfig to create a ternary expression. Inside the class component a const variable with the main object of { text, iconName } is equalled to the outer function named seasonConfig. seasonConfig is just defining what the text and icon value of each season should be. And then back in the component class two of the icons of the correct season are selected, and we call the message only once in a h1 header between the two icons.
