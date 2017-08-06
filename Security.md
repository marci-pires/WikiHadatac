## User Categories and Console Functionality Permissions

Users are either unregistered, pre-registered, or registered. A registered user is one who went through the process of signing up for the system and confirming the authenticity of her/his email address. A registered user is capable of logging into the system and own data. An admin user has the permission of granting admin permission to any registered user. A user can only sign up to become registered if the user was previously pre-registered into the system by an admin user. 
 
### Administration (admin) user

One default administration user is automatically created during a HADataC installation. This is the admin user who can pre-register new users and grant admin status to other registered users. A user is said to be a pre-registered if the user is included into the HADataC metadata repository as a PROV Agent and has not yet signed up with the system.   

### Data owner

Every registered user is considered a data owner, whether the use actually owns or not any data in the data repository. A data owner is capable of the following: uploading data and metadata into the system; recording deployment metadata; annotating data with metadata; setting the permission of who has the right of accessing their data; deleting their data from the system.  

### Guest user

Every user is considered unregistered until the user logs into the system. Unregistered users can access and download publicly available data. Unregistered users cannot upload and own data in the HADataC system.

## User Registration

### Pre-Registration

Admin users should fill out the HASNetO agent's spreadsheet with the relevant information about HADataC users including the list of organizations associated with users and relationship between associated organizations. An admin user should upload the spreadsheet into the system by using the metadata loader, which will transfer all the agent information into the knowledge base. Agent information added into the system includes all the relevant user pre-registration information.

### Full Registration

### User Graph and Authentication Backup and Recovery
Users having admin privilege can easily perform backup and recovery operations on user graph (e.g. user profiles, access levels, etc) and authentication (e.g. accounts, encrypted passwords, security roles, etc) when system upgrade necessitates this. To backup, go to the **Manage Users** page and then you will see an button called **Backup User Authentication** for exporting a **.json** file containing required information for recovering later, and another button called **Backup User Graph** for exporting a **.ttl** file containing the whole user graph. To recover, in the same page, use the file upload panel called **Load User Graph from turtle** first to upload the previously saved **.ttl** file for recovering the user graph and then use another file upload panel called **Load User Authentication from json** to upload the previously saved **.json** file for recovering the user authentication.

## Data Ownership and Data Access Permissions

### Users and Groups

### Changing Data Access Permissions


