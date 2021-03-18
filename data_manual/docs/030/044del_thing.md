# Delete a Thing with Python
- **This example assumes you know how to run a Python script.**
1. Download the Python script, 'sensorthings_delete.py' from [https://github.com/chaos-laboratory/sensorthingsAPIeg](https://github.com/chaos-laboratory/sensorthingsAPIeg). Under the code tab you can download all the codes as a zip file. Approach a lab member for the login credentials.
    </Br><Br/>
    a. The script is only 14 lines long. The main script shown below requires you to specify the object and its ID. Once you run the script the Thing will be deleted from our database.
    ```
    #========================================================================
    #thing + location
    #========================================================================
    obj = "Things"
    idx = str(33)
    delete = requests.delete(url+ obj + "(" + idx + ")", auth=HTTPBasicAuth(auth_user, auth_pass))
    content = delete.content
    print(content)
    ```
    b. Similarly you can delete all the other objects, refer to the [sensorthings API documentation](https://developers.sensorup.com/docs/) for more information on the various API commands.
