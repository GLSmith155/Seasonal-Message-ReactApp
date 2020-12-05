# Seasonal-Message-ReactApp
A React App that detects latitude of the user as well as the month, and based on that info they are greeted with a seasonally relevant message.

index.js:

The project functions by using a class component that initializes its state outside of the constructor method, as the project didn't call for a unique constructor. The method componentDidMount is then used to load the initial data, which gets the latitude of a user using geolocation, as well as setting the state as an error message for if the latitude is not found, or for if the user doesn't have location services enabled. Next a helper function has two if statements, and then an implied else statement. This makes it so that if there's an error, and no latitude found, the user is notified with an error message. If there isn't an error, and if a latitude is found, then the class component named SeasonDisplay is now returned. In all other cases, the else statement of 'Loading!' is given to the user. This helper function is then called inside this class component's render method. Additionally, this class component inside index.js is able to communicate the latitude to the SeasonDisplay class component by utilizing props, which have a prop value of the state '{this.state.lat},' which is one of the two values created when the state initializes (alongside a potential error message.)

How this React project works:

SeasonDisplay.js is a file that contains a functional component and two helper functions. The first function named getSeason determines the correct season using the latitude of the user and getMonth. The class component named SeasonDisplay works with the remaining function named seasonConfig to create a ternary expression. Inside the class component a const variable with the main object of { text, iconName } is equalled to the outer function named seasonConfig. seasonConfig is just defining what the text and icon value of each season should be, so that which ever season getSeason determined has an appropriate message/icons supplied to the main functional class component. Back in the main functional class component (SeasonDisplay), the return statement calls exactly two of the relevant icon ot the user's season and a text that gets passed into the return statement, where the return statement also applies formatting to them by calling css classes from the SeasonDisplay.css file. The information returned is then called into the helper function (renderConfig) inside the parent class component in the index.js file, which then calls and says, "if there's an error message and no lat, update the state by this.state.errorMessage. If there's no errorMessage and a latitude, then update the state with this.state.lat. If there is neither an errorMessage or lat, then return a reusable loading (spinner) component with the message, 'Please accept location request.' The render method then calls and returns the helper function, and the DOM is updated.
