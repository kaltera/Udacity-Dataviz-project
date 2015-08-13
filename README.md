# Project 6 - Data Visualization with d3.js

## Predictability of Football Games (European major leagues 2011-2015)

### Summary

Visualization link : http://bl.ocks.org/8a313a5f7e0fe2f2cad
Original Visuaization : http://bl.ocks.org/kaltera/raw/9d283f5c94b167bb1c24/
Note that index_original.html is not commented, I only commented the final html file

This visualization is about the ability of betting companies to accurately predict football games outcome and to identify if there are any months which are less or more predictable than others due to external effects, or simply chance.

The visualization includes 2 graphs, the top one accumulates the probability for a specific country for the past 4 seasons, while the bottom graph allows to dive deeper into specific seasons for the given country in order to identify patterns in a more granular way.

The betting accuracy is calculated by looking at the lowest betting odd for a specific game and to compare it with the actual final result. It ends up with a percentage of games that the betting company predicted correctly for the given month/season(s)

### Design

I had initially created only a single graph and I was allowing the user to switch from a accumulated view to a single season view and this seemed to mislead the readers. I therefore, as suggested by a coach on the forum, added a second graph which would be specifically used to dive into specific seasons.

Another issue was the values for the y-axis as I initially used betting odds (usually between 1 and 3), however it was difficult to understand for people who do not know how betting odds work. I therefore decided to change the y-axis to values which are more understandble by the public : A percentage of games accurately predicted by the betting company

I used a scatter plot combined with a line plot so the reader can actually see if the accuracy is going up or down from a month to the other. The bubbles are not ideal, however I needed a way to indicate the total number of games predicted over a specific month and it was the most natural way doing it when using scatter plot. The legend on the right side indicates the relative sizes, and as it is difficult to grasp by simply looking with the eye, I added a tooltip when the reader use a mouse-over in order to indicate the total number of games and the combined accuracy.

I initally had created an animation in order to introduce the reader to the concept of betting odds and also indicating how to use the plot, however it attracted more negative than positive feedback. As I changed the y-axis values to a more understandble concept (percentages), I decided to remove the animation. It was a good exercise and introduction to animations with d3.js though. The animation is available in the original visualization

All colors being used in my visualizations have been generated from http://colorbrewer2.org/ in order to have a well-defined and suitable set of colors. All aesthetics suggestions from feedback have been implemented (fonts, opacity etc..)

### Feedback

Most of the feedback has been received from the Udacity forum on this link : https://discussions.udacity.com/t/project-6-feedback-required-on-football-soccer-games-betting-rates/28073/12

###### Feedback No.1 : Munir

* Version 1
  * At first look and first visit, the first takeaway for me was the fact I wasn't immediately aware an animation was in fact going on. Perhaps provide a message or some type of visual cue for the user to initiate the animation upon first visit
  * The animation overlays appeared to be mis-centered.
  * Would the graphic provide better insight if the Y scale was readjusted ?
  * During the animation, perhaps revisit the complete fading out of countries not in focus, a blur might be more obvious to a user that a transition is happening from country to country.

* Version 2
  * The changes you've made on the animation are coming thru, looking good.
  * I would agree with @Charlie with regards to considering the possibility of two separate plots for showing the analysis breakdown by month and by season because it comes across as a big context switch in the display of data.
  * For instance, when viewing by month, I begin to associate the colors with the individual countries allowing for individual toggling and overlay. As I switch over to the by Season view, then the colors suddenly represent Years and the overlay and individual toggling of countries functions differently.


###### Feedback No.2 : Charlie

* Version 1
  * **Things I like**
  * The fact that you explain what a 'winning odd' was - this would not necessarily be intuitive to someone new to the topic
  * The fact that you used an animation to introduce the variables in the visualisation
  * the ability to toggle between month and year views (though I was confused about what was going on)


  * **Things I like less**
  * The years plot doesn't work exactly the same as the months one -- using the same colours but switching their meanings between countries and years was quite confusing. You could consider making two separate plots. I also have trouble seeing whether odds for a certain country have increased or not over the years, from season to season. The use of the same scale feels strange too, as all the dots get really small for this plot.
  * The fact that the 'instructions' disappear after the initial animation -- I'd like to have a reminder, in particular, of how the 'odds' work.


  * **Further thoughts**
  * I don't get a clear story or message that springs out at me from this. All of the odds seem to move around a bit through the season, but I can't see a trend or a relationship that is really easy to spot. What are you trying to share?
  * I hope you are already doing this, but please make sure your averaging of odds is mathematically correct - I think this should not be the usual arithmetic mean.

* Version 2
  * Convert the 'odds' back into the probability (say a percentage or a decimal between 0 and 1) and then take a (well-chosen) average of those.

###### Feedback No.3 : Andrew

* Version 2

  * Credit to you for building explanatory animation. I work with some UX people who struggle to get it perfect. I think the challenge lies in the point that we want things to be self explanatory and intuitive, so why explain anything? My main reaction was that it felt heavy, big and intrusive.

  * I think the visualization is laid out nicely and the country selectors front and center makes this seem the most important element of the story. But is it?
  
  * I struggled to get the message. Maybe there are points that could be tagged with call outs to accentuate the message. Or perhaps I don't know the significance of the variation. You have data by month by year and by season. What is the most interesting aspect?
  * For the by month visualization: The x axis is month - but i see little to no relationship by month because all the country lines jump up and down. Am I missing it? The last two months seem lower but that isn't universal. Perhaps adding a mean or median line will show the trend
  * My main takeaway is - Is there any difference?
  * I don't understand the by season view. This is complicated by the fact that the buttons work differently. In the month view (multi-select with colors) and in the season view (single select).
  * Use a more modern font than the original web default. Even the not so modern Verdana make your title and buttons (particularly the buttons) look so much better
  * Adjust the relative sizes of the heading text versus the axis label text. Increasing the label text to 10pt works nicely
  * The dots overplot sometimes. Perhaps they should have some transparency
  * I noticed Spain has just a couple (or one?) games in one year in June. I found this because on most of the other views your chart Jun has no data so it looked unbalanced -- a wide white column on the right. Is this really on outlier (unusual delay etc) so that for meaning full comparison does it really belong in June and should you adjust the data reflect in May rather than June,
  * After reading your reasons for doing this you mention the "October November crisis" - I went back to look through the charts. In the season view it seems to me there is something interesting. For most of the countries either in October or November, the odds are very close together . In other words, the spread between highest and lowest is very narrow. I think this is true of al countries except Italy, and Italy this still seems true except for one year. Here is Spain by season. Notice how tight the second set of dots is.
  * This led me to another thought: What is important about number of games and you have it as dots but I don't see any meaning or pattern? I then wondered if there may be a better x axis. I don't really know how the football leagues work, but is there something more common than month, like round of play, or perhaps just cumulative games played, assuming that the number of games played in a season remains about the same. This may also bring into sharper focus the changes at the end of the season.
  * Overall I think you have put a lot into this but the key message is missing.
  
### Resources

* d3.js Documentation https://github.com/mbostock/d3/wiki
* Buttons style http://viralpatel.net/blogs/css-radio-button-checkbox-background/
* Line chart https://www.dashingd3js.com/svg-paths-and-d3js
* Label on line chart https://gist.github.com/mbostock/2565344
* Color Brewer http://colorbrewer2.org/
