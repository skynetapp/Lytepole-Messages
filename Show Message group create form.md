#### Step 1:

Function **showMessageGroupCreateForm** will be called first from index.php to controller which shows the message group contacts create form, and passing contacts list as input.

- Function **createContactListInputVO** will create the value objects from contacts module contacts controller to contacts action.
- In action, user id will be set by function **getUserID**.
- Function **createContactListInputVO** will be called in action from ContactsData.php which gets the values from input array and sets the values for list value object to pass for WSDL call. It will prepare the query and required input to create contact.
- The list value object array result will be returned to controller.

#### Step 2:

- Function **getContactsList** is used to call the wsdl call for getting the contacts list from controller to action.
- In action, first ws client connection will be set by function **setWSDLHandle**.
- Function **getListArray** in ContactsWS.php which is used send data to wsdl for getting the contacts list array using the ws call **get_entry_list_con**.
- The contacts list array result will be returned to controller.

#### Step 3:

- Function **createContactListDataObjectArr** in controller will create the object array for list data.
- In action, Function **createContactListDataObject** will be called from ContactsData.php which gets the values from input array and sets the values for list data object.
- The contact data object array will be returned to controller.

#### Step 4:

- Function **showMessageGroupCreateForm** takes the input data object and shows message group contacts view.
- In action, function **showMessageGroupCreateForm** which displays the tpl page.
- The display tpl page will be **messageGroupCreateForm.tpl** which will be in views folder.
