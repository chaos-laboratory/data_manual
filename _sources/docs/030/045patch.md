# Patch a Datastream with Python
- **This example assumes you know how to run a Python script.**
1. Download the Python script, 'sensorthings_patch.py' from [https://github.com/chaos-laboratory/sensorthingsAPIeg](https://github.com/chaos-laboratory/sensorthingsAPIeg). Under the code tab you can download all the codes as a zip file. Approach a lab member for the login credentials.
    </Br><Br/>
    a. The script is only 18 lines long. The main script shown below requires you to specify the object and its ID. You have to specify the changes to the particular field of the object. In this example, we are making changes to the 'unitOfMeasurement' field of the Datastream object with ID:14. Once you run the script the field will be updated.
    ```
    obj = "Datastreams"
    idx = "14"
    ds_json = {"unitOfMeasurement": {
                                    "name": "g/kg",
                                    "symbol": "g/kg",
                                    "definition": "the amount of grams in a kg of air"
                                }
            }
    r = requests.patch(url+ obj + "(" + idx +  ")", auth=HTTPBasicAuth(auth_user, auth_pass),
                  json=ds_json, verify=True)
    ```
    b. Similarly you can patch all the other objects, refer to the [sensorthings API documentation](https://developers.sensorup.com/docs/) for more information on the various API commands.
