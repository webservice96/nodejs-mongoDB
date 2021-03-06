<h1>NodeJS With MongoDB Database</h1>

<!-- installation -->
<h2>Install MongoDB dependencies on your project</h2>
<pre>npm install mongodb --save</pre>

<!-- connection node with MongoDB -->
<h2>NodeJs Connection with MongoDB</h2>
<h3>
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
</h3>

<!-- insert one row -->
<h2>Insert Multiple Row</h2>

<h3>
    <pre>
function InsertData(MongoClient) {
    var MyDB = MongoClient.db('school');
    var MyCollect = MyDB.collection('students');

    var stdData = [{
            "ID": "44",
            "Name": "Unknown",
            "Gender": "0",
            "Class": "0",
            "Seat": "0",
            "Club": "0",
            "Persona": "0",
            "Crush": "0",
            "BreastSize": "1",
            "Strength": "0",
            "Hairstyle": "1",
            "Color": "White",
            "Eyes": "Black",
            "EyeType": "Default",
            "Stockings": "None",
            "Accessory": "0",
            "ScheduleTime": "7_7_8_13_13.375_15.5_16_99",
            "ScheduleDestination": "Spawn_Locker_Patrol_Seat_Patrol_Seat_Clean_Patrol",
            "ScheduleAction": "Stand_Stand_Patrol_Sit_Patrol_Sit_Clean_Patrol",
            "Info": ""
        },
        {
            "ID": "45",
            "Name": "Unknown",
            "Gender": "0",
            "Class": "0",
            "Seat": "0",
            "Club": "0",
            "Persona": "0",
            "Crush": "0",
            "BreastSize": "1",
            "Strength": "0",
            "Hairstyle": "1",
            "Color": "White",
            "Eyes": "Black",
            "EyeType": "Default",
            "Stockings": "None",
            "Accessory": "0",
            "ScheduleTime": "7_7_8_13_13.375_15.5_16_99",
            "ScheduleDestination": "Spawn_Locker_Patrol_Seat_Patrol_Seat_Clean_Patrol",
            "ScheduleAction": "Stand_Stand_Patrol_Sit_Patrol_Sit_Clean_Patrol",
            "Info": ""
        },
        {
            "ID": "82",
            "Name": "Kashiko Murasaki",
            "Gender": "0",
            "Class": "31",
            "Seat": "1",
            "Club": "14",
            "Persona": "10",
            "Crush": "0",
            "BreastSize": "1.4",
            "Strength": "0",
            "Hairstyle": "27",
            "Color": "Ganguro2",
            "Eyes": "Ganguro2",
            "EyeType": "Default",
            "Stockings": "Loose",
            "Accessory": "0",
            "ScheduleTime": "7_7_8_13_13.375_15.5_16_99",
            "ScheduleDestination": "Spawn_Locker_Graffiti_Seat_Bully_Seat_Hangout_Patrol",
            "ScheduleAction": "Stand_Stand_Graffiti_Sit_Bully_Sit_Gossip_Patrol",
            "Info": "Spends most of her time texting on her phone. \n \n Pretends to be a sweet girl, but in private, her personality is quite nasty. \n \n Secretly, her favorite activity is gossipping and spreading rumors."
        },
        {
            "ID": "83",
            "Name": "Hana Daidaiyama",
            "Gender": "0",
            "Class": "22",
            "Seat": "1",
            "Club": "14",
            "Persona": "10",
            "Crush": "0",
            "BreastSize": "1.3",
            "Strength": "0",
            "Hairstyle": "28",
            "Color": "Ganguro3",
            "Eyes": "Ganguro3",
            "EyeType": "Default",
            "Stockings": "Loose",
            "Accessory": "0",
            "ScheduleTime": "7_7_8_13_13.375_15.5_16_99",
            "ScheduleDestination": "Spawn_Locker_Graffiti_Seat_Bully_Seat_Hangout_Patrol",
            "ScheduleAction": "Stand_Stand_Graffiti_Sit_Bully_Sit_Gossip_Patrol",
            "Info": "Spends most of her time playing games on her phone. \n \n Pretends to be pure and innocent, but in private, she can be extremely vulgar. \n \n Secretly, her favorite activity is looking for dirt in peoples' pasts."
        },
        {
            "ID": "84",
            "Name": "Kokoro Momoiro",
            "Gender": "0",
            "Class": "21",
            "Seat": "1",
            "Club": "14",
            "Persona": "10",
            "Crush": "0",
            "BreastSize": "1.2",
            "Strength": "0",
            "Hairstyle": "29",
            "Color": "Ganguro4",
            "Eyes": "Ganguro4",
            "EyeType": "Default",
            "Stockings": "Loose",
            "Accessory": "0",
            "ScheduleTime": "7_7_8_13.0006_13.375_15.5006_16_99",
            "ScheduleDestination": "Spawn_Locker_Graffiti_Seat_Bully_Seat_Hangout_Patrol",
            "ScheduleAction": "Stand_Stand_Graffiti_Sit_Bully_Sit_Gossip_Patrol",
            "Info": "Spends most of her time taking selfies with her phone. \n \n Pretends to oppose bullying, but in private, she harasses the people she dislikes. \n \n Secretly, her favorite activity is shaming and ridiculing other people."
        }
    ];

    MyCollect.insertMany(stdData, function(error) {
        if (error) {
            console.log("Data insert fail!");
        } else {
            console.log("Data insert success!");
        }
    });
}
    </pre>
</h3>

<!-- Find row with multiple condition -->
<h2>Find row with multiple condition</h2>
<h3>
    <pre>
function FindQuery(MongoClient) {
    var MyDB = MongoClient.db('school');
    var MyCollect = MyDB.collection('students');

    var query = { Eyes: "Ganguro3", Class: "22" }

    MyCollect.find(query).toArray(function(error, result) {
        console.log(result);
        MongoClient.close();
    })
}
    </pre>
</h3>

<!--  -->
<h2>Find specific Column Projection</h2>

<h3>
    <pre>
function FindColumnProjection(MongoClient) {
    var MyDB = MongoClient.db('school');
    var MyCollect = MyDB.collection('students');

    var queryObj = {}
    var Itemprojection = { projection: { ID: 1, Name: 1 } }

    MyCollect.find(queryObj, Itemprojection).toArray(function(error, result) {
        console.log(result);
    })
}
    </pre>
</h3>