# simon
## By Myles Barney

This is a simple web application for playing the game Simon.  It demonstrates the use of basic HTML elements for structure, formatting, input, output, links, and drawing.

### Simon Web Services Deployment
The random picture api has to use a random number generator in order to get a random picture since each picture has a different page.  This is useful to know because I was wondering how to do this on an earlier assignment.  
In the play.js file, scores are updated using the 'POST' method, with local saving being the fallback if the server doesn't respond.  Setting the score is much more complicated than getting the scores, the fetch function is two simple lines of code.  
I learned how to implement an API to save information about users on my webpage.

I learned to use Playwright to test my UI.

| Command                                                    | Purpose                                                                          |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **pm2 ls**                                                 | List all of the hosted node processes                                            |
| **pm2 monit**                                              | Visual monitor                                                                   |
| **pm2 start index.js -n simon**                            | Add a new process with an explicit name                                          |
| **pm2 start index.js -n startup -- 4000**                  | Add a new process with an explicit name and port parameter                       |
| **pm2 stop simon**                                         | Stop a process                                                                   |
| **pm2 restart simon**                                      | Restart a process                                                                |
| **pm2 delete simon**                                       | Delete a process from being hosted                                               |
| **pm2 delete all**                                         | Delete all processes                                                             |
| **pm2 save**                                               | Save the current processes across reboot                                         |
| **pm2 restart all**                                        | Reload all of the processes                                                      |
| **pm2 restart simon-react --update-env**                   | Reload process and update the node version to the current environment definition |
| **pm2 update**                                             | Reload pm2                                                                       |
| **pm2 start env.js --watch --ignore-watch="node_modules"** | Automatically reload service when index.js changes                               |
| **pm2 describe simon**                                     | Describe detailed process information                                            |
| **pm2 startup**                                            | Displays the command to run to keep PM2 running after a reboot.                  |
| **pm2 logs simon**                                         | Display process logs                                                             |


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

Using a cursor paradigm to access the scores data allows the program to return an array of scores to be stored in the scores.html list.  This is a useful object that MongoDB supplies that makes it easier to handle large amounts of data all at once.  The cursor also contains a forEach() method that iterates through each data object, preventing performance issues that can arise when using the toArray() method.  

**SENSITIVE INFORMATION SHOULD NEVER BE STORED DIRECTLY IN THE PROGRAM FILES!!!** When storing keys and usernames and passwords, ensure the security of your database by storing the information to the development environment and accesssing the environment variables inside of your program. 


### Authorization Services
When recording user information, you authenticate a user by taking their credentials and store an authentication token (in the form of a cookie) for a period of time. 
Stick to trusted, well-tested, authorization services to handle the majority of authorization.
Consider AWS Cognito and Google Firebase.

#### Account Creation and Login
Requires to service endpoints, **Create** and **Login**.

Create the web service using Express. 

Refer to the Simon-login files in the future for how to set up those programs.
Use uuid to generate tokens for unique identifiers.
Always securely store passwords.  Crytpographically hash the password and never store the actual password.  Use bcrypt package.
Use cookieParser to handle cookies and ensure that cookies are only passed from the original site.  cookieParser has built in functions httpOnly, secure, and sameSite which we used for this project.  

### Simon React Deployment
This deployment recreated the Simon app using react components instead of HTML and Javascript.  
Here I copied the steps to convert a normal webpage to a React based service. 
1. ⭐ **Reorganize Simon**
1. **Commit**: Commit this version in Git as the starting place for the conversion to React. It won't run, but by committing at this point can revert if necessary, instead of starting over. Make sure you keep testing and committing throughout this process.
1. **Create template React application**. Run `npx create-react-app template-react`. This creates a new directory named `template-react` that contains the basic configuration and template React application code.
1. **Clean up template code**
   1. Uninstall and NPM packages you won't use (e.g. stats, test)
   1. Delete the unnecessary create-react-app files (e.g. images)
   1. Rename `js` JSX files have `jsx` extension
   1. Replace the `favicon.ico` with the Simon icon
   1. Update `manifest.json` to represent Simon
   1. Clean up the `index.html` file to have the proper fields for Simon
1. ⭐ **Move template files to Simon**
1. ⭐ **Convert to React Bootstrap**
1. ⭐ **Populate App.jsx**
1. ⭐ **Create view components**
1. ⭐ **Create the router**
1. ⭐ **Convert to React components**
1. ⭐ **Set up to debug**
1. Refactor play.jsx into simonGame.jsx, simonButton.jsx, and players.jsx
1. Refactor components to take advantage of React specific functionality and to create sub-components
1. Move webSocket code from play.jsx to gameNotifier.js

#### Things to remember about React
React components are rendered by calling the a function that renders them in the HTML page.  
React components have internal states that can be called through onclick methods.  
Deployment is more complicated.
