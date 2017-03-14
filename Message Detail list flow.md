#### Date: 14/03/2017

#### Description: This document explains the code flow of detail message list.

#### Step 1:

Function **controlMessageListFlowMessage** takes the inputs from the user, when user scroll on messages. From this function we call the wsdl to get the messages ajax list and displays.

- Function **createMessageListInputVO** will take the inputs array and send to data file and prepares the list object.
- In action, function **createMessageListInputVO** from MessageData.php will get the values from input array and sets the values for list value object to pass for WSDl call. It prepare the query and required input to create message.
- The parameters will be user id, module name, action name, query, sub action, offset.
- Result returns the message list value object array to controller.

#### Step 2:

- Function **getMeetingArray** will take the input meeting id and get the meeting details.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- Function **getMeetingArray** from MessageWS.php which is used to send data to wsdl for getting the account details using the **get_entry_list_acc**.
- The result returns the meeting id to controller.

#### Step 3:

- Function **setUnviewedCount** takes the input value object and set viewed cont of message.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- Function **setUnviewedCount** from MessageWS.php is used to create a set viewed count.
- Creating parameters for wsdl using object by ws call **set_entry_viewed**.
- If notifiaction id is not null then ws call will be **set_entry**.
- The result will be returned to controller.


#### Step 4:

- Function **messageCount** will be called from **Accounts** module which is used to get the total message count to in header.
- First it gets the user id by calling function **getUserID** from Accounts controller to Accounts action.
- Here it sets the wsdl client connection which returns the user id by ws call **get_user_id**.
- returns the login user id to controller.

- Function **getNotificationscount** is used to get notification count.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- In AccountWS.php function **getNotificationscount** is used to send data to wsdl for getting the notifiaction count.
- The parameters will be passed to ws call **get_entries_count** which returns the result to controller for displaying the message count.


#### Step 5:

- Function **getMessageList** is used to call the wsdl for getting the meeting related messages.
- In action, first wsdl client connection will be set by function **setWSDLHandle**.
- Function **getListArray** in MessageWS.php is used to send data to wsdl for getting the messages list array using the **get_entry_list**.
- The parameters will be session id, module name, query, orderby, offset, max result, deleted which will be passed in ws call.
- The result returns to controller.


#### Step 6:

- Function **createMessageListDataObjectArr** creates a list object array for the data get from wsdl and passes to view page.
- Function **createMessageListDataObject** from action to MessageData.php gets the values from input array and sets the values for list data object to pass and to create message data.
- The result returns the message data object array to controller.


#### Step 7:

- Function **displayMessageListDataObject** creates a list object array for the data get from wsdl and passes to view page.
- In action, function **displayMessageListDataObject** will be called from MessageData.php which gets the values from input array and sets the values for list data object to pass and to create message list.
- The parameters will be meeting name, meeting id, date created, created by name, created by id, event type, event id.
- The result returns the message list data object array to controller.


#### Step 8:

- If the **ajaxcall == new**, function **showMessageListAjax_New** calls the view page to show the message list ajax view.
- In action, function **showMessageListViewAjax_New** will be called from MessageView.php which displays the tpl page.
- The display tpl page will be **ajax_messageListFormNew.tpl** in views folder.

#### Step 9:

- If the **ajaxcall == yes**, function **showMessageListAjax** will be executed which takes the input data object and gives to the message list ajax view.
- In action, function **showMessageListViewAjax** will be called from MessageView.php which displays the tpl page.
- The display tpl page will be **ajax_messageListForm.tpl** in views folder.



