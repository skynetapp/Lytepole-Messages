#### Date: 14/03/2017

#### Description: This document explains the code flow of insertion of twilio messages.

#### Step 1:

Function **insertTwilioMessage** will be called first from index.php to controller which is used to insert message using twilio api.

- Function **insertTwilioMessages** will get the parameters which inserts the twilio messages.
- The parameters will be user id, message and login number.
- Function **insertTwilioMessages** in TwilioMessageWS.php will get the DB connection by calling function **getDbConnection** and messages will be inserted into DB based on the query.
- The message count will be updated as uncount as status will be 0. 
- The date will be updated based on the channel name.
