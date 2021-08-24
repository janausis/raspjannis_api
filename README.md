# Setup
Get your API-KEY [here](https://raspjannis.spdns.de/profile/#api)!

Pass the API-Key as "x-api-key" in the request header


# API Routes
The main route for the API is: **https://raspjannis.spdns.de/api**

All arguments need to be passed in the request Header.

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

* **/**:
  * *Arguments:*

  * *Description:* 

  * *Returns:* 







