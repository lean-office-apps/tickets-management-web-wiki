## Use Case TKT-001 - Manage roles

### Description

A system role is a grouping of one or more system privileges also known as permissions. A permission is a security 
restriction that is put on a specific system function.
Permissions use a common boilerplate: Ability to [system function]. 
A role enables grouping of permissions to create organization specific user functions or groups and 
roles are user defined. A role has the following attributes:

1. Name - Text
2. Description - Text
3. Permissions [List]

### Validation rules

Name is required and must be unique.
Description is optional.
At Least a permission must be specified.

### Privileges

1. System Administrator

### Steps

1. User logs into the system.
2. Under the Security menu, the user clicks on the Roles sub menu.
3. A list of roles in a data table with options to Add_New (Global), Edit (per record), and Filter the data table; is displayed.
4. User clicks on the Add_New button and a form with the role fields (specified under the description section above) is displayed.
5. The user enters data in the fields.
6. User clicks on the Save button to execute client and server side validations.
7. If an error occurs (Exception is thrown),  it is logged in the database and also an error message is displayed to the user.
8. If all validation rules are met, the role is saved to the database.
9. The user is redirected to a view with all roles sorted alphabetically. The view should maintain the filters the user could have defined before navigating away from that page.

### Assumptions

1. Migrations to create permissions successfully executed.