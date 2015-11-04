# Data Visualization: Baseball players Performance

##Summary
This plot ranks the top 50 home run hitters from a list of over 1100 MLB players. The axes indicate the Home runs and BMI of the players and the size of each bubble represent the batting average of the player. The bubbles are colored by player’s handedness and the legend can be used to toggle between them. The plot also highlights the players who are in ideal BMI range to show how BMI relates to the performance of a player.

##Design

####Exploratory Data Analysis in R
I downloaded the Baseball Data from Udacity’s dataset options that included performance and physical aspects like height, weight and handedness of 1157 players. I have analyzed the data and looking at the height and weight of players first thing stroke was to calculate the BMI. The body mass index, or BMI, is a calculation used to determine level of body fat. It helps to determine the overall fitness of a person.  I have been hearing a lot about the importance of BMI   and thought of verifying if the BMI of a player has any effect on their performance. Added a new calculated column in the dataset “BMI” by calculating using the formula:

**BMI= Weight in Kilograms/(Height in Meters) x (Height in Meters)**

I was primarily interested on the home runs of the players and started exploring my data to understand how its related to  other variables.  Below plots shows the relationship of Home runs against Height, Weight & BMI of the players.
![HomerunVsHeight](https://github.com/anuachankunju/DataVisualization/blob/master/Images/HomerunVsHeight.JPG)

The above graph shows a trend that there is a small positive correlation between Home runs and  height of the player
![HomerunVsWeight](https://github.com/anuachankunju/DataVisualization/blob/master/Images/HomerunVsWeight.JPG)

I didn’t see any increasing or decreasing trend as such between Home runs and weight. Next variable of interest is BMI.
![HomerunVsBMI](https://github.com/anuachankunju/DataVisualization/blob/master/Images/HomerunVsBMI.JPG)

The above graph clearly shows that there is a negative correlation between Home runs and BMI. I also tried to plot BMI vs performance by binning  players by BMI and visualized the average home runs for each bin. 
![HomerunVsBMI Bin](https://github.com/anuachankunju/DataVisualization/blob/master/Images/HomerunVsBMI_BinJPG.JPG)

Here again its showing a decreasing tread except for the one outlier we have in the last bin. Hence I decided to select my primary variables of interest as Home runs & BMI.

####Data Visualization (dimple.js)
Next I attempted to plot a scatter plot of Home Runs Vs BMI. I selected scatter plot primarily because I wanted to see the distribution of players. Another advantage of using scatter plot is the ability to allow the reader to get further information about specific player with tool tip. My final plot used this idea but changed slightly to bubble chart when I realized the need to map multiple dimensions.
![InitialSacetterPlot](https://github.com/anuachankunju/DataVisualization/blob/master/Images/InitialSacetterPlot.JPG)

It was clearly showing up that most of the players fall in the normal BMI range between 18.5-24.9 noticeably the players with high Home Runs. The chart was too busy to look at the effect of other aspects like Handedness and batting average on performance.
I decided to focus on the top 50 hitters. For that I selected the top 50 home run hitters from the 1100 players. The scatter plot drawn for truncated data set is shown below:
![TruncatedDataSet_ScatterPlot](https://github.com/anuachankunju/DataVisualization/blob/master/Images/TruncatedDataSet_ScatterPlot.JPG)

Looking at the above visual the first point stroke to me was there is a cluster forming between the range 18 & 25. I decided to focus on this point as there is an interesting story that Great hitter are in normal BMI range. Though we have seen the performance decreases with BMI increase in the exploratory analysis we should also consider the fact that most of the player population is in ideal BMI range and we see clearly see that top performers also fall in ideal BMI range.  Hence I would like to emphasize the importance of being in the normal BMI range to be a top performer.

Next I tried to categorize the players based on their handedness to check whether the top players are Left handers or Right handers or both.  The first impression seems to be there are more of Right handers in the top 50. I verified the proportion of left and right handed players in the original population and the top 50 and found there is not much difference in the proportion.  Still I’m keeping this encoding in my visual to show the distribution of handedness among top players.
![ScatterPlot_ByHandedness](https://github.com/anuachankunju/DataVisualization/blob/master/Images/ScatterPlot_ByHandedness.JPG)

The above graphic clearly shows that most of the players are Right Handers. This image can also be viewed in Index_3.html. 

Now the other information we have is the player’s batting average. In order to incorporate that in my visualization changed the graph type to Bubble chart so that the batting average can be encoded in the size of each bubble. Also added the other details of the players like Name, Height, Weight etc. in the mouse over display list. Below image displays the updated chart. This can also be viewed in Index_4.html.
![Initial_BubbleChart](https://github.com/anuachankunju/DataVisualization/blob/master/Images/Initial_BubbleChart.JPG)


##Feedback
I interviewed 3 individuals in person, and asked for their feedback on the data visualization after prompting them with the background information and a small set of questions. Highlighted comments from them are listed below:

#####Interview #1
I have showed this graph to my colleague and he gave the following comments:

“To me the graph is highlighting the Handedness of a player with the nicely colored bubbles than the BMI  as mentioned in the title.  It’s not giving any insight about the ideal BMI range or whether a given player is having a normal BMI. 

Highlighting the ideal BMI range in the visual will help you to draw the attention of your audience to BMI.”

#######Post-feedback Design -1
Highlighted the Normal BMI range and added a message about it at the bottom as shown in the below image.
![Interview1_DesignChanges](https://github.com/anuachankunju/DataVisualization/blob/master/Images/Interview1_DesignChanges.JPG)

#####Interview #2
Second person who reviewed the improved graph was another Nano-degree student in my organization and her commend was:
“The graph looks good to me. It clearly highlights the normal BMI range area. Hence the message you are trying to convey is clear. The color combination of the graph is very pleasant and soothing to eyes. 

Hovering over the points was interesting, but I kind of wanted to see more of animation as it makes more interactive and interesting to the viewer. One suggestion would be you can make it more interesting by making the legend clickable and interactive.”

#######Post-feedback Design -2
I improved my visualization by making the legend clickable as advised by my friend and I felt very nice about my new design.
![Interview2_DesignChanges](https://github.com/anuachankunju/DataVisualization/blob/master/Images/Interview2_DesignChanges.JPG)

#####Interview -3
Third person with whom I reviewed my graph with was a six sigma black belt of my team and here are the highlights from his comments:
“This is an excellent visual for the given data set. However some minor improvements suggested are:
•	Giving a ranking for the players and showing it in the visual will give an idea of where an individual player stands.
•	Removing the grid lines will give a better look for the graph as its not giving any added advantage and  mouse over draw lines to x and y axes.”

#######Post-feedback Design -3
I tried to incorporate the suggested improvements and also changed the title of the visual to something better.  Players were ranked from 1 to 50 based on the Home Runs, rank 1 being the highest home run hitter. Here is the graph I created.
![Interview3_DesignChanges](https://github.com/anuachankunju/DataVisualization/blob/master/Images/FinalDesign.JPG)

#####Udacity Submission 1 feedback- Highlights
* Chart title is not clearly explaining the visualization.
*	Binning the BMI data and taking summary statistics should give more insight into how BMI and performance are related to each other. 
*	Look at the proportion of right to left handed players and see if there is any trend.
*	If batting average is important to the story, find a different encoding.
* The README file mentions what the encodings are, but it doesn't really specify the reasoning behind the choices. For example, why was a scatter plot used (for example instead of bar charts or histograms)? Why as handedness put to bubble size instead of in a separate chart? Answering the "why" behind the decisions is what I'm looking for.
* The README file needs to be a .md file rather than a .pdf file
* The tooltip has some information listed more than one time. I think it will be more intuitive for the reader if the tooltip were limited to showing the most important information only once. The tooltip for the top couple of points is also getting cut off.

#######Post-feedback Design -4
Visualization was changed to incorporate the suggestions and below is the final graph I created:
![FinalDesign_PostFeedback](https://github.com/anuachankunju/DataVisualization/blob/master/Images/FinalDesign_PostFeedback.JPG)

Summary of my analysis about the top 50 player’s performance:
*	Scatter plot is selected as the chart type to see the relative distribution of top players BMI range. It also helped to highlight the clustering in Normal BMI range area and to provide the details of top players using tool tip
*	Home run is encoded in the Y – axis as I was primarily interested to analyze the performance of a player. Home run is considered as a performance measure
*	BMI is encoded in X – axis as it was showing a clear -ve trend in my exploratory analysis.
*	Handedness is encoded using color to see if top players are left or right both handed. There was no specific relationship proved between performance and handedness. Majority of players in original as well as the top 50 players seems to be Right handed and the color just highlights that fact.
*	72% of the top 50 players fall in the normal BMI range. Hence if you are in normal BMI range you have high chance to be a top performer.


##Resources
*[dimple.js Documentation](http://dimplejs.org/)
*[Data Visualization and D3.js(Udacity)](https://www.udacity.com/course/viewer#!/c-ud507-nd)
*[Various Stack Overflow posts:](http://stackoverflow.com/search?q=dimple.js)


##Data
