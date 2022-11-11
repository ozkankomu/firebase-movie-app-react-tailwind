<p align="center">
<a href="https://www.linkedin.com/in/ozkankomu/" target="_blank"><img src="photo1.png" alt="screenshot" target=_blanked></a>
</p>



## Table of contents

  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Project Skeleton ](#project-skeleton)
  - [Links](#links)
  - [Built with](#built-with)
  - [Useful resources](#useful-resources)
  - [Author](#author)



## The challenge
In this project I made with React, I wanted to make a movie site where Login and Google login processes are made using firebase. I got the movie info and trailers from "https://www.themoviedb.org/documentation/api". I used Tailwind for styling css. I added Night (dark) mode and Day (Light) mode.


## Project Skeleton

```
006 - Movie App (folder)
|
|----readme.md         # Given to the students (Definition of the project)
SOLUTION
├── public
│     └── index.html
├── src
│    ├── auth
│    │     └── firebase.js
│    ├── components
│    │     ├── MovieCard.js
│    │     └── Navbar.js
│    ├── context
│    │     └── AuthContext.js
│    ├── pages
│    │     ├── Login.js
│    │     ├── Register.js
│    │     ├── Main.js
│    │     └── MovieDetail.js
│    ├── router
│    │     └── Router.js
│    ├── App.js
│    ├── App.css
│    ├── index.js
│    └── index.css
├── package.json
├── .env
└── yarn.lock
```

![Project 006 Snapshot](movie-app_structure.png)

## Expected Outcome

![Project 006 Snapshot](movie-app.gif)

## Objective

Build a Movie App using ReactJS.

### Built with

- HTML

- TAILWIND 

- JS

- ReactJS


## Steps to Solution


- Step 2 : Signup `https://firebase.google.com/` and create new app in firebase.
  Firebase is a backed application development software that enables developers to develop iOS, Android and Web apps. It provides developers with a variety of tools and services to help them develop quality apps, grow their user base, and earn profit. It is built on Google’s infrastructure. Firebase offers a number of services, including: analytics,authentication, cloud messaging, realtime database, performance and test lab. Firebase is categorized as a NoSQL database program, which stores data in JSON-like documents.

## Screenshot
<p align="left">
<a href="https://ozkankomu.github.io/firebase-movie-app-react-tailwind/"><img src="screen.gif" alt="screenshot" target=_blanked></a>
</p>




- Step 3 : Use `https://firebase.google.com/docs/auth/web/start` and create `Authentication` operations.
  - Add the Firebase Authentication JS codes in your `firebase.js` file and initialize Firebase Authentication:

```jsx
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";

// TODO: Replace the following with your app's Firebase project configuration at project settings part
// See: https://firebase.google.com/docs/web/learn-more#config-object
const firebaseConfig = {
  // ...
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

// Initialize Firebase Authentication and get a reference to the service
const auth = getAuth(app);
```

- Use this method to `Sign up new users` :

```jsx
import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

createUserWithEmailAndPassword(auth, email, password)
  .then((userCredential) => {
    // Signed in
    const user = userCredential.user;
  })
  .catch((error) => {
    console.log(error);
  });
```

- Go to https://console.firebase.google.com => Authentication => sign-in-method => `enable Email/password`
- Use this method to `Sign in existing users` :

```jsx
import { getAuth, signInWithEmailAndPassword } from "firebase/auth";

signInWithEmailAndPassword(auth, email, password)
  .then((userCredential) => {
    // Signed in
    const user = userCredential.user;
  })
  .catch((error) => {
    console.log(error);
  });
```

- Use this method to `Set an authentication state observer and get user data` :

```jsx
import { getAuth, onAuthStateChanged } from "firebase/auth";

onAuthStateChanged(auth, (user) => {
  if (user) {
    // User is signed in, see docs for a list of available properties
    // https://firebase.google.com/docs/reference/js/firebase.User
  } else {
    // User is signed out
  }
});
```

- Go to https://console.firebase.google.com => Authentication => sign-in-method => `enable Google`
- Use this method to `Authenticate Using Google with Popup` :

```jsx
import { GoogleAuthProvider } from "firebase/auth";

const provider = new GoogleAuthProvider();

signInWithPopup(auth, provider)
  .then((result) => {
    // The signed-in user info.
    const user = result.user;
  })
  .catch((error) => {
    // Handle Errors here.
    console.log(error);
  });
```

- Use this method to `Sign Out` :

```jsx
import { getAuth, signOut } from "firebase/auth";

signOut(auth)
  .then(() => {
    // Sign-out successful.
  })
  .catch((error) => {
    // An error happened.
  });
```

- Use this method to `Send a password reset email` :

```jsx
import { getAuth, sendPasswordResetEmail } from "firebase/auth";

sendPasswordResetEmail(auth, email)
  .then(() => {
    // Password reset email sent!
  })
  .catch((error) => {
    const errorMessage = error.message;
    // ..
  });
```

### Useful resources

- Step 4 : Signup `https://www.themoviedb.org/documentation/api` and get API key. In order to get data use `https://api.themoviedb.org/3/discover/movie?api_key=${API_KEY}`, to search movies use `https://api.themoviedb.org/3/search/movie?api_key=${API_KEY}&query=`, to get movie details use `https://api.themoviedb.org/3/movie/${id}?api_key=${API_KEY}` and to get video key use `https://api.themoviedb.org/3/movie/${id}/videos?api_key=${API_KEY}`. Use `https://image.tmdb.org/t/p/w1280${poster_path}` for image `src`.



## Author

- Author - [Ozkan]

<center> &#8987; Happy Coding  &#9997; </center>
