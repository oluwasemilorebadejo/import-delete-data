# import-delete-data

This script is used to import and delete data from a MongoDB database.

It first requires the fs, mongoose, and dotenv modules. It also requires three local models: Tour, Review, and User.

The dotenv module is used to configure the environment variables stored in the config.env file.

The script then connects to the MongoDB database using the mongoose module, with the connection string stored in the DATABASE environment variable. The DATABASE_PASSWORD variable is also included in the connection string.

The script then reads in three JSON files: tours.json, users.json, and reviews.json, and stores the contents of these files in the variables tours, users, and reviews, respectively.

The script defines two async functions: importData and deleteData. The importData function uses the create method of each of the models (Tour, User, Review) to import the data from the corresponding JSON files into the MongoDB database. The deleteData function uses the deleteMany method of each of the models to delete all data from the corresponding collections in the MongoDB database.

The script then checks the value of the process.argv[2] variable. If it is equal to --import, the importData function is called. If it is equal to --delete, the deleteData function is called. If neither of these conditions are met, the script does nothing.

Finally, the process.exit() method is called at the end of both the importData and deleteData functions to exit the process.
