#### Date: 14/03/2017

#### Description: This document explains the code flow of Messages.

#### The Folder Structure is as follows:

 Root Directory | Sub Directory 
------------ | -------------
index.php | 
Global | LytepoleWSConnection
Lib | Smarty,nusoap
Modules | Messages
Views | messageListForm, messageListFormMessage, ajax_messageListForm, ajax_messageListFormNew, messageGroupCreateForm, twilioMessagelist, twilioMessagelistAjax


#### Architecture

- After login into lytepole, when we click on Messages in side menu, it will redirect to twilio chat page where all the contacts will be loaded with whom we have done the chat previously.
- If any messages are unread, the count will be mentioned there for particular user.
- Twilio api controls the flow of creating the channel, users, members for a channel etc.
- Here unread messages count status will be 0 and when messages are read status will be 1. 


#### Database details

- Database Name: twiliomessages
- Database Username: remoteroot
- Database Password: lytepole_Admin

Tables | Fields 
------------ | -------------
channels | id, service_id, channel_id, channel_name, created_by, chat_name, date_entered, date_modified
channel_members | id,service_id,channel_id,channel_name,member_id,member_name,target_name,created_by,created_name,date_entered,date_modified
chat_users | id,service_id,channel_id,channel_name,assigned_to,chat_name,date_entered,date_modified
messages | id,channel_id,channel_name,member_name,message_text,date_entered,date_modified
