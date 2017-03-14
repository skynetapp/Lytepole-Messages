#### Step 1:

Function **createMessageFlow** will be called first from controller to action which takes the inputs from the user. when user clicks on messages in meeting list view in any job list its call this function and creates a new messages ans set relation with meeting id.

- Function **createMessageListInputVO** will take the inputs array and send to data file and prepares the list object.
- In action, function **createMessageListInputVO** from MessageData.php will get the values from input array and sets the values for list value object to pass for WSDl call. It prepare the query and required input to create message.
- The parameters will be user id, module name, action name, query, sub action, offset.
- Result returns the message list value object array to controller.

#### Step 2:

- Function **createMessage** takes the input value object and passes to the wsdl call to create a new logevent.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- Function **createMessage** from action to MessageWS.php is used to create a new message by ws call **set_entry**.
- Creating parameters and passing the parameters to wsdl call.
- result will be returned to controller.


#### Step 3:

- Function **createMeetingMessageRelation** takes the input value object and set relation between message and meeting.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- Function **createMeetingMessageRelation** is used to create a relation between meeting and sms by ws call **set_relationship**.
- Result returns to controller.
