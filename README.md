# spotify-visualization
To view: https://lsouth.github.io/spotify-visualization/

Write-up
---------
A write-up of the visualization is located in the docs folder. To compile using the Makefile, run
    
    make pdf

Running without the argument 'pdf' will cause it to look for .eps versions of the images, which is not available for all of the images. This will likely cause an error.

## About This Visualization
This was produced as a final project for Michelle Borkin's Spring 2019 course CS 7250 by Sara Di Bartolomeo, Eysa Lee, Amogh Pradeep, and Laura South (ordered alphabetically).
## Motivation
Although Spotify is one of the most popular music streaming services, the app does not currently provide users with a way to view their personal listening history. Several third-party apps allow users to see their personal listening data, but none fully utilize the power of data visualizations to convey information. Most simply provide a static list of the user's top tracks with no interactivity or exploratory capabilities. In this work we create an interactive data visualization using information available from the Spotify API to help users better understand their personal listening patterns. 
## Data
All data used in this project is acquired using the [Spotify Web API](https://developer.spotify.com/documentation/web-api/ "Spotify Web API"). Each user first logs in to the Spotify platform and provides our webapp with authorization to fetch their public playlists, top tracks, top artists, and recently played list. Each list contains information regarding the artists/tracks depending on which request is performed. Using this information, we built our visualzation. All data is fetched from Spotify and processed by our browser app, thus, our website itself never handles any user data. We believe that this feature helps keep user data private and is an added benifit to using our visualization. All data is fetched using [XML HTTP Requests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest "XML HTTP Requests"); the data itself is in JSON format. We fetch data entry in batches of 50 elements, as this is the limit the Spotify API specifies.

## Task Analysis <!-- Summary of interview and task table -->
        
In order to determine tasks to prioritize in our design, we interviewed potential users of our visualization. Nine short interviews with people of varying listening habits were conducted to prevent overfitting to a single person's preferences. The interviews consisted of asking about listening habits, previous interactions with personalized music history visualizations (if at all), data they're interested in visualizing, and data they're not interested in being visualized. While all of the responses were unique and many of the users interviewed had vastly different ideas of what they would want out of a music history visualization, our main takeaway was that users were split on wanting this tool to be focused an individual user or to be used primarily to compare groups of friends. We ended up prioritizing solo use, as comparision can be done in an ad hoc manner with individualized results more easily than the other way around. Our high priority domain goals became viewing daily listening history split by genre and viewing top tracks and top artists, and comparing results with others became an optional goal.

## Design Process <!-- sketches and design choices to justify final visualization -->

Our design process began with considering the goals from our task analysis and technical limitations from the exploratory analysis. We sketched mockups of a preliminary design, which consisted of a stream graph plotting frequently listened to genres in the short, medium, and long term and six columns listing top tracks and top artists for the same three time periods. In the original design, the columns for the top tracks and top artists were below the stream graph. When we implemented this design, we found that having the columns below the graph pushed the bottom of the list past the end of the page, which prevented users from seeing both the stream graph and the entire lists. We also conducted usability testing with students in our class, which identified areas for improvement. A few interactions in our visualization involved highlighting related data across columns by bolding relevant text, and we found that the bolding was being lost in the general brightness of the text. From this, one of the modifications we made was to dim irrelevant text to enhance the highlighting across columns.

## Final Visualization

## Data Analysis

Data analysis is a personal process using our platform. Our tool is essentially an exploration tool that permits users to analyze their personal music-listening patterns. An example is that, on using the visualization tool, one of the authors found that their top artist has consistently stayed <a href="https://www.zhumusic.com/">ZHU</a> across all time periods we visualize. Thus, each person would have their own set of finding on using this tool. We urge the reader to use our tool to figure out your own music-listening patterns and hpe you enjoy it!

## Conclusion <!-- Short summary of work completed and areas for improvement/future-work -->
In this work we use data gathered through the Spotify API to construct an overview of a user's current topic artists and top tracks and a stream graph of the genres a user has most frequently listened to in the short, medium, and long term.  Future work for this project will focus on adding native support for comparision of music listening habits between users, which was an optional domain goal identified in our task analysis. Other potential improvements include adding a landing page for the visualization, introducing a walkthrough to introduce new users to the tool, and more complex computations over the data.
