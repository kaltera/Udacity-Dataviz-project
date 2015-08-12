# Project 6 - Data Visualization with d3.js

## Predictability of Football Games (European major leagues 2011-2015)

### Summary

This visualization is about the ability of betting companies to accurately predict football games outcome and to identify if there are any months which are less or more predictable than others due to external effects, or simply chance.

The visualization includes 2 graphs, the top one accumulates the probability for a specific country for the past 4 seasons, while the bottom graph allows to dive deeper into specific seasons for the given country in order to identify patterns in a more granular way.

The betting accuracy is calculated by looking at the lowest betting odd for a specific game and to compare it with the actual final result. It ends up with a percentage of games that the betting company predicted correctly for the given month/season(s)

### Design

I had initially created only a single graph and I was allowing the user to switch from a accumulated view to a single season view and this seemed to mislead the readers. I therefore, as suggested by a coach on the forum, to add a second graph which would be specifically used to dive into specific seasons.

Another issue was the values for the y-axis as I initially used betting odds (usually between 1 and 3), however it was difficult to understand for people who do not know how betting odds work. I therefore decided to change the y-axis to values which are more understandble by the public : A percentage of games accurately predicted by the betting company

I used a scatter plot combined with a line plot so the reader can actually see if the accuracy is going up or down from a month to the other. The bubbles are not ideal, however I needed a way to indicate the total number of games predicted over a specific month and it was the most natural way doing it when using scatter plot. The legend on the right side indicates the relative sizes, and as it is difficult to grasp by simply looking with the eye, I added a tooltip when the reader use a mouse-over in order to indicate the total number of games and the combined accuracy.

I initally had created an animation in order to introduce the reader to the concept of betting odds and also indicating how to use the plot, however it attracted more negative than positive feedback. As I changed the y-axis values to a more understandble concept (percentages), I decided to remove the animation. It was a good exercise and introduction to animations with d3.js though. The animation is available in the original visualization
