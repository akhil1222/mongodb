# mongodb

import com.mongodb.MongoClient;
import com.mongodb.MongoException;
import com.mongodb.WriteConcern;

import com.mongodb.DB;
import com.mongodb.DBCollection;
import com.mongodb.BasicDBObject;
import com.mongodb.DBObject;
import com.mongodb.DBCursor;

import com.mongodb.ServerAddress;
import java.util.Arrays;

public class MongoDBJDBC {

   public static void main( String args[] ) {
	
      try{   
		
         // To connect to mongodb server
         MongoClient mongoClient = new MongoClient( "localhost" , 27017 );
			
         // Now connect to your databases
         DB db = mongoClient.getDB( "test" );
         System.out.println("Connect to database successfully");
			
         boolean auth = db.authenticate(myUserName, myPassword);
         System.out.println("Authentication: "+auth);  
         DBCollection coll = db.createCollection("Twitter");
         System.out.println("Collection created successfully");
         DBCollection coll = db.getCollection("Twitter");
         System.out.println("Collection Twitter selected successfully");
			   BasicDBObject tweet1 = new BasicDBObject("Tweet 1", "Introducing @Truebluebrand to the world was an amazing experience! A truly global fashion brand with an Indian soul.").
            append("date", "july 1,2016").
            append("likes", 2600).
            coll.insert(tweet1);
             BasicDBObject tweet2 = new BasicDBObject("Tweet 2","Enjoyed the Castles in Scotland").
            append("date", "july 1,2016").
            append("likes", 6900).
            coll.insert(tweet2);
             BasicDBObject tweet3 = new BasicDBObject("Tweet 3","The solitude and remote stretches in Scotland").
            append("date", "july 2, 2016").
            append("likes", 7400).
            coll.insert(tweet3);
             BasicDBObject tweet4 = new BasicDBObject("Tweet 4","Happy birthday Bhajji! May God bless you with good health and happiness. Have a great year buddy! ").
            append("description", "july 3, 2016").
            append("likes", 13000).
            coll.insert(tweet4);
             BasicDBObject tweet5 = new BasicDBObject("Tweet 5","Ring mein ghusne k baad darr nahi lagta chahe harun ya jeetun").
            append("date", "july 3, 2016").
            append("likes", 2600).
            coll.insert(tweet5);
             BasicDBObject tweet6 = new BasicDBObject("Tweet 6","Andar se feel hona chahiye ki kuch karna hai").
            append("date", "july 6,2016").
            append("likes", 2000).
            coll.insert(tweet6);
             BasicDBObject tweet7 = new BasicDBObject("Tweet 7","Some injuries trouble even after retirement, Will be back soon doing things I enjoy. Had a knee operation & resting.").
            append("date", "july 6, 2016").
            append("likes",8700).
            coll.insert(tweet7);
             BasicDBObject tweet8 = new BasicDBObject("Tweet 8","Watched you fight back from 2 sets down and 0-40 down on your serve. Great fight back and fantastic spirit. All the best! ").
            append("date", "july 6, 2016").
            append("likes", 8900).
            coll.insert(tweet8);
             BasicDBObject tweet9 = new BasicDBObject("Tweet 9","Eid Mubarak!!").
            append("date", "july 6,2016").
            append("likes", 4100).
            coll.insert(tweet9);
             BasicDBObject tweet10 = new BasicDBObject("Tweet 10","Happy Birthday msdhoni .. Have a wonderful and blessed year ahead!!").
            append("date", "july 7, 2016").
            append("likes", 10000).
            coll.insert(tweet10);
            BasicDBObject tweet11 = new BasicDBObject("Tweet 11","Happy Birthday Dada, May all your dreams come true!! SGanguly99").
            append("date", "july 8, 2016").
            append("likes", 9600).
            coll.insert(tweet11);
         System.out.println("Tweets inserted successfully");
      }catch(Exception e){
         System.err.println( e.getClass().getName() + ": " + e.getMessage() );
      }
   }
}
When program is compiled and executed, it will produce the following result −

Connect to database successfully
Authentication: true
Collection mycol selected successfully
Document inserted successfully
