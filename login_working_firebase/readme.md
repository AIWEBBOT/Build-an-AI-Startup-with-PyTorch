additional files

this code is working ok but not getting email for verification.
https://stackoverflow.com/questions/37431128/firebase-confirmation-email-not-being-sent





Login-Signup-using-Firebase-master.zip  for additional information on firebase login




```firebase.auth().onAuthStateChanged(function(user) {
  user.sendEmailVerification(); 
});
```
Do note that:

    You can only send email verification to users object whom you created using Email&Password method createUserWithEmailAndPassword
    Only after you signed users into authenticated state, Firebase will return a promise of the auth object.
    The old onAuth method has been changed to onAuthStateChanged.

To check if email is verified:

```
firebase.auth().onAuthStateChanged(function(user) { 
  if (user.emailVerified) {
    console.log('Email is verified');
  }
  else {
    console.log('Email is not verified');
  }
});
```

