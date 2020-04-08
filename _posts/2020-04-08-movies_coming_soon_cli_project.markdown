---
layout: post
title:      "Movies Coming Soon CLI Project"
date:       2020-04-08 10:11:17 +0000
permalink:  movies_coming_soon_cli_project
---

For this project I have built a program to scrape upcoming movies from the rottentomatoes website and provide an interface that users can utilize to access this data.

Click [here](https://drive.google.com/open?id=1aj9t-NeWZJA7O7e4l_rRhrMyOxZcU5tN) for User Interface Demo Video

Click [here](https://github.com/Biotruss/Movies_Coming_soon) for Project Github Repo

### Getting Started

I started with coming up with a rough estimation on how I would want users to see this information and how they would interact with it. I made the assumption the best way to present the information is a numbered list of the upcoming movies from the website and the best way to interact with it is to allow the user to simply enter the number of the movie they wanted more information on. I also wanted to give the user the ability to type in the word list to see the list of movies again and exit to leave the program.

### Presenting the List of Movies

Then I started to think about how I wanted to scrape this info from their website. After looking at their website I decided that I wanted to first get the names of the movies and the corresponding links to their pages. To do this I created a class I named Scraper and created a method that would scrape all the names and links and use the data to instantiate new objects in a class I named ComingSoon. I then created a class named CLI and made two methods to set all objects in ComingSoon to an instance variable and list the number information for the user to see. A separate method was set to list the information because later we want to be able to print the list again by calling that method again.

### Allowing User Input to Select Desired Movie

I then started to make a method in the CLI, I named fetch_user_movie,  class that would allow the user to input the number of the movie that they wanted more information on. I did this by using a selector for the array inside the instance variable that would take in the user input. This would then go through a process to use the name and url stored in the chosen movie to call a new scraper method in the scraper class. The scraper class uses the url in order to scrape data inside of it and use it to start a new instance in a class I will be calling Movie which will store the information. Finally after the Movie class is done doing its thing the method in the CLI class finishes by printing the information for the user to see.

## Creating a Loop

After the ability to print information on the movie the user selects has been made I then added a conditional that would keep the code in the method running in a loop, until the user enters exit, so the user can continue to check out more movies without the program ending. Finally, I also added in the conditional to call the list method to list the upcoming movies again for the user to see again if desired.

### Finishing Up

There was some clean up work I had to do in the end. While testing the program I noticed that sometimes the movies on the website that I am scraping my information from will actually be missing information. This is because that information is missing from the website and this can be for any number of reasons. No need to pry though! Rottentomatoes is doing their best to provide accurate up to date information. So in the event that there is missing information I added a method in the Movie class to check if any attributes were empty it would set the attribute equal to a string that will explain the problem to the user.

### Thoughts and Feelings

I am really proud of how this project came out as I tried to make the code in a way that is easy to read and work on. My goal was to create an environment that would allow anyone else who tries working on this program to easily see what parts of the program are responsible for what. For example, if rottentomatoes decies it needs to do major changes to their website and my scrapes no longer work. All scrapes occur inside the Scraper class so we can go there to fix it. It also makes the Movie and ComingSoon classes responsible only for storing new instances of objects and their attributes. This was a little extra thing that I wanted to do because adding the scrapers to the classes themselves instead would also make them responsible for scraping their attributes. I did not want to add that extra responsibility in fear that it would make the classes harder to read and the program overall harder to interpret.

