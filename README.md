# Node Express Mongo sample app 
* This app and readme is meant to help beginners learn the basics of Node, Express and Mongo

# commands
* express nodetest1
* cd nodetest1
* open package.json
	* defines our dependencies for the project
* add following to it to use mongodb
	"mongodb": "~2.0.33",
	"monk": "~1.0.1"
* npm install
	* this creates a node_modules directory which contains all of our dependencies
* mkdir data
	* That's where we store our MongoDB data. If that directory doesn't exist, the database server will choke.
* npm start
	* http://localhost:3000/
	* Running our own Node JS webserver, with the Express engine and Jade HTML preprocessor installed. 

# notes

* when to restart the server
	* changes to Jade templates do not require a server restart, but whenever you change a js file, such as app.js or the route files, you'll need to restart to see changes.
	
* in app.js
	* Routes are kind of like a combination of models and controllers in this setup – they direct traffic and also contain some programming logic (you can establish a more traditional MVC architecture with Express if you like. That's outside of the scope of this app)

	* var app = express();
		* This instantiates Express and assigns our app variable to it. 
		* We this variable to configure a bunch of Express stuff.
	* 	app.set('views', path.join(__dirname, 'views')); app.set('view engine', 'jade');
		* this says where the views directory is an that we're going to use jade to process them

	* app.use(express.static(path.join(__dirname, 'public')));
		* this makes it so:
			* the images directory is /Users/pavankatepalli/Desktop/git/nodetest1/public/images … but it is accessed at http://localhost:3000/images

	* module.exports = app;

		* A core part of Node is that basically all modules export an object which can easily be called elsewhere in the code. Our master app exports its app object.

* in routes/index.js
	* Basically we're requiring our Express functionality, then attaching a "router" variable to Express's router method, then using that method when an attempt is made to HTTP get the top level directory of our website. Finally we export our router function back to our app.


