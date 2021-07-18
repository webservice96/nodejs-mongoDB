<h1>NodeJS With MongoDB Database</h1>

<!-- installation -->
<h2>Install MongoDB dependencies on your project</h2>
<pre>npm install mongodb --save</pre>

<!-- connection node with MongoDB -->
<h2>NodeJs Connection with MongoDB</h2>
<h4>
    <pre>
var MongoClient = require('mongodb').MongoClient;
var URL = "mongodb+srv://User:Password@cluster0.kthq4.mongodb.net/?retryWrites=true&w=majority";
<br/>
MongoClient.connect(URL, function(error, MongoClient) {
    if (error) {
        console.log("The connection is Failed!");
    } else {
        console.log("Connection Success!");
    }
});
</pre>
</h4>

<!-- insert one row -->
<!-- <h2></h2> -->