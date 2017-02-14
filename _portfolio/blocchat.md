---
layout: post
title: Bloc Chat
thumbnail-path: "img/bloc-chat.png"
short-description: Bloc Chat is a real-time chatting application using Angular JS and Firebase.

---

{:.center}
![]({{ site.baseurl }}/img/bloc-chat.png)

## Explanation

This is the first student project that I had to complete with minimal guidance. The goal of the project is to create a chatting application with multiple chatrooms and users that allows instant message relaying. Users can create a username, establish new chatrooms, join a chatroom and post messages. The application is Angular JS framework based and uses Google Firebase for database functions.

## Problem

Building the site was initially daunting since this is my first time Firebase is being incorporated in an application. The Firebase database was needed to store my chatrooms and messages. Then, I needed to be able to callback the values of the chatroom and message properties. Fortunately, the Firebase foundation was initially created for the integration of online chat capabilities on websites and the platform was straightforward for chatroom applications.

## Solution

Firebase was used in two services for my application. 

First, Firebase was required to store my chatrooms. In my application, the chatroom entries were treated as arrays and stored as a child in a folder called "rooms". Then, I was able to call the firebase array in "rooms" to list my chatrooms on  HTML with the help of a controller. To add new rooms, the .$add function was used. Since my rooms were stored as objects, it was important to specify the properties (ex. { name: nameOfChat }) when a new room was created and the room name was called in  HTML (ex. {{ rooms.name }}).

Second, the messages need to be stored. Initially, I was tempted to store messages into the various chatrooms in the "rooms" folder. Since messages are only specific to a particular chatroom, I believed it was appropriate to store the messages as an array of objects. For an example, I can have an object property called "messages" in the chatrooms and store the messages as an array in an object property. However, nesting data in Firebase is discouraged. If I had completed my project with my initial plan of nesting the messages into the chatrooms, my application would need to read through the entire data tree over and over again to pull each message. This would result in an inefficient and time-consuming application. Therefore, a flatten data structure was necessary. Instead, I stored the messages into another folder called "messages" and assigned a specific object property called "roomId". Each message had a "roomId" that corresponded to a particular chatroom Firebase key ID. Now, I was able to sort the messages by their "roomId" and display them into their correct chatrooms.

## Results

The flattened data structure was more appropriate to manage my messages in the chatroom. Planning the service was the most difficult part. It helped to use paper and pencil to write and visualize how the data was arranged. Once the plan was laid out, the coding portion was easier and clearer. 

## Conclusion

It was a great experience and practice to write this application. There are several other functions that I would like to incorporate in addition to design features in the future. Please check it out and leave me a message! Any feedback is welcome! http://lisajmin-bloc-chat.netlify.com/