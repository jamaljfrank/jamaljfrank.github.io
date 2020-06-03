---
layout: post
title:      "Clients Request and Servers Respond"
date:       2020-06-03 13:32:03 -0400
permalink:  clients_request_and_servers_respond
---


The way we interact with the internet has a cycle to it. A fundamental flow that persists between clients and servers. 
For a better understanding, I'm going to break it down into 5 steps.

**Step One: The Client and I**
I want to watch Netflix. For that, I need a client which can be an internet browser like Chrome or a phone app. 

**Step Two: HTTP Request**
A HTTP request is a string that gets sent to a server. Its makeup specifies the details of the request. 
For instance, 'netflix.com/browse' and 'netflix.com/YourAccount are, respectively, requesting to see a catalogue and the details of my account. 

**Step Three: "Let me check the back room..."**
Once we hit enter, the request hits a server's router. The router then matches the URL to the corresponding controller and action. Let's say there's a netflix controller. In reference to the mentioned URLs, we could be calling a 'browse' action or 'youraccount' action.

**Step Four: Make It Pretty**
Now the controller action goes to a view which in turn, takes all the information gathered and renders it into HTML.

**Step Five: "The Response!**
Once we're all good to go, the controller sends the pretty HTML to our client. That can be something like a '404' failed request page or a successful '500' which could lead to a library of must watch shows and movies like 'Ozark' or 'Ex Machina'.
