#### Date: 14/03/2017

#### Description: This document explains the code flow of creating twilio messages.

#### Step 1:

Function **createTwilioMessageForm** will be called first from index.php to controller which is used for create message using twilio api.

- First we will get the user id by function **getUserID**.
- Function **checkChannel** takes the input and check whether Twilio channel exist or not.
- In action, **checkChannel** will be called from TwilioMessageWS.php which gets the DB connection and executes the sql query to check the channel.
- Result will be returned to controller.


#### Step 2:

- If channel is empty function **createChannel** will be called which returns the channel name.
- Function **createChannelNew** takes the input and creates Twilio channel.
- In action, we will call the wsdl call to create a new channel which gets the DB connection and inserts the new channel into DB.


#### Step 3:

- Function **addUsertoChannel** will be called next which adds the users to that created channel.
- The logged in user and the user who is going to chat with logged in user.


#### Step 4:

- Function **createMemberNew** takes the input and creates Twilio channel member.
- In action, function **createMemberNew** will be executed which gets the DB connection and the members for the channel gets inserted.

#### Step 5:

- Function **createChatList** will take the input and create a chat list.
- In action, function **createChatList** will be called from TwilioMessageWS.php which gets the DB connection and users list will be inserted.

#### Step 6:

- Function **getChatList** takes the input and will get the chat list.
- passing the parameters as channel and login number which gets the DB connection from TwilioMessageWS.php and based on sql query chat list will be shown.

#### Step 7:

- Function **showTwilioMessageList** will take the input and shows the twilio message list.
- In action, function **showTwilioMessageList** from MessageView.php will display the tpl page.
- The display tpl page **twilioMessagelist.tpl** will be inviews folder.

#### Step 8:

- if the channel already exists, function **showTwilioMessageList** will get the channel name and view the display.



