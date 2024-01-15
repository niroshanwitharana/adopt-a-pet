# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `yarn build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)


Adopt a Pet!
In this project, you will have the opportunity to practice using React Router to add client-side routing to a React Application. Specifically, you will be building a pet adoption website that allows users to view all the animals of a particular species and view the profiles of specific animals.

Currently, the app renders a HomePage component that fetches and displays all adoptable pets (you can view the code for this page in src/pages/home/index.js). We have also built a PetDetailsPage to display the details for a particular pet (src/pages/detail/index.js), but this component will not render until you create a route to display it.

Your objective will be to add client-side routing to the application using React Router so that:

The HomePage component responds to the browser’s current URL by displaying only pets of the species the user wishes to view.
The PetDetailsPage page displays when the browser’s current URL includes a specific pet’s id.
The PetDetailsPage displays data for the correct pet based on the id in the URL parameters’ values.
When the user searches for a pet in the search bar, they are redirected to the SearchPage, which uses the query parameter called name to filter pets by name.
When a user clicks a pet whose details are not available, they are redirected to a PetNotFoundPage.
From the PetNotFound page, users can click “Go Home” button that will take them to the root path page.
Before you get started, spend some time familiarizing yourself with the project’s starting code. In particular, in the src/ folder, take note of the components that you’ll be primarily working with:

src/App.js (App)
src/pages/home/index.js (HomePage)
src/pages/detail/index.js (PetDetailsPage)
src/pages/search/index.js (SearchPage)
src/pages/petNotFound/index.js (PetDetailsNotFound)
This lesson uses Mock Service Worker (MSW) to replicate the functionality of an external API. To use MSW, you’ll want to use Google Chrome and enable third-party cookies.

Setup Instructions
This project should be completed on your own computer instead of on Codecademy. You can download what you’ll need by clicking the “Download” button below. If you need help setting up your computer, read our article about setting up a text editor for HTML/CSS development.

Once you’ve downloaded the project, open up the project folder in your text editor. Then, make sure to install all of the dependencies by running the command below:

npm install

Finally, you can start the application locally by running the command below:

npm start

As you can see, the project is bare-bones right now because you’ll need to create routes and hook up the router by using React Router.

Note: This application was created using Create React App.

Download
Tasks
20/31 complete
Mark the tasks as complete by checking them off
Installing React Router and Initial Set Up
1.
Let’s start by installing react-router-dom so that we can use React Router components in the project. Use the command below:

npm install --save react-router-dom@6

To check that you were successful, ensure that react-router-dom appears in the list of dependencies located within your project’s package.json file.


Stuck? Get a hint
2.
In order for the entire application to be able to communicate with React Router we’ll need to provide it at the root level of the application.

In src/App.js, import React Router’s RouterProvider.


Stuck? Get a hint
3.
In src/App.js you’ll notice a constant appRouter defined, and in the App component return statement you’ll also notice a <p> element with the text REPLACE ME.

Replace <p> with RouterProvider and define the attribute router with the value of appRouter.

Note: This won’t do anything until you adequately set up appRouter.


Stuck? Get a hint
4.
In this project, we’ll be using JSX to create routes so we’ll use React Router utility functions and components to help with that.

In src/App.js, import React Router’s createBrowserRouter, createRoutesFromElements, and Route.


Stuck? Get a hint
Creating Your First Route
5.
Now that the setup is complete, we can add routing to the application by adding the first route. In this application, we’ll want content that is always displayed regardless of the path like navigation/sidebars. To do this, let’s provide a “root” route to the path / that should render the Root component that was imported for you.

To create a route you’ll need to properly initialize the variable appRouter in src/App.js. Replace the string "REPLACE ME" with a new Route with the path /, that renders the element Root.

Note: This won’t display anything until you adequately set up appRouter.


Stuck? Get a hint
6.
We’ve created a Route element but the RouterProvider only accepts route objects. Using React Router’s createRoutesFromElements() utility function, we can transform a Route component to a route object.

In src/App.js, wrap the Route element created in the previous task with the createRoutesFromElements() function.

Note: This won’t display anything until you actually create a router object which you’ll do next.


Stuck? Get a hint
7.
Finally, in order to work with React Router, we’ll need a router. React Router’s createBrowserRouter() accepts route objects to initialize a router for us.

In src/App.js, wrap the call to createRoutesFromElements() from the previous exercise with createBrowserRouter(). Make sure this result is assigned to the appRouter constant defined for you.

You should be able to test this change at http://localhost:3000 and see the navigation bar rendered.

Note: You’ll see the navigation bar but won’t see any other content or click all the links without errors (you’ll fix this later).


Stuck? Get a hint
Nested Routes and the Index Route
8.
You may have noticed that only the navigation bar is currently visible and none of the main content of the webpage is. The application should render the HomePage component alongside the navigation bar when a user goes to the root, /, path. We can do this by creating a nested index route.

In src/App.js, where you defined the Route to render the Root element, add a nested Route that renders the HomePage component on the root path /.

Note: The HomePage element still won’t render until you add an Outlet (you’ll do this next).


Stuck? Get a hint
9.
In order for nested routes to render properly we’ll need to “tell” the parent route where it should render nested elements. We can use React Router’s Outlet component to do this.

In src/components/root/index.js, import Outlet from react-router-dom. In the return statement of Root, add the Outlet component under the Navigation component.

You should be able to see the navigation bar and the HomePage rendered on your screen when you visit the root path, /.


Stuck? Get a hint
Using URL Parameters in Your React Components
10.
The application is able to display all types of pet data available in HomePage but it can also filter the animals shown by the type selected in the navigation bar (“dogs”, “cats”, “rabbits”, “birds”). If you click on any of the links in the navigation bar you’ll notice the path changes to a path like /dogs or /cats but the HomePage doesn’t render. Let’s fix that by adding a dynamic path to the router.

In src/App.js, add a new nested route within the Root Route that renders HomePage using a dynamic path with a URL parameter called type.

To test that your code works, try clicking on a particular species or navigating to /cat or /dog.

Note: The HomePage will not filter pet data just yet until we use the URL parameter (you’ll do this next).


Stuck? Get a hint
11.
Within the HomePage component, a variable called type is defined that should hold the value of the :type URL parameter.

In src/pages/home/index.js, import useParams from react-router-dom and use it to update the type constant so that it holds the :type URL parameter’s value.

To test that your code works, click on one of the species links – you should now see only pets of that type!

How does this work? Inside the useEffect() hook, we’ve passed type to our API’s getPets method which fetches pets of the specified type to be rendered on the page. Now, this type comes from the URL parameter (rather than an empty string)! 


Stuck? Get a hint
12.
Great work! The functionality to navigate to different pet types works, however, we’re not seeing the individual animal’s details. The component designed to do that is the PetDetailsPage which has already been imported into src/App.js.

Back in src/App.js add another nested route under the Root Route that renders the PetDetailsPage component. This Route‘s path should match URLs such as /dog/123 or /cat/456. This URL path will need two URL parameters: the animal’s species and the specific id. The names for these parameters should be :type and :id respectively.

To test that your code works, click on one of the pets listed on the home page. You should be redirected to the detailed view of Shuri the cat!

But… maybe you didn’t click on Shuri? Continue on to the next task to fix this.


Stuck? Get a hint
13.
Try clicking on a few different pets and notice that you’ll keep seeing the details for Shuri the cat! Take a look at the PetDetailsPage component, found in src/pages/detail/index.js. Here, you’ll see that we’ve hard-coded a pet id.

To make this page render the details for the actual pet your user has selected, import and use the useParams() hook to get the value of the :id URL parameter and update the id variable in the PetDetailsPage component.

To test that your code works, refresh the page. You should see the details for the pet you clicked.

Note: Only the pets with a real picture will have pet details. Later on, we will route users to a default page when they click on a pet with a missing picture and missing details.


Hint
To get the value of the :id URL parameter, you’ll need to first import the useParams hook. Then, call it and use destructuring assignment to get the value of the id property on the resulting object and store it in a constant named id.

The syntax to get the value of the URL parameters for the dynamic path /:foo/:bar from the object returned by a call to useParams() will look like:

const { foo, bar } = useParams()

Replacing `<a>` Tags with React Router Elements
14.
When you tested your work for the last task by clicking on one of the species’ links in the navigation bar, you may have noticed a conspicuous page reload. Recall that this happens when we use native a tags (instead of React Router’s Link and NavLink components) to navigate to client-side routes.

In the Navigation component (located in src/components/navigation/index.js), we’ll improve your user’s experience by replacing the a tags with React Router’s NavLink component. First, you have to import NavLink from react-router-dom.


Stuck? Get a hint
15.
Next, replace the a tags in the Navigation component with NavLink components. As you give these NavLink components their props, remember that NavLink has a to prop instead of the a tag’s href attribute.

You can test these changes by clicking on one of the species’ links in the navigation bar and seeing the content change without refreshing.


Stuck? Get a hint
16.
When users navigate with the navigation bar it would be ideal if there was some visual indication on the page of which navigation link they’re currently on.

In public/index.css, we’ve written a CSS selector for the class .nav-link-active that will darken the background of any element with that class name. Modify all the NavLink className props to accept a function that receives an object (destructure this object to just a property called isActive). The function body should return the string 'nav-link nav-link-active' if isActive is true and 'nav-link' if false.

You can try navigating to different links in the navigation bar and see a darker background only on the link you are currently on.


Stuck? Get a hint
17.
Notice that if you click on an individual animal’s link, the page will refresh. Instead, we want to use React Router Links to skip that refresh. Like NavLink, the Link component has a to property in place of the a tag’s href.

First, in src/pages/home/index.js, import Link from ‘react-router-dom`.

Then, replace each a tag in the HomePage component with a Link component and href with a to prop.

When you complete this task, clicking on an individual pet will no longer cause the page to reload.


Stuck? Get a hint
Adding a Search Feature
18.
Nice job! Your next task will be to add a search feature to the pet adoption website. We’ve included a search bar for you in the Navigation component, but it doesn’t currently work. Your task will be to add React Router to this search bar so that when a user searches for a particular pet, they are redirected to a page showing all pets whose names match the search query.

First, we’ll need to make the search bar update the URL when the user enters a new search query. We will do this imperatively using the useNavigate hook.

Inside the Search component (src/components/search/index.js), import the useNavigate() hook. Then, inside the Search component, call useNavigate() and store the returned value in the navigate variable defined for you. This will allow us to control the current URL location.


Stuck? Get a hint
19.
In onSearchHandler(), a searchQuery variable has been created for you. This will be the query parameter we’ll want to add to the URL. Before being able to use searchQuery we’ll need to wrap it using createSearchParams() so it can be used with the navigate function.

First import createSearchParams from react-router-dom. Next, in onSearchHandler(), you’ll notice a variable called query. Use this to store the result of calling createSearchParams() with searchQuery as an argument.


Stuck? Get a hint
20.
In onSearchHandler(), we can use the query variable defined in the last task with the navigate function.

Below query, use the navigate function to imperatively redirect the user to a path with the pattern /search?name=fido.

Test out your code by searching for a value in the search bar. If you search for “fido” then the URL should become /search?name=fido.

Note: Only the path will change. You’ll render a new component on this path next. 


Stuck? Get a hint
21.
Back in src/App.js we want to render the SearchPage whenever the user enters text into the search bar and is redirected to paths like /search?name=fido.

Add a nested Route under the Root Route that renders the SearchPage component we’ve imported for you. This Route‘s path prop should match URLs that begin with /search.

To test that your code works, try typing something into the search bar and hitting enter. The SearchPage component should be rendered.

Note: The SearchPage will not show the filtered pets yet.


Hint
In the example URL /search?name=fido, the ?name=fido portion of the URL is a query parameter. Query parameters do not need to be specified in the path prop since they are part of the URL’s query string, not its path!

Therefore, the Route component for the SearchPage should look like this:

<Route path='/somepath' element={ <MyComponent/> } />

22.
Now, the SearchPage component will be rendered whenever the user types a query into the search bar. When searching for a pet, users will be redirected to URLs such as /search?name=fido, where fido is the search query.

In order to render the pets that match the specified query, we will need to capture the query parameter value from ?name=fido. Remember, we can do this with the useSearchParams() hook.

First, in src/pages/search/index.js, import React Router’s useSearchParams() hook.


Stuck? Get a hint
23.
Next, inside the SearchPage component, call useSearchParams() and get the searchParams property on the list it returns by using the destructuring assignment.


Stuck? Get a hint
24.
Finally, use the get() method of searchParams() to retrieve the ‘name’ query parameter and replace the value of petNameToFind with it.

To test that your code works, try searching for "Shuri" and you should see our favorite cat appear in the search results!


Stuck? Get a hint
Adding a "Pet Details Not Found" Page
25.
Nice work! The next (and last) feature we’ll add to the application is a PetDetailsNotFound page in the event that the user clicks on a pet whose details are not yet available. Back in src/App.js this component has already been imported for you.

First, in src/App.js, add a nested route under the Root Route that renders the PetDetailsNotFound component when the current URL’s path is '/pet-details-not-found'.

To test that your code works properly, navigate to /pet-details-not-found in your URL bar.


Stuck? Get a hint
26.
When a user clicks on a specific animal in the HomePage, the PetDetailsPage (found in src/pages/detail/index.js) will be rendered. If a pet’s details are not found the API call to getPetDetails(id) will return an error.

Your task is to conditionally redirect the user to '/pet-details-not-found' whenever that happens.

First, In src/pages/detail/index.js, import React Router’s Navigate component.


Stuck? Get a hint
27.
Next, update the return statement of the PetDetailsPage component to render Navigate if the getPetDetails API call returns an error. The to prop for Navigate should cause the application to render the PetDetailsNotFound component.

Test that your code works by clicking on ‘Dottie’—the second pet in the ‘All Pets’ view. Since we don’t have Dottie’s details, the API will return an error and you should be redirected to the PetDetailsNotFound page.


Stuck? Get a hint
28.
It would be nice if the user could easily navigate away from the PetDetailsNotFound page to the root page. We’ve provided a button for this purpose, but you will need to use React Router’s navigate function to imperatively redirect the user when it is clicked.

First, in src/pages/petDetailsNotFound/index.js import React Router’s useNavigate hook.


Stuck? Get a hint
29.
Inside the PetDetailsNotFound component, replace the value of the variable navigate with the function returned from useNavigate().


Stuck? Get a hint
30.
The onClick prop of the ‘Go Home’ button is set to the callback function goHome(). Use the navigate function to redirect the user to the home page when the user clicks on the ‘Go Home’ button.

Test out your code by clicking on a pet whose details have not been loaded yet and then click on the “Go Home” button. You should be redirected back to the root page.


Stuck? Get a hint
31.
Great work! Visit our forums to compare your project to our sample solution code. You can also learn how to host your own solution on GitHub so you can share it with other learners! Your solution might look different from ours, and that’s okay! There are multiple ways to solve these projects, and you’ll learn more by seeing others’ code.