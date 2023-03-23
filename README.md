# simon
## By Myles Barney

This is a simple web application for playing the game Simon.  It demonstrates the use of basic HTML elements for structure, formatting, input, output, links, and drawing.

### Simon Web Services Deployment
The random picture api has to use a random number generator in order to get a random picture since each picture has a different page.  This is useful to know because I was wondering how to do this on an earlier assignment.  
In the play.js file, scores are updated using the 'POST' method, with local saving being the fallback if the server doesn't respond.  Setting the score is much more complicated than getting the scores, the fetch function is two simple lines of code.  
