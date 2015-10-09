# Meet Meteor: Build a chat app in <100 lines of JavaScript - Part One

[Meteor](http://www.meteor.com) has been generating a level of excitement that we haven't seen from web developers in years. 

![](tweet.png)

![](tweet2.png)

In this tutorial, we will see what the excitement is about while exploring the core features and building a functional chat application with very little code. This tutorial will consist of 5 parts:

1. Install Meteor and create your app
2. [Implement basic chat](chat-tutorial-part-2.md)
3. [Add user accounts](chat-tutorial-part-3.md)
4. [Refine the UI of the app](chat-tutorial-part-4.md)
5. [Deploy the app and create a mobile version](chat-tutorial-part-5.md)

## What is Meteor?
Meteor is a full-stack platform that includes:

* a CLI tool for creating, modifying, debugging, and deploying projects
* an all-JavaScript codebase with support for ES2015/ES6 across all platforms (via Babel)
* a build system that coordinates code for the server, the browser, and mobile clients for iOS and Android
* integrated features that are essential for modern apps, such as websockets, live database query streaming, and reactive user interfaces.

Meteor shows itself best in action, though, so let's jump straight into the code.

## Install Meteor and create a project
You can install Meteor in a couple of minutes. You can use [the Windows installer](https://install.meteor.com/windows), or just paste the following into your terminal on Mac and Linux:

```bash
curl https://install.meteor.com/ | sh
```

This will install the Meteor CLI tool. You are now ready to create a project. Run these commands in the terminal:

```bash
    meteor create chat # => chat created. To run...
    cd chat
    meteor remove insecure # => insecure  removed from your project
    meteor remove autopublish # => autopublish  removed from your project
```
    
This has scaffolded a small app called `chat`.  We also removed a couple of packages, `insecure` and `autopublish`. These packages are designed to make prototyping simpler, but we won't use them here.

Now, in the terminal(while still in the `chat/` directory), type:

```
meteor
```

 This tells Meteor to run your app on a development server. As Meteor will tell you in the output, you can view the app by opening your browser to [localhost:3000](http://localhost:3000). You can try clicking the button in the app.

Let's replace the code in this app (you can leave the server running). Open the chat directory in your code editor. You will see the app is constructed of 3 files: chat.html, chat.js, and chat.css. 

* Delete all the code in chat.html, chat.js, and chat.css so that they are all empty files.

## Add the CSS

Let's go ahead and paste in some css code so the app will look good (we'll ignore the css from here on):

* Copy the CSS from [here](https://github.com/meteor/basic-chat/blob/master/chat-demo.css) (XXX currently private - should probably redo the app in the tutorial build order), paste it into chat.css, and save.

## Structure the HTML
Now add the following to chat.html (make sure you keep comments, enclosed in `<!--  -->` in html – we'll use those as markers to add more code later):

```html
<head>
  <title>Meteor Chat</title>
</head>

<body>
  <div class="container">
    <header>
      <h1>Meteor Chat</h1>
    </header>
    <!-- chat messages here -->
    <!-- more-messages button -->
    <footer>
        <form class="new-message">
          <input type="text" name="text" placeholder="Add a message" autocomplete="off"/>
        </form>
    </footer>
  </div>
</body>

<!-- message template here -->
```

We now have a skeleton. If everything went well, you should see an empty chat app: 

![Empty chat app](empty-chat-app.png)

## Hot code push

You may have noticed that when you hit save, the browser updated without restarting the server. This Meteor feature is called **hot code push**. When Meteor detects a file change, it rebuilds your app and pushes it to all connected clients. 

Go ahead and try changing the name or some of the styling of the app. This facilitates a very interactive kind of development. This is possible with some other frameworks by using a tool like LiveReload, but with Meteor, it comes built-in.

Not only is hot code push great for development, but it also  works in production, allowing you to push updates to connected users live – and Meteor has a mechanism for preserving their state so they don't lose their place in the app. This is a great example of how the Meteor platform looks at the entire development and deployment process, not just code framework features.

## Conclusion: Ready to rock

We've installed Meteor and scaffolded our chat app. Notice how little effort this took. Because Meteor has simple installation, easy app creation, an included development server, and hot code push, we are already focusing on our app rather than spending time installing Node.js, MongoDB, a templating system, or other components. In [part two](chat-tutorial-part-2.md), we'll complete the main functionality of the app: rendering messages to all connected clients.


