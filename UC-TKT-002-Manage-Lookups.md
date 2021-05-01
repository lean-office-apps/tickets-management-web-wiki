## Use Case TKT-002 - Manage Lookups

### Description

Lookups refer to general system settings that are setup in one table. A lookup has the following 
attributes:

1. Lookup Class - Enum
2. Lookup value
3. Parent - FK LookupUp table

### List of Lookup Classes [Enums]

This list will grow as the project evolves.

1. Gender (unique = true)

    1. Migrations to create: Male, Female, Other

2. TicketType (unique = true)

    1. Migrations to create: Task, Problem

**Note: Each Lookup class has additional attributes**

1. Values must be unique (boolean)

### Validation rules

1. Lookup class and Lookup value are required.
2. At the point of saving the lookup, validate the unique constraint defined on the respective lookup class.
3. Parent lookup is only specified for the following lookups.

### Privileges

1. Ability to create a lookup - To view the button that if clicked redirects to a form with options to create a lookup.
2. Ability to view lookups- To view the menu item that once clicked displays the lookups view.
3. Ability to edit lookups- To view the link that if clicked redirects to a form with options that loads the details of the clicked lookup and allows the actor to change the values of that lookup.
4. Ability to delete a lookup- To view the link that if clicked displays a confirmation dialog to delete a lookup. 
5. Deletion changes the record status from Active to Deleted. Deleted records are excluded from all queries related to data forms in the system. However, if a record is deleted and is referenced in other records, the referencing records will maintain that reference both in the database and on the UI views. 

### Steps to create a new user

1. User logs into the system.
2. Under the Security menu, the user clicks on the Lookups sub menu. 
3. A list of lookups in a data table with options to Add_New (Global), Edit (per record), Delete (per record), and Filter the data table; is displayed.
4. User clicks on the Add_New button and a form with the lookup fields (specified under the description section above) is displayed.
5. The user enters data in the fields.
6. User clicks on the Save button to execute client and server side validations.
7. If an error occurs (Exception is thrown), it is logged in the database and also an error message is displayed to the user.
8. If all validation rules are met, the lookup is saved to the database.
9. The user is redirected to a view with all users sorted alphabetically. The view should maintain the filters the user could have defined before navigating away from that page. Such filters include a dropdown for Lookup classes (must always contain a value or defaults to the first), textfield to search lookups using their lookup values as text. 

### Assumptions

1. Roles have been created.

