#### Step 1:

Function **showTwilioMessageForm** will be called first from index.php to controller which is used to show message list using twilio api.

- Function **getChatList** which takes the input and will get the twilio chat list.
- Will get the DB connection and based on the query returns the result.
- If channel name is not null then function **showTwilioMessageList** will be executed which gets the Db connection and returns the chat messages for that channel.
