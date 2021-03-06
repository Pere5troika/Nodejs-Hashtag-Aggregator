# *hidden company* Coding Challenge for Conor Lamb

## Conor's Summary:
### Run instructions
\> npm install

\> node tagAggregater.js

### Notes
Unfortunately, the twitter api has dropped it's support for this since/until params and
thus, searching through a user's timeline by date, is impossible via direct access.
I had to employ a searching algorithm to find the first/last post of localDeep's
feed. :/. The way it works is 500 tweets are read in from the api at a time,
(*This is an arbitrary # the api call allows up to 3.2k per call but
deeplocal's tweets (discounting retweets) isn't >500. *)
from there, the logic of each tweet looks like:

If (2016) <br/>
&nbsp;  if (hasHashtags)<br/>
&nbsp;&nbsp;    if (!unseen hashtag)<br/>
&nbsp;&nbsp;&nbsp;      add to array with count of 1<br/>
&nbsp;&nbsp;    else if (seen hashtag)<br/>
&nbsp;&nbsp;&nbsp;      increment<br/>
&nbsp;  else<br/>
&nbsp;&nbsp;    nextTweet<br/>
else if (2015)<br/>
&nbsp;  stop<br/>
else //2017<br/>
&nbsp;  next tweet<br/>

another way this could have been done would have been to manually find the id of the first/
last tweet of 2016 for deepLocal and hardcode those dates as bounds for a search through
deepLocal's tweets which would have less computation time but also be less a show of my programming skills.......and that's no fun now is it?



### *hidden company* Dev Take Home Exercise

The goal of this exercise is for you to create a small sample of work so that *hidden company* can get a feel forhow you attack problems. We have some stipulations outlined below, but beyond those feel free touse any tools you would normally employ in your day to day work (editors, IDE’s, StackOverflow, etc.)

Please don’t spend more than 2 hours on this task.

### Challenge

*hidden company* is pretty active on social media; our Twitter account has over 4,000 posts. We want to know if there are any trends to our posts so we’d like you to create a tool that goes through all of our posts and aggregates the hashtags that we have used on Twitter in 2016.

Please write your tool using Node.js (https://nodejs.org) and provide instructions on how to install it along with all of its dependencies and run it.

Your minimal output should be an ordered list of hashtags along with their usage counts. For example:

>node myapp.js

Hashtag Count
Tag1 34
Tag2 23
Tag3 9
....

You may create a web interface for the interaction and output if you prefer but command line only is acceptable as well.
You may use any method you choose to access our Twitter feed -- whether it be via a library and an official API key, some sort of scraper, or anything else.

### Deliverables

A link to a private git repo on github/bitbucket/whatever that includes your code along with a readme file explaining how to install + run your application.

