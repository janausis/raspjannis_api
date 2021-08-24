# Setup
Get your API-KEY [here](https://raspjannis.spdns.de/profile/#api)!

Pass the API-Key as "x-api-key" in the request header


# API Routes
The main route for the API is: **https://raspjannis.spdns.de/api**

All arguments need to be passed in the request Header.

Invalid Api-Key returns {"data": "Invalid API-Key"} and error `403` all other errors return `401`

## Authorization Routes

* **/login**:
  * *Arguments:* email, password
        
  * *Description:* returns a UUID as a Token for other Methods 

  * *Returns:* {"data": {"UUID": `UUID`}}


* **/login/update**:
  * *Arguments:* UUID

  * *Description:* updates the UUID timeout. /login will have to be called again after 14 days if this method isn't used in the 14 Days

  * *Returns:* {"data": {"UUID": `UUID`}}


* **/login/valid**:
  * *Arguments:* UUID

  * *Description:* checks if the UUID has been updated within the last 14 Days and is valid

  * *Returns:* {"data": `"True" || "False"`}

* **/signup**:
  * *Arguments:* email, password, name

  * *Description:* signs up a user. Add double checks for passwords and/or email addresses

  * *Returns:* {"data": `"True" || "Invalid Email" || "User already exists"`}

## Userdata

* **/getUserData**:
  * *Arguments:* UUID

  * *Description:* get basic userData about the currently logged in user

  * *Returns:* {"data": {"email": `email`, "name": `username`, "id": `user id`}}

* **/changePassword**:
  * *Arguments:* UUID, oldPassword, newPassword

  * *Description:* change the password of the current user

  * *Returns:* {"data": `"True" || "password incorrect" || "passwords are the same"`}

* **/deleteUser**:
  * *Arguments:* UUID, password

  * *Description:* delete the current user and all their data

  * *Returns:* {"data": `"Successfully deleted user" || "Invalid password or email"`}

* **/getApiKey**:
  * *Arguments:* UUID

  * *Description:* get the Api-Key of the current user

  * *Returns:* {"data": `Api-Key`}

* **/generateApiKey**:
  * *Arguments:* UUID

  * *Description:* generate a new Api-Key for the current user

  * *Returns:* {"data": `Api-Key`}


* **/isAdmin**:
  * *Arguments:* UUID

  * *Description:* check the admin status of the current user

  * *Returns:* {"data": `"True" || "False"`}

## File System
* **/files/files/`path`**:
  * *Arguments:* UUID

  * *Description:* 

  * *Returns:* {"data": {"back": `back path`, "path" : `current path`, "files" : `{name, encrypted, path, fileSize, isFolder, thumbnail}`}}

* **/files/upload/`path`**:
  * *Arguments:* UUID, one of those: (file, link, folder)

  * *Description:* Upload a file, file by link or a add a folder to a path

  * *Returns:* {"data": `"True" || Errors`}

* **/files/all/`path`**:
  * *Arguments:* UUID

  * *Description:* list all image/video files

  * *Returns:* {"data": `{name, RealName, type}`)}

* **/files/delete/`path`**:
  * *Arguments:* UUID

  * *Description:* Delete a file/folder

  * *Returns:* {"data": `"True" || Error`}

* **/files/thumbnail/`path`**:
  * *Arguments:* UUID

  * *Description:* creates a thumbnail for an image file

  * *Returns:* `{"data": "Can't create Thumbnail for folder"} || image file`

* **/files/corrupt**:
  * *Arguments:* filename, size

  * *Description:* creates a corrupted file

  * *Returns:* file

## Other Routes

* **/**:
  * *Arguments:*

  * *Description:* 

  * *Returns:* 

* **/**:
  * *Arguments:*

  * *Description:* 

  * *Returns:* 

* **/**:
  * *Arguments:*

  * *Description:* 

  * *Returns:* 

* **/**:
  * *Arguments:*

  * *Description:* 

  * *Returns:* 






