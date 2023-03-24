# simon
## By Myles Barney

This is a simple web application for playing the game Simon.  It demonstrates the use of basic HTML elements for structure, formatting, input, output, links, and drawing.

### Simon Web Services Deployment
The random picture api has to use a random number generator in order to get a random picture since each picture has a different page.  This is useful to know because I was wondering how to do this on an earlier assignment.  
In the play.js file, scores are updated using the 'POST' method, with local saving being the fallback if the server doesn't respond.  Setting the score is much more complicated than getting the scores, the fetch function is two simple lines of code.  
I learned how to implement an API to save information about users on my webpage.

I learned to use Playwright to test my UI.

#### |pm2 | Commands pm2 |
|----|--------------------|
|ls |	List all of the hosted node processes |
| pm2 monit	| Visual monitor |
| pm2 start index.js -n simon	| Add a new process with an explicit name |
| pm2 start index.js -n startup -- 4000	| Add a new process with an explicit name and port parameter |
| pm2 stop simon	| Stop a process |
| pm2 restart simon	| Restart a process | 
| pm2 delete simon	| Delete a process from being hosted |
| pm2 delete all	| Delete all processes |
| pm2 save	| Save the current processes across reboot |
| pm2 restart all	| Reload all of the processes |
| pm2 restart simon-react --update-env	| Reload process and update the node version to the current environment definition |
| pm2 update	| Reload pm2 |
| pm2 start env.js --watch --ignore-watch="node_modules"	| Automatically reload service when index.js changes |
| pm2 describe simon	| Describe detailed process information |
| pm2 startup	| Displays the command to run to keep PM2 running after a reboot. |
| pm2 logs simon	| Display process logs |


### Simon Database Deployment
This episode of Simon taught about creating a database using Mongo database which we can access using javascript commands.  MongoDB uses JSON objects to store data, making it simple to create collections of user data.  Here is a list of some other data services from the CS260 GitHub.

| Service       | Specialty             |
| ------------- | --------------------- |
| MySQL         | Relational queries    |
| Redis         | Memory cached objects |
| ElasticSearch | Ranked free text      |
| MongoDB       | JSON objects          |
| DynamoDB      | Key value pairs       |
| Neo4J         | Graph based data      |
| InfluxDB      | Time series data      |

