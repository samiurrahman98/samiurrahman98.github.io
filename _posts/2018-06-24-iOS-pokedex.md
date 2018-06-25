---
layout: post
title: "Pokédex Mobile Application"
description: "An overview and video demonstration of an iOS mobile application involving Pokémon."
thumb_image: "documentation/sample-image.jpg"
tags: [personal, development]
---

{% highlight html %}
<div class="background">
  <h2> We're doing this HTML body again? </h2>
  <p>
    Yes, yes we are. In fact, I quite like the way 
    it looks so I think I'll continue using it as an 
    introduction to all of my blog posts. Now before 
    we go any further, let's get this out of the way. 
    Yes, I am a HUGE Pokémon fanatic. Great, now that 
    we have that out of the way, give me a moment to 
    escape this body of HTML.
  </p>
</div>
{% endhighlight %}

So in this blog post, I'm going to give you an overview of a little side project I worked on a while back. For those of you that aren't familiar with Pokémon, I do advise that you read the following passage so you can develop an understanding for the motivation behind this little side project of mine.

{% highlight markdown %}
"The Pokédex is a digital encyclopedia created by 
Professor Oak as an invaluable tool to Trainers in the 
Pokémon world. It gives information about all Pokémon in 
the world that are contained in its database, although it 
differs in how it acquires and presents information over 
the different media ... Pokédex entries typically describe 
a Pokémon in only two or three sentences. They may give 
background information on the habitat or activities of a 
Pokémon in the wild or other information on the Pokémon's 
history or anatomy. Pokédex entries also include height, 
weight, cry, footprint (prior to Generation VI), location, 
other forms, and a picture of the Pokémon." 

From Bulbapedia, the community-driven Pokémon encyclopedia.
{% endhighlight %}

So at this point, I'm going to assume that you are familiar with what a Pokédex is, and what it's used for. A Pokédex is a 
handy tool for all Pokémon trainers to carry. It is essentially a database that contains relevant information regarding each 
Pokémon species, and in a game where the motto is "Gotta catch 'em all!", it's probably worth your time to familiarize 
yourself with the Pokédex, as every species that you come across is registered in this nifty device.

So why did I decide to develop a Pokédex mobile application? Simple - to introduce myself to the world of mobile development, 
while also being able to incorporate a core feature of one of my hobbies into a personal project.

### <strong>Tools</strong>

For this project, I used a RESTful API called "pokéapi", which contains Pokédex data for 803 different Pokémon species! Yes, the 
Pokémon world is quite saturated with an abundance of different Pokémon. If you'd like to check out "pokéapi", you can visit the following site for more details: <a href="https://pokeapi.co/" target="_blank">https://pokeapi.co/</a>.

To handle requests to/from the API, I used Alamofire, a HTTP-based networking library, which simplifies a variety of networking tasks that you can read more about by visiting the following site: <a href="https://github.com/Alamofire/Alamofire" target="_blank">https://github.com/Alamofire/Alamofire</a>. And of course, to add Alamofire to my project, I needed to use Cocoapods, a dependency manager for Swift projects. If you would like to learn more about Cocoapods, check them out at: <a href="https://cocoapods.org/" target="_blank">https://cocoapods.org/</a>.

The structure of the codebase itself is not that complex. I implemented an MVC architectural pattern, which contained a simple 
Pokémon model that is populated with the results received from the API upon completion of the GET request. The controller is used to encapsulate the logic for this application, as all controllers should in a MVC architecture. And the view, well that's pretty self-explanatory.

### <strong>Walkthrough</strong>

On the primary page, the user is able to view each Pokémon species, and then make a selection. Upon their selection, the user is navigated to a details page, where information regarding the Pokémon is displayed. The application also provides the user with 
the option to filter their search with a search bar, where they are able to enter the name of the Pokémon species that they would like to learn more about. And finally, there is a music player button to toggle the audio of the application, which you 
won't be able to hear in the below demonstration because I would like to avoid any potential legal implications.

<div class="embed-responsive embed-responsive-16by9">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/9PqRmGsyU58" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

In the background of the actual demonstration, you'll notice a bunch of warnings that Xcode is trying to communicate to me. Additionally, you should have noticed the placeholder text on the details page for Pikachu - that means something is wrong with the handling of the API response. It worked flawlessly just a few months ago, but actually, this application was developed for iOS 9, and if I'm not mistaken, iOS 12 should be arriving in the next couple of months. Yes, it's severely outdated and requires a ton of refactoring that I hope to get to eventually, but I just wanted to provide readers with a video demonstration of the application and some of the features that it includes.

And that's all for this blog post folks. Stay tuned for new content, thanks for reading!