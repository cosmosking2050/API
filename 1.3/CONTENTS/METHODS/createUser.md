[Back to the Table of Contents](/1.3/README.md)

__Synopsis:__  
Creates new user with given username and password. The rest of the parameters required for account creation are inherited from creator’s account.

__Request:__
```xml
<REQUEST>
  <ACTION>createUser</ACTION>
    <API_KEY>API KEY</API_KEY>
    <NEWUSER>New Username</NEWUSER>
    <NEWPASS>New Password</NEWPASS>
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, NewUser, NewPass
    Optional: N/A

__Response Parameters:__

    Status, Username, Password, API_KEY, Errorcode, Errorinfo

__Related Errorcodes:__

    E150, E151, E152, E153, E154

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>createUser</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <NewUser>john</NewUser>
    <NewPass>john_pass</NewPass>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=createuser&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &newuser=john&newpass=john_pass
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <USERNAME>john</USERNAME>
    <PASSWORD>42363deef6129efa1dc0a54b26cf1426</PASSWORD>
    <API_KEY>umfKkSLCDKI9yJ5b7fDBk5I8EQaoq88l</API_KEY>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E151</ERRORCODE>
    <ERRORINFO>'username' already exists. Duplicate username</ERRORINFO>
</RESPONSE>
```
