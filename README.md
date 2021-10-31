# Create customer on Paystack and charge the customer on Firestore write

This sample project shows you how to create a customer on Paystack when a user signs up and then charges them when a new document is written to Firestore.

### Features

- Create a Paystack customer when a user signs up. ([Learn more](https://paystack.com/docs/api/#customer)).
- Create a Charge to initiate payment when a new document is written to the `payments` collection. ([Learn more](https://paystack.com/docs/api/#charge-create)).

#### Further reading:

- Paystack Docs: https://paystack.com/docs/api
- Firebase docs: https://firebase.google.com/docs/functions

## Deploy and test

- Create a Firebase Project using the [Firebase Developer Console](https://console.firebase.google.com)
- Enable billing on your project by switching to the Blaze plan. See [pricing](https://firebase.google.com/pricing/) for more details. This is required to be able to do requests to non-Google services.
- Enable Google & Email sign-in in your [authentication provider settings](https://console.firebase.google.com/project/_/authentication/providers).
- Install [Firebase CLI Tools](https://github.com/firebase/firebase-tools) if you have not already and log in with `firebase login`.
- Configure this sample to use your project using `firebase use --add` and select your project.
- Install dependencies locally by running: `cd functions; npm install; cd -`
- [Add your Paystack Secret Key](https://dashboard.paystack.com/#/settings/developer) to firebase config:
  ```bash
  firebase functions:config:set paystack.secret=<YOUR PAYSTACK SECRET KEY>
  ```
- Deploy your project using `firebase deploy`

### Run the client locally

Since this project uses Firebase Auth triggers, the functions need to be deployed.
```
firebase deploy --only functions ## only needs to be run when you make changes to your functions
```