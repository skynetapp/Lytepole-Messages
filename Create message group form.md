#### Date: 14/03/2017

#### Description: This document explains the code flow of creating message group.

#### Step 1:

Function **createMessageGroupCreateForm** will be called first from index.php to controller which is used for create message group contacts, after selecting the contacts in list click on save then this function will call to create.

- First we will get the user id by calling function **getUserID**.
- Function **getAccountArray** takes the input user id and get the account details.
- In action, first ws client connection will be set by function **setWSDLHandle**.
- Function **getAccountArray** is used to send data to wsdl for getting the account details using the **get_entry_list_acc**.
- The result returns the message list array to controller.

#### Step 2:

- If **action == NewMessage**, function **createMeetingListInputVO** will be called from module Meetings -> action which will get the user id and retrieves the list object array.
- Calling the WSDL to get meeting list by calling function **getmeetingList**.


#### Step 3:

- Function **createAddMessageInputVO** takes the inputs array and send to data file and prepares the list object. It pepare the input to add message wsdl.
- In action, function **createAddMessageInputVO** will be called from MessageData.php which gets the values from input array and sets the values for list value object to pass for WSDL call. It prepare the query and required input to create new message.
- The result returns the Message list value object array.
- If **action == NewMessage**, Event type will set to Direct chat else the type will be Group chat.


#### Step 4:

- Function **createNewGroupMessage** takes the input value object and creates group message.
- In action, first ws client connection will be set by function **setWSDLHandle**.
- Function **createNewGroupmessage** from MessageWS.php is used to create a new group message by wsdl call **set_entry**.
- The parameters will be name,description,max invitee,event type,access type,user id,direct chat.
- The parameters will be passed to ws call. The result returns the group id.


#### Step 5:

- Function **createAddMessageInviteesInputVO** which takes the input array and send to data file and prepares the list object. It pepares the input to add invitees to message.
- In action, function **createAddMessageInviteesInputVO** will be called from MeetingData.php which gets the values from input array and sets the values for list value object to pass for WSDL call. It prepare the query and required input to create message invitees.
- Result returns the Message invitees value object array.


#### Step 6:

- Function **createMessageInvitees** takes the input value object and creates message invitees.
- In action, first ws client connection will be set by function **setWSDLHandle**.
- Function **createMessageInvitees** from MeetingWS.php is used create a invitee and set relation with message by wsdl call **set_entry**.
- Creating parameters  as name, email, meeting id, phone, is referred for wsdl using object.
- Set relationship by calling wsdl **set_relationship** which returns the relation id as result.
- Header location will be redirected to the detail view based on the record id.






