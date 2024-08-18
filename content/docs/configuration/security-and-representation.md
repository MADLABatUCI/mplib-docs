---
title: Security Rules and Data Representation
weight: 4
---

The security rules of the realtime database determine which users can have access to which
information. How we think about security rules depends on the organization of our data and
how flexible we are about data access. We discuss three models, A, B, and C, and we start with
the default security model A that is assumed by all code in this course.

## Model A (default)

**Participants can only access their own data (read + write) but some study information is shared among all**

In the scripts in this course, we will assume that the database will store data from multiple
studies (we want to set up a database only once), multiple participants per experiment, and
multiple trials per participant. This is a fairly general setup that should work for most
experiments.

For the code examples in this course, we will use this particular tree organization to store
information related to the study and the participants:

```
studyId --> participantData --> participantId --> trialData --> trial 
        |                                     |
        |                                     +-> participantInfo
        +--> studyInfo
```

At the first level of the tree, we have the ==studyId== which refers to the name of the study. We
will assume that our database can store the data from multiple studies so each new study will be
associated with its own subtree. At the second level, we make a distinction between a branch
==participantData== where we store data produced by individual participants. The other branch,
==studyInfo==, will be used to store general information about the study that can be shared among
all participants. In the ==participantData== branch, ==participantId== refers to the unique
*firebase id* given to the browser of the participant. Basically, every time a person connects
through the browser with Google Firebase, a unique id is assigned to that browser. It will be the
same id every time the same browser is used to connect to firebase, but if a person uses a
different browser (or an incognito browser), a different firebase id is assigned. For now, don't
worry about the possibility of having potentially multiple id's associated with the same person
as we will use additional types of user id's (e.g. an MTurk worker id or Prolific participant id)
to keep track of people.

For our default security model, we have set up the following rules:

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

With these rules, each participant (based on their firebase id represented by ==auth.uid== in the
code above) can access, *read* and *write*, only their own data and not the data from other
participants. However, the subtree ==studyInfo== is shared among all participants so we will have
to be careful and not place any sensitive data in that branch. In the code example, we will use
the ==studyInfo== branch to store information about counterbalancing (i.e., how many times each
condition has been run already) here we won't get into the details of this representation.

If you want to learn more about the language used to express the security rules, you can read the
[Google Documentation](https://firebase.google.com/docs/database/security).

## Model B

**Anybody can read or write any data (including other participants' data)**

The most flexible and least secure setting is where anybody can access any data. This is not
recommended for any of your studies as we don't want to expose sensitive data from one participant
to another participant. However, this setting can help when building and testing entirely new data
representations.

```json
{
    "rules": {        
        ".write": true,
        ".read":  true           
    }
}
```

A simple variant of this security model is one where only authenticated users can read and write
data:

```json
{
    "rules": {        
        ".write": "$auth.uid !== null",
        ".read":  "$auth.uid !== null"           
    }
}
```

However, this change doesn't change the fact that a person at one browser can still access the
experimental data from any other participant from the study, which is problematic.

## Model C

**Anybody can write any data but reading is disallowed**

A somewhat more secure and still very flexible model is where the browser client of a participant
can write anywhere in the database (and potentially overwrite other participants' data) but cannot
read any data.

```json
{
    "rules": {        
        ".write": true,
        ".read":  false          
    }
}
```

<!--
## Next

Continue configuring your firebase database:

{{< cards >}}
  {{< card url="../account-setup" title="Account Set Up" icon="user" >}}
  {{< card url="../security-rules" title="Security Rules and Data Representation" icon="lock-closed" >}}
{{< /cards >}}
-->