#GlucoApp
###Why?
Imagine you have just discovered that you are diabetic and you would need to carefully manage your blood glucose for the rest of your life. This requires a strict discipline of watching what you eat, maintaining the regular physical activity level, being aware of your blood glucose levels and keeping a close eye on it. Over the long period of time these tasks become tiring and motivation to continue that discipline starts fading away which can cause serious long term health damages. 
###What?
As humans we always do better when we have support and we work with others. With GlucoApp you can not only record and monitor your own blood glucose, food intake, medication but also can share that information with the other people who are suffering from the same condition. You can share tips and information that is working for you and follow others who have proven to manage their own diabetes well over a long period of time. The idea of this app is to let the community support and motivate each other to live healthy with this condition. The app would also try to keep the users motivated by rewarding good habbits and will improve your ranking to have more influence in the community. 

##Features
1. A user can register using email and password
2. A user can login to the app using registered email and password
3. A user can record a blood glucose reading that would include:
  * Timestamp of the reading
  * Actual measurement
  * Context of reading: Before breakfast, Before meal/snack, After meal/snack, General. In case of after meal record amount of carbs taken in the meal
  * Medication taken = Insulin, Oral
  * Any physical activity
  * Any additional note
4. Record HbA1c
  * The actual reading
  * Any note that can be saved as part of the reading
  * The screen shows the last reading and the months/days since last reading
5. View history of blood glucose readings 
  1. Detail view
    * daily/weekly/monthly
    * Each reading should include the details of each reading
    * Based on the time period selected there should be 
  2. Summary view
    * A graph of the time period selected
    * Average of the time period selected
    * Number of high readings
    * Number of low readings
    * Number of normal readings
6. View history of HbA1c readings as a graph
7. Home screen
  * Includes a message at the top that gives a textual summary of their activity e.g.
    1. Hi John Doe, you have been following the structure very rigorously. You are a warrior. Keep up the good work.
    2. Hi John Doe, you have not recorded your blood glucose level for three days. Studies show that recording blood glucose levels regularly is a key step towards ensuring your long term health.
    3. Hi John Doe, Your HbA1c test is due in another month. With the current discipline we expect you to have great results in your next test result.
  * Shows a list of shared messages from other friends like a story feed. The user can "high five" the message or reply to it
  * Each time a user records a reading it will show up in other members story feed. Depending upon how much information can be shared this message can be as short as "John Doe recorded their reading" or it may have additional information as to what the actual reading was and what other details were recorded as part of the reading.
  * Upon clicking the user's profile image the feed will show messages by only that particular user.
8. Post a message
  * User can post a shared message that will show in other members story feed
  * User can add an image to the message
  * User may choose to share the last reading as part of the message
  * The message can be posted as public or shared only with friends
9. Reminders and Notifications
10. Settings
  * Language selection
  * Personal information (name, profile image, profession)
  * Privacy and security include options
    1. Share everytime I record a reading (public/friends only)
    2. Share everytime I record an HbA1c reading (public/ friends only)

##Models
#### User
| Name          | Type          | 
| ------------- | --------------| 
|id  |  number |
|last name  |  string |
|first name  |  string |
|username  |  string |
|email  |  string |
|password  |  string |
|date joined  |  Date |
|profile image  |  ?? (how does parse handle images)|
|profession  |  string (perhaps an enum)|
|friends:   |  [list of users] |
|last modified  |  Date |
|last logged in  |  Date |


####Reading
| Name          | Type          | 
| ------------- | --------------| 
id  | number |
|type   | string enum (blood glucose, HbA1c) |
|timestamp  | Date |
|value  | number |
|medication_type  | string enum (insulin, oral) |
|context   | string enum (Before Breakfast, Before meal/snack, After meal/snack, General) |
|carbs_taken  | integer |
|physical_activity  | string enum  (none, mild, moderate, high) |
|note  | string |
|shared  | boolean |
|shared_with  | [public/ friends only] |


####Story
| Name          | Type          | 
| ------------- | --------------| 
|id  | number |
|timestamp  | Date |
|message  | Message Object |
|liked  | boolean |
|replied  | boolean |
|reading  | Reading Object |
|user (posted by user)  | User Object |
|like_count  | number |
|shared   | boolean |
|shared_with  | boolean |


####Message
| Name          | Type          | 
| ------------- | --------------| 
|id  | number |
|timestamp  | Date |
|text  | string |
|in_reply_to   | story object |