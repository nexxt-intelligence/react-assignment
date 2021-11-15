# Nexxt Intelligence - ReactJS assignments

Here we provide the instructions for developing a ReactJS application, designed by the Nexxt Intelligence team, to test the proficiency of applicants for the ReactJS Frontend Developer position(s):

## Prerequisites
* Knowledge of ReactJS (obviously), HTML, CSS
* Knowledge of installing npm packages (both local & global)
* Knowledge of creating React application using [Create React App](https://facebook.github.io/create-react-app/)
* Knowledge of fetching JSON data from a REST API endpoint
* A Github account in order to share his/her code with us

## Submission guidelines

### Sharing the code

All applicants must share their code in one of the following ways:

 - Upload their code on their Github account by creating a public repository and sharing the link via email.
 - Creating a zip file of their project folder (excluding the node_modules directory) and either uploading it to a cloud service (sharing the link with us) or attaching it to an email (if size < 20 MB).

### What are we looking for?

With this assignment we would evaluate the following:

 - Understanding of React fundamentals
 - Understanding of functional components and hooks API
 - Basic understanding of state management and component lifecycle methods
 - Fetching data from an API endpoint
 - Working with structured data
 - Ability of the applicant to learn a new React UI library and use its components in their app
 - Ability to implement a component adhering to design specifications


## Assignment Details

- This is a frontend React applications with no backend development required.
- The idea is to build a single page with a stacked bar chart, displaying the number of photos (per album) for 6 users (the data is obtained from an API endpoint). Each user may have multiple albums, and each album may have multiple photos. Each bar therefore shows the total number of photos per user; and each stack within each bar corresponds to each album.
- In addition to the bar chart, there are two controllable UIs:
  - a simple sort control, which sorts the bars according to the alphabetical value of the user's email address (ascending or descending).
  - a filter which lets you remove certain albums from consideration in the bar chart.
- UI should be fully responsive (mobile, tablet and desktop) and will be tested on Chrome browser.
- Implementation should use functional React component, and make use of the hooks API.

#### API endpoint for users data
@TODO
All 10 users profile data is to be downloaded from the following API endpoint:
```
Method: GET
URL: https://jsonplaceholder.typicode.com/users
```

The schema of the data received in the response is:
```Javascript
// Array of 10 users
[
  {
    id,	// The user's id
    username,
    name,
    email,
    phone,
    website,
    address: {
	  street, // Address line 1
	  suite, // Address line 2
	  city,
	  zipcode
    },
    company: {
	  name, // The name of company where the user works
    }
  }
]
```

#### Loading Indicator

Upon opening the app a loading indicator is displayed until the data is fetched from the API and is ready to be displayed. The source code for the loading indicator can be obtained from: [http://tobiasahlin.com/spinkit/](http://tobiasahlin.com/spinkit/).

#### Bar Chart & Controls

You will follow these design specifications for this app: https://www.figma.com/file/qcovixXgzZ0smmUjZgJZRZ/Nexxt-React-Test

For the bar chart, you will use the [@nivo/bar](https://nivo.rocks/bar) library.

For the two controls (sort and filter), you will use the [react-select](https://react-select.com/) library.
