<p>S.Yılmaz<img align="right"
  src="https://miro.medium.com/v2/resize:fit:1200/1*OYUijA9Q8o_U243FEdwjUA.jpeg"  width="25px"></p>

# React Movie App

## Description

Project aims to create a Movie App.


## Project Skeleton

```
React Movie App
|
|----readme.md         
SOLUTION
├── public
│     └── index.html
├── src
│    ├── auth
│    │     └── firebase.js
│    ├── components
│    │     ├── MovieCard.jsx
│    │     └── Navbar.jsx
│    │     └── Switch.jsx 
│    │     └── VideoSection.jsx.js
│    │
│    │
│    ├── context
│    │     └── AuthContext.js
│    │     └── MovieContext.js│    │
│    │
│    │ 
│    ├── helper      
│    │      └── ToastNotify.js
│    │ 
│    │
│    │
│    │
│    ├── pages
│    │     ├── Login.jsx
│    │     ├── Register.jsx
│    │     ├── Main.jsx
│    │     └── MovieDetail.jsx
│    │
│    │
│    ├── router
│    │     └── AppRouter.jsx
│    │     └── PrivateRouter.jsx
│    │
│    │
│    ├── App.js
│    ├── index.js
│    └── index.css
├── package.json
├── .env
└── yarn.lock
```

![Project Snapshot](movie-app_structure.png)

## Expected Outcome

![Project Snapshot](movie.gif)

## Objective

I created a Movie App using ReactJS.

### At the end of the project, following topics are to be covered;

- HTML

- CSS

- JS

- ReactJS

### Project Movie App with React

- I used improve coding skills within HTML & CSS & JS & ReactJS.

- I used git commands (push, pull, commit, add etc.) and Github as Version Control System.

## Steps to Solution

- Before start you can watch these tutorials:
  - https://www.youtube.com/watch?v=9bXhf_TELP4
  - https://www.youtube.com/watch?v=vDT7EnUpEoo
- Step 1 : Create React App using `npx create-react-app movie-app` and install firebase `npm i firebase` / `yarn add firebase`

- Step 2 : Signup `https://firebase.google.com/` and create new app in firebase.
  Firebase is a backed application development software that enables developers to develop iOS, Android and Web apps. It provides developers with a variety of tools and services to help them develop quality apps, grow their user base, and earn profit. It is built on Google’s infrastructure. Firebase offers a number of services, including: analytics,authentication, cloud messaging, realtime database, performance and test lab. Firebase is categorized as a NoSQL database program, which stores data in JSON-like documents.

![Project 005 Snapshot](firebase-create-app.gif)

- Step 3 : I used`https://firebase.google.com/docs/auth/web/start` and create `Authentication` operations.
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

- I used this method to `Sign up new users` :

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
- I used this method to `Sign in existing users` :

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

- I used this method to `Set an authentication state observer and get user data` :

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
- I used this method to `Authenticate Using Google with Popup` :

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

- I used this method to `Sign Out` :

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

- I used this method to 'send a password reset email` :

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

- Step 4 : Signup `https://www.themoviedb.org/documentation/api` and get API key. In order to get data use `https://api.themoviedb.org/3/discover/movie?api_key=${API_KEY}`, to search movies use `https://api.themoviedb.org/3/search/movie?api_key=${API_KEY}&query=`, to get movie details use `https://api.themoviedb.org/3/movie/${id}?api_key=${API_KEY}` and to get video key use `https://api.themoviedb.org/3/movie/${id}/videos?api_key=${API_KEY}`. Use `https://image.tmdb.org/t/p/w1280${poster_path}` for image `src`.

-  I used tailwind.css in the project.



## Notes

- I added dark mode and light mode to my project with tailwind.css

## Demo
<a href="https://movieapp-tailwind.vercel.app/" target="_blank">React Movie App</a>

**<p align="center">&#9786; Happy Coding &#9997;</p>**
