---
title: Realtime Database Set Up
weight: 3
---

In this section, we are going to set up a Realtime Database and use some security rules that will
work with the code examples.

## Setting Up a Realtime Database:

{{% steps %}}

### Go to the Firebase Console

- Navigate to [Google Firebase](https://firebase.google.com/)
- Click on **go to console** in the upper right
- Login with your google account (if you weren't logged in already)

  It is possible that you have to start a google developer account, which is fine. You also might
  have to add billing information. Don't worry about this step as the programs we are creating and
  the extent of the internet traffic will not lead to any charges.

### Create the Firebase Project

- Add a new firebase project, and provide a name, e.g. **MyExp**
- Disable google analytics
- When project has been created, click on </> icon above **add an app to get started** to create a
  web app.
- Register the app with the name **MyExp** and Disable Firebase hosting
- Click **Register app**
- In Step 2, **Add Firebase SDK**, choose **Use a < script > tag**. This should produce some code
  snippet that looks as follows:

  ```json
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "firebase/app";
  // TODO: Add SDKs for Firebase products that you want to use
  // https://firebase.google.com/docs/web/setup#available-libraries

  // Your web app's Firebase configuration
  const firebaseConfig = {
    apiKey: "YOUR INFO",
    authDomain: "YOUR INFO",
    databaseURL: "YOUR INFO",
    projectId: "YOUR INFO",
    storageBucket: "YOUR INFO",
    messagingSenderId: "YOUR INFO",
    appId: "YOUR INFO"
  };

  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  ```

  Note that the specific details of the configuration are hidden here (the YOUR INFO placeholders),
  and this configuration will be unique to your project. We will need to use the text circles in
  red.

- Copy the text from lines 6-15 and save to a text file called `firebaseconfig.js`. Place this
  JavaScript file in a directory where you will store all your HTML code. Your file will look like
  this:

  ```json
  // Your web app's Firebase configuration
  //  (insert your own configuration info)
  const firebaseConfig = {
    apiKey: "YOUR INFO",
    authDomain: "YOUR INFO",
    databaseURL: "YOUR INFO",
    projectId: "YOUR INFO",
    storageBucket: "YOUR INFO",
    messagingSenderId: "YOUR INFO",
    appId: "YOUR INFO"
  };
  ```

- Click **continue to console**

### Create a Realtime Database

- Under the **build** menu on the left, click **Realtime database**
- Choose your database location (default is fine) and click **next**
- Select **start in test mode** and click **Enable**
- Let's change the security rules to the default setting for this course. Click on the
  **rules tab**
- There should be a screen that looks like this:
  <img src="/mplib-docs/imgs/firebase/firebase-rules.png" />
- Edit this text to the following

  ```json
  {        
    "rules": {
        "$studyId": {         
            "studyInfo": {
                // Allow any participant read and write access to child node "[studyId]\studyInfo"
                ".write": "auth.uid !== null", 
                ".read":  "auth.uid !== null"
            },
            "participantData": {
                "$userId": {
                    // Allow participant read and write access only to their own data 
                    // under child node "[studyId]\participantData\[userid]"
                    ".write": "$userId === auth.uid",
                    ".read":  "$userId === auth.uid"
                }
            }
        }
    }
  }
  ```
- Click to update the rules
- In another section, we will [explain these security settings](https://canvas.eee.uci.edu/courses/54190/pages/different-security-models).
  For now, just note that with these security rules, the browser of a particular participant running the study will be able to access
  only the data for that participant and not any other participant. However, there is a subtree for each study (under studyInfo) that is
  accessible to all participants. This is useful if some information needs to be shared among all participants. 

### Changing Authentication Settings

- In the left-side menu, under the **build menu**, go to **authentication**
- Click on the **Sign-In Method** tab
- Select **Anonymous**, select **Enable** and click save

{{% /steps %}}

You should now have a working realtime database.

<!--
## Next

Continue configuring your firebase database:

{{< cards >}}
  {{< card url="../account-setup" title="Account Set Up" icon="user" >}}
  {{< card url="../security-rules" title="Security Rules and Data Representation" icon="lock-closed" >}}
{{< /cards >}}
-->