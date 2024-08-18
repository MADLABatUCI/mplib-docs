---
title: Configuration
weight: 1
sidebar:
  open: true
---

## Google Firebase
One of the primary challenges in conducting online experiments is the storage and management of experimental data. In a typical scenario, a lab member may have previously written a script that saves data to a lab server, which then gets passed on to new lab members over time. While this solution is functional, it can pose difficulties when someone transitions to different labs or servers, or requires more sophisticated data management that encompasses not only writing and reading data, but also facilitating real-time collaboration between participants in advanced experiments.

In the following sections, we will discuss how to utilize Google Firebase, specifically the Google Realtime Database, for more efficient and effective data management in online experiments. While it will be a challenge to directly code in JavaScript to interface with Google Firebase, we will show how you can use a JavaScript library, the FirebasePsych library that will greatly simplify data management.

## Background on Google Firebase
Originally, Firebase started as a set of chat application tools. The idea was to facilitate the development of apps that quickly synchronize chat data such as text messages and images but without burdening app designers with all the complexities of programming back-end server software. The Firebase developers discovered that the tools were used for more than chat applications and realized that there is a need for data management tools that do not require specialized server-side coding skills. The original startup that developed the tools (Envolve) was acquired by Google, and the tools developed into a general product called Firebase. In the Firebase documentation, there is still a focus on chat applications, reminiscent of its history, but for our purposes, we can use Firebase to store (and retrieve) any kind of data that is produced in psychology experiments.   

The main difference between the traditional approach and Firebase is illustrated below. Traditionally, you have to program software at both the front-end (e.g., the software on your client that controls your browser/app) and the software at the back-end (e.g. the software that controls the data management of storing and retrieving data from a server. Those can involve different programming languages and different programming environments, which complicates software development. The Firebase model removes the complexities of back-end programming, setting up your own servers, and/or getting permissions from administrators to use university based servers.

Firebase makes it very easy to set up a cloud-based server and for our purposes *all the work is done at the client side*. Therefore, there is only one programming language needed at one location. For our purposes, we use JavaScript, and we could, if we wanted to, place all the software needed to run our experiment *in a single script*. In other words, in our JavaScript code, we will not only control the logic of the experiment but also describe where in the (cloud-based) database the data will get stored. We can also create JavaScript code to read data from a database which might be useful for more complex experiments.

<img src="/mplib-docs/imgs/firebase/google-firebase.png" />

## Realtime Database and Firestore Database
One of the confusing aspects of Firebase is that there are two models to manage data: *Realtime Database* and *Firestore Database*. The terminology is unfortunate because the framing suggests that the Firestore Database is not real-time but this is not the case. Both databases are *cloud-based* and *real-time*. In addition, both databases are *noSQL*, meaning that it does not involve relational or tabular data and *noSQL* language is needed to handle the database.

For our purposes, we will use the Realtime Database,  but it wouldn't be very hard to switch to the Firestore model. For a detailed comparison of the differences between the two types of database, see this Google documentationLinks to an external site.. One of the key differences is that in the Realtime database, data is stored as one large *JSON tree* whereas in Cloud Firestore, data is stored as a collection of documents.

Below is some sample experimental data stored in a Realtime Database using a *JSON tree*. At the root of the tree, we have the name of the study, followed by a branch participantData that has child nodes corresponding to different participants and their data.

<img src="/mplib-docs/imgs/firebase/firebase-example.png" />

To keep your database efficient, it is recommended not to create very deep hierarchies. A shallow tree involving just a few levels will be easier and quicker to work with.

Note that the cloud-based data can easily be retrieved from the Realtime Database. With a few clicks, you can export the JSON data to your own computer for further analyses. There are a number of tools one can use to convert a JSON data structure to a tabular data structure that is more convenient for data analysis. 


{{< cards >}}
  {{< card url="metadata" title="Metadata" icon="server" >}}
  {{< card url="players" title="Players" icon="user-group" >}}
{{< /cards >}}
