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

- This is a frontend React applications with no backend development required, bootstrapped using Create React App](https://facebook.github.io/create-react-app/)
- The idea is to build a single page with a stacked bar chart, displaying the number of photos (per album) for 7 users (the data is obtained from an API endpoint). Each user may have multiple albums, and each album may have multiple photos. Each bar therefore shows the total number of photos per user; and each stack within each bar corresponds to each album.
- In addition to the bar chart, there are two controllable UIs:
  - a simple sort control, which sorts the bars according to the alphabetical value of the user's email address (ascending or descending).
  - a filter which lets you remove certain albums from consideration in the bar chart.
- UI should be fully responsive (mobile, tablet and desktop) and will be tested on Chrome browser.
- Implementation should use functional React component, and make use of the hooks API.

#### API endpoint for users data

You will use https://jsonplaceholder.typicode.com/ to retrieve user profile, album, and photo data. The API endpoints contain data for ten users, however for the purpose of this application you should randomly display seven of those users. Each time the page refreshes, the seven users should be randomly re-chosen.

The following API endpoint will retrieve the data that you need for the user profiles:
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

For the purpose of this application, we are only interested in the user's `email` and `id`.

The `id` parameter can be matched with the albums list. You may use either of these endpoints to retrieve the album data:
```
METHOD: GET
URL: https://jsonplaceholder.typicode.com/albums
```
to get album information for all users, OR
```
METHOD: GET
URL: https://jsonplaceholder.typicode.com/users/${userId}/albums
```
where `${userId}` is replaced with each user's id.

Either way, you schema of the data in the response is :
```Javascript
// Array of albums
[
  {
    userId,	// The user's id, matched to the previous API
    id, // album id
    title
  }
]
```
You will use all three of the fields (`userId`, `id`, and `title`) in this application.

To get the list of photos belonging to each album, you can use either of the following endpoints:
```
METHOD: GET
URL: https://jsonplaceholder.typicode.com/photos
```
to get photos for all albums, OR
```
METHOD: GET
URL: https://jsonplaceholder.typicode.com/albums/${albumId}/photos
```
where `${albumId}` is replaced with each album's id.

Either way, you schema of the data in the response is :
```Javascript
// Array of photos
[
  {
    albumId,	// The album's id, matched to the previous API
    id, // photo id
    title,
    url,
    thumbnailUrl
  }
]
```
For the purpose of this application, you will only need to count the number of photos per album: the `title`, `url`, and `thumbnailUrl` fields can be discarded.

Tip: make sure not to mix up the user, album, and photo ids!


#### Bar Chart & Controls

You will follow these design specifications for this app: https://www.figma.com/file/qcovixXgzZ0smmUjZgJZRZ/Nexxt-React-Test

For the bar chart, you will use the [@nivo/bar](https://nivo.rocks/bar) library.

For the two controls (sort and filter), you will use the [react-select](https://react-select.com/) library. The sort control will simply use the email of each user, sorting them alphabetically (ascending or descending). The filter control will show a complete list of album titles for every user, using the `title` field from the album API. Selecting any of the albums should cause that data to be filtered out of the bar chart. For example, if user 1 has 6 albums, they would normally have 6 stacks in their bar. If one of their albums if filtered out, then their bar chart would only have 5 stacks.


#### Bonus
- To make the experience complete, you can add a loading indicator to display while the data is being fetched from the API. You may want to use [http://tobiasahlin.com/spinkit/](http://tobiasahlin.com/spinkit/).
- If you are familiar with Typescript, you can use this as a chance to show off your typing knowledge!
- What happens when the API fails? Consider adding a React error boundary to show an appropriate error message.
