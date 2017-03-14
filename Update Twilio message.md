#### Step 1:

Function **updateTwilioMessage** will update the message using twilio api.

- Function **updateTwilioMessages** is used to update twilio messages.
- In TwilioMessageWS.php, the above function will get the DB connection by calling function **getDbConnection** and update the message status to 1 as user reads the message.
- The update will be done based on the channel name and will check the user.
