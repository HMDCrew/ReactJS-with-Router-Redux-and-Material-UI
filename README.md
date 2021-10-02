# ReactJS with Router, Redux and Material UI
#### Login system Front-End for [Laravel with JWT Auth](https://github.com/HMDCrew/Laravel-Backend-JWT-Auth "Laravel Backend with JWT Auth")
<br />

## Install React
    npx create-react-app *<name-of-app>*
    cd <name-of-app>

## Install React-Router and React-Router-Dom
    npm i --save react-router react-router-dom

## Install Material-UI: 
    npm i @material-ui/core
    npm i @material-ui/icons

## Install Redux and React Redux, Redux-thunk
    npm i --save-dev redux react-redux redux-devtool redux-devtools redux-thunk

## Directory Structure
![alt text](https://github.com/HMDCrew/ReactJS-with-Router-Redux-and-Material-UI/blob/main/GitImages/three.png?raw=true)

## Services
*/src/services/HttpService.js*<br />
HTTP is a service that sets a global URL for GET and POST requests
<br /><br />
*/src/services/AuthService.js*<br />
AuthService is a service that manages user authentication, registration and logout
<br /><br />
*/src/services/ProfileService.js*<br />
ProfileService is an information request service only if the user is authenticated
<br /><br /><br />
## Redux
*/src/redux/CreateStore.js*<br />
Create redux store and load redux-devtools extension
<br /><br />
*/src/redux/ActionTypes.js*<br />
Create ActionTypes
<br /><br />
*/src/redux/actions/AuthActions.js*<br />
*/src/redux/actions/ProfileActions.js*<br />
AuthActions.js and ProfileActions.js, in these files we will send our various actions (we will export them from the ActionTypes files) to the application.
<br /><br />
*/src/redux/reducer/AuthReducer.js*<br />
For each of the cases, except the default case, we deconstruct the state, then add the response to the unstructured state based on the submitted actions.
<br /><br />
*/src/redux/reducer/ProfileReducer.js*<br />
we set the value of userProfile to an empty string, then we manipulate the state by first deconstructing the state and adding the response to the state depending on the actions sent.
<br /><br />

> redux allows us to combine multiple reducers into one which can be passed to our store using a helper function called combineReducers.

*/src/redux/reducer/RootReducer.js*<br />
We import combineReducers from redux and we also import the individual reducer files. We then invoke combineReducers and pass to it as argument an object that contains all the individual reducers (AuthReducer and ProfileReducer) in this case.
<br /><br /><br /><br />

## Create Guards and Routes
*/src/Guards.js*<br />
We import the Routes and Redirects from react-router-dom. Our Guard will take parameters.
<br /><br />
1. Component - The component that we want to pass to our guard
2. Token - This is our access token
3. Path - This is basically the path we want to redirect to
4.… Rest (we deconstruct it from the rest) That is, we take all the remaining properties defined on the props object and collect them inside an argument called rest.
Next, we call our which will take our last unstructured parameter and render a function which will pass our props as a parameter. The function will check if our access token exists in our local storage. If the token exists, it redirects the user to the path the user wants to access, otherwise it redirects the user to a path that we will specify.
<br /><br />

*/src/PrivateRoute.js*<br />
Specify the routes of token
<br /><br />
*/src/Routes.js*<br />
This Route.js will enable us to navigate between different pages of our application.
<br /><br /><br />

## Core of application
*/src/index.js*<br />
First, we import our store from our redux folder and Provider from react-redux. We wrap the Provider around our application. The provider makes our redux store available to every component inside our application.
<br /><br />
*/src/App.js*<br />
In our App.js, as you can see, we import the Routes.js and also wrap the whole application inside the BrowserRouter imported from ‘react-router-dom’. This enables routing on our application using url segments. This makes our single page application feel more like a traditional webpage.
<br /><br /><br />

## Parts of page and Pages
*/src/components/layouts/*<br />
In this folder we can specify the general layout parts for example the header or footer of application 
<br /><br />
*/src/components/pages/*<br />
In this folder we can create the all pages of application
